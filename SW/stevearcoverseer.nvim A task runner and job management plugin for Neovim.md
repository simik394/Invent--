---
page-title: "stevearc/overseer.nvim: A task runner and job management plugin for Neovim"
url: https://github.com/stevearc/overseer.nvim
date: "2024-08-16 23:41:29"
tags: [a/sw/plugin, f/prod/homepage, c/, p/pwf/automation]
about: ["[[NeoVim]]"]
aliases: 
- 
by: 
length: 4050
dir: 
---

## overseer.nvim

[](https://github.com/stevearc/overseer.nvim#overseernvim)

A task runner and job management plugin for Neovim

-   [Features](https://github.com/stevearc/overseer.nvim#features)
-   [Requirements](https://github.com/stevearc/overseer.nvim#requirements)
-   [Installation](https://github.com/stevearc/overseer.nvim#installation)
-   [Quick start](https://github.com/stevearc/overseer.nvim#quick-start)
-   [Tutorials](https://github.com/stevearc/overseer.nvim#tutorials)
    -   [Build a C++ file](https://github.com/stevearc/overseer.nvim/blob/master/doc/tutorials.md#build-a-c-file)
    -   [Run a file on save](https://github.com/stevearc/overseer.nvim/blob/master/doc/tutorials.md#run-a-file-on-save)
-   [Guides](https://github.com/stevearc/overseer.nvim#guides)
    -   [Custom tasks](https://github.com/stevearc/overseer.nvim/blob/master/doc/guides.md#custom-tasks)
    -   [Actions](https://github.com/stevearc/overseer.nvim/blob/master/doc/guides.md#actions)
    -   [Custom components](https://github.com/stevearc/overseer.nvim/blob/master/doc/guides.md#custom-components)
    -   [Customizing built-in tasks](https://github.com/stevearc/overseer.nvim/blob/master/doc/guides.md#customizing-built-in-tasks)
    -   [Parsing output](https://github.com/stevearc/overseer.nvim/blob/master/doc/guides.md#parsing-output)
    -   [Running tasks sequentially](https://github.com/stevearc/overseer.nvim/blob/master/doc/guides.md#running-tasks-sequentially)
    -   [VS Code tasks](https://github.com/stevearc/overseer.nvim/blob/master/doc/guides.md#vs-code-tasks)
-   [Explanation](https://github.com/stevearc/overseer.nvim#explanation)
    -   [Architecture](https://github.com/stevearc/overseer.nvim/blob/master/doc/explanation.md#architecture)
    -   [Task list](https://github.com/stevearc/overseer.nvim/blob/master/doc/explanation.md#task-list)
    -   [Task editor](https://github.com/stevearc/overseer.nvim/blob/master/doc/explanation.md#task-editor)
    -   [Alternatives](https://github.com/stevearc/overseer.nvim/blob/master/doc/explanation.md#alternatives)
    -   [FAQ](https://github.com/stevearc/overseer.nvim/blob/master/doc/explanation.md#faq)
-   [Third-party integrations](https://github.com/stevearc/overseer.nvim#third-party-integrations)
    -   [Lualine](https://github.com/stevearc/overseer.nvim/blob/master/doc/third_party.md#lualine)
    -   [Heirline](https://github.com/stevearc/overseer.nvim/blob/master/doc/third_party.md#heirline)
    -   [Neotest](https://github.com/stevearc/overseer.nvim/blob/master/doc/third_party.md#neotest)
    -   [DAP](https://github.com/stevearc/overseer.nvim/blob/master/doc/third_party.md#dap)
    -   [ToggleTerm](https://github.com/stevearc/overseer.nvim/blob/master/doc/third_party.md#toggleterm)
    -   [Session managers](https://github.com/stevearc/overseer.nvim/blob/master/doc/third_party.md#session-managers)
-   [Recipes](https://github.com/stevearc/overseer.nvim#recipes)
    -   [Restart last task](https://github.com/stevearc/overseer.nvim/blob/master/doc/recipes.md#restart-last-task)
    -   [Run shell scripts in the current directory](https://github.com/stevearc/overseer.nvim/blob/master/doc/recipes.md#run-shell-scripts-in-the-current-directory)
    -   [Directory-local tasks with exrc](https://github.com/stevearc/overseer.nvim/blob/master/doc/recipes.md#directory-local-tasks-with-exrc)
    -   [:Make similar to vim-dispatch](https://github.com/stevearc/overseer.nvim/blob/master/doc/recipes.md#make-similar-to-vim-dispatch)
    -   [Asynchronous :Grep command](https://github.com/stevearc/overseer.nvim/blob/master/doc/recipes.md#asynchronous-grep-command)
-   [Reference](https://github.com/stevearc/overseer.nvim#reference)
    -   [Setup options](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#setup-options)
    -   [Commands](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#commands)
    -   [Highlight groups](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#highlight-groups)
    -   [Lua API](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#lua-api)
    -   [Components](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#components)
    -   [Strategies](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#strategies)
    -   [Parsers](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#parsers)
    -   [Parameters](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#parameters)
-   [Screenshots](https://github.com/stevearc/overseer.nvim#screenshots)

## Features

[](https://github.com/stevearc/overseer.nvim#features)

-   Built-in support for many task frameworks (make, npm, cargo, `.vscode/tasks.json`, etc)
-   Simple integration with vim.diagnostics and quickfix
-   UI for viewing and managing tasks
-   Quick controls for common actions (restart task, rerun on save, or user-defined functions)
-   Extreme customizability. Very easy to attach custom logic to tasks
-   Define and run complex multi-stage workflows
-   Support for `preLaunchTask` when used with [nvim-dap](https://github.com/mfussenegger/nvim-dap)

## Requirements

[](https://github.com/stevearc/overseer.nvim#requirements)

-   Neovim 0.8+ (for older versions, use the [nvim-0.7 branch](https://github.com/stevearc/overseer.nvim/tree/nvim-0.7))
-   (optional) patches for `vim.ui` (e.g. [dressing.nvim](https://github.com/stevearc/dressing.nvim)). Provides nicer UI for input and selection.
-   (optional) [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim). When used with [dressing.nvim](https://github.com/stevearc/dressing.nvim) provides best selection UI.
-   (optional) [nvim-notify](https://github.com/rcarriga/nvim-notify) a nice UI for `vim.notify`

## Installation

[](https://github.com/stevearc/overseer.nvim#installation)

overseer supports all the usual plugin managers

lazy.nvim

{
  'stevearc/overseer.nvim',
  opts \= {},
}

Packer

require('packer').startup(function()
    use {
      'stevearc/overseer.nvim',
      config \= function() require('overseer').setup() end
    }
end)

Paq

require "paq" {
    {'stevearc/overseer.nvim'};
}

vim-plug

Plug 'stevearc/overseer.nvim'

dein

call dein#add('stevearc/overseer.nvim')

Pathogen

git clone --depth=1 https://github.com/stevearc/overseer.nvim.git ~/.vim/bundle/

Neovim native package

git clone --depth=1 https://github.com/stevearc/overseer.nvim.git \\
  "${XDG\_DATA\_HOME:-$HOME/.local/share}"/nvim/site/pack/overseer/start/overseer.nvim

## Quick start

[](https://github.com/stevearc/overseer.nvim#quick-start)

Add the following to your init.lua

require('overseer').setup()

To get started, all you need to know is `:OverseerRun` to select and start a task, and `:OverseerToggle` to open the task list.

demo.mp4

If you don't see any tasks from `:OverseerRun`, it might mean that your task runner is not yet supported. There is currently support for VS Code tasks, make, npm, cargo, and some others. If yours is not supported, ([request support here](https://github.com/stevearc/overseer.nvim/issues/new/choose)).

If you want to define custom tasks for your project, I'd recommend starting with [the tutorials](https://github.com/stevearc/overseer.nvim/blob/master/doc/tutorials.md).

## Tutorials

[](https://github.com/stevearc/overseer.nvim#tutorials)

-   [Build a C++ file](https://github.com/stevearc/overseer.nvim/blob/master/doc/tutorials.md#build-a-c-file)
-   [Run a file on save](https://github.com/stevearc/overseer.nvim/blob/master/doc/tutorials.md#run-a-file-on-save)

## Guides

[](https://github.com/stevearc/overseer.nvim#guides)

-   [Custom tasks](https://github.com/stevearc/overseer.nvim/blob/master/doc/guides.md#custom-tasks)
    -   [Template definition](https://github.com/stevearc/overseer.nvim/blob/master/doc/guides.md#template-definition)
    -   [Template providers](https://github.com/stevearc/overseer.nvim/blob/master/doc/guides.md#template-providers)
-   [Actions](https://github.com/stevearc/overseer.nvim/blob/master/doc/guides.md#actions)
-   [Custom components](https://github.com/stevearc/overseer.nvim/blob/master/doc/guides.md#custom-components)
    -   [Component aliases](https://github.com/stevearc/overseer.nvim/blob/master/doc/guides.md#component-aliases)
    -   [Task result](https://github.com/stevearc/overseer.nvim/blob/master/doc/guides.md#task-result)
-   [Customizing built-in tasks](https://github.com/stevearc/overseer.nvim/blob/master/doc/guides.md#customizing-built-in-tasks)
-   [Parsing output](https://github.com/stevearc/overseer.nvim/blob/master/doc/guides.md#parsing-output)
-   [Running tasks sequentially](https://github.com/stevearc/overseer.nvim/blob/master/doc/guides.md#running-tasks-sequentially)
-   [VS Code tasks](https://github.com/stevearc/overseer.nvim/blob/master/doc/guides.md#vs-code-tasks)

## Explanation

[](https://github.com/stevearc/overseer.nvim#explanation)

-   [Architecture](https://github.com/stevearc/overseer.nvim/blob/master/doc/explanation.md#architecture)
    -   [Tasks](https://github.com/stevearc/overseer.nvim/blob/master/doc/explanation.md#tasks)
    -   [Components](https://github.com/stevearc/overseer.nvim/blob/master/doc/explanation.md#components)
    -   [Templates](https://github.com/stevearc/overseer.nvim/blob/master/doc/explanation.md#templates)
-   [Task list](https://github.com/stevearc/overseer.nvim/blob/master/doc/explanation.md#task-list)
-   [Task editor](https://github.com/stevearc/overseer.nvim/blob/master/doc/explanation.md#task-editor)
-   [Alternatives](https://github.com/stevearc/overseer.nvim/blob/master/doc/explanation.md#alternatives)
-   [FAQ](https://github.com/stevearc/overseer.nvim/blob/master/doc/explanation.md#faq)

## Third-party integrations

[](https://github.com/stevearc/overseer.nvim#third-party-integrations)

-   [Lualine](https://github.com/stevearc/overseer.nvim/blob/master/doc/third_party.md#lualine)
-   [Heirline](https://github.com/stevearc/overseer.nvim/blob/master/doc/third_party.md#heirline)
-   [Neotest](https://github.com/stevearc/overseer.nvim/blob/master/doc/third_party.md#neotest)
-   [DAP](https://github.com/stevearc/overseer.nvim/blob/master/doc/third_party.md#dap)
-   [ToggleTerm](https://github.com/stevearc/overseer.nvim/blob/master/doc/third_party.md#toggleterm)
-   [Session managers](https://github.com/stevearc/overseer.nvim/blob/master/doc/third_party.md#session-managers)
    -   [resession.nvim](https://github.com/stevearc/overseer.nvim/blob/master/doc/third_party.md#resessionnvim)
    -   [Other session managers](https://github.com/stevearc/overseer.nvim/blob/master/doc/third_party.md#other-session-managers)

## Recipes

[](https://github.com/stevearc/overseer.nvim#recipes)

-   [Restart last task](https://github.com/stevearc/overseer.nvim/blob/master/doc/recipes.md#restart-last-task)
-   [Run shell scripts in the current directory](https://github.com/stevearc/overseer.nvim/blob/master/doc/recipes.md#run-shell-scripts-in-the-current-directory)
-   [Directory-local tasks with exrc](https://github.com/stevearc/overseer.nvim/blob/master/doc/recipes.md#directory-local-tasks-with-exrc)
-   [:Make similar to vim-dispatch](https://github.com/stevearc/overseer.nvim/blob/master/doc/recipes.md#make-similar-to-vim-dispatch)
-   [Asynchronous :Grep command](https://github.com/stevearc/overseer.nvim/blob/master/doc/recipes.md#asynchronous-grep-command)

## Reference

[](https://github.com/stevearc/overseer.nvim#reference)

-   [Setup options](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#setup-options)
-   [Commands](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#commands)
-   [Highlight groups](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#highlight-groups)
-   [Lua API](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#lua-api)
    -   [setup(opts)](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#setupopts)
    -   [on\_setup(callback)](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#on_setupcallback)
    -   [new\_task(opts)](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#new_taskopts)
    -   [toggle(opts)](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#toggleopts)
    -   [open(opts)](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#openopts)
    -   [close()](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#close)
    -   [list\_task\_bundles()](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#list_task_bundles)
    -   [load\_task\_bundle(name, opts)](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#load_task_bundlename-opts)
    -   [save\_task\_bundle(name, tasks, opts)](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#save_task_bundlename-tasks-opts)
    -   [delete\_task\_bundle(name)](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#delete_task_bundlename)
    -   [list\_tasks(opts)](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#list_tasksopts)
    -   [run\_template(opts, callback)](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#run_templateopts-callback)
    -   [preload\_task\_cache(opts, cb)](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#preload_task_cacheopts-cb)
    -   [clear\_task\_cache(opts)](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#clear_task_cacheopts)
    -   [run\_action(task, name)](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#run_actiontask-name)
    -   [wrap\_template(base, override, default\_params)](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#wrap_templatebase-override-default_params)
    -   [add\_template\_hook(opts, hook)](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#add_template_hookopts-hook)
    -   [remove\_template\_hook(opts, hook)](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#remove_template_hookopts-hook)
    -   [register\_template(defn)](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#register_templatedefn)
    -   [load\_template(name)](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#load_templatename)
    -   [debug\_parser()](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#debug_parser)
    -   [register\_alias(name, components)](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#register_aliasname-components)
-   [Components](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#components)
-   [Strategies](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#strategies)
-   [Parsers](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#parsers)
-   [Parameters](https://github.com/stevearc/overseer.nvim/blob/master/doc/reference.md#parameters)

## Screenshots

[](https://github.com/stevearc/overseer.nvim#screenshots)

2022-07-23.12-42-37.mp4