---
page-title: "nocksock/do.nvim: A tiny task manager within nvim that helps you stay on track. (づ◡﹏◡)づ"
url: https://github.com/nocksock/do.nvim
date: "2024-06-23 23:40:47"
tags: [A/sw/plugin, F/prod/homepage, C/, P/pwf/productivity ,m/⭐]
about: ["[[NeoVim]]"]
aliases: 
- 
by: 
length: 2956
dir: 
---

## Do.nvim

[](https://github.com/nocksock/do.nvim#donvim)

A tiny task manager within nvim that helps you stay on track.

[![Preview](https://github.com/nocksock/do.nvim/raw/main/assets/demo.png)](https://github.com/nocksock/do.nvim/blob/main/assets/demo.png)

## Introduction

[](https://github.com/nocksock/do.nvim#introduction)

[![Introduction Gif](https://github.com/nocksock/do.nvim/raw/main/demo/demo.gif)](https://github.com/nocksock/do.nvim/blob/main/demo/demo.gif)

## Rationale

[](https://github.com/nocksock/do.nvim#rationale)

While coding, we often need to do several things that depend on another. And it's quite easy to loose track of what we initially set out to do in the first place, which is also know as [Yak Shaving](https://en.wiktionary.org/wiki/yak_shaving). *Or* we just have a list of tasks that we want to work off step by step.

This plugin provides a few simple commands to help you stay on track.

It manages a list of things and always shows you the first item. It provides you with some commands to add things to it, without leaving context. And it uses a simple, intuitive floating buffer to manage that list.

## Usage

[](https://github.com/nocksock/do.nvim#usage)

-   `:Do` add a line to the end of the list.
-   `:Do!` add a line to the front of list.
-   `:Done!` remove the first line from the list.
-   `:DoEdit` edit the list in a floating window.
-   `:DoSave` create `.do_tasks` file in cwd. Will auto-sync afterwards.
-   `:DoToggle` toggle the display. Use with caution!

## Installation

[](https://github.com/nocksock/do.nvim#installation)

Requires Neovim 0.8.

\-- use the package manager of your choice, eg. packer
use("https://github.com/nocksock/do.nvim")

\-- setup wherever you do that in you config (eg init.lua)
require("do").setup({
  \-- default options
  message\_timeout \= 2000, \-- how long notifications are shown
  kaomoji\_mode \= 0, \-- 0 kaomoji everywhere, 1 skip kaomoji in doing
  winbar \= false,
  doing\_prefix \= "Doing: ",
  store \= {
    auto\_create\_file \= false, \-- automatically create a .do\_tasks when calling :Do
    file\_name \= ".do\_tasks",
  }
})

## Winbar

[](https://github.com/nocksock/do.nvim#winbar)

This plugin felt best to me using the winbar - which is a new feature in neovim 0.8. In order to use it, enable it:

require('do').setup({
  winbar \= true
})

## Lualine

[](https://github.com/nocksock/do.nvim#lualine)

In case you'd rather use it in the statusline or tabbar, you can use the exposed views to do so. For example with lualine:

require('lualine').setup {
  winbar \= {
    lualine\_a \= {
      function()
        return require('do').view('active')
      end,
    },
  },
  inactive\_winbar \= {
    \-- in order to prevent jumping of code in certain cursor positions this will
    \-- (at the moment) show an empty line - but only if .view has contents.
    lualine\_a \= { require("do").view\_inactive },
  },
}

## Events

[](https://github.com/nocksock/do.nvim#events)

This plugin exposes a custom event, for when a task is added or modified. You can use it like so:

vim.api.nvim\_create\_autocmd({ "User" }, {
   group \= require("do.state").state.auGroupID,
   pattern \= "TaskModified",
   desc \= "This is called when a task is added or deleted",
   callback \= function()
      vim.notify("A task has been modified")
   end,
})

## Development

[](https://github.com/nocksock/do.nvim#development)

### Run tests

[](https://github.com/nocksock/do.nvim#run-tests)

Running tests requires [plenary.nvim](https://github.com/nvim-lua/plenary.nvim) to be checked out in the parent directory of *this* repository. You can then run:

nvim --headless --noplugin -u tests/minimal.vim -c "PlenaryBustedDirectory tests/ {minimal\_init = 'tests/minimal.vim'}"

Or if you want to run a single test file:

nvim --headless --noplugin -u tests/minimal.vim -c "PlenaryBustedDirectory tests/path\_to\_file.lua {minimal\_init = 'tests/minimal.vim'}"