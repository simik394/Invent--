---
page-title: "jdhao/nvim-config: A modern Neovim configuration with full battery for Python, Lua, C++, Markdown, LaTeX, and more..."
url: https://github.com/jdhao/nvim-config
date: "2024-05-12 11:03:31"
tags: 
- A/sw/plugin
- F/homepage
- C/
- P/
about: 
- "[[NeoVim]]"
aliases: 
- c46d7f8f-abd5-41f2-9b5e-51e0c1121abe
- jdhao/nvim-config: A modern Neovim configuration with full battery for Python, Lua, C++, Markdown, LaTeX, and more...
by: 
length: 6808
dir: 
---

[![Linux](https://camo.githubusercontent.com/395d3b7b643061da8d829ec3d3ca4b55d66017127880a6ef362a158c74a3b23f/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4c696e75782d2532332e7376673f7374796c653d666c61742d737175617265266c6f676f3d6c696e757826636f6c6f723d464343363234266c6f676f436f6c6f723d626c61636b)](https://camo.githubusercontent.com/395d3b7b643061da8d829ec3d3ca4b55d66017127880a6ef362a158c74a3b23f/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4c696e75782d2532332e7376673f7374796c653d666c61742d737175617265266c6f676f3d6c696e757826636f6c6f723d464343363234266c6f676f436f6c6f723d626c61636b) [![macOS](https://camo.githubusercontent.com/9de1b6c8230ab22ffc7c8fac0dc5e97458221a0b777fd2979d0dd1a09ca47f29/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f6d61634f532d2532332e7376673f7374796c653d666c61742d737175617265266c6f676f3d6170706c6526636f6c6f723d303030303030266c6f676f436f6c6f723d7768697465)](https://camo.githubusercontent.com/9de1b6c8230ab22ffc7c8fac0dc5e97458221a0b777fd2979d0dd1a09ca47f29/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f6d61634f532d2532332e7376673f7374796c653d666c61742d737175617265266c6f676f3d6170706c6526636f6c6f723d303030303030266c6f676f436f6c6f723d7768697465) [![Windows](https://camo.githubusercontent.com/dce47ee7e6652429029bf0d584b278ed780e0a6388f61a1162b6018928fcddac/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f57696e646f77732d2532332e7376673f7374796c653d666c61742d737175617265266c6f676f3d77696e646f777326636f6c6f723d303037384436266c6f676f436f6c6f723d7768697465)](https://camo.githubusercontent.com/dce47ee7e6652429029bf0d584b278ed780e0a6388f61a1162b6018928fcddac/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f57696e646f77732d2532332e7376673f7374796c653d666c61742d737175617265266c6f676f3d77696e646f777326636f6c6f723d303037384436266c6f676f436f6c6f723d7768697465) [![Latest release](https://camo.githubusercontent.com/27e623e0a45cc29c8abb41a9cff276c4bdc9450b91f1edf2db248c02010a2f54/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f762f72656c656173652f6a6468616f2f6e76696d2d636f6e666967) ](https://github.com/jdhao/nvim-config/releases/latest)[![Neovim minimum version](https://camo.githubusercontent.com/ba7586e13554ccbb852008c130f08d17ce73166f9c0bfcaf12a804d4d62fed18/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4e656f76696d2d302e392e352d626c756576696f6c65742e7376673f7374796c653d666c61742d737175617265266c6f676f3d4e656f76696d266c6f676f436f6c6f723d677265656e) ](https://github.com/neovim/neovim/releases/tag/stable)[![Top languages](https://camo.githubusercontent.com/73cc3862a783fe50eee53caedb92f92a0185e8431897b1b1240b79b490687bfa/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6c616e6775616765732f746f702f6a6468616f2f6e76696d2d636f6e666967) ](https://github.com/jdhao/nvim-config/search?l=vim-script)[![](https://camo.githubusercontent.com/e67a171995af4069273405b8301cbaa5d7c8d4f0f4fb0f99ce41b6e7fca63846/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f636f6d6d69742d61637469766974792f6d2f6a6468616f2f6e76696d2d636f6e6669673f7374796c653d666c61742d737175617265) ](https://github.com/jdhao/nvim-config/graphs/commit-activity)[![](https://camo.githubusercontent.com/1c2ef813981ba9211c230e9c8eca3861d806fbd8d2e0580a7f7566bcdbeed6d9/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f636f6d6d6974732d73696e63652f6a6468616f2f6e76696d2d636f6e6669672f76302e392e353f7374796c653d666c61742d737175617265) ](https://github.com/jdhao/nvim-config/releases/tag/v0.9.5)[![](https://camo.githubusercontent.com/58dbfdc3168acb095c397f1198a91e4d69f3831988733c9d0ff66cd3bb4f7db4/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f636f6e7472696275746f72732f6a6468616f2f6e76696d2d636f6e6669673f7374796c653d666c61742d737175617265) ](https://github.com/jdhao/nvim-config/graphs/contributors)[![](https://camo.githubusercontent.com/956bcf64c5cc66c8f176564153b0b57b3ebd2092c53640173a89a1d5b642fbbf/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f7265706f2d73697a652f6a6468616f2f6e76696d2d636f6e6669673f7374796c653d666c61742d737175617265)](https://camo.githubusercontent.com/956bcf64c5cc66c8f176564153b0b57b3ebd2092c53640173a89a1d5b642fbbf/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f7265706f2d73697a652f6a6468616f2f6e76696d2d636f6e6669673f7374796c653d666c61742d737175617265) [![License](https://camo.githubusercontent.com/bd2c85882a3b42429c8a781410c33910a60bc5214ad24d41870c44feeb9b640f/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6c6963656e73652f6a6468616f2f6e76696d2d636f6e6669673f7374796c653d666c61742d737175617265266c6f676f3d474e55266c6162656c3d4c6963656e7365)](https://github.com/jdhao/nvim-config/blob/master/LICENSE)

## Introduction

[](https://github.com/jdhao/nvim-config#introduction)

This repo hosts my Nvim configuration for Linux, macOS, and Windows. `init.lua` is the config entry point for terminal Nvim, and `ginit.vim` is the additional config file for [GUI client of Nvim](https://github.com/neovim/neovim/wiki/Related-projects#gui).

My configurations are heavily documented to make it as clear as possible. While you can clone the whole repository and use it, it is not recommended though. Good configurations are personal. Everyone should have his or her unique config file. You are encouraged to copy from this repo the part you want and add it to your own config.

To reduce the possibility of breakage, **this config is only maintained for [the latest nvim stable release](https://github.com/neovim/neovim/releases/tag/stable). No effort is spent on maintaining backward compatibility.**

## Install and setup

[](https://github.com/jdhao/nvim-config#install-and-setup)

See [doc here](https://github.com/jdhao/nvim-config/blob/master/docs/README.md) on how to install Nvim's dependencies, Nvim itself, and how to set up on different platforms (Linux, macOS, and Windows).

## Features

[](https://github.com/jdhao/nvim-config#features)

-   Plugin management via [Lazy.nvim](https://github.com/folke/lazy.nvim).
-   Code, snippet, word auto-completion via [nvim-cmp](https://github.com/hrsh7th/nvim-cmp).
-   Language server protocol (LSP) support via [nvim-lspconfig](https://github.com/neovim/nvim-lspconfig).
-   Git integration via [vim-fugitive](https://github.com/tpope/vim-fugitive).
-   Better escaping from insert mode via [better-escape.vim](https://github.com/nvim-zh/better-escape.vim).
-   Ultra-fast project-wide fuzzy searching via [LeaderF](https://github.com/Yggdroot/LeaderF).
-   Faster code commenting via [vim-commentary](https://github.com/tpope/vim-commentary).
-   Faster matching pair insertion and jump via [delimitMate](https://github.com/Raimondi/delimitMate).
-   Smarter and faster matching pair management (add, replace or delete) via [vim-sandwich](https://github.com/machakann/vim-sandwich).
-   Fast buffer jump via [hop.nvim](https://github.com/phaazon/hop.nvim).
-   Powerful snippet insertion via [Ultisnips](https://github.com/SirVer/ultisnips).
-   Beautiful statusline via [lualine.nvim](https://github.com/nvim-lualine/lualine.nvim).
-   File tree explorer via [nvim-tree.lua](https://github.com/nvim-tree/nvim-tree.lua).
-   Better quickfix list with [nvim-bqf](https://github.com/kevinhwang91/nvim-bqf).
-   Show search index and count with [nvim-hlslens](https://github.com/kevinhwang91/nvim-hlslens).
-   Command line auto-completion via [wilder.nvim](https://github.com/gelguy/wilder.nvim).
-   User-defined mapping hint via [which-key.nvim](https://github.com/folke/which-key.nvim).
-   Asynchronous code execution via [asyncrun.vim](https://github.com/skywind3000/asyncrun.vim).
-   Code highlighting via [nvim-treesitter](https://github.com/nvim-treesitter/nvim-treesitter).
-   Code editing using true nvim inside browser via [firenvim](https://github.com/glacambre/firenvim).
-   Beautiful colorscheme via [sainnhe/gruvbox-material](https://github.com/sainnhe/gruvbox-material) and other colorschemes.
-   Markdown writing and previewing via [vim-markdown](https://github.com/preservim/vim-markdown) and [markdown-preview.nvim](https://github.com/iamcco/markdown-preview.nvim).
-   LaTeX editing and previewing via [vimtex](https://github.com/lervag/vimtex)
-   Animated GUI style notification via [nvim-notify](https://github.com/rcarriga/nvim-notify).
-   Tags navigation via [vista](https://github.com/liuchengxu/vista.vim).
-   Code formatting via [Neoformat](https://github.com/sbdchd/neoformat).
-   Undo management via [vim-mundo](https://github.com/simnalamburt/vim-mundo)
-   ......

## UI Demo

[](https://github.com/jdhao/nvim-config#ui-demo)

For more UI demos, check [here](https://github.com/jdhao/nvim-config/issues/15).

## Start screen with dashboard-nvim

[](https://github.com/jdhao/nvim-config#start-screen-with-dashboard-nvim)

[![](https://user-images.githubusercontent.com/16662357/183256752-fb23b215-a6b8-4646-beed-9999f52d53f1.png)](https://user-images.githubusercontent.com/16662357/183256752-fb23b215-a6b8-4646-beed-9999f52d53f1.png)

## File fuzzy finding using LeaderF

[](https://github.com/jdhao/nvim-config#file-fuzzy-finding-using-leaderf)

[![](https://user-images.githubusercontent.com/16662357/183257017-2d9d7605-3c4b-4e1d-8955-30998f9b6f28.gif)](https://user-images.githubusercontent.com/16662357/183257017-2d9d7605-3c4b-4e1d-8955-30998f9b6f28.gif)

## Code autocompletion with nvim-cmp

[](https://github.com/jdhao/nvim-config#code-autocompletion-with-nvim-cmp)

[![](https://user-images.githubusercontent.com/16662357/128590006-0fc1451f-fac1-49b2-bb95-8aba21bfa44e.gif)](https://user-images.githubusercontent.com/16662357/128590006-0fc1451f-fac1-49b2-bb95-8aba21bfa44e.gif)

## Git add, commit and push via fugitive.vim

[](https://github.com/jdhao/nvim-config#git-add-commit-and-push-via-fugitivevim)

[![](https://user-images.githubusercontent.com/16662357/128590833-aaa05d53-19ef-441d-a5a9-ba1bbd3936c1.gif)](https://user-images.githubusercontent.com/16662357/128590833-aaa05d53-19ef-441d-a5a9-ba1bbd3936c1.gif)

## Command-line autocompletion with wilder.nvim

[](https://github.com/jdhao/nvim-config#command-line-autocompletion-with-wildernvim)

[![](https://user-images.githubusercontent.com/16662357/147677787-8e5d229a-a16a-420e-98f5-88f2a1be84a2.gif)](https://user-images.githubusercontent.com/16662357/147677787-8e5d229a-a16a-420e-98f5-88f2a1be84a2.gif)

## Tags

[](https://github.com/jdhao/nvim-config#tags)

[![](https://user-images.githubusercontent.com/16662357/128589584-4036a1a2-2e0a-4bbe-8aaf-ff8b91644648.jpg)](https://user-images.githubusercontent.com/16662357/128589584-4036a1a2-2e0a-4bbe-8aaf-ff8b91644648.jpg)

## Cursor jump via hop.nvim

[](https://github.com/jdhao/nvim-config#cursor-jump-via-hopnvim)

Go to a string starting with `se`

[![](https://user-images.githubusercontent.com/16662357/139459219-8a7e6ac4-1d24-4008-a370-b56773d7cb85.gif)](https://user-images.githubusercontent.com/16662357/139459219-8a7e6ac4-1d24-4008-a370-b56773d7cb85.gif)

## GUI-style notification with nvim-notify

[](https://github.com/jdhao/nvim-config#gui-style-notification-with-nvim-notify)

[![](https://user-images.githubusercontent.com/16662357/128589873-aadb8264-1098-4834-9876-fa66a309be05.gif)](https://user-images.githubusercontent.com/16662357/128589873-aadb8264-1098-4834-9876-fa66a309be05.gif)

## Shortcuts

[](https://github.com/jdhao/nvim-config#shortcuts)

Some of the shortcuts I use frequently are listed here. In the following shortcuts, `<leader>` represents ASCII character `,`.

Shortcut

Mode

platform

Description

`<leader>ff`

Normal

Linux/macOS/Win

Fuzzy file searching in a floating window

`<leader>fh`

Normal

Linux/macOS/Win

Fuzzy help file grepping in a floating window

`<leader>fg`

Normal

Linux/macOS/Win

Fuzzy project-wide grepping in a floating window

`<leader>ft`

Normal

Linux/macOS/Win

Fuzzy buffer tag searching in a floating window

`<leader>fb`

Normal

Linux/macOS/Win

Fuzzy buffer switching in a floating window

`<leader><Space>`

Normal

Linux/macOS/Win

Remove trailing white spaces

`<leader>v`

Normal

Linux/macOS/Win

Reselect last pasted text

`<leader>ev`

Normal

Linux/macOS/Win

Edit Nvim config in a new tabpage

`<leader>sv`

Normal

Linux/macOS/Win

Reload Nvim config

`<leader>st`

Normal

Linux/macOS/Win

Show highlight group for cursor text

`<leader>q`

Normal

Linux/macOS/Win

Quit current window

`<leader>Q`

Normal

Linux/macOS/Win

Quit all window and close Nvim

`<leader>w`

Normal

Linux/macOS/Win

Save current buffer content

`<leader>y`

Normal

Linux/macOS/Win

Copy the content of entire buffer to default register

`<leader>cl`

Normal

Linux/macOS/Win

Toggle cursor column

`<leader>cd`

Normal

Linux/macOS/Win

Change current working directory to to the dir of current buffer

`<space>t`

Normal

Linux/macOS/Win

Toggle tag window (show project tags in the right window)

`<leader>gs`

Normal

Linux/macOS/Win

Show Git status result

`<leader>gw`

Normal

Linux/macOS/Win

Run Git add for current file

`<leader>gd`

Normal

Linux/macOS/Win

Run git diff for current file

`<leader>gc`

Normal

Linux/macOS/Win

Run git commit

`<leader>gpl`

Normal

Linux/macOS/Win

Run git pull

`<leader>gpu`

Normal

Linux/macOS/Win

Run git push

`<leader>gl`

Normal/Visual

Linux/macOS/Win

Get perm link for current/visually-select lines

`<leader>gb`

Normal

macOS

Browse current git repo in browser

`<F9>`

Normal

Linux/macOS/Win

Compile&run current source file (for C++, LaTeX, Lua, Python)

`<F11>`

Normal

Linux/macOS/Win

Toggle spell checking

`<F12>`

Normal

Linux/macOS/Win

Toggle paste mode

`\x`

Normal

Linux/macOS/Win

Close location or quickfix window

`\d`

Normal

Linux/macOS/Win

Close current buffer and go to previous buffer

`{count}gb`

Normal

Linux/macOS/Win

Go to buffer `{count}` or next buffer in the buffer list.

`{operator}iB`

Normal

Linux/macOS/Win

Operate in the whole buffer, `{operator}` can be `v`, `y`, `c`, `d` etc.

`Alt-k`

Normal

Linux/macOS/Win

Move current line or selected lines up

`Alt-j`

Normal

Linux/macOS/Win

Move current line or selected lines down

`Alt-m`

Normal

macOS/Win

Markdown previewing in system browser

`Alt-Shift-m`

Normal

macOS/Win

Stopping Markdown previewing in system browser

`ob`

Normal/Visual

macOS/Win

Open link under cursor or search visual selection

`ctrl-u`

Insert

Linux/macOS/Win

Turn word under cursor to upper case

`ctrl-t`

Insert

Linux/macOS/Win

Turn word under cursor to title case

`jk`

Insert

Linux/macOS/Win

Return to Normal mode without lagging

## Custom commands

[](https://github.com/jdhao/nvim-config#custom-commands)

In addition to commands provided by various plugins, I have also created some custom commands for personal use.

command

description

example

`Redir`

capture command output to a tabpage for easier inspection.

`Redir hi`

`Edit`

edit multiple files at the same time, supports globing

`Edit *.vim`

`Datetime`

print current date and time or convert Unix time stamp to date and time

`Datetime 12345` or `Datetime`

## Contributing

[](https://github.com/jdhao/nvim-config#contributing)

If you find anything that needs improving, do not hesitate to point it out or create a PR.

If you come across an issue, you can first use `:checkhealth` command provided by `nvim` to trouble-shoot yourself. Please read carefully the messages provided by health check.

If you still have an issue, [open a new issue](https://github.com/jdhao/nvim-config/issues).

## Further readings

[](https://github.com/jdhao/nvim-config#further-readings)

Some of the resources that I find helpful in mastering Nvim is documented [here](https://github.com/jdhao/nvim-config/blob/master/docs/nvim_resources.md). You may also be interested in my posts on configuring Nvim:

-   My nvim notes can be found [here](https://jdhao.github.io/categories/Nvim/)
-   [Using Neovim for Three years](https://jdhao.github.io/2021/12/31/using_nvim_after_three_years/)
-   [Config nvim on Linux for Python development](https://jdhao.github.io/2018/12/24/centos_nvim_install_use_guide_en/)
-   [Nvim config on Windows 10](https://jdhao.github.io/2018/11/15/neovim_configuration_windows/)
-   [Nvim-qt config on Windows 10](https://jdhao.github.io/2019/01/17/nvim_qt_settings_on_windows/)