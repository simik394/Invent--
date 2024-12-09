---
page-title: "A Neovim Task Runner in 30 lines of Lua"
url: https://www.hillelwayne.com/post/task-runner-neovim/
date: "2024-08-16 23:40:19"
tags: [a/sw/plugin, f/prod/homepage, c/, p/pwf/automation]
about: ["[[NeoVim]]"]
aliases: 
- 
by: 
length: 7411
dir: 
---

I like how easy it is to configure neovim. Last month I wanted a task runner for a very *particular* use-case that none of the available plugins handled. So I wrote my own.

Show Code

This is not good code.

```
vim.g.global_task = {}

function LoadTask(cmd, num, silent)
  local tmp = vim.g.global_task -- (a)
  if not num then
    num = vim.tbl_count(vim.g.global_task) + 1
  end
  tmp[tonumber(num)] = cmd -- (a)
  vim.g.global_task = tmp -- (a)
  if not silent then
    print("Loaded [[" .. cmd .. "]] to key " .. num)
  end
end

function RunTask(num)
  local cmd
  if num then
    cmd = vim.g.global_task[tonumber(num)]
  elseif vim.tbl_count(vim.g.global_task) == 1 then
    cmd = vim.g.global_task[1]
  else
    vim.ui.select( --(b)
      vim.g.global_task, {prompt=""}, function(choice) cmd = choice end
    )
  end
  if cmd then
    vim.cmd(cmd)
  end
end

vim.cmd [[command! -nargs=? RunTask call v:lua.RunTask(<f-args>)]] -- (c)
vim.keymap.set('n', 'gxp', RunTask, {silent = true})
vim.keymap.set('n', 'gxP', function() RunTask(1) end, {silent = true})
```

Code notes:

(a) The tmp swaparoo in LoadTask happens because you cannot directly assign a field in a table that’s also a vim variable. So instead I create a tmp copy and reassign the field in the tmp.

