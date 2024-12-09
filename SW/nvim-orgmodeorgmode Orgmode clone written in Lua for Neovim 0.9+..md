---
page-title: "nvim-orgmode/orgmode: Orgmode clone written in Lua for Neovim 0.9+."
url: https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file
date: "2024-08-16 23:25:21"
tags: [a/sw/plugin, f/prod/homepage, c/, p/pwf]
about: ["[[NeoVim]]"]
aliases: 
- 
by: 
length: 8964
dir: 
---

## Quickstart

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#quickstart)

### Requirements

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#requirements)

-   Neovim 0.9.4 or later

### Installation

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#installation)

Use your favourite package manager:

**[lazy.nvim](https://github.com/folke/lazy.nvim) (recommended)**  

{
  'nvim-orgmode/orgmode',
  event \= 'VeryLazy',
  ft \= { 'org' },
  config \= function()
    \-- Setup orgmode
    require('orgmode').setup({
      org\_agenda\_files \= '~/orgfiles/\*\*/\*',
      org\_default\_notes\_file \= '~/orgfiles/refile.org',
    })

    \-- NOTE: If you are using nvim-treesitter with ~ensure\_installed = "all"~ option
    \-- add ~org~ to ignore\_install
    \-- require('nvim-treesitter.configs').setup({
    \--   ensure\_installed = 'all',
    \--   ignore\_install = { 'org' },
    \-- })
  end,
}

**[packer.nvim](https://github.com/wbthomason/packer.nvim)**  

use {'nvim-orgmode/orgmode', config \= function()
  require('orgmode').setup{}
end
}

[**vim-plug**](https://github.com/junegunn/vim-plug)  

Plug 'nvim-orgmode/orgmode'

[**dein.vim**](https://github.com/Shougo/dein.vim)  

call dein#add('nvim-orgmode/orgmode')

### Setup

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#setup)

Note that this setup is not needed for [lazy.nvim](https://github.com/folke/lazy.nvim) since instructions above covers full setup

\-- init.lua

require('orgmode').setup({
  org\_agenda\_files \= {'~/Dropbox/org/\*', '~/my-orgs/\*\*/\*'},
  org\_default\_notes\_file \= '~/Dropbox/org/refile.org',
})

\-- NOTE: If you are using nvim-treesitter with ~ensure\_installed = "all"~ option
\-- add ~org~ to ignore\_install
\-- require('nvim-treesitter.configs').setup({
\--   ensure\_installed = 'all',
\--   ignore\_install = { 'org' },
\-- })

Or if you are using ~init.vim~, wrap the above snippet like so:
" init.vim
lua << EOF

require('orgmode').setup({
  org\_agenda\_files \= {'~/Dropbox/org/\*', '~/my-orgs/\*\*/\*'},
  org\_default\_notes\_file \= '~/Dropbox/org/refile.org',
})

EOF

#### Completion

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#completion)

[**nvim-cmp**](https://github.com/hrsh7th/nvim-cmp)  

require('cmp').setup({
  sources \= {
    { name \= 'orgmode' }
  }
})

[**completion-nvim**](https://github.com/nvim-lua/completion-nvim)  

vim.g.completion\_chain\_complete\_list \= {
  org \= {
    { mode \= 'omni'},
  },
}
\-- add additional keyword chars
vim.cmd\[\[autocmd FileType org setlocal iskeyword+=:,#,+\]\]

Or just use `omnifunc` via `<C-x><C-o>`

### Usage

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#usage)

-   **Open agenda prompt**: `<Leader>oa`
-   **Open capture prompt**: `<Leader>oc`
-   In any orgmode buffer press `g?` for help

If you are new to Orgmode, see [Getting started](https://github.com/nvim-orgmode/orgmode/blob/master/DOCS.md#getting-started-with-orgmode) section in the Docs or a hands-on [tutorial](https://github.com/nvim-orgmode/orgmode/wiki/Getting-Started) in our wiki.

## Showcase

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#showcase)

### Agenda

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#agenda)

[![https://user-images.githubusercontent.com/1782860/123549968-8521f600-d76b-11eb-9a93-02bad08b37ce.gif](https://user-images.githubusercontent.com/1782860/123549968-8521f600-d76b-11eb-9a93-02bad08b37ce.gif)](https://user-images.githubusercontent.com/1782860/123549968-8521f600-d76b-11eb-9a93-02bad08b37ce.gif)

### Org file

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#org-file)

[![https://user-images.githubusercontent.com/1782860/123549982-90752180-d76b-11eb-8828-9edf9f76af08.gif](https://user-images.githubusercontent.com/1782860/123549982-90752180-d76b-11eb-8828-9edf9f76af08.gif)](https://user-images.githubusercontent.com/1782860/123549982-90752180-d76b-11eb-8828-9edf9f76af08.gif)

### Capturing and refiling

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#capturing-and-refiling)

[![https://user-images.githubusercontent.com/1782860/123549993-9a972000-d76b-11eb-814b-b348a93df08a.gif](https://user-images.githubusercontent.com/1782860/123549993-9a972000-d76b-11eb-814b-b348a93df08a.gif)](https://user-images.githubusercontent.com/1782860/123549993-9a972000-d76b-11eb-814b-b348a93df08a.gif)

### Autocompletion

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#autocompletion)

[![https://user-images.githubusercontent.com/1782860/123550227-e8605800-d76c-11eb-96f6-c0a677d562d4.gif](https://user-images.githubusercontent.com/1782860/123550227-e8605800-d76c-11eb-96f6-c0a677d562d4.gif)](https://user-images.githubusercontent.com/1782860/123550227-e8605800-d76c-11eb-96f6-c0a677d562d4.gif)

## Treesitter Info

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#treesitter-info)

The built-in treesitter parser is used for parsing the org files.

### Known highlighting issues and limitations

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#known-highlighting-issues-and-limitations)

-   LaTex is still highlighted through syntax file

## Troubleshoot

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#troubleshoot)

### Indentation is not working

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#indentation-is-not-working)

Make sure you are not overriding indentexpr in Org buffers with [nvim-treesitter indentation](https://github.com/nvim-treesitter/nvim-treesitter#indentation)

### I get `treesitter/query.lua` errors when opening agenda/capture prompt or org files

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#i-get-treesitterquerylua-errors-when-opening-agendacapture-prompt-or-org-files)

Tree-sitter parser might not be installed. Try running `:lua require('orgmode.config'):reinstall_grammar()` to reinstall it.

### Dates are not in English

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#dates-are-not-in-english)

Dates are generated with Lua native date support, and it reads your current locale when creating them.

To use different locale you can add this to your `init.lua`:

vim.cmd('language en\_US.utf8')

or `init.vim`

Just make sure you have `en_US` locale installed on your system. To see what you have available on the system you can start the command `:language` and press `<TAB>` to autocomplete possible options.

### Links are not concealed

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#links-are-not-concealed)

Links are concealed with Vim’s conceal feature (see `:help conceal`). To enable concealing, add this to your `init.lua`:

vim.opt.conceallevel \= 2
vim.opt.concealcursor \= 'nc'

Or if you are using `init.vim`:

set conceallevel\=2
set concealcursor\=nc

### Jumping to file path is not working for paths with forward slash

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#jumping-to-file-path-is-not-working-for-paths-with-forward-slash)

If you are using Windows, paths are by default written with backslashes. To use forward slashes, you must enable `shellslash` option (see `:help shellslash`).

vim.opt.shellslash \= true

Or if you are using `init.vim`:

More info on issue [#281](https://github.com/nvim-orgmode/orgmode/issues/281#issuecomment-1120200775)

## Features

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#features)

### TL;DR

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#tldr)

-   Agenda view
-   Search by tags/keyword
-   Clocking time
-   Repeatable dates, date and time ranges
-   Capturing to default notes file/destination
-   Archiving (archive file or ARCHIVE tag)
-   Exporting (via `emacs`, `pandoc` and custom export options)
-   Notifications (experimental, see issue [#49](https://github.com/nvim-orgmode/orgmode/issues/49))
-   Calendar popup for easier navigation and date updates
-   Various org file mappings:
    -   Promote/Demote
    -   Change TODO state
    -   Change dates
    -   Insert/Move/Refile headlines
    -   Change tags
    -   Toggle checkbox state
-   Remote editing from agenda view
-   Repeatable mapping via [vim-repeat](https://github.com/tpope/vim-repeat)

### Detailed breakdown

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#detailed-breakdown)

-   Agenda prompt:
    -   Agenda view (`a`):
        -   Ability to show daily(`vd`)/weekly(`vw`)/monthly(`vm`)/yearly(`vy`) agenda
        -   Support for various date settings:
            -   DEADLINE: Warning settings - example: `<2021-06-11 Fri 11:00 -1d>`
            -   SCHEDULED: Delay setting - example: `<2021-06-11 Fri 11:00 -2d>`
            -   All dates - Repeater settings:
                -   Cumulate type: `<2021-06-11 Fri 11:00 +1w>`
                -   Catch-up type: `<2021-06-11 Fri 11:00 ++1w>`
                -   Restart type: `<2021-06-11 Fri 11:00 .+1w>`
            -   Time ranges - example: `<2021-06-11 Fri 11:00-12:30>`
            -   Date ranges - example: `<2021-06-11 Fri 11:00-12:30>--<2021-06-13 Sun 22:00>`
        -   Properly lists tasks according to defined dates (DEADLINE,SCHEDULED,Plain date)
        -   Navigate forward (`f`)/backward(`b`) or jump to specific date (`J`)
        -   Go to task under cursor in current window(`<CR>`) or other window(`<TAB>`)
        -   Print category from “:CATEGORY:” property if defined
    -   List tasks that have “TODO” state (`t`):
    -   Find headlines matching tag(s) (`m`):
    -   Search for headlines (and it’s content) for a query (`s`):
    -   [Advanced search](https://github.com/nvim-orgmode/orgmode/blob/master/DOCS.md#advanced-search) for tags/todo kewords/properties
    -   Notifications (experimental, see issue [#49](https://github.com/nvim-orgmode/orgmode/issues/49))
    -   Clocking time
-   Capture:
    -   Define custom templates
    -   Fast capturing to default notes file via `<C-c>`
    -   Capturing to specific destination `<Leader>or`
    -   Abort capture with `<Leader>ok`
-   Org files
    -   Clocking time
    -   Refile to destination/headline: `<Leader>or`
    -   Increase/Decrease date under cursor: `<C-a>` / `<C-x>`
    -   Change date under cursor via calendar popup: `cid`
    -   Change headline TODO state: forward `cit` or backward `ciT`
    -   Open hyperlink or date under cursor: `<Leader>oo`
    -   Toggle checkbox: `<C-space>`
    -   Toggle current line to headline and vice versa: `<Leader>o*`
    -   Toggle folding of current headline: `<TAB>`
    -   Toggle folding in whole file: `<S-TAB>`
    -   Archive headline: `<Leader>o$`
    -   Add archive tag: `<Leader>oA`
    -   Change tags: `<Leader>ot`
    -   Promote headline: `<<`
    -   Demote headline: `>>`
    -   Promote subtree: `<s`
    -   Demote subtree: `>s`
    -   Add headline/list item/checkbox: `<Leader><CR>`
    -   Insert heading after current heading and it’s content: `<Leader>oih`
    -   Insert TODO heading after current line: `<Leader>oiT`
    -   Insert TODO heading after current heading and it’s content: `<Leader>oit`
    -   Move headline up: `<Leader>oK`
    -   Move headline down: `<Leader>oJ`
    -   Highlighted code blocks (`#+BEGIN_SRC filetype`) Exporting (via `emacs`, `pandoc` and custom export options)

Link to detailed documentation: [DOCS](https://github.com/nvim-orgmode/orgmode/blob/master/DOCS.md)

## Plugins

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#plugins)

-   [org-roam.nvim](https://github.com/chipsenkbeil/org-roam.nvim) - Implementation of [Org-roam](https://orgroam.com/) knowledge management system
-   [telescope-orgmode.nvim](https://github.com/nvim-orgmode/telescope-orgmode.nvim) - Telescope extension to find headlines, refile and insert links
-   [org-bullets.nvim](https://github.com/akinsho/org-bullets.nvim) - Show org mode bullets as UTF-8 characters
-   [headlines.nvim](https://github.com/lukas-reineke/headlines.nvim) - Add few highlight options for code blocks and headlines
-   [sniprun](https://github.com/michaelb/sniprun) - For code evaluation in blocks
-   [vim-table-mode](https://github.com/dhruvasagar/vim-table-mode) - For table support

See all available plugins on [orgmode-nvim](https://github.com/topics/orgmode-nvim)

**If you built a plugin please add “orgmode-nvim” topic to it.**

> **NOTE**: None of the Emacs Orgmode plugins will be built into nvim-orgmode. Anything that’s a separate plugin in Emacs Orgmode should be a separate plugin in here. The point of this plugin is to provide functionality that’s built into Emacs Orgmode core, and a good foundation for external plugins.

If you want to build a plugin, post suggestions and improvements on [Plugins infrastructure](https://github.com/nvim-orgmode/orgmode/issues/26) issue.

### 🔧 API

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#wrench-api)

Documentation for our work-in-progress API can be found [here](https://github.com/nvim-orgmode/orgmode/blob/master/doc/orgmode_api.txt)

## Contributing

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#contributing)

See [CONTRIBUTING.md](https://github.com/nvim-orgmode/orgmode/blob/master/CONTRIBUTING.md)

## Documentation

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#documentation)

If you are just starting out with orgmode, have a look at the [Getting Started](https://github.com/nvim-orgmode/orgmode/wiki/Getting-Started) section in our wiki.

Vim documentation is auto generated from [DOCS.md](https://github.com/nvim-orgmode/orgmode/blob/master/DOCS.md) file with [md2vim](https://github.com/FooSoft/md2vim).

Hosted documentation is on: [https://nvim-orgmode.github.io/](https://nvim-orgmode.github.io/)

## Roadmap

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#roadmap)

-   ✅ Support searching by properties
-   🔳 Improve checkbox hierarchy
-   ✅ Support todo keyword faces
-   ✅ Support clocking work time
-   ✅ Improve folding
-   ✅ Support exporting (via existing emacs tools)
-   🔳 Support archiving to specific headline
-   ✅ Support tables
-   🔳 Support diary format dates
-   🔳 Support evaluating code blocks

## Thanks to

[](https://github.com/nvim-orgmode/orgmode?tab=readme-ov-file#thanks-to)

-   [@dhruvasagar](https://github.com/dhruvasagar) and his [vim-dotoo](https://github.com/dhruvasagar/vim-dotoo) plugin that got me started using orgmode. Without him this plugin would not happen.
-   [@milisims](https://github.com/milisims) for writing a treesitter parser for org
-   [vim-orgmode](https://github.com/jceb/vim-orgmode) for some parts of the code (mostly syntax)