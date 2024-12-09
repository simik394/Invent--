---
page-title: nvim-orgmode/org-bullets.nvim
url: https://github.com/nvim-orgmode/org-bullets.nvim
date: 2024-06-21 03:23:49
tags:
  - A/sw/plugin
  - F/prod/homepage
  - C/
  - P/pwf
about:
  - "[[NeoVim]]"
  - "[[Inv/SW/nvim-orgmodeorgmode Orgmode clone written in Lua for Neovim 0.9+.|nvim.orgmode]]"
aliases: 
by: 
length: 2124
dir:
---

## Org-bullets.nvim

[](https://github.com/nvim-orgmode/org-bullets.nvim#org-bulletsnvim)

This plugin is a clone of [org-bullets](https://github.com/sabof/org-bullets). It replaces the asterisks in org syntax with unicode characters.

This plugin is an extension intended for use with [orgmode.nvim](https://github.com/kristijanhusak/orgmode.nvim)

This plugin works by using neovim `extmarks`, rather than `conceal` for a few reasons.

-   conceal can only have one global highlight see `:help hl-Conceal`.
-   conceal doesn't work when a block is folded.

*see below for a simpler conceal-based solution*

[![folded](https://user-images.githubusercontent.com/22454918/125088455-525df300-e0c5-11eb-9b36-47c238b46971.png)](https://user-images.githubusercontent.com/22454918/125088455-525df300-e0c5-11eb-9b36-47c238b46971.png)

## Pre-requisites

[](https://github.com/nvim-orgmode/org-bullets.nvim#pre-requisites)

-   **This plugin requires the use of treesitter with `tree-sitter-org` installed**
-   neovim 0.7+

## Installation

[](https://github.com/nvim-orgmode/org-bullets.nvim#installation)

#### With packer.nvim

[](https://github.com/nvim-orgmode/org-bullets.nvim#with-packernvim)

use 'akinsho/org-bullets.nvim'

## Usage

[](https://github.com/nvim-orgmode/org-bullets.nvim#usage)

To use the defaults use:

use {'akinsho/org-bullets.nvim', config \= function()
  require('org-bullets').setup()
end}

The full options available are:

**NOTE**: Do **NOT** copy and paste this block as it is not valid, it is just intended to show the available configuration options

use {"akinsho/org-bullets.nvim", config \= function()
  require("org-bullets").setup {
    concealcursor \= false, \-- If false then when the cursor is on a line underlying characters are visible
    symbols \= {
      \-- list symbol
      list \= "•",
      \-- headlines can be a list
      headlines \= { "◉", "○", "✸", "✿" },
      \-- or a function that receives the defaults and returns a list
      headlines \= function(default\_list)
        table.insert(default\_list, "♥")
        return default\_list
      end,
      \-- or false to disable the symbol. Works for all symbols
      headlines \= false,
      checkboxes \= {
        half \= { "", "OrgTSCheckboxHalfChecked" },
        done \= { "✓", "OrgDone" },
        todo \= { "˟", "OrgTODO" },
      },
    }
  }
end}

### Conceal-based alternative

[](https://github.com/nvim-orgmode/org-bullets.nvim#conceal-based-alternative)

A simpler conceal based alternative is:

syntax match OrgHeadlineStar1 /^\\\*\\ze\\s/me\=e\-1 conceal cchar\=◉ containedin\=OrgHeadlineLevel1 contained
syntax match OrgHeadlineStar2 /^\\\*\\{2}\\ze\\s/me\=e\-1 conceal cchar\=○ containedin\=OrgHeadlineLevel2 contained
syntax match OrgHeadlineStar3 /^\\\*\\{3}\\ze\\s/me\=e\-1 conceal cchar\=✸ containedin\=OrgHeadlineLevel3 contained
syntax match OrgHeadlineStar4 /^\\\*{4}\\ze\\s/me\=e\-1 conceal cchar\=✿ containedin\=OrgHeadlineLevel4 contained