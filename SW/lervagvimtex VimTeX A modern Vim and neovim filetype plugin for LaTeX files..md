---
page-title: "lervag/vimtex: VimTeX: A modern Vim and neovim filetype plugin for LaTeX files."
url: https://github.com/lervag/vimtex
date: 2024-06-21 03:52:18
tags:
  - A/sw/plugin
  - F/prod/homepage
  - C/
  - P/pwf
about:
  - "[[NeoVim]]"
  - "[[Inv/SW/latex|LaTeX]]"
aliases: 
by: 
length: 11474
dir:
---

## VimTeX

[](https://github.com/lervag/vimtex#vimtex)

VimTeX is a modern [Vim](http://www.vim.org/) and [Neovim](https://neovim.io/) filetype and syntax plugin for LaTeX files.

[![Gitter](https://camo.githubusercontent.com/e5d6a0b8dc0e43582f7cef037b63a9c86a1aa342ea4ba07fe56995ced8dfcd7f/68747470733a2f2f6261646765732e6769747465722e696d2f76696d7465782d636861742f636f6d6d756e6974792e737667)](https://gitter.im/vimtex-chat/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge) [![CI tests](https://github.com/lervag/vimtex/workflows/CI%20tests/badge.svg)](https://github.com/lervag/vimtex/workflows/CI%20tests/badge.svg) [![Donate](https://camo.githubusercontent.com/0283ea90498d8ea623c07906a5e07e9e6c2a5eaa6911d52033687c60cfa8d22f/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f446f6e6174652d50617950616c2d677265656e2e737667)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=5N4MFVXN7U8NW)

## Table of contents

[](https://github.com/lervag/vimtex#table-of-contents)

-   [Requirements](https://github.com/lervag/vimtex#requirements)
-   [Installation](https://github.com/lervag/vimtex#installation)
-   [Configuration](https://github.com/lervag/vimtex#configuration)
-   [Quick Start](https://github.com/lervag/vimtex#quick-start)
    -   [Tutorial](https://github.com/lervag/vimtex#tutorial)
    -   [Documentation](https://github.com/lervag/vimtex#documentation)
-   [Screenshots](https://github.com/lervag/vimtex#screenshots)
    -   [GIFs](https://github.com/lervag/vimtex#gifs)
-   [Features](https://github.com/lervag/vimtex#features)
-   [Other relevant plugins](https://github.com/lervag/vimtex#other-relevant-plugins)
    -   [Linting and syntax checking](https://github.com/lervag/vimtex#linting-and-syntax-checking)
    -   [Snippets and templates](https://github.com/lervag/vimtex#snippets-and-templates)
    -   [Tag navigation](https://github.com/lervag/vimtex#tag-navigation)
-   [Alternatives](https://github.com/lervag/vimtex#alternatives)
-   [VimTeX on the Web](https://github.com/lervag/vimtex#vimtex-on-the-web)

## Requirements

[](https://github.com/lervag/vimtex#requirements)

VimTeX requires Vim version 8.2.3995 or Neovim version 0.9.5. The requirements were updated in April 2024 after the release of VimTeX 2.15. If you are stuck on older versions of Vim or Neovim, then you should not use the most recent version of VimTeX, but instead remain at the v2.15 tag.

Some features require external tools. For example, the default compiler backend relies on [latexmk](https://www.cantab.net/users/johncollins/latexmk/index.html). Users are encouraged to read the requirements section in the [documentation](https://github.com/lervag/vimtex/blob/master/doc/vimtex.txt) (`:h vimtex-requirements`).

## Installation

[](https://github.com/lervag/vimtex#installation)

There are a lot of methods for installing plugins. The following explains the most common and popular approaches.

**Note**: Many plugin managers provide mechanisms to lazy load plugins. Please don't use this for VimTeX! VimTeX is already lazy loaded by virtue of being a filetype plugin and by using the autoload mechanisms. There is therefore nothing to gain by forcing VimTeX to lazily load through the plugin manager. In fact, doing it will *break* the inverse-search mechanism, which relies on a *global* command (`:VimtexInverseSearch`).

### lazy.nvim

[](https://github.com/lervag/vimtex#lazynvim)

In Neovim, [lazy.nvim](https://github.com/folke/lazy.nvim) is probably the most popular plugin manger. To install VimTeX, add a plugin spec similar to this:

{
  "lervag/vimtex",
  lazy \= false,     \-- we don't want to lazy load VimTeX
  \-- tag = "v2.15", -- uncomment to pin to a specific release
  init \= function()
    \-- VimTeX configuration goes here, e.g.
    vim.g.vimtex\_view\_method \= "zathura"
  end
}

VimTeX is mostly implemented with Vimscript and is configured with the classical vimscript variable convention like `g:vimtex_OPTION_NAME`. Nowadays, Neovim is often configured with Lua, thus some users may be interested in reading `:help lua-vimscript`.

### vim-plug

[](https://github.com/lervag/vimtex#vim-plug)

If you use [vim-plug](https://github.com/junegunn/vim-plug), then add *one* of the following lines to your configuration. The first will use the latest versions from the `master` branch, whereas the second will pin to a release tag.

Plug 'lervag/vimtex'
Plug 'lervag/vimtex', { 'tag': 'v2.15' }

### Other

[](https://github.com/lervag/vimtex#other)

There are many other plugin managers out there. They are typically well documented, and it should be straightforward to extrapolate the above snippets.

**Note**: If you use the built-in package feature, then:

-   Make sure to read and understand the package feature: `:help package`!
-   Use the `/pack/foo/start` subdirectory to make sure the filetype plugin is automatically loaded for the `tex` filetypes.
-   Helptags are not generated automatically. Run `:helptags` to generate them.
-   Please note that by default Vim puts custom `/start/` plugin directories at the end of the `&runtimepath`. This means the built in filetype plugin is loaded, which prevents VimTeX from loading. See [#1413](https://github.com/lervag/vimtex/issues/1413) for two suggested solutions to this. To see which scripts are loaded and in which order, use `:scriptnames`.
-   For more information on how to use the Vim native package solution, see [here](https://vi.stackexchange.com/questions/9522/what-is-the-vim8-package-feature-and-how-should-i-use-it) and [here](https://shapeshed.com/vim-packages/).

## Configuration

[](https://github.com/lervag/vimtex#configuration)

After installing VimTeX, you should edit your `.vimrc` file or `init.vim` file to configure VimTeX to your liking. Users should read the documentation to learn the various configuration possibilities, but the below is a simple overview of some of the main aspects.

**PLEASE don't just copy this without reading the comments!**

" This is necessary for VimTeX to load properly. The "indent" is optional.
" Note: Most plugin managers will do this automatically!
filetype plugin indent on

" This enables Vim's and neovim's syntax-related features. Without this, some
" VimTeX features will not work (see ":help vimtex-requirements" for more
" info).
" Note: Most plugin managers will do this automatically!
syntax enable

" Viewer options: One may configure the viewer either by specifying a built-in
" viewer method:
let g:vimtex\_view\_method \= 'zathura'

" Or with a generic interface:
let g:vimtex\_view\_general\_viewer \= 'okular'
let g:vimtex\_view\_general\_options \= '\--unique file:@pdf\\#src:@line@tex'

" VimTeX uses latexmk as the default compiler backend. If you use it, which is
" strongly recommended, you probably don't need to configure anything. If you
" want another compiler backend, you can change it as follows. The list of
" supported backends and further explanation is provided in the documentation,
" see ":help vimtex-compiler".
let g:vimtex\_compiler\_method \= 'latexrun'

" Most VimTeX mappings rely on localleader and this can be changed with the
" following line. The default is usually fine and is the symbol "\\".
let maplocalleader \= ","

**Note**: If the compiler or the viewer doesn't start properly, one may type `<localleader>li` to view the system commands that were executed to start them. To inspect the compiler output, use `<localleader>lo`.

## Quick Start

[](https://github.com/lervag/vimtex#quick-start)

The following video shows how to use VimTeX's main features (credits: [@DustyTopology](https://github.com/DustyTopology) from [#1946](https://github.com/lervag/vimtex/issues/1946#issuecomment-846345095)). The example LaTeX file used in the video is available under [`test/example-quick-start/main.tex`](https://github.com/lervag/vimtex/blob/master/test/example-quick-start/main.tex) and it may be instructive to copy the file and play with it to learn some of these basic functions.

Screencast.mp4

### Tutorial

[](https://github.com/lervag/vimtex#tutorial)

Both new and experienced users are encouraged to read the excellent guide by @ejmastnak: [Getting started with the VimTeX plugin](https://ejmastnak.com/tutorials/vim-latex/vimtex/). The guide covers all the fundamentals of setting up a VimTeX-based LaTeX workflow, including usage of the VimTeX plugin, compilation, setting up forward and inverse search with a PDF reader, and Vimscript tools for user-specific customization.

### Documentation

[](https://github.com/lervag/vimtex#documentation)

Users are of course *strongly* encouraged to read the documentation, at least the introduction, to learn about the different features and possibilities provided by VimTeX (see [`:h vimtex`](https://github.com/lervag/vimtex/blob/master/doc/vimtex.txt)). Advanced users and potential developers may also be interested in reading the supplementary documents:

-   [CONTRIBUTING.md](https://github.com/lervag/vimtex/blob/master/CONTRIBUTING.md)
-   [DOCUMENTATION.md](https://github.com/lervag/vimtex/blob/master/DOCUMENTATION.md)

## Screenshots

[](https://github.com/lervag/vimtex#screenshots)

Here is an example of the syntax highlighting provided by VimTeX. The conceal feature is active on the right-hand side split. The example is made by @DustyTopology with the [vim-colors-xcode](https://github.com/arzg/vim-colors-xcode) colorscheme with some minor adjustments [described here](https://github.com/lervag/vimtex/issues/1946#issuecomment-843674951).

[![Syntax example](https://github.com/lervag/vimtex-media/raw/main/img/syntax.png)](https://github.com/lervag/vimtex-media/blob/main/img/syntax.png)

### GIFs

[](https://github.com/lervag/vimtex#gifs)

See the file [VISUALS.md](https://github.com/lervag/vimtex/blob/master/VISUALS.md) for screencast-style GIFs demonstrating VimTeX's core motions, text-editing commands, and text objects.

## Features

[](https://github.com/lervag/vimtex#features)

Below is a list of features offered by VimTeX. The features are accessible as both commands and mappings. The mappings generally start with `<localleader>l`, but if desired one can disable default mappings to define custom mappings. Nearly all features are enabled by default, but each feature may be disabled if desired. The two exceptions are code folding and formating, which are disabled by default and must be manually enabled.

-   Document compilation with [latexmk](https://www.cantab.net/users/johncollins/latexmk/index.html), [latexrun](https://github.com/aclements/latexrun), [tectonic](https://tectonic-typesetting.github.io/), or [arara](https://github.com/cereda/arara)
-   LaTeX log parsing for quickfix entries using
    -   internal method
    -   [pplatex](https://github.com/stefanhepp/pplatex)
-   Compilation of selected part of document
-   Support for several PDF viewers with forward search
    -   [MuPDF](http://www.mupdf.com/)
    -   [Okular](https://okular.kde.org/)
    -   [qpdfview](https://launchpad.net/qpdfview)
    -   [Skim](http://skim-app.sourceforge.net/)
    -   [SumatraPDF](http://www.sumatrapdfreader.org/free-pdf-reader.html)
    -   [TeXShop](https://pages.uoregon.edu/koch/texshop/)
    -   [Zathura](https://pwmt.org/projects/zathura/)
    -   Other viewers are supported through a general interface
-   Completion of
    -   citations
    -   labels
    -   commands
    -   file names for figures, input/include, includepdf, includestandalone
    -   glossary entries
    -   package and documentclass names based on available `.sty` and `.cls` files
-   Document navigation through
    -   table of contents
    -   table of labels
    -   proper settings for `'include'`, `'includexpr'`, `'suffixesadd'` and `'define'`, which among other things
        -   allow `:h include-search` and `:h definition-search`
        -   give enhanced `gf` command
-   Easy access to (online) documentation of packages
-   Word count (through `texcount`)
-   Motions ([link to GIF demonstrations](https://github.com/lervag/vimtex/blob/master/VISUALS.md#motion-commands))
    -   Move between section boundaries with `[[`, `[]`, `][`, and `]]`
    -   Move between environment boundaries with `[m`, `[M`, `]m`, and `]M`
    -   Move between math environment boundaries with `[n`, `[N`, `]n`, and `]N`
    -   Move between frame environment boundaries with `[r`, `[R`, `]r`, and `]R`
    -   Move between comment boundaries with `[*` and `]*`
    -   Move between matching delimiters with `%`
-   Text objects ([link to GIF demonstrations](https://github.com/lervag/vimtex/blob/master/VISUALS.md#text-objects))
    -   `ic ac` Commands
    -   `id ad` Delimiters
    -   `ie ae` LaTeX environments
    -   `i$ a$` Math environments
    -   `iP aP` Sections
    -   `im am` Items
-   Other mappings ([link to GIF demonstrations](https://github.com/lervag/vimtex/blob/master/VISUALS.md#deleting-surrounding-latex-content))
    -   Delete the surrounding command, environment or delimiter with `dsc`/`dse`/`ds$`/`dsd`
    -   Change the surrounding command, environment or delimiter with `csc`/`cse`/`cs$`/`csd`
    -   Toggle starred command or environment with `tsc`/`tse`
    -   Toggle inline and displaymath with `ts$`
    -   Toggle between e.g. `()` and `\left(\right)` with `tsd`
    -   Toggle (inline) fractions with `tsf`
    -   Toggle line-break macro `\\` with `tsb`
    -   Close the current environment/delimiter in insert mode with `]]`
    -   Add `\left ... \right)` modifiers to surrounding delimiters with `<F8>`
    -   Insert new command with `<F7>`
    -   Convenient insert mode mappings for faster typing of e.g. maths
    -   Context menu on citations (e.g. `\cite{...}`) mapped to `<cr>`
-   Improved folding (`:h 'foldexpr'`)
-   Improved indentation (`:h 'indentexpr'`)
-   Syntax highlighting
    -   A consistent core syntax specification
    -   General syntax highlighting for several popular LaTeX packages
    -   Nested syntax highlighting for several popular LaTeX packages
    -   Highlight matching delimiters
-   Support for multi-file project packages
    -   [import](http://ctan.uib.no/macros/latex/contrib/import/import.pdf)
    -   [subfiles](http://ctan.uib.no/macros/latex/contrib/subfiles/subfiles.pdf)

See the documentation for a thorough introduction to VimTeX (e.g. `:h vimtex`).

## Other relevant plugins

[](https://github.com/lervag/vimtex#other-relevant-plugins)

Even though VimTeX provides a lot of nice features for working with LaTeX documents, there are several features that are better served by other, dedicated plugins. For a more detailed listing of these, please see [`:help vimtex-and-friends`](https://github.com/lervag/vimtex/blob/master/doc/vimtex.txt#L540).

### Linting and syntax checking

[](https://github.com/lervag/vimtex#linting-and-syntax-checking)

-   [ale](https://github.com/w0rp/ale)
-   [neomake](https://github.com/neomake/neomake)
-   [syntastic](https://github.com/vim-syntastic/syntastic)

### Snippets and templates

[](https://github.com/lervag/vimtex#snippets-and-templates)

-   [UltiSnips](https://github.com/SirVer/ultisnips)
-   [neosnippet](https://github.com/Shougo/neosnippet.vim)

### Tag navigation

[](https://github.com/lervag/vimtex#tag-navigation)

-   [vim-gutentags](https://github.com/ludovicchabant/vim-gutentags)

## Alternatives

[](https://github.com/lervag/vimtex#alternatives)

The following are some alternative LaTeX plugins for Vim:

-   [LaTeX-Suite](http://vim-latex.sourceforge.net/)
    
    The main difference between VimTeX and LaTeX-Suite (aka vim-latex) is probably that VimTeX does not try to implement a full fledged IDE for LaTeX inside Vim. E.g.:
    
    -   VimTeX does not provide a full snippet feature, because this is better handled by [UltiSnips](https://github.com/SirVer/ultisnips) or [neosnippet](https://github.com/Shougo/neosnippet.vim) or similar snippet engines.
    -   VimTeX builds upon Vim principles: It provides text objects for environments, inline math, it provides motions for sections and paragraphs
    -   VimTeX uses `latexmk`, `latexrun`, `tectonic` or `arara` for compilation with a callback feature to get instant feedback on compilation errors
    -   VimTeX is very modular: if you don't like a feature, you can turn it off.
-   [TexMagic.nvim](https://github.com/jakewvincent/texmagic.nvim)
    
    "A simple, lightweight Neovim plugin that facilitates LaTeX build engine selection via magic comments. It is designed with the TexLab LSP server's build functionality in mind, which at the time of this plugin's inception had to be specified in init.lua/init.vim and could not be set on a by-project basis."
    
    This plugin should be combined with the TexLab LSP server, and it only works on neovim.
    
-   [LaTeX-Box](https://github.com/LaTeX-Box-Team/LaTeX-Box)
    
    VimTeX currently has most of the features of LaTeX-Box, as well as some additional ones. See [here](https://github.com/lervag/vimtex#features) for a relatively complete list of features.
    
    One particular feature that LaTeX-Box has but VimTeX misses, is the ability to do single-shot compilation *with callback*. This functionality was removed because it adds a lot of complexity for relatively little gain (IMHO).
    
-   [AutomaticTexPlugin](http://atp-vim.sourceforge.net/)
    
-   [vim-latex-live-preview](https://github.com/xuhdev/vim-latex-live-preview)
    

For more alternatives and more information and discussions regarding LaTeX plugins for Vim, see:

-   [What are the differences between LaTeX plugins](http://vi.stackexchange.com/questions/2047/what-are-the-differences-between-latex-plugins)
-   [List of LaTeX editors (not only Vim)](https://tex.stackexchange.com/questions/339/latex-editors-ides)