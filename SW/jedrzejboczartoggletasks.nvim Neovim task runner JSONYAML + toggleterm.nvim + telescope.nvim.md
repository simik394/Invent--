---
page-title: "jedrzejboczar/toggletasks.nvim: Neovim task runner: JSON/YAML + toggleterm.nvim + telescope.nvim"
url: https://github.com/jedrzejboczar/toggletasks.nvim
date: "2024-08-16 23:41:12"
tags: [a/sw/plugin, f/prod/homepage, c/, p/pwf/automation]
about: ["[[NeoVim]]"]
aliases: 
- 
by: 
length: 13021
dir: 
---

[![Lint](https://github.com/jedrzejboczar/toggletasks.nvim/actions/workflows/lint.yml/badge.svg)](https://github.com/jedrzejboczar/toggletasks.nvim/actions/workflows/lint.yml)

## toggletasks.nvim

[](https://github.com/jedrzejboczar/toggletasks.nvim#toggletasksnvim)

Neovim task runner: JSON/YAML + [toggleterm.nvim](https://github.com/akinsho/toggleterm.nvim) + [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim/).

## Features

[](https://github.com/jedrzejboczar/toggletasks.nvim#features)

-   Define task via JSON, similarly to [VS Code Tasks](https://code.visualstudio.com/Docs/editor/tasks)
-   Support for **YAML**\-based configuration using [lyaml](https://github.com/gvvaughan/lyaml)
-   Collect configs from multiple directories: global/tab/win CWD, LSP root dir
-   Run tasks in terminals managed by [toggleterm](https://github.com/akinsho/toggleterm.nvim)
-   Use [telescope](https://github.com/nvim-telescope/telescope.nvim/) to spawn single/multiple tasks
-   Filter tasks based on #tags defined in config files
-   Use [telescope](https://github.com/nvim-telescope/telescope.nvim/) to view/open/kill tasks
-   Automatic spawning on e.g. `SessionLoadPost` (see [Automatic task spawning](https://github.com/jedrzejboczar/toggletasks.nvim#automatic-task-spawning))

[![usage video example](https://camo.githubusercontent.com/842aa10ebab690a237f5597fc91c5394c16e6db51f6d7adbe0ec326ba2c5a3a0/68747470733a2f2f6d656469612e67697068792e636f6d2f6d656469612f4a7254454f3071386c6b4c564e4c726568512f67697068792e676966)](https://camo.githubusercontent.com/842aa10ebab690a237f5597fc91c5394c16e6db51f6d7adbe0ec326ba2c5a3a0/68747470733a2f2f6d656469612e67697068792e636f6d2f6d656469612f4a7254454f3071386c6b4c564e4c726568512f67697068792e676966)

## Other options

[](https://github.com/jedrzejboczar/toggletasks.nvim#other-options)

If you're looking for even more features I'd recommend trying [overseer.nvim](https://github.com/stevearc/overseer.nvim), as toggletasks.nvim probably won't be receiving new features in the nearest future. See [#16 (comment)](https://github.com/jedrzejboczar/toggletasks.nvim/issues/16#issuecomment-1460742344) for more info.

## Overview

[](https://github.com/jedrzejboczar/toggletasks.nvim#overview)

The main idea behind this plugin is to be able to easily define build/setup commands for different projects, independently of your global editor configuration and to easily manage multiple background tasks.

This task management plugin is heavily inspired by plugins such as [yabs.nvim](https://github.com/pianocomposer321/yabs.nvim) and [projectlaunch.nvim](https://github.com/sheodox/projectlaunch.nvim), as well as by [VS Code Tasks](https://code.visualstudio.com/Docs/editor/tasks). In fact, initially I planned to just extend [projectlaunch.nvim](https://github.com/sheodox/projectlaunch.nvim) but after some work I decided that it would require to much changes and it will be easier to write a separate plugin.

The main difference between [toggletasks.nvim](https://github.com/jedrzejboczar/toggletasks.nvim) and other plugins is that toggletasks strictly integrates with existing solutions instead of writing things from scratch, i.e.

-   no terminal management from scratch - integrate with [toggleterm.nvim](https://github.com/akinsho/toggleterm.nvim)
-   no selection UI from scratch - integrate with [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim/)

Other differences:

-   `yabs.nvim` (currently, see [blog post](https://pianocomposer321.github.io/2022/05/03/why-im-rewriting-yabs.html)) sources arbitrary Lua files; toggletasks uses only JSON which is much safer, though less powerfull
-   `yabs.nvim` has the concept of different outputs/runners; toggletasks always uses toggleterm.nvim
-   `projectlaunch.nvim` has a dedicated UI for managing tasks and running groups of tasks; toggletasks uses telescope to achieve similar results, allowing for multi-selection when spawning/selecting tasks
-   `projectlaunch.nvim` has builtin runners for things like package.json/Makefile; this is not supported, but maybe something to consider in the future

## Installation

[](https://github.com/jedrzejboczar/toggletasks.nvim#installation)

Example using [packer.nvim](https://github.com/wbthomason/packer.nvim):

use {
    'jedrzejboczar/toggletasks.nvim',
    requires \= {
        'nvim-lua/plenary.nvim',
        'akinsho/toggleterm.nvim',
        'nvim-telescope/telescope.nvim/',
    },
    \-- To enable YAML config support
    rocks \= 'lyaml',
}

## Configuration

[](https://github.com/jedrzejboczar/toggletasks.nvim#configuration)

Run `require('toggletasks').setup { ... }` in your `init.lua` to configure this plugin. Available options (with default values):

require('toggletasks').setup {
    debug \= false,
    silent \= false,  \-- don't show "info" messages
    short\_paths \= true,  \-- display relative paths when possible
    \-- Paths (without extension) to task configuration files (relative to scanned directory)
    \-- All supported extensions will be tested, e.g. '.toggletasks.json', '.toggletasks.yaml'
    search\_paths \= {
        'toggletasks',
        '.toggletasks',
        '.nvim/toggletasks',
    },
    \-- Directories to consider when searching for available tasks for current window
    scan \= {
        global\_cwd \= true,    \-- vim.fn.getcwd(-1, -1)
        tab\_cwd \= true,       \-- vim.fn.getcwd(-1, tab)
        win\_cwd \= true,       \-- vim.fn.getcwd(win)
        lsp\_root \= true,      \-- root\_dir for first LSP available for the buffer
        dirs \= {},            \-- explicit list of directories to search or function(win): dirs
        rtp \= false,          \-- scan directories in &runtimepath
        rtp\_ftplugin \= false, \-- scan in &rtp by filetype, e.g. ftplugin/c/toggletasks.json
    },
    tasks \= {}, \-- list of global tasks or function(win): tasks
                \-- this is basically the "Config format" defined using Lua tables
    \-- Language server priorities when selecting lsp\_root (default is 0)
    lsp\_priorities \= {
        \['null-ls'\] \= \-10,
    },
    \-- Defaults used when opening task's terminal (see Terminal:new() in toggleterm/terminal.lua)
    toggleterm \= {
        close\_on\_exit \= false,
        hidden \= true,
    },
    \-- Configuration of telescope pickers
    telescope \= {
        spawn \= {
            open\_single \= true,  \-- auto-open terminal window when spawning a single task
            show\_running \= false, \-- include already running tasks in picker candidates
            \-- Replaces default select\_\* actions to spawn task (and change toggleterm
            \-- direction for select horiz/vert/tab)
            mappings \= {
                select\_float \= '<C-f>',
                spawn\_smart \= '<C-a>',  \-- all if no entries selected, else use multi-select
                spawn\_all \= '<M-a>',    \-- all visible entries
                spawn\_selected \= nil,   \-- entries selected via multi-select (default <tab>)
            },
        },
        \-- Replaces default select\_\* actions to open task terminal (and change toggleterm
        \-- direction for select horiz/vert/tab)
        select \= {
            mappings \= {
                select\_float \= '<C-f>',
                open\_smart \= '<C-a>',
                open\_all \= '<M-a>',
                open\_selected \= nil,
                kill\_smart \= '<C-q>',
                kill\_all \= '<M-q>',
                kill\_selected \= nil,
                respawn\_smart \= '<C-s>',
                respawn\_all \= '<M-s>',
                respawn\_selected \= nil,
            },
        },
    },
}

To load telescope pickers:

require('telescope').load\_extension('toggletasks')

## Config format

[](https://github.com/jedrzejboczar/toggletasks.nvim#config-format)

JSON configuration files are supported out-of-the-box via `vim.json` module. To enable YAML support, [lyaml](https://github.com/gvvaughan/lyaml) must be installed. It is possible to [use packer to install luarocks](https://github.com/wbthomason/packer.nvim#luarocks-support=), see [Installation](https://github.com/jedrzejboczar/toggletasks.nvim#installation).

Available fields:

Field

Type

Description

name

`string`

descriptive name for the task; pair (name, config\_file) is used to uniquely identify a task (to kill existing if re-running or to filter out already running tasks in picker)

id

`string?`

Optional ID to use instead of the default pair (name, config\_file)

cmd

`string`

Command to run

cwd

`string?`

Task working directory

tags

`table<string>?`

Tags used to group and filter tasks

env

`table<string, string>?`

Additional environmental variables passed to task

clear\_env

`boolean?`

If set to true, only environmental variables from `env` will be passed to task

close\_on\_exit

`boolean?`

Auto-close terminal when task job exists ([see toggleterm](https://github.com/akinsho/toggleterm.nvim#custom-terminals))

hidden

`boolean?`

Don't include this task in toggleterm tasks list ([see toggleterm](https://github.com/akinsho/toggleterm.nvim#custom-terminals))

count

`number?`

Use given terminal number ([see toggleterm](https://github.com/akinsho/toggleterm.nvim#custom-terminals))

Variable expansion is supported using the syntax `${VAR}` (escaped by double `$`, e.g. `$${VAR}` will expand to `${VAR}`).

Environmental variables will be expanded in fields: `cwd`, `env`. Additionally some special variables will be expanded in fields: `cmd`, `cwd`, `env`. Available special variables (snake case to minimize collisions with env):

-   `${config_dir}` - location of the config file from which the task has been loaded
-   `${lsp_root}` - root\_dir of a language server with highest priority for current buffer
-   `${win_cwd}` - Vim's window-local CWD
-   `${tab_cwd}` - Vim's tab-local CWD
-   `${global_cwd}` - Vim's global CWD
-   `${file}` - absolute path to the current buffer's file
-   `${cursor_line}` - cursor line of the current window
-   `${cursor_column}` - cursor column of the current window

Vim [filename-modifiers](https://neovim.io/doc/user/cmdline.html#filename-modifiers) can be used inside the expansion to modify the paths (by default all paths are absoulte), e.g. `${file:t:r}` will transform `/path/to/my-file.txt` into `my-file`.

JSON configuration example file:

{
    "tasks": \[
        {
            "name": "Echo example",
            "cmd": "echo 'Current file = ${file}'"
        },
        {
            "name": "System logs",
            "cmd": "journalctl -b --follow",
            "tags": \["dev"\]
        },
        {
            "name": "Makefile build",
            "cmd": "make -j",
            "cwd": "${config\_dir}",
            "tags": \["build", "make"\]
        },
        {
            "name": "CMake setup",
            "cmd": "mkdir -p build && cd build && cmake ..",
            "cwd": "${config\_dir}",
            "tags": \["cmake"\]
        },
        {
            "name": "CMake build",
            "cmd": "cmake --build build -j",
            "cwd": "${config\_dir}",
            "tags": \["build", "cmake"\]
        },
        {
            "name": "django runserver",
            "cmd": "python manage.py runserver",
            "cwd": "${config\_dir}",
            "env": {
                "PATH": "${config\_dir}/venv/bin:${PATH}"
            },
            "tags": \["dev"\]
        },
        {
            "name": "frontend",
            "cmd": "npm run serve",
            "cwd": "${config\_dir}/frontend",
            "tags": \["dev"\]
        }
    \]
}

YAML configuration example:

tasks:
- name: Echo example
  cmd: echo 'Current file = ${file}'
- name: django runserver
  cmd: python manage.py runserver
  cwd: ${config\_dir}
  env:
    PATH: ${config\_dir}/venv/bin:${PATH}
  tags:
  - dev

YAML configuration with [anchors and aliases](https://www.educative.io/blog/advanced-yaml-syntax-cheatsheet#anchors) to share common keys:

# Common for commands that run in python virtual environment
\_venv: &venv
  cwd: ${config\_dir}
  env:
    PATH: ${config\_dir}/venv/bin:${PATH}

tasks:
  - name: django runserver
    cmd: python manage.py runserver
    <<: \*venv

  - name: django test
    cmd: python manage.py test
    <<: \*venv

## Usage

[](https://github.com/jedrzejboczar/toggletasks.nvim#usage)

To use this plugin use the included telescope pickers:

-   spawn tasks: `Telescope toggletasks spawn`
-   select running tasks (open/kill/respawn): `Telescope toggletasks select`
-   edit config files: `Telescope toggletasks edit`

These commands can be mapped to keybindings, e.g.

vim.keymap.set('n', '<space>ts', require('telescope').extensions.toggletasks.spawn,
    { desc \= 'toggletasks: spawn' })

When selecting tasks to be spawned, one can just type `#tagname` in the prompt to filter based on tag. This is currently using the default string based matching but should work correctly in most cases. To select all tasks that are currently visible press `<C-a>` (default). To manually pick tasks use `<Tab>`/`<S-Tab>` (telescope defaults) to perform multi-selection and press `<C-a>` to spawn selected tasks.

### Commands

[](https://github.com/jedrzejboczar/toggletasks.nvim#commands)

The following commands are available:

-   `ToggleTasksInfo` - show current configuration
-   `ToggleTasksConvert <from_file> <to_file>` - convert between configuration file formats (by file extension)

### Automatic task spawning

[](https://github.com/jedrzejboczar/toggletasks.nvim#automatic-task-spawning)

It is possible to automatically launch tasks on autocmd events, e.g. to launch tasks on `VimEnter` or `SessionLoadPost`. This plugin exposes convenient function to achieve that.

For example, to launch all tasks marked with the `auto` tag whenever a session is loaded use:

require('toggletasks').auto\_spawn('SessionLoadPost', 'auto')

The first argument (`event`) is the same as for `vim.api.nvim_create_autocmd`. For more fine grained `auto_spawn` can take a function as the second argument:

require('toggletasks').auto\_spawn({'VimEnter', 'SessionLoadPost'}, function(tasks)
    return tasks
        :with\_tag('auto')
        :not\_tag('test')
        :from\_file('/some/path/toggletasks.json')
        :name\_matches('^/some/path.\*$')
        :filter(function(task)
            return task.config.name ~= 'Hello world'
        end)
end)

## Global tasks

[](https://github.com/jedrzejboczar/toggletasks.nvim#global-tasks)

Sometimes it would be handy to share some common tasks between projects without the need to add config files to all of these. It might also be handy to only include some tasks for certain filetypes. There are several ways to achieve this in `toggletasks.nvim`.

1.  Put task config file somewhere under `&runtimepath` (e.g. `~/.config/nvim/toggletasks.json`) and enable option `scan.rtp = true`. Note that this adds a lot of paths for scanning so in theory it might have some performance impact (but probably not noticeable).
    
2.  Put task config files for given filetypes under `ftplugin/FILETYPE` in `&runtimepath` and enable the option `scan.rtp_ftplugin = true` (should be much faster than 1.). For example, to add Lua-specific tasks one could add a file `~/.config/nvim/ftplugin/lua/toggletasks.json`.
    
3.  Use the setup option `scan.dirs` as a `function(win)`, and return the directories in which to search for task config files. You can use the `win` argument to get the filetype of current buffer, or to check any other conditions, which can be used to select specific directories with task config files.
    
4.  Define tasks directly in Lua in your setup function. Use a function to have even more control over which tasks should be included, e.g.
    

require('toggletasks').setup {
    tasks \= function(win)
        local ft \= vim.api.nvim\_buf\_get\_option(vim.api.nvim\_win\_get\_buf(win), 'filetype')
        local tasks \= {
            {
                name \= 'Some task',
                cmd \= 'echo "hello"'
            },
        }
        if ft \== 'lua' then
            \-- table.insert(tasks, { name = ... })
        end
        return tasks
    end,
    \-- ...
}

## TODO

[](https://github.com/jedrzejboczar/toggletasks.nvim#todo)

-   Integration with [possession.nvim](https://github.com/jedrzejboczar/possession.nvim) by marking tasks with `possession` tag - no changes required in this plugin
-   Task "templates": one task could inherit options from another ("extends")