([TJ DeVries](https://twitter.com/teej_dv) recommended I use a lua global instead of a vim variable but I like being able to refer to the variable from both lua and vimscript)

(b) `vim.ui.select` is basically a nicer version of the vimL `inputlist()` function.

(c) Having a `RunTask` *command* isn’t strictly necessary, since you can do `:lua RunTask(2)`, but whatever. `-nargs=?` means “0 or 1 params”.

You create a new task like this:

```
:lua LoadTask [[echo "hello world"]]
```

And run it with `gxp`. The fun starts when you add a *second* task:

```
:lua LoadTask [[echo "hello different world"]]
```

Then `gxp` will give you a choice of which to run:

![](https://www.hillelwayne.com/post/task-runner-neovim/img/selector.png)

As a couple of QoL features, you can assign a task to a specific number by doing `:lua LoadTask([[task]], n)` and you can skip the input prompt with `:RunTask <num>`. I set `gxP` to always run the first set task.

To delete tasks, just run `:lua vim.g.global_task = {}`.

## Some benefits

It’s all a bit crude, but it’s also been *really* useful to me. While standard task runners have a better UX and polish, they separate the act of defining tasks from the process of using Vim. This script works in the vim layer, which makes it *incredibly* flexible.

For one, anything that can be done in the vim command mode can be made into a task. With `:g` and `:norm`, this includes standard vim keystrokes.

To run a shell command, I just add `!foo` as a task. This uses the standard vim expansion rules, so `!foo %` will run `foo` on the active buffer’s file. I can also hard-code a specific filename, to run a task on that file regardless of which buffer I’m editing.

Since the task executes *as vim*, I can dynamically determine part of the final task. This helped a lot when I was working on a tutorial. I had a bunch of iterations of the same file, and a [metafile](https://buttondown.email/hillelwayne/archive/on-metafiles/) that generated them. I wanted to make edits to the metafile and then run a fixed test on the generated file.

```
:lua LoadTask([[:exe ":!tlacli check " .. bufname(winbufnr(1003))]])
```

In Vim, each window has a fixed ID. `winbufnr(win_id)` gets the buffer id for that window, then `bufname(buf_id)` gets the filename of that buffer. This is dynamically appended to the shell command, which is then executed via `:exe`(cute).[1](https://www.hillelwayne.com/post/task-runner-neovim/#fn:exe) So if the buffer in window 2 was “foo/bar1.tla”, the final task run would be `:!tlacli check foo/bar1.tla`, regardless of which buffer I’m in! If I then load `foo/bar2.tla` into the same window, the task automatically “updates”.

With a bit of [cleverness](https://www.hillelwayne.com/post/cleverness/) I’ve been able to get some common features of polished task runners:

### Running Async Jobs

If I wanted to be *proper* about things, I’d use the `jobstart` API. But I find it easier to create local terminals and run the commands in them. First I pick a terminal buffer as the task target:

```
let g:task_term = b:terminal_job_id
:echo g:task_term
4
```

Then it’s just a matter of using `chansend` to send something that terminal.

```
:lua LoadTask([[call chansend(g:task_term, "cargo check\n")]])
```

It works even if the terminal is hidden or on another tab, and it’s extendable to multiple terminals for multiple tasks. At some point I’ll write some helper functions for myself, so I can instead write `:lua LoadTermTask("cargo check")` and have it fill in the boilerplate.

### Persisting Tasks

Normally tasks are defined in a `tasks.json` file. Since the tasks are instead defined as part of the editing session, they’re reset whenever I close vim.[2](https://www.hillelwayne.com/post/task-runner-neovim/#fn:sessions) Fortunately, because they’re Just Vim Records, they’re also really easy to serialize. I can dump the task list with `put =g:global_tasks`. When I want to restore the list, I just copy that line back into command mode.

```
let g:global_tasks = ["task1", "task2"]

" or

lua vim.g.global_tasks = {[[task1]], [[task2]]}
```

I have a little helper script to execute buffer lines as vim commands, which makes this extra easy.

```
vim.keymap.set('n', '<leader>e', [[:exe getline(line('.'))<cr>]])
```

This also gives some form of per-workspace task customization. I can put a bunch of different task sets in the same file, and then just load in the one I want for a session.

### Dynamic Parameters

```
let g:flags = "--flag1 param1 --flag2 param2"
lua LoadTask([[exe !cmd ]] .. vim.g.flags)
```

By changing and reloading `g:flags`, The task also automatically updates. This is where that `<leader>e` map comes in real handy. I can also replace it with `b:flags` to have the task change per-buffer.

For anything more than a one-liner, though, I’d rather define a new lua function `F` in a scratch file and then make the task `lua F(params)`.

## Drawbacks

Three drawbacks to this over a real task runner plugin:

1.  It doesn’t integrate with quickfix, lsp, etc
2.  You need to know vim scripting pretty well to use it properly
3.  It is ludicrously, hilariously insecure.

The last two drawbacks are good reasons why a publicly shared task runner would *never*, *ever* work like this. I don’t think it’s dangerous if you know what you’re doing, but scale that up to hundreds of thousands of potential devs and yeah there’s no way *something* isn’t going wrong.

If you want to add this to your own config, just drop it wholesale in either your `init.lua` or in an `after/` file. [after/](https://neovim.io/doc/user/options.html#after-directory) is great, I love it.

## On writing small things

So I wrote this post for two reasons:

1.  To show a cool bit of vim tech I made.
2.  To show that people *can* make useful vim tech for their personal use.

(2) is something that more people would benefit from knowing about. There’s not a whole lot out there on leveraging custom functions! So people mostly stick to customization via mappings and plugins. And it’s *totally fine* to use vim this way. Many vim experts don’t roll their own stuff!

At the same time, I believe there’s a lot of devs who would *choose* to write their own functions, and only don’t because they haven’t been exposed to the idea. I didn’t put more than an hour or two into making this and it was well worth it. I’ve written a lot of other functions, too, often for more specific and finicky tasks. Rolling my own functions has been a huge boon to my productivity and I heartily recommend other devs give it a shot.

*Thanks to [TJ DeVries](https://twitter.com/teej_dv) for feedback. If you liked this, I also have a [newsletter](https://buttondown.email/hillelwayne/) I update weekly.*