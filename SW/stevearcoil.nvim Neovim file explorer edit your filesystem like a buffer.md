---
page-title: "stevearc/oil.nvim: Neovim file explorer: edit your filesystem like a buffer"
url: https://github.com/stevearc/oil.nvim/tree/master
date: "2024-06-21 03:53:45"
tags: [A/sw/plugin, F/prod/homepage, C/, P/pwf, a/do/file-mgmt]
about: ["[[NeoVim]]"]
aliases: 
- 
by: 
length: 11886
dir: 
---

## oil.nvim

[](https://github.com/stevearc/oil.nvim/tree/master#oilnvim)

A [vim-vinegar](https://github.com/tpope/vim-vinegar) like file explorer that lets you edit your filesystem like a normal Neovim buffer.

oil.demo.mp4

-   [Requirements](https://github.com/stevearc/oil.nvim/tree/master#requirements)
-   [Installation](https://github.com/stevearc/oil.nvim/tree/master#installation)
-   [Quick start](https://github.com/stevearc/oil.nvim/tree/master#quick-start)
-   [Options](https://github.com/stevearc/oil.nvim/tree/master#options)
-   [Adapters](https://github.com/stevearc/oil.nvim/tree/master#adapters)
-   [Recipes](https://github.com/stevearc/oil.nvim/tree/master#recipes)
-   [API](https://github.com/stevearc/oil.nvim/tree/master#api)
-   [FAQ](https://github.com/stevearc/oil.nvim/tree/master#faq)

## Requirements

[](https://github.com/stevearc/oil.nvim/tree/master#requirements)

-   Neovim 0.8+
-   (optional) [nvim-web-devicons](https://github.com/nvim-tree/nvim-web-devicons) for file icons

## Installation

[](https://github.com/stevearc/oil.nvim/tree/master#installation)

oil.nvim supports all the usual plugin managers

lazy.nvim

{
  'stevearc/oil.nvim',
  opts \= {},
  \-- Optional dependencies
  dependencies \= { "nvim-tree/nvim-web-devicons" },
}

Packer

require("packer").startup(function()
  use({
    "stevearc/oil.nvim",
    config \= function()
      require("oil").setup()
    end,
  })
end)

Paq

require("paq")({
  { "stevearc/oil.nvim" },
})

vim-plug dein

call dein#add('stevearc/oil.nvim')

Pathogen

git clone --depth=1 https://github.com/stevearc/oil.nvim.git ~/.vim/bundle/

Neovim native package

git clone --depth=1 https://github.com/stevearc/oil.nvim.git \\
  "${XDG\_DATA\_HOME:-$HOME/.local/share}"/nvim/site/pack/oil/start/oil.nvim

## Quick start

[](https://github.com/stevearc/oil.nvim/tree/master#quick-start)

Add the following to your init.lua

Then open a directory with `nvim .`. Use `<CR>` to open a file/directory, and `-` to go up a directory. Otherwise, just treat it like a normal buffer and make changes as you like. Remember to `:w` when you're done to actually perform the actions.

If you want to mimic the `vim-vinegar` method of navigating to the parent directory of a file, add this keymap:

vim.keymap.set("n", "\-", "<CMD>Oil<CR>", { desc \= "Open parent directory" })

You can open a directory with `:edit <path>` or `:Oil <path>`. To open oil in a floating window, do `:Oil --float <path>`.

## Options

[](https://github.com/stevearc/oil.nvim/tree/master#options)

require("oil").setup({
  \-- Oil will take over directory buffers (e.g. \`vim .\` or \`:e src/\`)
  \-- Set to false if you want some other plugin (e.g. netrw) to open when you edit directories.
  default\_file\_explorer \= true,
  \-- Id is automatically added at the beginning, and name at the end
  \-- See :help oil-columns
  columns \= {
    "icon",
    \-- "permissions",
    \-- "size",
    \-- "mtime",
  },
  \-- Buffer-local options to use for oil buffers
  buf\_options \= {
    buflisted \= false,
    bufhidden \= "hide",
  },
  \-- Window-local options to use for oil buffers
  win\_options \= {
    wrap \= false,
    signcolumn \= "no",
    cursorcolumn \= false,
    foldcolumn \= "0",
    spell \= false,
    list \= false,
    conceallevel \= 3,
    concealcursor \= "nvic",
  },
  \-- Send deleted files to the trash instead of permanently deleting them (:help oil-trash)
  delete\_to\_trash \= false,
  \-- Skip the confirmation popup for simple operations (:help oil.skip\_confirm\_for\_simple\_edits)
  skip\_confirm\_for\_simple\_edits \= false,
  \-- Selecting a new/moved/renamed file or directory will prompt you to save changes first
  \-- (:help prompt\_save\_on\_select\_new\_entry)
  prompt\_save\_on\_select\_new\_entry \= true,
  \-- Oil will automatically delete hidden buffers after this delay
  \-- You can set the delay to false to disable cleanup entirely
  \-- Note that the cleanup process only starts when none of the oil buffers are currently displayed
  cleanup\_delay\_ms \= 2000,
  lsp\_file\_methods \= {
    \-- Time to wait for LSP file operations to complete before skipping
    timeout\_ms \= 1000,
    \-- Set to true to autosave buffers that are updated with LSP willRenameFiles
    \-- Set to "unmodified" to only save unmodified buffers
    autosave\_changes \= false,
  },
  \-- Constrain the cursor to the editable parts of the oil buffer
  \-- Set to \`false\` to disable, or "name" to keep it on the file names
  constrain\_cursor \= "editable",
  \-- Set to true to watch the filesystem for changes and reload oil
  experimental\_watch\_for\_changes \= false,
  \-- Keymaps in oil buffer. Can be any value that \`vim.keymap.set\` accepts OR a table of keymap
  \-- options with a \`callback\` (e.g. { callback = function() ... end, desc = "", mode = "n" })
  \-- Additionally, if it is a string that matches "actions.<name>",
  \-- it will use the mapping at require("oil.actions").<name>
  \-- Set to \`false\` to remove a keymap
  \-- See :help oil-actions for a list of all available actions
  keymaps \= {
    \["g?"\] \= "actions.show\_help",
    \["<CR>"\] \= "actions.select",
    \["<C-s>"\] \= { "actions.select", opts \= { vertical \= true }, desc \= "Open the entry in a vertical split" },
    \["<C-h>"\] \= { "actions.select", opts \= { horizontal \= true }, desc \= "Open the entry in a horizontal split" },
    \["<C-t>"\] \= { "actions.select", opts \= { tab \= true }, desc \= "Open the entry in new tab" },
    \["<C-p>"\] \= "actions.preview",
    \["<C-c>"\] \= "actions.close",
    \["<C-l>"\] \= "actions.refresh",
    \["\-"\] \= "actions.parent",
    \["\_"\] \= "actions.open\_cwd",
    \["\`"\] \= "actions.cd",
    \["~"\] \= { "actions.cd", opts \= { scope \= "tab" }, desc \= ":tcd to the current oil directory" },
    \["gs"\] \= "actions.change\_sort",
    \["gx"\] \= "actions.open\_external",
    \["g."\] \= "actions.toggle\_hidden",
    \["g\\\\"\] \= "actions.toggle\_trash",
  },
  \-- Set to false to disable all of the above keymaps
  use\_default\_keymaps \= true,
  view\_options \= {
    \-- Show files and directories that start with "."
    show\_hidden \= false,
    \-- This function defines what is considered a "hidden" file
    is\_hidden\_file \= function(name, bufnr)
      return vim.startswith(name, ".")
    end,
    \-- This function defines what will never be shown, even when \`show\_hidden\` is set
    is\_always\_hidden \= function(name, bufnr)
      return false
    end,
    \-- Sort file names in a more intuitive order for humans. Is less performant,
    \-- so you may want to set to false if you work with large directories.
    natural\_order \= true,
    sort \= {
      \-- sort order can be "asc" or "desc"
      \-- see :help oil-columns to see which columns are sortable
      { "type", "asc" },
      { "name", "asc" },
    },
  },
  \-- Extra arguments to pass to SCP when moving/copying files over SSH
  extra\_scp\_args \= {},
  \-- EXPERIMENTAL support for performing file operations with git
  git \= {
    \-- Return true to automatically git add/mv/rm files
    add \= function(path)
      return false
    end,
    mv \= function(src\_path, dest\_path)
      return false
    end,
    rm \= function(path)
      return false
    end,
  },
  \-- Configuration for the floating window in oil.open\_float
  float \= {
    \-- Padding around the floating window
    padding \= 2,
    max\_width \= 0,
    max\_height \= 0,
    border \= "rounded",
    win\_options \= {
      winblend \= 0,
    },
    \-- preview\_split: Split direction: "auto", "left", "right", "above", "below".
    preview\_split \= "auto",
    \-- This is the config that will be passed to nvim\_open\_win.
    \-- Change values here to customize the layout
    override \= function(conf)
      return conf
    end,
  },
  \-- Configuration for the actions floating preview window
  preview \= {
    \-- Width dimensions can be integers or a float between 0 and 1 (e.g. 0.4 for 40%)
    \-- min\_width and max\_width can be a single value or a list of mixed integer/float types.
    \-- max\_width = {100, 0.8} means "the lesser of 100 columns or 80% of total"
    max\_width \= 0.9,
    \-- min\_width = {40, 0.4} means "the greater of 40 columns or 40% of total"
    min\_width \= { 40, 0.4 },
    \-- optionally define an integer/float for the exact width of the preview window
    width \= nil,
    \-- Height dimensions can be integers or a float between 0 and 1 (e.g. 0.4 for 40%)
    \-- min\_height and max\_height can be a single value or a list of mixed integer/float types.
    \-- max\_height = {80, 0.9} means "the lesser of 80 columns or 90% of total"
    max\_height \= 0.9,
    \-- min\_height = {5, 0.1} means "the greater of 5 columns or 10% of total"
    min\_height \= { 5, 0.1 },
    \-- optionally define an integer/float for the exact height of the preview window
    height \= nil,
    border \= "rounded",
    win\_options \= {
      winblend \= 0,
    },
    \-- Whether the preview window is automatically updated when the cursor is moved
    update\_on\_cursor\_moved \= true,
  },
  \-- Configuration for the floating progress window
  progress \= {
    max\_width \= 0.9,
    min\_width \= { 40, 0.4 },
    width \= nil,
    max\_height \= { 10, 0.9 },
    min\_height \= { 5, 0.1 },
    height \= nil,
    border \= "rounded",
    minimized\_border \= "none",
    win\_options \= {
      winblend \= 0,
    },
  },
  \-- Configuration for the floating SSH window
  ssh \= {
    border \= "rounded",
  },
  \-- Configuration for the floating keymaps help window
  keymaps\_help \= {
    border \= "rounded",
  },
})

## Adapters

[](https://github.com/stevearc/oil.nvim/tree/master#adapters)

Oil does all of its filesystem interaction through an *adapter* abstraction. In practice, this means that oil can be used to view and modify files in more places than just the local filesystem, so long as the destination has an adapter implementation.

Note that file operations work *across adapters*. This means that you can use oil to copy files to/from a remote server using the ssh adapter just as easily as you can copy files from one directory to another on your local machine.

### SSH

[](https://github.com/stevearc/oil.nvim/tree/master#ssh)

This adapter allows you to browse files over ssh, much like netrw. To use it, simply open a buffer using the following name template:

```
nvim oil-ssh://[username@]hostname[:port]/[path]
```

This may look familiar. In fact, this is the same url format that netrw uses.

Note that at the moment the ssh adapter does not support Windows machines, and it requires the server to have a `/bin/sh` binary as well as standard unix commands (`ls`, `rm`, `mv`, `mkdir`, `chmod`, `cp`, `touch`, `ln`, `echo`).

## Recipes

[](https://github.com/stevearc/oil.nvim/tree/master#recipes)

-   [Toggle file detail view](https://github.com/stevearc/oil.nvim/blob/master/doc/recipes.md#toggle-file-detail-view)
-   [Hide gitignored files](https://github.com/stevearc/oil.nvim/blob/master/doc/recipes.md#hide-gitignored-files)

## API

[](https://github.com/stevearc/oil.nvim/tree/master#api)

-   [get\_entry\_on\_line(bufnr, lnum)](https://github.com/stevearc/oil.nvim/blob/master/doc/api.md#get_entry_on_linebufnr-lnum)
-   [get\_cursor\_entry()](https://github.com/stevearc/oil.nvim/blob/master/doc/api.md#get_cursor_entry)
-   [discard\_all\_changes()](https://github.com/stevearc/oil.nvim/blob/master/doc/api.md#discard_all_changes)
-   [set\_columns(cols)](https://github.com/stevearc/oil.nvim/blob/master/doc/api.md#set_columnscols)
-   [set\_sort(sort)](https://github.com/stevearc/oil.nvim/blob/master/doc/api.md#set_sortsort)
-   [set\_is\_hidden\_file(is\_hidden\_file)](https://github.com/stevearc/oil.nvim/blob/master/doc/api.md#set_is_hidden_fileis_hidden_file)
-   [toggle\_hidden()](https://github.com/stevearc/oil.nvim/blob/master/doc/api.md#toggle_hidden)
-   [get\_current\_dir()](https://github.com/stevearc/oil.nvim/blob/master/doc/api.md#get_current_dir)
-   [open\_float(dir)](https://github.com/stevearc/oil.nvim/blob/master/doc/api.md#open_floatdir)
-   [toggle\_float(dir)](https://github.com/stevearc/oil.nvim/blob/master/doc/api.md#toggle_floatdir)
-   [open(dir)](https://github.com/stevearc/oil.nvim/blob/master/doc/api.md#opendir)
-   [close()](https://github.com/stevearc/oil.nvim/blob/master/doc/api.md#close)
-   [open\_preview(opts)](https://github.com/stevearc/oil.nvim/blob/master/doc/api.md#open_previewopts)
-   [select(opts, callback)](https://github.com/stevearc/oil.nvim/blob/master/doc/api.md#selectopts-callback)
-   [save(opts, cb)](https://github.com/stevearc/oil.nvim/blob/master/doc/api.md#saveopts-cb)
-   [setup(opts)](https://github.com/stevearc/oil.nvim/blob/master/doc/api.md#setupopts)

## FAQ

[](https://github.com/stevearc/oil.nvim/tree/master#faq)

**Q: Why "oil"**?

**A:** From the [vim-vinegar](https://github.com/tpope/vim-vinegar) README, a quote by Drew Neil:

> Split windows and the project drawer go together like oil and vinegar

Vinegar was taken. Let's be oil. Plus, I think it's pretty slick ;)

**Q: Why would I want to use oil vs any other plugin?**

**A:**

-   You like to use a netrw-like view to browse directories (as opposed to a file tree)
-   AND you want to be able to edit your filesystem like a buffer
-   AND you want to perform cross-directory actions. AFAIK there is no other plugin that does this. (update: [mini.files](https://github.com/echasnovski/mini.nvim/blob/main/readmes/mini-files.md) also offers this functionality)

If you don't need those features specifically, check out the alternatives listed below

**Q: Why write another plugin yourself instead of adding functionality to one that already exists**?

**A:** Because I am a *maniac control freak*.

**Q: Can oil display files as a tree view**?

**A:** No. A tree view would require a completely different methodology, necessitating a complete rewrite. I don't use tree views, so I will leave this as a plugin for someone else to write.

**Q: What are some alternatives?**

**A:**

-   [mini.files](https://github.com/echasnovski/mini.nvim/blob/main/readmes/mini-files.md): A newer plugin that also supports cross-directory filesystem-as-buffer edits. It utilizes a unique column view.
-   [vim-vinegar](https://github.com/tpope/vim-vinegar): The granddaddy. This made me fall in love with single-directory file browsing. I stopped using it when I encountered netrw bugs and performance issues.
-   [defx.nvim](https://github.com/Shougo/defx.nvim): What I switched to after vim-vinegar. Much more flexible and performant, but requires python and the API is a little hard to work with.
-   [dirbuf.nvim](https://github.com/elihunter173/dirbuf.nvim): The first plugin I encountered that let you edit the filesystem like a buffer. Never used it because it [can't do cross-directory edits](https://github.com/elihunter173/dirbuf.nvim/issues/7).
-   [lir.nvim](https://github.com/tamago324/lir.nvim): What I used prior to writing this plugin. Similar to vim-vinegar, but with better Neovim integration (floating windows, lua API).
-   [vim-dirvish](https://github.com/justinmk/vim-dirvish): Never personally used, but well-established, stable, simple directory browser.
-   [vidir](https://github.com/trapd00r/vidir): Never personally used, but might be the first plugin to come up with the idea of editing a directory like a buffer.

There's also file trees like [neo-tree](https://github.com/nvim-neo-tree/neo-tree.nvim) and [nvim-tree](https://github.com/nvim-tree/nvim-tree.lua), but they're really a different category entirely.