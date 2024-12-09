---
page-title: "lukas-reineke/cmp-rg: ripgrep source for nvim-cmp"
url: https://github.com/lukas-reineke/cmp-rg
date: "2024-06-21 03:11:21"
tags: [A/sw/plugin, F/prod/homepage, C/, P/pwf]
about: ["[[NeoVim]]","[[nvim.cmp]]"]
aliases: 
- 
by: 
length: 658
dir: 
---

## cmp-rg

[](https://github.com/lukas-reineke/cmp-rg#cmp-rg)

[ripgrep](https://github.com/BurntSushi/ripgrep) source for [nvim-cmp](https://github.com/hrsh7th/nvim-cmp)

## Dependencies

[](https://github.com/lukas-reineke/cmp-rg#dependencies)

You need to have [ripgrep](https://github.com/BurntSushi/ripgrep) installed.

## Install

[](https://github.com/lukas-reineke/cmp-rg#install)

Use your favourite plugin manager to install.

#### Example with Packer

[](https://github.com/lukas-reineke/cmp-rg#example-with-packer)

[wbthomason/packer.nvim](https://github.com/wbthomason/packer.nvim)

\-- init.lua
require("packer").startup(function()
    use "lukas-reineke/cmp-rg"
end)

#### Example with Plug

[](https://github.com/lukas-reineke/cmp-rg#example-with-plug)

[junegunn/vim-plug](https://github.com/junegunn/vim-plug)

" init.vim
call plug#begin('~/.vim/plugged')
Plug 'lukas-reineke/cmp-rg'
call plug#end()

## Setup

[](https://github.com/lukas-reineke/cmp-rg#setup)

Add `rg` to your cmp sources

require("cmp").setup {
    sources \= {
        {
            name \= "rg",
            \-- Try it when you feel cmp performance is poor
            \-- keyword\_length = 3
        },
    },
}

For more options see `:help cmp-rg`

## Screenshot

[](https://github.com/lukas-reineke/cmp-rg#screenshot)

[![Screenshot](https://user-images.githubusercontent.com/12900252/143555260-8567fb04-eea6-4a73-a1dc-d36d4df8cb64.png)](https://user-images.githubusercontent.com/12900252/143555260-8567fb04-eea6-4a73-a1dc-d36d4df8cb64.png)