---
page-title: "folke/todo-comments.nvim: ✅ Highlight, list and search todo comments in your projects"
url: https://github.com/folke/todo-comments.nvim
date: "2024-06-20 22:49:49"
tags: 
- A/sw/plugin
- F/homepage
- C/
- P/
about: 
- "[[NeoVim]]"
aliases: 
- 89deb0ec-5c64-4f19-9659-b49a5e252c32
- folketodo-comments.nvim ✅ Highlight, list and search todo comments in your projects
by: 
length: 5515
dir: 
---

## ✅ Todo Comments

[](https://github.com/folke/todo-comments.nvim#-todo-comments)

**todo-comments** is a lua plugin for Neovim >= 0.8.0 to highlight and search for todo comments like `TODO`, `HACK`, `BUG` in your code base.

[![image](https://user-images.githubusercontent.com/292349/118135272-ad21e980-b3b7-11eb-881c-e45a4a3d6192.png)](https://user-images.githubusercontent.com/292349/118135272-ad21e980-b3b7-11eb-881c-e45a4a3d6192.png)

## ✨ Features

[](https://github.com/folke/todo-comments.nvim#-features)

-   **highlight** your todo comments in different styles
-   optionally only highlights todos in comments using **TreeSitter**
-   configurable **signs**
-   open todos in a **quickfix** list
-   open todos in [Trouble](https://github.com/folke/trouble.nvim)
-   search todos with [Telescope](https://github.com/nvim-telescope/telescope.nvim)

## ⚡️ Requirements

[](https://github.com/folke/todo-comments.nvim#%EF%B8%8F-requirements)

-   Neovim >= 0.8.0 (use the `neovim-pre-0.8.0` branch for older versions)
-   a [patched font](https://www.nerdfonts.com/) for the icons, or change them to simple ASCII characters
-   optional:
    -   [ripgrep](https://github.com/BurntSushi/ripgrep) and [plenary.nvim](https://github.com/nvim-lua/plenary.nvim) are used for searching.
    -   [Trouble](https://github.com/folke/trouble.nvim)
    -   [Telescope](https://github.com/nvim-telescope/telescope.nvim)

## 📦 Installation

[](https://github.com/folke/todo-comments.nvim#-installation)

Install the plugin with your preferred package manager:

### [lazy.nvim](https://github.com/folke/lazy.nvim)

[](https://github.com/folke/todo-comments.nvim#lazynvim)

{
  "folke/todo-comments.nvim",
  dependencies \= { "nvim-lua/plenary.nvim" },
  opts \= {
    \-- your configuration comes here
    \-- or leave it empty to use the default settings
    \-- refer to the configuration section below
  }
}

## ⚙️ Configuration

[](https://github.com/folke/todo-comments.nvim#%EF%B8%8F-configuration)

Todo comes with the following defaults:

{
  signs \= true, \-- show icons in the signs column
  sign\_priority \= 8, \-- sign priority
  \-- keywords recognized as todo comments
  keywords \= {
    FIX \= {
      icon \= " ", \-- icon used for the sign, and in search results
      color \= "error", \-- can be a hex color, or a named color (see below)
      alt \= { "FIXME", "BUG", "FIXIT", "ISSUE" }, \-- a set of other keywords that all map to this FIX keywords
      \-- signs = false, -- configure signs for some keywords individually
    },
    TODO \= { icon \= " ", color \= "info" },
    HACK \= { icon \= " ", color \= "warning" },
    WARN \= { icon \= " ", color \= "warning", alt \= { "WARNING", "XXX" } },
    PERF \= { icon \= " ", alt \= { "OPTIM", "PERFORMANCE", "OPTIMIZE" } },
    NOTE \= { icon \= " ", color \= "hint", alt \= { "INFO" } },
    TEST \= { icon \= "⏲ ", color \= "test", alt \= { "TESTING", "PASSED", "FAILED" } },
  },
  gui\_style \= {
    fg \= "NONE", \-- The gui style to use for the fg highlight group.
    bg \= "BOLD", \-- The gui style to use for the bg highlight group.
  },
  merge\_keywords \= true, \-- when true, custom keywords will be merged with the defaults
  \-- highlighting of the line containing the todo comment
  \-- \* before: highlights before the keyword (typically comment characters)
  \-- \* keyword: highlights of the keyword
  \-- \* after: highlights after the keyword (todo text)
  highlight \= {
    multiline \= true, \-- enable multine todo comments
    multiline\_pattern \= "^.", \-- lua pattern to match the next multiline from the start of the matched keyword
    multiline\_context \= 10, \-- extra lines that will be re-evaluated when changing a line
    before \= "", \-- "fg" or "bg" or empty
    keyword \= "wide", \-- "fg", "bg", "wide", "wide\_bg", "wide\_fg" or empty. (wide and wide\_bg is the same as bg, but will also highlight surrounding characters, wide\_fg acts accordingly but with fg)
    after \= "fg", \-- "fg" or "bg" or empty
    pattern \= \[\[.\*<(KEYWORDS)\\s\*:\]\], \-- pattern or table of patterns, used for highlighting (vim regex)
    comments\_only \= true, \-- uses treesitter to match keywords in comments only
    max\_line\_len \= 400, \-- ignore lines longer than this
    exclude \= {}, \-- list of file types to exclude highlighting
  },
  \-- list of named colors where we try to extract the guifg from the
  \-- list of highlight groups or use the hex color if hl not found as a fallback
  colors \= {
    error \= { "DiagnosticError", "ErrorMsg", "#DC2626" },
    warning \= { "DiagnosticWarn", "WarningMsg", "#FBBF24" },
    info \= { "DiagnosticInfo", "#2563EB" },
    hint \= { "DiagnosticHint", "#10B981" },
    default \= { "Identifier", "#7C3AED" },
    test \= { "Identifier", "#FF00FF" }
  },
  search \= {
    command \= "rg",
    args \= {
      "\--color=never",
      "\--no-heading",
      "\--with-filename",
      "\--line-number",
      "\--column",
    },
    \-- regex that will be used to match keywords.
    \-- don't replace the (KEYWORDS) placeholder
    pattern \= \[\[\\b(KEYWORDS):\]\], \-- ripgrep regex
    \-- pattern = \[\[\\b(KEYWORDS)\\b\]\], -- match without the extra colon. You'll likely get false positives
  },
}

### Jumping

[](https://github.com/folke/todo-comments.nvim#jumping)

Two methods are available to jump to the next/previous todo comment.

vim.keymap.set("n", "\]t", function()
  require("todo-comments").jump\_next()
end, { desc \= "Next todo comment" })

vim.keymap.set("n", "\[t", function()
  require("todo-comments").jump\_prev()
end, { desc \= "Previous todo comment" })

\-- You can also specify a list of valid jump keywords

vim.keymap.set("n", "\]t", function()
  require("todo-comments").jump\_next({keywords \= { "ERROR", "WARNING" }})
end, { desc \= "Next error/warning todo comment" })

## 🚀 Usage

[](https://github.com/folke/todo-comments.nvim#-usage)

**Todo** matches on any text that starts with one of your defined keywords (or alt) followed by a colon:

-   TODO: do something
-   FIX: this should be fixed
-   HACK: weird code warning

Todos are highlighted in all regular files.

Each of the commands below accept the following arguments:

-   `cwd` - Specify the directory to search for comments, like:

:TodoTelescope cwd\=~/projects/foobar

-   `keywords` - Comma separated list of keywords to filter results by. Keywords are case-sensitive.

:TodoTelescope keywords\=TODO,FIX

### 🔎 `:TodoQuickFix`

[](https://github.com/folke/todo-comments.nvim#-todoquickfix)

This uses the quickfix list to show all todos in your project.

[![image](https://user-images.githubusercontent.com/292349/118135332-bf9c2300-b3b7-11eb-9a40-1307feb27c44.png)](https://user-images.githubusercontent.com/292349/118135332-bf9c2300-b3b7-11eb-9a40-1307feb27c44.png)

### 🔎 `:TodoLocList`

[](https://github.com/folke/todo-comments.nvim#-todoloclist)

This uses the location list to show all todos in your project.

[![image](https://user-images.githubusercontent.com/292349/118135332-bf9c2300-b3b7-11eb-9a40-1307feb27c44.png)](https://user-images.githubusercontent.com/292349/118135332-bf9c2300-b3b7-11eb-9a40-1307feb27c44.png)

### 🚦 `:Trouble todo`

[](https://github.com/folke/todo-comments.nvim#-trouble-todo)

List all project todos in [trouble](https://github.com/folke/trouble.nvim)

Use Trouble's filtering: `Trouble todo filter = {tag = {TODO,FIX,FIXME}}`

> See screenshot at the top

### 🔭 `:TodoTelescope`

[](https://github.com/folke/todo-comments.nvim#-todotelescope)

Search through all project todos with Telescope

[![image](https://user-images.githubusercontent.com/292349/118135371-ccb91200-b3b7-11eb-9002-66af3b683cf0.png)](https://user-images.githubusercontent.com/292349/118135371-ccb91200-b3b7-11eb-9002-66af3b683cf0.png)