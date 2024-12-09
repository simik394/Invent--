---
page-title: "folke/trouble.nvim: 🚦 A pretty diagnostics, references, telescope results, quickfix and location list to help you solve all the trouble your code is causing."
url: https://github.com/folke/trouble.nvim
date: "2024-06-24 00:08:26"
tags: [a/sw/plugin, f/prod/homepage, c/, p/pwf]
about: ["[[NeoVim]]"]
aliases: 
- 
by: 
length: 21172
dir: 
---

## 🚦 Trouble

[](https://github.com/folke/trouble.nvim#-trouble)

A pretty list for showing diagnostics, references, telescope results, quickfix and location lists to help you solve all the trouble your code is causing.

[![image](https://private-user-images.githubusercontent.com/292349/317971850-481bc1f7-cb93-432d-8ab6-f54044334b96.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTkxODA3MjAsIm5iZiI6MTcxOTE4MDQyMCwicGF0aCI6Ii8yOTIzNDkvMzE3OTcxODUwLTQ4MWJjMWY3LWNiOTMtNDMyZC04YWI2LWY1NDA0NDMzNGI5Ni5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwNjIzJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDYyM1QyMjA3MDBaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1jODI3MGVhNTNiZDBmNWUyMzM3MmVlODFhYjYwNDEyYmEzZTFlZmUwNTRkZDAxNzA1OTVjZjgzM2YzYTJmYzA3JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.9FczXEwzwTc8LDSbPUXfbL1iugVweyHw5nO6tIXMh8k)](https://private-user-images.githubusercontent.com/292349/317971850-481bc1f7-cb93-432d-8ab6-f54044334b96.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTkxODA3MjAsIm5iZiI6MTcxOTE4MDQyMCwicGF0aCI6Ii8yOTIzNDkvMzE3OTcxODUwLTQ4MWJjMWY3LWNiOTMtNDMyZC04YWI2LWY1NDA0NDMzNGI5Ni5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwNjIzJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDYyM1QyMjA3MDBaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1jODI3MGVhNTNiZDBmNWUyMzM3MmVlODFhYjYwNDEyYmEzZTFlZmUwNTRkZDAxNzA1OTVjZjgzM2YzYTJmYzA3JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.9FczXEwzwTc8LDSbPUXfbL1iugVweyHw5nO6tIXMh8k)

## ✨ Features

[](https://github.com/folke/trouble.nvim#-features)

-   Diagnostics
-   LSP references
-   LSP implementations
-   LSP definitions
-   LSP type definitions
-   LSP Document Symbols
-   LSP Incoming/Outgoing calls
-   quickfix list
-   location list
-   [Telescope](https://github.com/nvim-telescope/telescope.nvim) search results
-   [fzf-lua](https://github.com/ibhagwan/fzf-lua) results

## 📰 What's new?

[](https://github.com/folke/trouble.nvim#-whats-new)

This is a full rewrite of the original **trouble.nvim**.

The new version is much more flexible and powerful, with a lot of new features and improvements:

-   multiple trouble windows at the same time
-   LSP document symbols
-   LSP incoming/outgoing calls
-   lots of options to configure trouble windows (floats or splits)
-   `focus` option to focus the trouble window when opened (or not)
-   `follow` option to follow the item under the cursor
-   `pinned` option to pin the buffer as the source for the opened trouble window
-   full tree views of anything
-   highly configurable views with custom formatters, filters, and sorters
-   show multiple sections in the same view
-   multi-line messages
-   prettier and configurable indent guides
-   tree view that follows the natural hierarchy of the items (like document symbols, or file structure)
-   expansive API and `Trouble` command
-   trouble `modes` to define custom views
-   statusline component (useful with document symbols)

## ⚡️ Requirements

[](https://github.com/folke/trouble.nvim#%EF%B8%8F-requirements)

-   Neovim >= 0.9.2
-   Neovim >= 0.10.0 **OR** the `markdown` and `markdown_inline` [nvim-treesitter](https://github.com/nvim-treesitter/nvim-treesitter) parsers
-   Properly configured Neovim LSP client
-   [nvim-web-devicons](https://github.com/nvim-tree/nvim-web-devicons) is optional to enable file icons
-   a theme with properly configured highlight groups for Neovim Diagnostics
-   a [patched font](https://www.nerdfonts.com/) for the default severity and fold icons

## 📦 Installation

[](https://github.com/folke/trouble.nvim#-installation)

Install the plugin with your preferred package manager:

### [lazy.nvim](https://github.com/folke/lazy.nvim)

[](https://github.com/folke/trouble.nvim#lazynvim)

{
  "folke/trouble.nvim",
  opts \= {}, \-- for default options, refer to the configuration section for custom setup.
  cmd \= "Trouble",
  keys \= {
    {
      "<leader>xx",
      "<cmd>Trouble diagnostics toggle<cr>",
      desc \= "Diagnostics (Trouble)",
    },
    {
      "<leader>xX",
      "<cmd>Trouble diagnostics toggle filter.buf=0<cr>",
      desc \= "Buffer Diagnostics (Trouble)",
    },
    {
      "<leader>cs",
      "<cmd>Trouble symbols toggle focus=false<cr>",
      desc \= "Symbols (Trouble)",
    },
    {
      "<leader>cl",
      "<cmd>Trouble lsp toggle focus=false win.position=right<cr>",
      desc \= "LSP Definitions / references / ... (Trouble)",
    },
    {
      "<leader>xL",
      "<cmd>Trouble loclist toggle<cr>",
      desc \= "Location List (Trouble)",
    },
    {
      "<leader>xQ",
      "<cmd>Trouble qflist toggle<cr>",
      desc \= "Quickfix List (Trouble)",
    },
  },
}

## ⚙️ Configuration

[](https://github.com/folke/trouble.nvim#%EF%B8%8F-configuration)

### Setup

[](https://github.com/folke/trouble.nvim#setup)

**Trouble** is highly configurable. Please refer to the default settings below.

Default Settings

\---@class trouble.Mode: trouble.Config,trouble.Section.spec
\---@field desc? string
\---@field sections? string\[\]

\---@class trouble.Config
\---@field mode? string
\---@field config? fun(opts:trouble.Config)
\---@field formatters? table<string,trouble.Formatter> custom formatters
\---@field filters? table<string, trouble.FilterFn> custom filters
\---@field sorters? table<string, trouble.SorterFn> custom sorters
local defaults \= {
  auto\_close \= false, \-- auto close when there are no items
  auto\_open \= false, \-- auto open when there are items
  auto\_preview \= true, \-- automatically open preview when on an item
  auto\_refresh \= true, \-- auto refresh when open
  auto\_jump \= false, \-- auto jump to the item when there's only one
  focus \= false, \-- Focus the window when opened
  restore \= true, \-- restores the last location in the list when opening
  follow \= true, \-- Follow the current item
  indent\_guides \= true, \-- show indent guides
  max\_items \= 200, \-- limit number of items that can be displayed per section
  multiline \= true, \-- render multi-line messages
  pinned \= false, \-- When pinned, the opened trouble window will be bound to the current buffer
  warn\_no\_results \= true, \-- show a warning when there are no results
  open\_no\_results \= false, \-- open the trouble window when there are no results
  \---@type trouble.Window.opts
  win \= {}, \-- window options for the results window. Can be a split or a floating window.
  \-- Window options for the preview window. Can be a split, floating window,
  \-- or \`main\` to show the preview in the main editor window.
  \---@type trouble.Window.opts
  preview \= {
    type \= "main",
    \-- when a buffer is not yet loaded, the preview window will be created
    \-- in a scratch buffer with only syntax highlighting enabled.
    \-- Set to false, if you want the preview to always be a real loaded buffer.
    scratch \= true,
  },
  \-- Throttle/Debounce settings. Should usually not be changed.
  \---@type table<string, number|{ms:number, debounce?:boolean}\>
  throttle \= {
    refresh \= 20, \-- fetches new data when needed
    update \= 10, \-- updates the window
    render \= 10, \-- renders the window
    follow \= 100, \-- follows the current item
    preview \= { ms \= 100, debounce \= true }, \-- shows the preview for the current item
  },
  \-- Key mappings can be set to the name of a builtin action,
  \-- or you can define your own custom action.
  \---@type table<string, trouble.Action.spec>
  keys \= {
    \["?"\] \= "help",
    r \= "refresh",
    R \= "toggle\_refresh",
    q \= "close",
    o \= "jump\_close",
    \["<esc>"\] \= "cancel",
    \["<cr>"\] \= "jump",
    \["<2-leftmouse>"\] \= "jump",
    \["<c-s>"\] \= "jump\_split",
    \["<c-v>"\] \= "jump\_vsplit",
    \-- go down to next item (accepts count)
    \-- j = "next",
    \["}"\] \= "next",
    \["\]\]"\] \= "next",
    \-- go up to prev item (accepts count)
    \-- k = "prev",
    \["{"\] \= "prev",
    \["\[\["\] \= "prev",
    dd \= "delete",
    d \= { action \= "delete", mode \= "v" },
    i \= "inspect",
    p \= "preview",
    P \= "toggle\_preview",
    zo \= "fold\_open",
    zO \= "fold\_open\_recursive",
    zc \= "fold\_close",
    zC \= "fold\_close\_recursive",
    za \= "fold\_toggle",
    zA \= "fold\_toggle\_recursive",
    zm \= "fold\_more",
    zM \= "fold\_close\_all",
    zr \= "fold\_reduce",
    zR \= "fold\_open\_all",
    zx \= "fold\_update",
    zX \= "fold\_update\_all",
    zn \= "fold\_disable",
    zN \= "fold\_enable",
    zi \= "fold\_toggle\_enable",
    gb \= { \-- example of a custom action that toggles the active view filter
      action \= function(view)
        view:filter({ buf \= 0 }, { toggle \= true })
      end,
      desc \= "Toggle Current Buffer Filter",
    },
    s \= { \-- example of a custom action that toggles the severity
      action \= function(view)
        local f \= view:get\_filter("severity")
        local severity \= ((f and f.filter.severity or 0) + 1) % 5
        view:filter({ severity \= severity }, {
          id \= "severity",
          template \= "{hl:Title}Filter:{hl} {severity}",
          del \= severity \== 0,
        })
      end,
      desc \= "Toggle Severity Filter",
    },
  },
  \---@type table<string, trouble.Mode>
  modes \= {
    \-- sources define their own modes, which you can use directly,
    \-- or override like in the example below
    lsp\_references \= {
      \-- some modes are configurable, see the source code for more details
      params \= {
        include\_declaration \= true,
      },
    },
    \-- The LSP base mode for:
    \-- \* lsp\_definitions, lsp\_references, lsp\_implementations
    \-- \* lsp\_type\_definitions, lsp\_declarations, lsp\_command
    lsp\_base \= {
      params \= {
        \-- don't include the current location in the results
        include\_current \= false,
      },
    },
    \-- more advanced example that extends the lsp\_document\_symbols
    symbols \= {
      desc \= "document symbols",
      mode \= "lsp\_document\_symbols",
      focus \= false,
      win \= { position \= "right" },
      filter \= {
        \-- remove Package since luals uses it for control flow structures
        \["not"\] \= { ft \= "lua", kind \= "Package" },
        any \= {
          \-- all symbol kinds for help / markdown files
          ft \= { "help", "markdown" },
          \-- default set of symbol kinds
          kind \= {
            "Class",
            "Constructor",
            "Enum",
            "Field",
            "Function",
            "Interface",
            "Method",
            "Module",
            "Namespace",
            "Package",
            "Property",
            "Struct",
            "Trait",
          },
        },
      },
    },
  },
  \-- stylua: ignore
  icons \= {
    \---@type trouble.Indent.symbols
    indent \= {
      top           \= "│ ",
      middle        \= "├╴",
      last          \= "└╴",
      \-- last          = "-╴",
      \-- last       = "╰╴", -- rounded
      fold\_open     \= " ",
      fold\_closed   \= " ",
      ws            \= "  ",
    },
    folder\_closed   \= " ",
    folder\_open     \= " ",
    kinds \= {
      Array         \= " ",
      Boolean       \= "󰨙 ",
      Class         \= " ",
      Constant      \= "󰏿 ",
      Constructor   \= " ",
      Enum          \= " ",
      EnumMember    \= " ",
      Event         \= " ",
      Field         \= " ",
      File          \= " ",
      Function      \= "󰊕 ",
      Interface     \= " ",
      Key           \= " ",
      Method        \= "󰊕 ",
      Module        \= " ",
      Namespace     \= "󰦮 ",
      Null          \= " ",
      Number        \= "󰎠 ",
      Object        \= " ",
      Operator      \= " ",
      Package       \= " ",
      Property      \= " ",
      String        \= " ",
      Struct        \= "󰆼 ",
      TypeParameter \= " ",
      Variable      \= "󰀫 ",
    },
  },
}

Make sure to check the [Examples](https://github.com/folke/trouble.nvim/blob/main/docs/examples.md)!

## 🚀 Usage

[](https://github.com/folke/trouble.nvim#-usage)

### Commands

[](https://github.com/folke/trouble.nvim#commands)

The **Trouble** command is a wrapper around the **Trouble** API. It can do anything the regular API can do.

-   `Trouble [mode] [action] [options]`

Some examples:

-   Toggle diagnostics for the current buffer and stay in the current window:
    -   `Trouble diagnostics toggle focus=false filter.buf=0`
-   Show document symbols on the right of the current window. Keep the document symbols in sync with the buffer you started the command in.
    -   `Trouble symbols toggle pinned=true results.win.relative=win results.win.position=right`
-   You can use **lua** code in the options for the `Trouble` command. The examples below all do the same thing.
    -   `Trouble diagnostics filter.severity=vim.diagnostic.severity.ERROR`
    -   `Trouble diagnostics filter.severity = vim.diagnostic.severity.ERROR`
    -   `Trouble diagnostics filter = { severity=vim.diagnostic.severity.ERROR }`
-   Merging of nested options, with or without quoting strings:
    -   `Trouble diagnostics results.win.type = split result.win.position=right`
    -   `Trouble diagnostics results.win = { type = split, position=right}`
    -   `Trouble diagnostics results.win = { type = "split", position='right'}`

Please refer to the API section for more information on the available actions and options.

Modes:

-   **diagnostics**: diagnostics
-   **fzf**: FzfLua results previously opened with `require('trouble.sources.fzf').open()`.
-   **fzf\_files**: FzfLua results previously opened with `require('trouble.sources.fzf').open()`.
-   **loclist**: Location List
-   **lsp**: LSP definitions, references, implementations, type definitions, and declarations
-   **lsp\_command**: command
-   **lsp\_declarations**: declarations
-   **lsp\_definitions**: definitions
-   **lsp\_document\_symbols**: document symbols
-   **lsp\_implementations**: implementations
-   **lsp\_incoming\_calls**: Incoming Calls
-   **lsp\_outgoing\_calls**: Outgoing Calls
-   **lsp\_references**: references
-   **lsp\_type\_definitions**: type definitions
-   **qflist**: Quickfix List
-   **quickfix**: Quickfix List
-   **symbols**: document symbols
-   **telescope**: Telescope results previously opened with `require('trouble.sources.telescope').open()`.
-   **telescope\_files**: Telescope results previously opened with `require('trouble.sources.telescope').open()`.

### Filters

[](https://github.com/folke/trouble.nvim#filters)

Please refer to the [filter docs](https://github.com/folke/trouble.nvim/blob/main/docs/filter.md) for more information examples on filters.

### API

[](https://github.com/folke/trouble.nvim#api)

You can use the following functions in your keybindings:

API

\-- Opens trouble with the given mode.
\-- If a view is already open with the same mode,
\-- it will be focused unless \`opts.focus = false\`.
\-- When a view is already open and \`opts.new = true\`,
\-- a new view will be created.
\---@param opts? trouble.Mode | { new?: boolean, refresh?: boolean } | string
\---@return trouble.View?
require("trouble").open(opts)

\-- Closes the last open view matching the filter.
\---@param opts? trouble.Mode|string
\---@return trouble.View?
require("trouble").close(opts)

\-- Toggle the view with the given mode.
\---@param opts? trouble.Mode|string
\---@return trouble.View?
require("trouble").toggle(opts)

\-- Returns true if there is an open view matching the mode.
\---@param opts? trouble.Mode|string
require("trouble").is\_open(opts)

\-- Refresh all open views. Normally this is done automatically,
\-- unless you disabled auto refresh.
\---@param opts? trouble.Mode|string
require("trouble").refresh(opts)

\-- Get all items from the active view for a given mode.
\---@param opts? trouble.Mode|string
require("trouble").get\_items(opts)

\-- Renders a trouble list as a statusline component.
\-- Check the docs for examples.
\---@param opts? trouble.Mode|string|{hl\_group?:string}
\---@return {get: (fun():string), has: (fun():boolean)}
require("trouble").statusline(opts)

\-- Closes the preview and goes to the main window.
\-- The Trouble window is not closed.
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").cancel(opts)

\-- Open the preview
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").delete(opts)

\-- filter
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").filter(opts)

\-- Go to the first item
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").first(opts)

\-- Focus the trouble window
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").focus(opts)

\-- Fold close 
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").fold\_close(opts)

\-- fold close all
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").fold\_close\_all(opts)

\-- Fold close recursive
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").fold\_close\_recursive(opts)

\-- fold disable
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").fold\_disable(opts)

\-- fold enable
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").fold\_enable(opts)

\-- fold more
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").fold\_more(opts)

\-- Fold open 
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").fold\_open(opts)

\-- fold open all
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").fold\_open\_all(opts)

\-- Fold open recursive
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").fold\_open\_recursive(opts)

\-- fold reduce
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").fold\_reduce(opts)

\-- Fold toggle 
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").fold\_toggle(opts)

\-- fold toggle enable
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").fold\_toggle\_enable(opts)

\-- Fold toggle recursive
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").fold\_toggle\_recursive(opts)

\-- fold update
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").fold\_update(opts)

\-- fold update all
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").fold\_update\_all(opts)

\-- Show the help
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").help(opts)

\-- Dump the item to the console
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").inspect(opts)

\-- Jump to the item if on an item, otherwise fold the node
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").jump(opts)

\-- Jump to the item and close the trouble window
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").jump\_close(opts)

\-- Jump to the item if on an item, otherwise do nothing
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").jump\_only(opts)

\-- Open the item in a split
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").jump\_split(opts)

\-- Open the item in a vsplit
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").jump\_vsplit(opts)

\-- Go to the last item
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").last(opts)

\-- Go to the next item
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").next(opts)

\-- Go to the previous item
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").prev(opts)

\-- Open the preview
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").preview(opts)

\-- Refresh the trouble source
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").refresh(opts)

\-- Toggle the preview
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").toggle\_preview(opts)

\-- Toggle the auto refresh
\---@param opts? trouble.Mode | { new? : boolean } | string
\---@return trouble.View
require("trouble").toggle\_refresh(opts)

### Telescope

[](https://github.com/folke/trouble.nvim#telescope)

You can easily open any search results in **Trouble**, by defining a custom action:

local actions \= require("telescope.actions")
local open\_with\_trouble \= require("trouble.sources.telescope").open

\-- Use this to add more results without clearing the trouble list
local add\_to\_trouble \= require("trouble.sources.telescope").add

local telescope \= require("telescope")

telescope.setup({
  defaults \= {
    mappings \= {
      i \= { \["<c-t>"\] \= open\_with\_trouble },
      n \= { \["<c-t>"\] \= open\_with\_trouble },
    },
  },
})

When you open telescope, you can now hit `<c-t>` to open the results in **Trouble**

### fzf-lua

[](https://github.com/folke/trouble.nvim#fzf-lua)

You can easily open any search results in **Trouble**, by defining a custom action:

local config \= require("fzf-lua.config")
local actions \= require("trouble.sources.fzf").actions
config.defaults.actions.files\["ctrl-t"\] \= actions.open

When you open fzf-lua, you can now hit `<c-t>` to open the results in **Trouble**

### Statusline Component

[](https://github.com/folke/trouble.nvim#statusline-component)

Example for [lualine.nvim](https://github.com/nvim-lualine/lualine.nvim):

{
  "nvim-lualine/lualine.nvim",
  opts \= function(\_, opts)
    local trouble \= require("trouble")
    local symbols \= trouble.statusline({
      mode \= "lsp\_document\_symbols",
      groups \= {},
      title \= false,
      filter \= { range \= true },
      format \= "{kind\_icon}{symbol.name:Normal}",
      \-- The following line is needed to fix the background color
      \-- Set it to the lualine section you want to use
      hl\_group \= "lualine\_c\_normal",
    })
    table.insert(opts.sections.lualine\_c, {
      symbols.get,
      cond \= symbols.has,
    })
  end,
}

## 🎨 Colors

[](https://github.com/folke/trouble.nvim#-colors)

The table below shows all the highlight groups defined for Trouble.

Highlight Groups

Highlight Group

Default Group

Description

**TroubleBasename**

***TroubleFilename***

**TroubleCode**

***Special***

**TroubleCount**

***TabLineSel***

**TroubleDirectory**

***Directory***

**TroubleFilename**

***Directory***

**TroubleIconArray**

***@punctuation.bracket***

**TroubleIconBoolean**

***@boolean***

**TroubleIconClass**

***@type***

**TroubleIconConstant**

***@constant***

**TroubleIconConstructor**

***@constructor***

**TroubleIconDirectory**

***Special***

**TroubleIconEnum**

***@lsp.type.enum***

**TroubleIconEnumMember**

***@lsp.type.enumMember***

**TroubleIconEvent**

***Special***

**TroubleIconField**

***@variable.member***

**TroubleIconFile**

***Normal***

**TroubleIconFunction**

***@function***

**TroubleIconInterface**

***@lsp.type.interface***

**TroubleIconKey**

***@lsp.type.keyword***

**TroubleIconMethod**

***@function.method***

**TroubleIconModule**

***@module***

**TroubleIconNamespace**

***@module***

**TroubleIconNull**

***@constant.builtin***

**TroubleIconNumber**

***@number***

**TroubleIconObject**

***@constant***

**TroubleIconOperator**

***@operator***

**TroubleIconPackage**

***@module***

**TroubleIconProperty**

***@property***

**TroubleIconString**

***@string***

**TroubleIconStruct**

***@lsp.type.struct***

**TroubleIconTypeParameter**

***@lsp.type.typeParameter***

**TroubleIconVariable**

***@variable***

**TroubleIndent**

***LineNr***

**TroubleIndentFoldClosed**

***CursorLineNr***

**TroubleIndentFoldOpen**

***TroubleIndent***

**TroubleIndentLast**

***TroubleIndent***

**TroubleIndentMiddle**

***TroubleIndent***

**TroubleIndentTop**

***TroubleIndent***

**TroubleIndentWs**

***TroubleIndent***

**TroubleNormal**

***NormalFloat***

**TroubleNormalNC**

***NormalFloat***

**TroublePos**

***LineNr***

**TroublePreview**

***Visual***

**TroubleSource**

***Comment***

**TroubleText**

***Normal***