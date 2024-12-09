---
page-title: "lpenz/vimcommander: Total-commander-like file manager for VIM"
url: https://github.com/lpenz/vimcommander/
date: "2024-07-16 18:39:30"
tags: [a/sw/plugin, f/prod/homepage, c/, p/pwf]
about: ["[[NeoVim]]"]
aliases: 
- 
by: 
length: 879
dir: 
---

## vimcommander

[](https://github.com/lpenz/vimcommander/#vimcommander)

This is an adaptation of opsplorer ([vimscript #362](http://www.vim.org/scripts/script.php?script_id=808)), intended to be more like the [Total Commander](http://www.ghisler.com/) file explorer.

## Installation

[](https://github.com/lpenz/vimcommander/#installation)

-   Drop *vimcommander.vim* in *~/.vim/plugin* **OR** add this repository to your plugin manager ([Vundle](https://github.com/VundleVim/Vundle.vim), for example)
-   Add a map to *VimCommanderToggle()* in you *.vimrc*, like this:

```
noremap <silent> <F11> :cal VimCommanderToggle()<CR>
```

## Usage

[](https://github.com/lpenz/vimcommander/#usage)

vimcommander opens two panels of file explorers on the top half of the vim screen. Targets for moving and copying defaults to the other panel, like totalcmd. TAB switches between panels.

vimcommander keys are mostly totalcommander's:

-   F3 - view
-   F4 - edit
-   F5 - copy
-   F6 - move
-   F7 - create dir
-   F8 - del
-   Others: C-U, C-Left/C-Right, C-R, BS, DEL, C-H, etc.
-   Selection of files/dirs also works: INS, +, -. Then copy/move/del selected files.

Tested on Linux. I have reports that vimcommander doesn't work on Windows.