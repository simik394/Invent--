---
page-title: "dhruvasagar/vim-dotoo: Org-mode like task logging & time tracking in Vim"
url: https://github.com/dhruvasagar/vim-dotoo
date: 2024-06-21 03:36:35
tags:
  - A/sw/plugin
  - F/prod/homepage
  - C/
  - P/pwf
about:
  - "[[NeoVim]]"
  - "[[Inv/SW/Vim]]"
aliases:
  - 
by: 
length: 4900
dir: 
---

## VIM Do Too v0.14.3.2 [![Build](https://github.com/dhruvasagar/vim-dotoo/actions/workflows/ci.yml/badge.svg)](https://github.com/dhruvasagar/vim-dotoo/actions/workflows/ci.yml)

[](https://github.com/dhruvasagar/vim-dotoo#vim-do-too-v01432-)

An awesome task manager & clocker inspired by org-mode written in pure viml.

## Pre-requisites

[](https://github.com/dhruvasagar/vim-dotoo#pre-requisites)

It is recommended that you enable the vim setting `'hidden'` which allows us to keep dotoo files hidden in the background for the purpose of showing accurate agenda information and also for faster updates to these files.

## Getting Started

[](https://github.com/dhruvasagar/vim-dotoo#getting-started)

1.  Document Structure: The document structure is borrowed from emacs' Org Mode.
    
    > NOTE : Check out the file `dotoo.dotoo` in this repo as an example
    
    These are the dotoo document mappings :
    
    -   gI: clock-in headline under cursor
    -   gO: clock-out headline under cursor
    -   gM: move headline under cursor to selected target
    -   cit: change TODO of headline under cursor
    -   cic: toggle checkbox under cursor
    -   <C-A>: Increment date under cursor by 1 day, can be preceded with a \[count\]
    -   <C-X>: Decrement date under cursor by 1 day, can be preceded with a \[count\]
    -   <C-C><C-C>: Normalize a date (fixes day name if incorrect)
    -   <Tab>: Cycle headline visibility similar to Org mode
    -   <CR>: Follow link under cursor
    -   <BS>: Go back to previous document after following a link
    
    The <C-X>, <C-A>, and cic commands all work with . if you have [repeat.vim](http://github.com/tpope/vim-repeat) installed
    
    A few helpful `:iabbrev`:
    
    -   `:date:` Enters the current date
    -   `:time:` Enters the current time
    -   `:datetime:` Enters the current date & time
2.  Agenda Views: You can have a look at the agenda views at anytime using the key binding gA, this displays the list of currently registered agenda views available, selecting one of them then opens up the view. The agenda views pulls information from agenda files, this can be configured by setting `g:dotoo#agenda#files` which is a list of file names / file blobs.
    
    These are the agenda view mappings common to all :
    
    -   gq: quit agenda buffer
    -   r: refresh agenda buffer (force reload / parse agenda files)
    -   c: change TODO of headline under cursor
    -   u: undo change in file of headline under the cursor
    -   s: save all agenda files
    -   C: trigger capture menu
    -   i: clock-in for headline under cursor
    -   o: clock-out for headline under cursor
    -   m: Move headline to selected target
    -   /: Filter by file, tags or todos
    -   <CR>: Open headline under cursor & close agenda
    -   <C-S>: Open headline under cursor in `split`
    -   <C-T>: Open headline under cursor in `tab`
    -   <C-V>: Open headline under cursor in `vsplit`
    -   <Tab>: same as <C-V>
    
    1.  Agenda View : This displays all TODOs that are nearing deadline. It provides a variety of mappings to manipulate the TODO items from the agenda view itself.
        
        These are mappings specific to agenda view:
        
        -   f: go forward by 1 day
        -   b: go backward by 1 day
        -   .: go to today's date
        -   S: Change agenda span to day, week or month
        -   R: Report of clocking summary for the current span
    2.  TODOs View : This displays all unscheduled TODO items from your agenda files.
        
    3.  Refiles : This displays all headlines in the refile file that you should then move to an appropriate target file / project / headline.
        
    4.  Notes : This displays all the notes from all the agenda files.
        
    5.  Tagged : This lists all headlines that have tags.
        
    6.  Search : This lists all headlines that match an input search term.
        
    7.  Wiki : This lists all headlines that have `notes` in the path, assuming you manage notes in a notes folder that is under the agenda files path. This is better than Notes view since it does not require the presence of `:NOTE:` tag. If you just want to see everything in your knowledge base at a quick glance this is useful.
        
3.  Capture: This launches the capture menu that you can use to quickly capture TODOs, NOTES etc. This can be invoked using the keybinding gC from anywhere. The capture launches with a split window in select mode, you can just start typing to edit the capture. On saving the capture is then moved to the refile file, this can be configured using `g:dotoo#capture#refile`. You can always look at your refiles in the refiles view and move them to the desired target file / headline from there. Capture also clocks the tasks so you can log how much time was spent doing them by default, you can disable this behavior by setting `let g:dotoo#capture#clock = 0`.
    

## Screenshots

[](https://github.com/dhruvasagar/vim-dotoo#screenshots)

1.  Agenda Menu - [![](https://camo.githubusercontent.com/edf1a564a849d392e8bb4c25c7364de8e920f5635a7601012376cf1f44ecbf7f/687474703a2f2f692e696d6775722e636f6d2f3137646f4e5a6e2e706e67)](https://camo.githubusercontent.com/edf1a564a849d392e8bb4c25c7364de8e920f5635a7601012376cf1f44ecbf7f/687474703a2f2f692e696d6775722e636f6d2f3137646f4e5a6e2e706e67)
2.  Agenda View - [![](https://camo.githubusercontent.com/9d89c4d36e532fd8caf932f41065cde8664464b94c9ebc0a36311f4f184c1b38/687474703a2f2f692e696d6775722e636f6d2f4a7374633936312e706e67)](https://camo.githubusercontent.com/9d89c4d36e532fd8caf932f41065cde8664464b94c9ebc0a36311f4f184c1b38/687474703a2f2f692e696d6775722e636f6d2f4a7374633936312e706e67)
3.  Agenda View with Log Summary - [![](https://camo.githubusercontent.com/090c661cbb494eab35dd01196f272465435f222d3b5a6c07eee85fa475331bc3/687474703a2f2f692e696d6775722e636f6d2f3773535635646d2e706e67)](https://camo.githubusercontent.com/090c661cbb494eab35dd01196f272465435f222d3b5a6c07eee85fa475331bc3/687474703a2f2f692e696d6775722e636f6d2f3773535635646d2e706e67)
4.  Todos View - [![](https://camo.githubusercontent.com/c95b63bcf318954bef0c9c7d79f69202c1bf51242c979365ddfc3a4755962562/687474703a2f2f692e696d6775722e636f6d2f304a6730457a732e706e67)](https://camo.githubusercontent.com/c95b63bcf318954bef0c9c7d79f69202c1bf51242c979365ddfc3a4755962562/687474703a2f2f692e696d6775722e636f6d2f304a6730457a732e706e67)
5.  Refile View - [![](https://camo.githubusercontent.com/7d992e7d24a07630fbe356307fcaf4d8ea2f52d5dbc6374917f09cd438477432/687474703a2f2f692e696d6775722e636f6d2f486f534a6b45752e706e67)](https://camo.githubusercontent.com/7d992e7d24a07630fbe356307fcaf4d8ea2f52d5dbc6374917f09cd438477432/687474703a2f2f692e696d6775722e636f6d2f486f534a6b45752e706e67)
6.  Notes View - [![](https://camo.githubusercontent.com/77b2aa8b79634ca223b8f7d803c8752fbb3c1205347e37854c29da6547474960/687474703a2f2f692e696d6775722e636f6d2f547945654e57612e706e67)](https://camo.githubusercontent.com/77b2aa8b79634ca223b8f7d803c8752fbb3c1205347e37854c29da6547474960/687474703a2f2f692e696d6775722e636f6d2f547945654e57612e706e67)

## Screencast

[](https://github.com/dhruvasagar/vim-dotoo#screencast)

[https://www.youtube.com/watch?v=nsv33iOnH34](https://www.youtube.com/watch?v=nsv33iOnH34)

## Credits

[](https://github.com/dhruvasagar/vim-dotoo#credits)

This plugin was inspired by the original emacs org-mode and the workflow described by Bernt Hansen at [http://doc.norang.ca/org-mode.html](http://doc.norang.ca/org-mode.html).

I have taken bits of the syntax definitions & ideas from [vim-orgmode](https://github.com/jceb/vim-orgmode)

I will also like to shout out for bairui [http://of-vim-and-vigor.blogspot.in/](http://of-vim-and-vigor.blogspot.in/) who helped me a lot in building this.

## Contributors

[](https://github.com/dhruvasagar/vim-dotoo#contributors)

### Code Contributors

[](https://github.com/dhruvasagar/vim-dotoo#code-contributors)

This project exists thanks to all the people who contribute. \[[Contribute](https://opencollective.com/vim-dotoo/contribute)\]. [![](https://camo.githubusercontent.com/0b24944c6094c126af06dd3a639e7d2abe8a1bab19bf6f8d119988be11a591f6/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f76696d2d646f746f6f2f636f6e7472696275746f72732e7376673f77696474683d38393026627574746f6e3d66616c7365)](https://github.com/dhruvasagar/vim-dotoo/graphs/contributors)

### Financial Contributors

[](https://github.com/dhruvasagar/vim-dotoo#financial-contributors)

Become a financial contributor and help us sustain our community. \[[Contribute](https://opencollective.com/vim-dotoo/contribute)\]

#### Individuals

[](https://github.com/dhruvasagar/vim-dotoo#individuals)

[![](https://camo.githubusercontent.com/3eb79ff4a940e0e54fb50ce0d20836b7765a61821916358083bc7d0fba225fbc/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f76696d2d646f746f6f2f696e646976696475616c732e7376673f77696474683d383930)](https://opencollective.com/vim-dotoo)

#### Organizations

[](https://github.com/dhruvasagar/vim-dotoo#organizations)

Support this project with your organization. Your logo will show up here with a link to your website. \[[Contribute](https://opencollective.com/vim-dotoo/contribute)\]

[![](https://camo.githubusercontent.com/5a1bfed6319ed9ff4c69386be2a6fac153450afdeabbb06409a733d931855f32/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f76696d2d646f746f6f2f6f7267616e697a6174696f6e2f302f6176617461722e737667)](https://opencollective.com/vim-dotoo/organization/0/website) [![](https://camo.githubusercontent.com/185d58d66034646fc5410e713e51ddd9d0bb907a9b1b76a6603841b2d01c7c4a/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f76696d2d646f746f6f2f6f7267616e697a6174696f6e2f312f6176617461722e737667)](https://opencollective.com/vim-dotoo/organization/1/website) [![](https://camo.githubusercontent.com/0e57c8cacf68be18123a4bbb5b1e5a95e3efcbe224ce40ee6a8072ab66f72cf4/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f76696d2d646f746f6f2f6f7267616e697a6174696f6e2f322f6176617461722e737667)](https://opencollective.com/vim-dotoo/organization/2/website) [![](https://camo.githubusercontent.com/eff61f0e31f5c976cae76a67a9bbd7c8dbaaa7b84a4d6f5e4907ccf44dec7e7c/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f76696d2d646f746f6f2f6f7267616e697a6174696f6e2f332f6176617461722e737667)](https://opencollective.com/vim-dotoo/organization/3/website) [![](https://camo.githubusercontent.com/b2499dd53671a6b0c5b092e3583eac65343b0e4fd00054a422706f35a14b1121/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f76696d2d646f746f6f2f6f7267616e697a6174696f6e2f342f6176617461722e737667)](https://opencollective.com/vim-dotoo/organization/4/website) [![](https://camo.githubusercontent.com/95ba7bb921767efc357808ffa0f40daf48e23ebee9aa43965ecfe719a37fb370/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f76696d2d646f746f6f2f6f7267616e697a6174696f6e2f352f6176617461722e737667)](https://opencollective.com/vim-dotoo/organization/5/website) [![](https://camo.githubusercontent.com/f5afa08d80cd2fc933fbba2ce785fe9f2b1ecaad150e9f1d898fe4008198eeae/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f76696d2d646f746f6f2f6f7267616e697a6174696f6e2f362f6176617461722e737667)](https://opencollective.com/vim-dotoo/organization/6/website) [![](https://camo.githubusercontent.com/1589203ee0606d5c762c69b71d321c733275b212da5c99e9d470ee7fa5c31c49/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f76696d2d646f746f6f2f6f7267616e697a6174696f6e2f372f6176617461722e737667)](https://opencollective.com/vim-dotoo/organization/7/website) [![](https://camo.githubusercontent.com/74a46d4b58c11cb92d99b82cc0e08d358064f66cb0301a23420c0524d58f0271/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f76696d2d646f746f6f2f6f7267616e697a6174696f6e2f382f6176617461722e737667)](https://opencollective.com/vim-dotoo/organization/8/website) [![](https://camo.githubusercontent.com/85213f96ba6ffba213f0194244e61ffd7b645bb155b2dc6100b7a93356746b5a/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f76696d2d646f746f6f2f6f7267616e697a6174696f6e2f392f6176617461722e737667)](https://opencollective.com/vim-dotoo/organization/9/website)