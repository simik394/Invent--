---
page-title: "akinsho/toggleterm.nvim: A neovim lua plugin to help easily manage multiple terminal windows"
url: https://github.com/akinsho/toggleterm.nvim
date: "2024-06-24 00:30:52"
tags: [a/sw/plugin, f/prod/homepage, c/, p/pwf]
about: ["[[NeoVim]]"]
aliases: 
- 
by: 
length: 18876
dir: 
---

## toggleterm.nvim

[](https://github.com/akinsho/toggleterm.nvim#--toggletermnvim)

A *neovim* plugin to persist and toggle multiple terminals during an editing session

[![toggleterm in action](https://user-images.githubusercontent.com/22454918/224485816-8b0cb1b8-b0e6-4da6-9d71-a7299d39f1a0.gif)](https://user-images.githubusercontent.com/22454918/224485816-8b0cb1b8-b0e6-4da6-9d71-a7299d39f1a0.gif)

### Multiple orientations

[](https://github.com/akinsho/toggleterm.nvim#multiple-orientations)

-   **Float**

[![floating window](https://user-images.githubusercontent.com/22454918/115306123-42d2ac00-a15f-11eb-84fc-c4246ee82a09.png)](https://user-images.githubusercontent.com/22454918/115306123-42d2ac00-a15f-11eb-84fc-c4246ee82a09.png)

-   **Vertical**

[![vertical-terms](https://user-images.githubusercontent.com/22454918/224485828-cd509271-8288-46e2-afb4-4e520fa049cb.png)](https://user-images.githubusercontent.com/22454918/224485828-cd509271-8288-46e2-afb4-4e520fa049cb.png)

-   **Tab**

[![tab orientation](https://user-images.githubusercontent.com/22454918/133490969-6a59e623-79db-4ca7-a73b-ef4b24a73b91.gif)](https://user-images.githubusercontent.com/22454918/133490969-6a59e623-79db-4ca7-a73b-ef4b24a73b91.gif)

### Send commands to different terminals

[](https://github.com/akinsho/toggleterm.nvim#send-commands-to-different-terminals)

[![exec](https://user-images.githubusercontent.com/22454918/112119367-36d1e980-8bb5-11eb-9787-5936391127a3.gif)](https://user-images.githubusercontent.com/22454918/112119367-36d1e980-8bb5-11eb-9787-5936391127a3.gif)

### Winbar (Experimental/Nightly ONLY)

[](https://github.com/akinsho/toggleterm.nvim#winbar-experimentalnightly-only)

[![image](https://user-images.githubusercontent.com/22454918/179199998-75ec16cb-8271-490e-925f-6c82c50ffc5d.png)](https://user-images.githubusercontent.com/22454918/179199998-75ec16cb-8271-490e-925f-6c82c50ffc5d.png)

## Requirements

[](https://github.com/akinsho/toggleterm.nvim#requirements)

This plugin only works in *Neovim 0.7* or newer.

## Installation

[](https://github.com/akinsho/toggleterm.nvim#installation)

Using [packer](https://github.com/wbthomason/packer.nvim) in lua

use {"akinsho/toggleterm.nvim", tag \= '\*', config \= function()
  require("toggleterm").setup()
end}

Using [lazy.nvim](https://github.com/folke/lazy.nvim) in lua

{
  \-- amongst your other plugins
  {'akinsho/toggleterm.nvim', version \= "\*", config \= true}
  \-- or
  {'akinsho/toggleterm.nvim', version \= "\*", opts \= {\--\[\[ things you want to change go here\]\]}}
}

Using [vim-plug](https://github.com/junegunn/vim-plug) in vimscript

Plug 'akinsho/toggleterm.nvim', {'tag' : '\*'}

lua require("toggleterm").setup()

You can/should specify a tag for the current major version of the plugin, to avoid breaking changes as this plugin evolves. To use a version of this plugin compatible with nvim versions less than 0.7 please use the tag `v1.*`.

## Notices

[](https://github.com/akinsho/toggleterm.nvim#notices)

-   **28/07/1990** — If using `persist_mode` terminal mappings should be changed to use `wincmd` instead otherwise persist mode will not work correctly. See [here](https://github.com/akinsho/toggleterm.nvim#terminal-window-mappings) for details.

## Why?

[](https://github.com/akinsho/toggleterm.nvim#why)

Neovim's terminal is a very cool, but not super ergonomic tool to use. I find that I often want to set a process going and leave it to continue to run in the background. I don't need to see it all the time. I just need to be able to refer back to it at intervals. I also sometimes want to create a new terminal and run a few commands.

Sometimes I want these side by side, and I *really* want these terminals to be easy to access. I also want my terminal to look different from non-terminal buffers, so I use `winhighlight` to darken them based on the `Normal` background colour.

This is the exact use case this was designed for. If that's your use case this might work for you.

## Roadmap

[](https://github.com/akinsho/toggleterm.nvim#roadmap)

All I really want this plugin to be is what I described above. A wrapper around the terminal functionality.

It basically (almost) does all that I need it to.

I won't be turning this into a REPL plugin or doing a bunch of complex stuff. If you find any issues, *please* consider a *pull request* not an issue. I'm also going to be pretty conservative about what I add.

### Setup

[](https://github.com/akinsho/toggleterm.nvim#setup)

This plugin must be explicitly enabled by using `require("toggleterm").setup{}`

Setting the `open_mapping` key to use for toggling the terminal(s) will set up mappings for *normal* mode. The `open_mapping` can be a key string or an array of key strings. If you prefix the mapping with a number that particular terminal will be opened. Otherwise if a prefix is not set, then the last toggled terminal will be opened. In case there are multiple terminals opened they'll all be closed, and on the next mapping key they'll be restored.

If you set the `insert_mappings` key to `true`, the mapping will also take effect in insert mode; similarly setting `terminal_mappings` to `true` will have the mappings take effect in the opened terminal.

However you will not be able to use a count with the open mapping in terminal and insert modes. You can create buffer specific mappings to exit terminal mode and then use a count with the open mapping. Check *Terminal window mappings* for an example of how to do this.

alternatively you can do this manually (not recommended but, your prerogative)

" set
autocmd TermEnter term://\*toggleterm#\*
      \\ tnoremap <silent><c-t> <Cmd>exe v:count1 . "ToggleTerm"<CR>
" By applying the mappings this way you can pass a count to your
" mapping to open a specific window.
" For example: 2<C-t> will open terminal 2
nnoremap <silent><c-t> <Cmd>exe v:count1 . "ToggleTerm"<CR>
inoremap <silent><c-t> <Esc><Cmd>exe v:count1 . "ToggleTerm"<CR>

**NOTE**: Please ensure you have set `hidden` in your neovim config, otherwise the terminals will be discarded when closed.

**WARNING**: Please do not copy and paste this configuration! It is here to show what options are available. It is not written to be used as is.

require("toggleterm").setup{
  \-- size can be a number or function which is passed the current terminal
  size \= 20 | function(term)
    if term.direction \== "horizontal" then
      return 15
    elseif term.direction \== "vertical" then
      return vim.o.columns \* 0.4
    end
  end,
  open\_mapping \= \[\[<c-\\>\]\], \-- or { \[\[<c-\\>\]\], \[\[<c-¥>\]\] } if you also use a Japanese keyboard.
  on\_create \= fun(t: Terminal), \-- function to run when the terminal is first created
  on\_open \= fun(t: Terminal), \-- function to run when the terminal opens
  on\_close \= fun(t: Terminal), \-- function to run when the terminal closes
  on\_stdout \= fun(t: Terminal, job: number, data: string\[\], name: string) \-- callback for processing output on stdout
  on\_stderr \= fun(t: Terminal, job: number, data: string\[\], name: string) \-- callback for processing output on stderr
  on\_exit \= fun(t: Terminal, job: number, exit\_code: number, name: string) \-- function to run when terminal process exits
  hide\_numbers \= true, \-- hide the number column in toggleterm buffers
  shade\_filetypes \= {},
  autochdir \= false, \-- when neovim changes it current directory the terminal will change it's own when next it's opened
  highlights \= {
    \-- highlights which map to a highlight group name and a table of it's values
    \-- NOTE: this is only a subset of values, any group placed here will be set for the terminal window split
    Normal \= {
      guibg \= "<VALUE-HERE>",
    },
    NormalFloat \= {
      link \= 'Normal'
    },
    FloatBorder \= {
      guifg \= "<VALUE-HERE>",
      guibg \= "<VALUE-HERE>",
    },
  },
  shade\_terminals \= true, \-- NOTE: this option takes priority over highlights specified so if you specify Normal highlights you should set this to false
  shading\_factor \= '<number>', \-- the percentage by which to lighten terminal background, default: -30 (gets multiplied by -3 if background is light)
  start\_in\_insert \= true,
  insert\_mappings \= true, \-- whether or not the open mapping applies in insert mode
  terminal\_mappings \= true, \-- whether or not the open mapping applies in the opened terminals
  persist\_size \= true,
  persist\_mode \= true, \-- if set to true (default) the previous terminal mode will be remembered
  direction \= 'vertical' | 'horizontal' | 'tab' | 'float',
  close\_on\_exit \= true, \-- close the terminal window when the process exits
   \-- Change the default shell. Can be a string or a function returning a string
  shell \= vim.o.shell,
  auto\_scroll \= true, \-- automatically scroll to the bottom on terminal output
  \-- This field is only relevant if direction is set to 'float'
  float\_opts \= {
    \-- The border key is \*almost\* the same as 'nvim\_open\_win'
    \-- see :h nvim\_open\_win for details on borders however
    \-- the 'curved' border is a custom border type
    \-- not natively supported but implemented in this plugin.
    border \= 'single' | 'double' | 'shadow' | 'curved' | ... other options supported by win open
    \-- like \`size\`, width, height, row, and col can be a number or function which is passed the current terminal
    width \= <value>,
    height \= <value>,
    row \= <value>,
    col \= <value>,
    winblend \= 3,
    zindex \= <value>,
    title\_pos \= 'left' | 'center' | 'right', position of the title of the floating window
  },
  winbar \= {
    enabled \= false,
    name\_formatter \= function(term) \--  term: Terminal
      return term.name
    end
  },
}

### Usage

[](https://github.com/akinsho/toggleterm.nvim#usage)

### `ToggleTerm`

[](https://github.com/akinsho/toggleterm.nvim#toggleterm)

This is the command the mappings call under the hood. You can use it directly and prefix it with a count to target a specific terminal. This function also takes arguments `size`, `dir`, `direction` and `name`. e.g.

:ToggleTerm size\=40 dir\=~/Desktop direction\=horizontal name\=desktop

If `dir` is specified on creation toggle term will open at the specified directory. If the terminal has already been opened at a particular directory it will remain in that directory.

The directory can also be specified as `git_dir` which toggleterm will then use to try and derive the git repo directory. *NOTE*: This will not work for `git-worktrees` or other more complex setups.

If `size` is specified, and the command opens a split (horizontal/vertical) terminal, the height/width of all terminals in the same direction will be changed to `size`.

If `direction` is specified, and the command opens a terminal, the terminal will be changed to the specified direction.

If `name` is specified, the display name is set for the toggled terminal. This name will be visible when using `TermSelect` command to indicate the specific terminal.

`size` and `direction` are ignored if the command closes a terminal.

#### Caveats

[](https://github.com/akinsho/toggleterm.nvim#caveats)

-   Having multiple terminals with different directions open at the same time is unsupported.

### `ToggleTermToggleAll`

[](https://github.com/akinsho/toggleterm.nvim#toggletermtoggleall)

This command allows you to open all the previously toggled terminal in one go or close all the open terminals at once.

### `TermExec`

[](https://github.com/akinsho/toggleterm.nvim#termexec)

This command allows you to open a terminal with a specific action. e.g. `2TermExec cmd="git status" dir=~/<my-repo-path>` will run git status in terminal 2. note that the `cmd` argument **must be quoted**.

*NOTE:* the `dir` argument can also be *optionally* quoted if it contains spaces.

The `cmd` and `dir` arguments can also expand the same special keywords as `:h expand` e.g. `TermExec cmd="echo %"` will be expanded to `TermExec cmd="echo /file/example"`

These special keywords can be escaped using the `\` character, if you want to print character as is.

The `size`, `direction` and `name` arguments are like the `size`, `direction` and `name` arguments of `ToggleTerm`.

By default, focus is returned to the original window after executing the command (except for floating terminals). Use argument `go_back=0` to disable this behaviour.

You can send commands to a terminal without opening its window by using the `open=0` argument.

see `:h expand()` for more details

### TermSelect

[](https://github.com/akinsho/toggleterm.nvim#termselect)

This command uses `vim.ui.select` to allow a user to select a terminal to open or to focus it if it's already open. This can be useful if you have a lot of terminals and want to open a specific one.

### Sending lines to the terminal

[](https://github.com/akinsho/toggleterm.nvim#sending-lines-to-the-terminal)

You can "send lines" to the toggled terminals with the following commands:

-   `:ToggleTermSendCurrentLine <T_ID>`: sends the whole line where you are standing with your cursor
-   `:ToggleTermSendVisualLines <T_ID>`: sends all the (whole) lines in your visual selection
-   `:ToggleTermSendVisualSelection <T_ID>`: sends only the visually selected text (this can be a block of text or a selection in a single line)

(`<T_ID` is an optional terminal ID parameter, which defines where should we send the lines. If the parameter is not provided, then the default is the `first terminal`)

Alternatively, for more fine-grained control and use in mappings, in lua:

local trim\_spaces \= true
vim.keymap.set("v", "<space>s", function()
    require("toggleterm").send\_lines\_to\_terminal("single\_line", trim\_spaces, { args \= vim.v.count })
end)
    \-- Replace with these for the other two options
    \-- require("toggleterm").send\_lines\_to\_terminal("visual\_lines", trim\_spaces, { args = vim.v.count })
    \-- require("toggleterm").send\_lines\_to\_terminal("visual\_selection", trim\_spaces, { args = vim.v.count })

\-- For use as an operator map:
\-- Send motion to terminal
vim.keymap.set("n", \[\[<leader><c-\\>\]\], function()
  set\_opfunc(function(motion\_type)
    require("toggleterm").send\_lines\_to\_terminal(motion\_type, false, { args \= vim.v.count })
  end)
  vim.api.nvim\_feedkeys("g@", "n", false)
end)
\-- Double the command to send line to terminal
vim.keymap.set("n", \[\[<leader><c-\\><c-\\>\]\], function()
  set\_opfunc(function(motion\_type)
    require("toggleterm").send\_lines\_to\_terminal(motion\_type, false, { args \= vim.v.count })
  end)
  vim.api.nvim\_feedkeys("g@\_", "n", false)
end)
\-- Send whole file
vim.keymap.set("n", \[\[<leader><leader><c-\\>\]\], function()
  set\_opfunc(function(motion\_type)
    require("toggleterm").send\_lines\_to\_terminal(motion\_type, false, { args \= vim.v.count })
  end)
  vim.api.nvim\_feedkeys("ggg@G''", "n", false)
end)

Set `trim_spaces=false` for sending to REPLs for whitespace-sensitive languages like python. (For python, you probably want to start ipython with `ipython --no-autoindent`.)

Example:

send\_lines\_example.mov

### ToggleTermSetName

[](https://github.com/akinsho/toggleterm.nvim#toggletermsetname)

This function allows setting a display name for a terminal. This name is primarily used inside the winbar, and can be a more descriptive way to remember, which terminal is for what.

You can map this to a key and call it with a count, which will then prompt you a name for the terminal with the matching ID. Alternatively you can call it with just the name e.g. `:ToggleTermSetName work<CR>` this will the prompt you for which terminal it should apply to. Lastly you can call it without any arguments, and it will prompt you for which terminal it should apply to then prompt you for the name to use.

### Set terminal shading

[](https://github.com/akinsho/toggleterm.nvim#set-terminal-shading)

This plugin automatically shades terminal filetypes to be darker than other window you can disable this by setting `shade_terminals = false` in the setup object

require'toggleterm'.setup {
  shade\_terminals \= false
}

alternatively you can set, *which* filetypes should be shaded by setting

\-- fzf is just an example
require'toggleterm'.setup {
  shade\_filetypes \= { "none", "fzf" }
}

setting `"none"` will allow normal terminal buffers to be highlighted.

### Set persistent size

[](https://github.com/akinsho/toggleterm.nvim#set-persistent-size)

By default, this plugin will persist the size of horizontal and vertical terminals. Split terminals in the same direction always have the same size. You can disable this behaviour by setting `persist_size = false` in the setup object. Disabling this behaviour forces the opening terminal size to the `size` defined in the setup object.

require'toggleterm'.setup{
  persist\_size \= false
}

### Terminal window mappings

[](https://github.com/akinsho/toggleterm.nvim#terminal-window-mappings)

It can be helpful to add mappings to make moving in and out of a terminal easier once toggled, whilst still keeping it open.

function \_G.set\_terminal\_keymaps()
  local opts \= {buffer \= 0}
  vim.keymap.set('t', '<esc>', \[\[<C-\\><C-n>\]\], opts)
  vim.keymap.set('t', 'jk', \[\[<C-\\><C-n>\]\], opts)
  vim.keymap.set('t', '<C-h>', \[\[<Cmd>wincmd h<CR>\]\], opts)
  vim.keymap.set('t', '<C-j>', \[\[<Cmd>wincmd j<CR>\]\], opts)
  vim.keymap.set('t', '<C-k>', \[\[<Cmd>wincmd k<CR>\]\], opts)
  vim.keymap.set('t', '<C-l>', \[\[<Cmd>wincmd l<CR>\]\], opts)
  vim.keymap.set('t', '<C-w>', \[\[<C-\\><C-n><C-w>\]\], opts)
end

\-- if you only want these mappings for toggle term use term://\*toggleterm#\* instead
vim.cmd('autocmd! TermOpen term://\* lua set\_terminal\_keymaps()')

### Custom Terminals

[](https://github.com/akinsho/toggleterm.nvim#custom-terminals)

[![lazy git](https://user-images.githubusercontent.com/22454918/116447435-e69f1480-a84f-11eb-86dd-19fa29646aa1.png)](https://user-images.githubusercontent.com/22454918/116447435-e69f1480-a84f-11eb-86dd-19fa29646aa1.png) *using [lazygit](https://github.com/jesseduffield/lazygit)*

Toggleterm also exposes the `Terminal` class so that this can be used to create custom terminals for showing terminal UIs like `lazygit`, `htop` etc.

Each terminal can take the following arguments:

Terminal:new {
  cmd \= string \-- command to execute when creating the terminal e.g. 'top'
  display\_name \= string \-- the name of the terminal
  direction \= string \-- the layout for the terminal, same as the main config options
  dir \= string \-- the directory for the terminal
  close\_on\_exit \= bool \-- close the terminal window when the process exits
  highlights \= table \-- a table with highlights
  env \= table \-- key:value table with environmental variables passed to jobstart()
  clear\_env \= bool \-- use only environmental variables from \`env\`, passed to jobstart()
  on\_open \= fun(t: Terminal) \-- function to run when the terminal opens
  on\_close \= fun(t: Terminal) \-- function to run when the terminal closes
  auto\_scroll \= boolean \-- automatically scroll to the bottom on terminal output
  \-- callbacks for processing the output
  on\_stdout \= fun(t: Terminal, job: number, data: string\[\], name: string) \-- callback for processing output on stdout
  on\_stderr \= fun(t: Terminal, job: number, data: string\[\], name: string) \-- callback for processing output on stderr
  on\_exit \= fun(t: Terminal, job: number, exit\_code: number, name: string) \-- function to run when terminal process exits
}

If you want to spawn a custom terminal without running any command, you can omit the `cmd` option.

#### Custom terminal usage

[](https://github.com/akinsho/toggleterm.nvim#custom-terminal-usage)

local Terminal  \= require('toggleterm.terminal').Terminal
local lazygit \= Terminal:new({ cmd \= "lazygit", hidden \= true })

function \_lazygit\_toggle()
  lazygit:toggle()
end

vim.api.nvim\_set\_keymap("n", "<leader>g", "<cmd>lua \_lazygit\_toggle()<CR>", {noremap \= true, silent \= true})

This will create a new terminal, but the specified command is not being run immediately. The command will run once the terminal is opened. Alternatively `term:spawn()` can be used to start the command in a background buffer without opening a terminal window yet. If the `hidden` key is set to true, this terminal will not be toggled by normal toggleterm commands such as `:ToggleTerm` or the open mapping. It will only open and close by using the returned terminal object. A mapping for toggling the terminal can be set as in the example above.

Alternatively the terminal can be specified with a count, which is the number that can be used to trigger this specific terminal. This can then be triggered using the current count e.g. `:5ToggleTerm<CR>`

local lazygit \= Terminal:new({ cmd \= "lazygit", count \= 5 })

You can also set a custom layout for a terminal.

local lazygit \= Terminal:new({
  cmd \= "lazygit",
  dir \= "git\_dir",
  direction \= "float",
  float\_opts \= {
    border \= "double",
  },
  \-- function to run on opening the terminal
  on\_open \= function(term)
    vim.cmd("startinsert!")
    vim.api.nvim\_buf\_set\_keymap(term.bufnr, "n", "q", "<cmd>close<CR>", {noremap \= true, silent \= true})
  end,
  \-- function to run on closing the terminal
  on\_close \= function(term)
    vim.cmd("startinsert!")
  end,
})

function \_lazygit\_toggle()
  lazygit:toggle()
end

vim.api.nvim\_set\_keymap("n", "<leader>g", "<cmd>lua \_lazygit\_toggle()<CR>", {noremap \= true, silent \= true})

**WARNING**: do not use any of the private functionality of the terminal or other non-public parts of the API as these can change in the future.

### Statusline

[](https://github.com/akinsho/toggleterm.nvim#statusline)

To tell each terminal apart you can use the terminal buffer variable `b:toggle_number` in your statusline

" this is pseudo code
let statusline .= '%{&ft == "toggleterm" ? "terminal (".b:toggle\_number.")" : ""}'

### Custom commands

[](https://github.com/akinsho/toggleterm.nvim#custom-commands)

You can create your own commands by using the lua functions this plugin provides directly

command! -count\=1 TermGitPush  lua require'toggleterm'.exec("git push",    <count>, 12)
command! -count\=1 TermGitPushF lua require'toggleterm'.exec("git push -f", <count>, 12)

### Open multiple terminals side-by-side

[](https://github.com/akinsho/toggleterm.nvim#open-multiple-terminals-side-by-side)

Direction

Supported

vertical

✔️

horizontal

✔️

tab

✖️

float

✖️

In your first terminal, you need to leave the `TERMINAL` mode using C-\\C-N which can be remapped to Esc for ease of use. [![image](https://user-images.githubusercontent.com/31947091/133395516-22fef1e6-633d-4964-9175-f76fabf66794.png)](https://user-images.githubusercontent.com/31947091/133395516-22fef1e6-633d-4964-9175-f76fabf66794.png)

Then you type on: `2<C-\>`, and the result: [![image](https://user-images.githubusercontent.com/31947091/133396789-fdf68b30-3a8c-440b-822f-6549f282c4fc.png)](https://user-images.githubusercontent.com/31947091/133396789-fdf68b30-3a8c-440b-822f-6549f282c4fc.png)

Explain:

-   `2`: this is the terminal's number (or ID), your first terminal is `1` (e.g. your 3rd terminal will be `3<C-\>`, so on).
-   C-\\: this is the combined key mapping to the command `:ToggleTerm`.

### FAQ

[](https://github.com/akinsho/toggleterm.nvim#faq)

#### How do I get this plugin to work with Powershell?

[](https://github.com/akinsho/toggleterm.nvim#how-do-i-get-this-plugin-to-work-with-powershell)

Please check out the [Wiki section on this topic](https://github.com/akinsho/toggleterm.nvim/wiki/Tips-and-Tricks#using-toggleterm-with-powershell).