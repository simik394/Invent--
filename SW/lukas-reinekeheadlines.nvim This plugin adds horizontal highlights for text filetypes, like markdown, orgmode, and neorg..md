---
page-title: "lukas-reineke/headlines.nvim: This plugin adds horizontal highlights for text filetypes, like markdown, orgmode, and neorg."
url: https://github.com/lukas-reineke/headlines.nvim
date: "2024-06-21 02:57:45"
tags: [A/sw/plugin, F/prod/homepage, C/, P/pwf, m/⭐]
about: ["[[NeoVim]]"]
aliases: 
- 
by: 
length: 7837
dir: 
---

## Headlines.nvim

[](https://github.com/lukas-reineke/headlines.nvim#headlinesnvim)

This plugin adds highlights for text filetypes, like `markdown`, `orgmode`, and `neorg`.

1.  Background highlighting for headlines
2.  Background highlighting for code blocks
3.  Whole window separator for horizontal line
4.  Bar for Quotes

Treesitter grammar needs to be installed for the languages.

## Install

[](https://github.com/lukas-reineke/headlines.nvim#install)

Use your favourite plugin manager to install.

#### Example with Packer

[](https://github.com/lukas-reineke/headlines.nvim#example-with-packer)

[wbthomason/packer.nvim](https://github.com/wbthomason/packer.nvim)

\-- init.lua
require("packer").startup(function()
    use {
        "lukas-reineke/headlines.nvim",
        after \= "nvim-treesitter",
        config \= function()
            require("headlines").setup()
        end,
    }
end)

#### Example with Plug

[](https://github.com/lukas-reineke/headlines.nvim#example-with-plug)

[junegunn/vim-plug](https://github.com/junegunn/vim-plug)

" init.vim
call plug#begin('~/.vim/plugged')
Plug 'lukas-reineke/headlines.nvim'
call plug#end()

lua << EOF
require("headlines").setup()
EOF

#### Example with Lazy

[](https://github.com/lukas-reineke/headlines.nvim#example-with-lazy)

[folke/lazy.nvim](https://github.com/folke/lazy.nvim)

\-- init.lua
require("lazy").setup {
    {
        "lukas-reineke/headlines.nvim",
        dependencies \= "nvim-treesitter/nvim-treesitter",
        config \= true, \-- or \`opts = {}\`
    },
}

## Setup

[](https://github.com/lukas-reineke/headlines.nvim#setup)

To configure headlines.nvim pass a config table into the setup function.

Default config:

require("headlines").setup {
    markdown \= {
        query \= vim.treesitter.parse\_query(
            "markdown",
            \[\[
                (atx\_heading \[
                    (atx\_h1\_marker)
                    (atx\_h2\_marker)
                    (atx\_h3\_marker)
                    (atx\_h4\_marker)
                    (atx\_h5\_marker)
                    (atx\_h6\_marker)
                \] @headline)
                (thematic\_break) @dash
                (fenced\_code\_block) @codeblock
                (block\_quote\_marker) @quote
                (block\_quote (paragraph (inline (block\_continuation) @quote)))
                (block\_quote (paragraph (block\_continuation) @quote))
                (block\_quote (block\_continuation) @quote)
            \]\]
        ),
        headline\_highlights \= { "Headline" },
        bullet\_highlights \= {
            "@text.title.1.marker.markdown",
            "@text.title.2.marker.markdown",
            "@text.title.3.marker.markdown",
            "@text.title.4.marker.markdown",
            "@text.title.5.marker.markdown",
            "@text.title.6.marker.markdown",
        },
        bullets \= { "◉", "○", "✸", "✿" },
        codeblock\_highlight \= "CodeBlock",
        dash\_highlight \= "Dash",
        dash\_string \= "\-",
        quote\_highlight \= "Quote",
        quote\_string \= "┃",
        fat\_headlines \= true,
        fat\_headline\_upper\_string \= "▃",
        fat\_headline\_lower\_string \= "🬂",
    },
    rmd \= {
        query \= vim.treesitter.parse\_query(
            "markdown",
            \[\[
                (atx\_heading \[
                    (atx\_h1\_marker)
                    (atx\_h2\_marker)
                    (atx\_h3\_marker)
                    (atx\_h4\_marker)
                    (atx\_h5\_marker)
                    (atx\_h6\_marker)
                \] @headline)
                (thematic\_break) @dash
                (fenced\_code\_block) @codeblock
                (block\_quote\_marker) @quote
                (block\_quote (paragraph (inline (block\_continuation) @quote)))
                (block\_quote (paragraph (block\_continuation) @quote))
                (block\_quote (block\_continuation) @quote)
            \]\]
        ),
        treesitter\_language \= "markdown",
        headline\_highlights \= { "Headline" },
        bullet\_highlights \= {
            "@text.title.1.marker.markdown",
            "@text.title.2.marker.markdown",
            "@text.title.3.marker.markdown",
            "@text.title.4.marker.markdown",
            "@text.title.5.marker.markdown",
            "@text.title.6.marker.markdown",
        },
        bullets \= { "◉", "○", "✸", "✿" },
        codeblock\_highlight \= "CodeBlock",
        dash\_highlight \= "Dash",
        dash\_string \= "\-",
        quote\_highlight \= "Quote",
        quote\_string \= "┃",
        fat\_headlines \= true,
        fat\_headline\_upper\_string \= "▃",
        fat\_headline\_lower\_string \= "🬂",
    },
    norg \= {
        query \= vim.treesitter.parse\_query(
            "norg",
            \[\[
                \[
                    (heading1\_prefix)
                    (heading2\_prefix)
                    (heading3\_prefix)
                    (heading4\_prefix)
                    (heading5\_prefix)
                    (heading6\_prefix)
                \] @headline
                (weak\_paragraph\_delimiter) @dash
                (strong\_paragraph\_delimiter) @doubledash
                (\[(ranged\_tag
                    name: (tag\_name) @\_name
                    (#eq? @\_name "code")
                )
                (ranged\_verbatim\_tag
                    name: (tag\_name) @\_name
                    (#eq? @\_name "code")
                )\] @codeblock (#offset! @codeblock 0 0 1 0))
                (quote1\_prefix) @quote
            \]\]
        ),
        headline\_highlights \= { "Headline" },
        bullet\_highlights \= {
            "@neorg.headings.1.prefix",
            "@neorg.headings.2.prefix",
            "@neorg.headings.3.prefix",
            "@neorg.headings.4.prefix",
            "@neorg.headings.5.prefix",
            "@neorg.headings.6.prefix",
        },
        bullets \= { "◉", "○", "✸", "✿" },
        codeblock\_highlight \= "CodeBlock",
        dash\_highlight \= "Dash",
        dash\_string \= "\-",
        doubledash\_highlight \= "DoubleDash",
        doubledash\_string \= "\=",
        quote\_highlight \= "Quote",
        quote\_string \= "┃",
        fat\_headlines \= true,
        fat\_headline\_upper\_string \= "▃",
        fat\_headline\_lower\_string \= "🬂",
    },
    org \= {
        query \= vim.treesitter.parse\_query(
            "org",
            \[\[
                (headline (stars) @headline)
                (
                    (expr) @dash
                    (#match? @dash "^-----+$")
                )
                (block
                    name: (expr) @\_name
                    (#match? @\_name "(SRC|src)")
                ) @codeblock
                (paragraph . (expr) @quote
                    (#eq? @quote ">")
                )
            \]\]
        ),
        headline\_highlights \= { "Headline" },
        bullet\_highlights \= {
            "@org.headline.level1",
            "@org.headline.level2",
            "@org.headline.level3",
            "@org.headline.level4",
            "@org.headline.level5",
            "@org.headline.level6",
            "@org.headline.level7",
            "@org.headline.level8",
        },
        bullets \= { "◉", "○", "✸", "✿" },
        codeblock\_highlight \= "CodeBlock",
        dash\_highlight \= "Dash",
        dash\_string \= "\-",
        quote\_highlight \= "Quote",
        quote\_string \= "┃",
        fat\_headlines \= true,
        fat\_headline\_upper\_string \= "▃",
        fat\_headline\_lower\_string \= "🬂",
    },
}

To change any setting, pass a table with that option. Or add a completely new filetype. You can turn off highlighting by removing that part from the query, or setting highlight to `false`.

require("headlines").setup {
    markdown \= {
        headline\_highlights \= false,
    },
    yaml \= {
        query \= vim.treesitter.parse\_query(
            "yaml",
            \[\[
                (
                    (comment) @dash
                    (#match? @dash "^# ---+$")
                )
            \]\]
        ),
        dash\_highlight \= "Dash",
    },
}

Please see `:help headlines.txt` for more details.

## Screenshots

[](https://github.com/lukas-reineke/headlines.nvim#screenshots)

All screenshots use [my custom onedark color scheme](https://github.com/lukas-reineke/onedark.nvim).

### Simple org file

[](https://github.com/lukas-reineke/headlines.nvim#simple-org-file)

vim.cmd \[\[highlight Headline1 guibg=#1e2718\]\]
vim.cmd \[\[highlight Headline2 guibg=#21262d\]\]
vim.cmd \[\[highlight CodeBlock guibg=#1c1c1c\]\]
vim.cmd \[\[highlight Dash guibg=#D19A66 gui=bold\]\]

require("headlines").setup {
    org \= {
        headline\_highlights \= { "Headline1", "Headline2" },
    },
}

[![Screenshot](https://user-images.githubusercontent.com/12900252/152090098-f0fe7ad5-efea-42d9-b3d7-a4bfd6391189.png)](https://user-images.githubusercontent.com/12900252/152090098-f0fe7ad5-efea-42d9-b3d7-a4bfd6391189.png)