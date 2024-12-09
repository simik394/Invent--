---
page-title: "epwalsh/obsidian.nvim: Obsidian 🤝 Neovim"
url: https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#configuration-options
date: "2024-08-16 23:26:32"
tags: [a/sw/plugin, f/prod/homepage, c/, p/pwf]
about: ["[[NeoVim]]","[[Obsidian]]"]
aliases: 
- 
by: 
length: 30077
dir: 
---

## obsidian.nvim

[](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#obsidiannvim)

[![Latest release](https://camo.githubusercontent.com/511694a9d70853ebf33e42007e2a670eb25c1a046906a554b8948bb6bab01192/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f762f72656c656173652f657077616c73682f6f6273696469616e2e6e76696d3f7374796c653d666f722d7468652d6261646765266c6f676f3d7374617273686970266c6f676f436f6c6f723d443945304545266c6162656c436f6c6f723d3330324434312626636f6c6f723d64396233666626696e636c7564655f70726572656c6561736526736f72743d73656d766572)](https://github.com/epwalsh/obsidian.nvim/releases/latest) [![Last commit](https://camo.githubusercontent.com/3218277deeaaf4ae9be62c0657afa1c80ce9f26db3777e9ec885707a965ce775/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6c6173742d636f6d6d69742f657077616c73682f6f6273696469616e2e6e76696d3f7374796c653d666f722d7468652d6261646765266c6f676f3d676974687562266c6f676f436f6c6f723d443945304545266c6162656c436f6c6f723d33303244343126636f6c6f723d396664663966)](https://github.com/epwalsh/obsidian.nvim/pulse) [![Latest Neovim](https://camo.githubusercontent.com/da67299430a6faa9c0f8d10fab1495493da4471af5229c3c21dd00824b4155de/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f762f72656c656173652f6e656f76696d2f6e656f76696d3f7374796c653d666f722d7468652d6261646765266c6f676f3d6e656f76696d266c6f676f436f6c6f723d443945304545266c6162656c3d4e656f76696d266c6162656c436f6c6f723d33303244343126636f6c6f723d39396436666626736f72743d73656d766572)](https://github.com/neovim/neovim/releases/latest) [![Made with Lua](https://camo.githubusercontent.com/d7cbdb499467896c911905da3f0f8b1c58ff1c6029b73c0b4b300ec2310e0b9f/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4275696c74253230776974682532304c75612d677265793f7374796c653d666f722d7468652d6261646765266c6f676f3d6c7561266c6f676f436f6c6f723d443945304545266c6162656c3d4c7561266c6162656c436f6c6f723d33303244343126636f6c6f723d623362336666)](http://www.lua.org/) [![Buy me a coffee](https://camo.githubusercontent.com/fe0faf02f65b92cc0c63215eb3bb3a5d91546e589905fc8078b270a5fb61fd4b/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4275792532306d6525323061253230636f666665652d677265793f7374796c653d666f722d7468652d6261646765266c6f676f3d6275796d6561636f66666565266c6f676f436f6c6f723d443945304545266c6162656c3d53706f6e736f72266c6162656c436f6c6f723d33303244343126636f6c6f723d666666663939)](https://www.buymeacoffee.com/epwalsh)

---

A Neovim plugin for writing and navigating [Obsidian](https://obsidian.md/) vaults, written in Lua.

Built for people who love the concept of Obsidian -- a simple, markdown-based notes app -- but love Neovim too much to stand typing characters into anything else.

If you're new to Obsidian I highly recommend watching [this excellent YouTube video](https://youtu.be/5ht8NYkU9wQ?si=8nbnNsRVnw0xfX2S) for a great overview.

*Keep in mind this plugin is not meant to replace Obsidian, but to complement it.* The Obsidian app is very powerful in its own way; it comes with a mobile app and has a lot of functionality that's not feasible to implement in Neovim, such as the graph explorer view. That said, this plugin stands on its own as well. You don't necessarily need to use it alongside the Obsidian app.

## Table of contents

[](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#table-of-contents)

-   👉 [Features](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#features)
    -   [Commands](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#commands)
    -   [Demo](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#demo)
-   ⚙️ [Setup](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#setup)
    -   [System requirements](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#system-requirements)
    -   [Install and configure](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#install-and-configure)
    -   [Plugin dependencies](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#plugin-dependencies)
    -   [Configuration options](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#configuration-options)
    -   [Notes on configuration](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#notes-on-configuration)
    -   [Using templates](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#using-templates)
    -   [Usage outside of a workspace or vault](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#usage-outside-of-a-workspace-or-vault)
-   ➕ [Contributing](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#contributing)

## Features

[](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#features)

▶️ **Completion:** Ultra-fast, asynchronous autocompletion for note references and tags via [nvim-cmp](https://github.com/hrsh7th/nvim-cmp) (triggered by typing `[[` for wiki links, `[` for markdown links, or `#` for tags), powered by [`ripgrep`](https://github.com/BurntSushi/ripgrep).

[![See this screenshot](https://private-user-images.githubusercontent.com/8812459/301296514-90d5f218-06cd-4ebb-b00b-b59c2f5c3cc1.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MjM4NDM4NTMsIm5iZiI6MTcyMzg0MzU1MywicGF0aCI6Ii84ODEyNDU5LzMwMTI5NjUxNC05MGQ1ZjIxOC0wNmNkLTRlYmItYjAwYi1iNTljMmY1YzNjYzEucG5nP1gtQW16LUFsZ29yaXRobT1BV1M0LUhNQUMtU0hBMjU2JlgtQW16LUNyZWRlbnRpYWw9QUtJQVZDT0RZTFNBNTNQUUs0WkElMkYyMDI0MDgxNiUyRnVzLWVhc3QtMSUyRnMzJTJGYXdzNF9yZXF1ZXN0JlgtQW16LURhdGU9MjAyNDA4MTZUMjEyNTUzWiZYLUFtei1FeHBpcmVzPTMwMCZYLUFtei1TaWduYXR1cmU9MzlkNGVjOWExNzNhYzk0MjAxZjkzODJmMmFjMjk5ZjM5YmJlMzVmMjdhNTQzOGFkMTAzOWJjY2FiYjJjMmFiNyZYLUFtei1TaWduZWRIZWFkZXJzPWhvc3QmYWN0b3JfaWQ9MCZrZXlfaWQ9MCZyZXBvX2lkPTAifQ.Q4l8O1YHz95WDIDl7JxGtwhqsmjb8LeC1WV0h2lq6ho)](https://github.com/epwalsh/obsidian.nvim/assets/8812459/90d5f218-06cd-4ebb-b00b-b59c2f5c3cc1)

🏃 **Navigation:** Navigate throughout your vault by typing `gf` on any link to another note.

📷 **Images:** Paste images into notes.

💅 **Syntax:** Additional markdown syntax highlighting, concealing, and extmarks for references, tags, and check-boxes.

[![See this screenshot](https://private-user-images.githubusercontent.com/8812459/301295230-e74f5267-21b5-49bc-a3bb-3b9db5fa6687.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MjM4NDM4NTMsIm5iZiI6MTcyMzg0MzU1MywicGF0aCI6Ii84ODEyNDU5LzMwMTI5NTIzMC1lNzRmNTI2Ny0yMWI1LTQ5YmMtYTNiYi0zYjlkYjVmYTY2ODcucG5nP1gtQW16LUFsZ29yaXRobT1BV1M0LUhNQUMtU0hBMjU2JlgtQW16LUNyZWRlbnRpYWw9QUtJQVZDT0RZTFNBNTNQUUs0WkElMkYyMDI0MDgxNiUyRnVzLWVhc3QtMSUyRnMzJTJGYXdzNF9yZXF1ZXN0JlgtQW16LURhdGU9MjAyNDA4MTZUMjEyNTUzWiZYLUFtei1FeHBpcmVzPTMwMCZYLUFtei1TaWduYXR1cmU9NzAxMGFmODkzMGM4MzRhNWFlYzQ2MWRhYTg5M2M3NTc0OWY2OGNhZmNmM2Y0NjM5MDdhZjk5NTkyNzk5ZjUwZSZYLUFtei1TaWduZWRIZWFkZXJzPWhvc3QmYWN0b3JfaWQ9MCZrZXlfaWQ9MCZyZXBvX2lkPTAifQ.QtGM1Uf-Qq7fbucduvzWXBvouJQ1ZPB6pdb5fmTKWmo)](https://github.com/epwalsh/obsidian.nvim/assets/8812459/e74f5267-21b5-49bc-a3bb-3b9db5fa6687)

### Commands

[](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#commands)

-   `:ObsidianOpen [QUERY]` to open a note in the Obsidian app. This command has one optional argument: a query used to resolve the note to open by ID, path, or alias. If not given, the note corresponding to the current buffer is opened.
    
-   `:ObsidianNew [TITLE]` to create a new note. This command has one optional argument: the title of the new note.
    
-   `:ObsidianQuickSwitch` to quickly switch to (or open) another note in your vault, searching by its name using [ripgrep](https://github.com/BurntSushi/ripgrep) with your preferred picker (see [plugin dependencies](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#plugin-dependencies) below).
    
-   `:ObsidianFollowLink [vsplit|hsplit]` to follow a note reference under the cursor, optionally opening it in a vertical or horizontal split.
    
-   `:ObsidianBacklinks` for getting a picker list of references to the current buffer.
    
-   `:ObsidianTags [TAG ...]` for getting a picker list of all occurrences of the given tags.
    
-   `:ObsidianToday [OFFSET]` to open/create a new daily note. This command also takes an optional offset in days, e.g. use `:ObsidianToday -1` to go to yesterday's note. Unlike `:ObsidianYesterday` and `:ObsidianTomorrow` this command does not differentiate between weekdays and weekends.
    
-   `:ObsidianYesterday` to open/create the daily note for the previous working day.
    
-   `:ObsidianTomorrow` to open/create the daily note for the next working day.
    
-   `:ObsidianDailies [OFFSET ...]` to open a picker list of daily notes. For example, `:ObsidianDailies -2 1` to list daily notes from 2 days ago until tomorrow.
    
-   `:ObsidianTemplate [NAME]` to insert a template from the templates folder, selecting from a list using your preferred picker. See ["using templates"](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#using-templates) for more information.
    
-   `:ObsidianSearch [QUERY]` to search for (or create) notes in your vault using `ripgrep` with your preferred picker.
    
-   `:ObsidianLink [QUERY]` to link an inline visual selection of text to a note. This command has one optional argument: a query that will be used to resolve the note by ID, path, or alias. If not given, the selected text will be used as the query.
    
-   `:ObsidianLinkNew [TITLE]` to create a new note and link it to an inline visual selection of text. This command has one optional argument: the title of the new note. If not given, the selected text will be used as the title.
    
-   `:ObsidianLinks` to collect all links within the current buffer into a picker window.
    
-   `:ObsidianExtractNote [TITLE]` to extract the visually selected text into a new note and link to it.
    
-   `:ObsidianWorkspace [NAME]` to switch to another workspace.
    
-   `:ObsidianPasteImg [IMGNAME]` to paste an image from the clipboard into the note at the cursor position by saving it to the vault and adding a markdown image link. You can configure the default folder to save images to with the `attachments.img_folder` option.
    
-   `:ObsidianRename [NEWNAME] [--dry-run]` to rename the note of the current buffer or reference under the cursor, updating all backlinks across the vault. Since this command is still relatively new and could potentially write a lot of changes to your vault, I highly recommend committing the current state of your vault (if you're using version control) before running it, or doing a dry-run first by appending "--dry-run" to the command, e.g. `:ObsidianRename new-id --dry-run`.
    
-   `:ObsidianToggleCheckbox` to cycle through checkbox options.
    
-   `:ObsidianNewFromTemplate [TITLE]` to create a new note from a template in the templates folder. Selecting from a list using your preferred picker. This command has one optional argument: the title of the new note.
    
-   `:ObsidianTOC` to load the table of contents of the current note into a picker list.
    

### Demo

[](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#demo)

[![2024-01-31 14 22 52](https://private-user-images.githubusercontent.com/8812459/301327007-2986e1d2-13e8-40e2-9c9e-75691a3b662e.gif?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MjM4NDM4NTMsIm5iZiI6MTcyMzg0MzU1MywicGF0aCI6Ii84ODEyNDU5LzMwMTMyNzAwNy0yOTg2ZTFkMi0xM2U4LTQwZTItOWM5ZS03NTY5MWEzYjY2MmUuZ2lmP1gtQW16LUFsZ29yaXRobT1BV1M0LUhNQUMtU0hBMjU2JlgtQW16LUNyZWRlbnRpYWw9QUtJQVZDT0RZTFNBNTNQUUs0WkElMkYyMDI0MDgxNiUyRnVzLWVhc3QtMSUyRnMzJTJGYXdzNF9yZXF1ZXN0JlgtQW16LURhdGU9MjAyNDA4MTZUMjEyNTUzWiZYLUFtei1FeHBpcmVzPTMwMCZYLUFtei1TaWduYXR1cmU9OGUyNTc5NDc0Njk0OWYwY2Y3OTZkMmY0YjM3NzYxY2EwODJjOGUxOTg2NmI0NjQ4MzdmMTEwMzQwMzU3MTZmNCZYLUFtei1TaWduZWRIZWFkZXJzPWhvc3QmYWN0b3JfaWQ9MCZrZXlfaWQ9MCZyZXBvX2lkPTAifQ.QpCbVl_hfKvxU4t5-qtL76Cik6cuZhMks0n7DXy1s68)](https://github.com/epwalsh/obsidian.nvim/assets/8812459/2986e1d2-13e8-40e2-9c9e-75691a3b662e)

## Setup

[](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#setup)

### System requirements

[](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#system-requirements)

-   NeoVim >= 0.8.0 (this plugin uses `vim.fs` which was only added in 0.8).
-   If you want completion and search features (recommended) you'll need [ripgrep](https://github.com/BurntSushi/ripgrep) to be installed and on your `$PATH`. See [ripgrep#installation](https://github.com/BurntSushi/ripgrep) for install options.

Specific operating systems also require additional dependencies in order to use all of obsidian.nvim's functionality:

-   **Windows WSL** users need [`wsl-open`](https://gitlab.com/4U6U57/wsl-open) for the `:ObsidianOpen` command.
-   **MacOS** users need [`pngpaste`](https://github.com/jcsalterego/pngpaste) (`brew install pngpaste`) for the `:ObsidianPasteImg` command.
-   **Linux** users need xclip (X11) or wl-clipboard (Wayland) for the `:ObsidianPasteImg` command.

Search functionality (e.g. via the `:ObsidianSearch` and `:ObsidianQuickSwitch` commands) also requires a picker such [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim) (see [plugin dependencies](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#plugin-dependencies) below).

### Install and configure

[](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#install-and-configure)

To configure obsidian.nvim you just need to call `require("obsidian").setup({ ... })` with the desired options. Here are some examples using different plugin managers. The full set of [plugin dependencies](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#plugin-dependencies) and [configuration options](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#configuration-options) are listed below.

> ⚠️ WARNING: if you install from the latest release (recommended for stability) instead of `main`, be aware that the README on `main` may reference features that haven't been released yet. For that reason I recommend viewing the README on the tag for the [latest release](https://github.com/epwalsh/obsidian.nvim/releases) instead of `main`.

#### Using [`lazy.nvim`](https://github.com/folke/lazy.nvim)

[](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#using-lazynvim)

return {
  "epwalsh/obsidian.nvim",
  version \= "\*",  \-- recommended, use latest release instead of latest commit
  lazy \= true,
  ft \= "markdown",
  \-- Replace the above line with this if you only want to load obsidian.nvim for markdown files in your vault:
  \-- event = {
  \--   -- If you want to use the home shortcut '~' here you need to call 'vim.fn.expand'.
  \--   -- E.g. "BufReadPre " .. vim.fn.expand "~" .. "/my-vault/\*.md"
  \--   -- refer to \`:h file-pattern\` for more examples
  \--   "BufReadPre path/to/my-vault/\*.md",
  \--   "BufNewFile path/to/my-vault/\*.md",
  \-- },
  dependencies \= {
    \-- Required.
    "nvim-lua/plenary.nvim",

    \-- see below for full list of optional dependencies 👇
  },
  opts \= {
    workspaces \= {
      {
        name \= "personal",
        path \= "~/vaults/personal",
      },
      {
        name \= "work",
        path \= "~/vaults/work",
      },
    },

    \-- see below for full list of options 👇
  },
}

#### Using [`packer.nvim`](https://github.com/wbthomason/packer.nvim)

[](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#using-packernvim)

use({
  "epwalsh/obsidian.nvim",
  tag \= "\*",  \-- recommended, use latest release instead of latest commit
  requires \= {
    \-- Required.
    "nvim-lua/plenary.nvim",

    \-- see below for full list of optional dependencies 👇
  },
  config \= function()
    require("obsidian").setup({
      workspaces \= {
        {
          name \= "personal",
          path \= "~/vaults/personal",
        },
        {
          name \= "work",
          path \= "~/vaults/work",
        },
      },

      \-- see below for full list of options 👇
    })
  end,
})

### Plugin dependencies

[](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#plugin-dependencies)

The only **required** plugin dependency is [plenary.nvim](https://github.com/nvim-lua/plenary.nvim), but there are a number of optional dependencies that enhance the obsidian.nvim experience.

**Completion:**

-   **\[recommended\]** [hrsh7th/nvim-cmp](https://github.com/hrsh7th/nvim-cmp): for completion of note references.

**Pickers:**

-   **\[recommended\]** [nvim-telescope/telescope.nvim](https://github.com/nvim-telescope/telescope.nvim): for search and quick-switch functionality.
-   [Mini.Pick](https://github.com/echasnovski/mini.pick) from the mini.nvim library: an alternative to telescope for search and quick-switch functionality.
-   [ibhagwan/fzf-lua](https://github.com/ibhagwan/fzf-lua): another alternative to telescope for search and quick-switch functionality.

**Syntax highlighting:**

-   **\[recommended\]** [nvim-treesitter](https://github.com/nvim-treesitter/nvim-treesitter): for base markdown syntax highlighting. See [syntax highlighting](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#syntax-highlighting) for more details.
-   [preservim/vim-markdown](https://github.com/preservim/vim-markdown): an alternative to nvim-treesitter for syntax highlighting (see [syntax highlighting](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#syntax-highlighting) for more details), plus other cool features.

**Miscellaneous:**

-   🆕 [pomo.nvim](https://github.com/epwalsh/pomo.nvim): for running lightweight [pomodoro](https://en.wikipedia.org/wiki/Pomodoro_Technique) timers.

If you choose to use any of these you should include them in the "dependencies" or "requires" field of the obsidian.nvim plugin spec for your package manager.

### Configuration options

[](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#configuration-options)

This is a complete list of all of the options that can be passed to `require("obsidian").setup()`. The settings below are *not necessarily the defaults, but represent reasonable default settings*. Please read each option carefully and customize it to your needs:

{
  \-- A list of workspace names, paths, and configuration overrides.
  \-- If you use the Obsidian app, the 'path' of a workspace should generally be
  \-- your vault root (where the \`.obsidian\` folder is located).
  \-- When obsidian.nvim is loaded by your plugin manager, it will automatically set
  \-- the workspace to the first workspace in the list whose \`path\` is a parent of the
  \-- current markdown file being edited.
  workspaces \= {
    {
      name \= "personal",
      path \= "~/vaults/personal",
    },
    {
      name \= "work",
      path \= "~/vaults/work",
      \-- Optional, override certain settings.
      overrides \= {
        notes\_subdir \= "notes",
      },
    },
  },

  \-- Alternatively - and for backwards compatibility - you can set 'dir' to a single path instead of
  \-- 'workspaces'. For example:
  \-- dir = "~/vaults/work",

  \-- Optional, if you keep notes in a specific subdirectory of your vault.
  notes\_subdir \= "notes",

  \-- Optional, set the log level for obsidian.nvim. This is an integer corresponding to one of the log
  \-- levels defined by "vim.log.levels.\*".
  log\_level \= vim.log.levels.INFO,

  daily\_notes \= {
    \-- Optional, if you keep daily notes in a separate directory.
    folder \= "notes/dailies",
    \-- Optional, if you want to change the date format for the ID of daily notes.
    date\_format \= "%Y-%m-%d",
    \-- Optional, if you want to change the date format of the default alias of daily notes.
    alias\_format \= "%B %-d, %Y",
    \-- Optional, default tags to add to each new daily note created.
    default\_tags \= { "daily-notes" },
    \-- Optional, if you want to automatically insert a template from your template directory like 'daily.md'
    template \= nil
  },

  \-- Optional, completion of wiki links, local markdown links, and tags using nvim-cmp.
  completion \= {
    \-- Set to false to disable completion.
    nvim\_cmp \= true,
    \-- Trigger completion at 2 chars.
    min\_chars \= 2,
  },

  \-- Optional, configure key mappings. These are the defaults. If you don't want to set any keymappings this
  \-- way then set 'mappings = {}'.
  mappings \= {
    \-- Overrides the 'gf' mapping to work on markdown/wiki links within your vault.
    \["gf"\] \= {
      action \= function()
        return require("obsidian").util.gf\_passthrough()
      end,
      opts \= { noremap \= false, expr \= true, buffer \= true },
    },
    \-- Toggle check-boxes.
    \["<leader>ch"\] \= {
      action \= function()
        return require("obsidian").util.toggle\_checkbox()
      end,
      opts \= { buffer \= true },
    },
    \-- Smart action depending on context, either follow link or toggle checkbox.
    \["<cr>"\] \= {
      action \= function()
        return require("obsidian").util.smart\_action()
      end,
      opts \= { buffer \= true, expr \= true },
    }
  },

  \-- Where to put new notes. Valid options are
  \--  \* "current\_dir" - put new notes in same directory as the current buffer.
  \--  \* "notes\_subdir" - put new notes in the default notes subdirectory.
  new\_notes\_location \= "notes\_subdir",

  \-- Optional, customize how note IDs are generated given an optional title.
  \---@param title string|?
  \---@return string
  note\_id\_func \= function(title)
    \-- Create note IDs in a Zettelkasten format with a timestamp and a suffix.
    \-- In this case a note with the title 'My new note' will be given an ID that looks
    \-- like '1657296016-my-new-note', and therefore the file name '1657296016-my-new-note.md'
    local suffix \= ""
    if title ~= nil then
      \-- If title is given, transform it into valid file name.
      suffix \= title:gsub(" ", "\-"):gsub("\[^A-Za-z0-9-\]", ""):lower()
    else
      \-- If title is nil, just add 4 random uppercase letters to the suffix.
      for \_ \= 1, 4 do
        suffix \= suffix .. string.char(math.random(65, 90))
      end
    end
    return tostring(os.time()) .. "\-" .. suffix
  end,

  \-- Optional, customize how note file names are generated given the ID, target directory, and title.
  \---@param spec { id: string, dir: obsidian.Path, title: string|? }
  \---@return string|obsidian.Path The full path to the new note.
  note\_path\_func \= function(spec)
    \-- This is equivalent to the default behavior.
    local path \= spec.dir / tostring(spec.id)
    return path:with\_suffix(".md")
  end,

  \-- Optional, customize how wiki links are formatted. You can set this to one of:
  \--  \* "use\_alias\_only", e.g. '\[\[Foo Bar\]\]'
  \--  \* "prepend\_note\_id", e.g. '\[\[foo-bar|Foo Bar\]\]'
  \--  \* "prepend\_note\_path", e.g. '\[\[foo-bar.md|Foo Bar\]\]'
  \--  \* "use\_path\_only", e.g. '\[\[foo-bar.md\]\]'
  \-- Or you can set it to a function that takes a table of options and returns a string, like this:
  wiki\_link\_func \= function(opts)
    return require("obsidian.util").wiki\_link\_id\_prefix(opts)
  end,

  \-- Optional, customize how markdown links are formatted.
  markdown\_link\_func \= function(opts)
    return require("obsidian.util").markdown\_link(opts)
  end,

  \-- Either 'wiki' or 'markdown'.
  preferred\_link\_style \= "wiki",

  \-- Optional, boolean or a function that takes a filename and returns a boolean.
  \-- \`true\` indicates that you don't want obsidian.nvim to manage frontmatter.
  disable\_frontmatter \= false,

  \-- Optional, alternatively you can customize the frontmatter data.
  \---@return table
  note\_frontmatter\_func \= function(note)
    \-- Add the title of the note as an alias.
    if note.title then
      note:add\_alias(note.title)
    end

    local out \= { id \= note.id, aliases \= note.aliases, tags \= note.tags }

    \-- \`note.metadata\` contains any manually added fields in the frontmatter.
    \-- So here we just make sure those fields are kept in the frontmatter.
    if note.metadata ~= nil and not vim.tbl\_isempty(note.metadata) then
      for k, v in pairs(note.metadata) do
        out\[k\] \= v
      end
    end

    return out
  end,

  \-- Optional, for templates (see below).
  templates \= {
    folder \= "templates",
    date\_format \= "%Y-%m-%d",
    time\_format \= "%H:%M",
    \-- A map for custom variables, the key should be the variable and the value a function
    substitutions \= {},
  },

  \-- Optional, by default when you use \`:ObsidianFollowLink\` on a link to an external
  \-- URL it will be ignored but you can customize this behavior here.
  \---@param url string
  follow\_url\_func \= function(url)
    \-- Open the URL in the default web browser.
    vim.fn.jobstart({"open", url})  \-- Mac OS
    \-- vim.fn.jobstart({"xdg-open", url})  -- linux
    \-- vim.cmd(':silent exec "!start ' .. url .. '"') -- Windows
    \-- vim.ui.open(url) -- need Neovim 0.10.0+
  end,

  \-- Optional, by default when you use \`:ObsidianFollowLink\` on a link to an image
  \-- file it will be ignored but you can customize this behavior here.
  \---@param img string
  follow\_img\_func \= function(img)
    vim.fn.jobstart { "qlmanage", "\-p", img }  \-- Mac OS quick look preview
    \-- vim.fn.jobstart({"xdg-open", url})  -- linux
    \-- vim.cmd(':silent exec "!start ' .. url .. '"') -- Windows
  end,

  \-- Optional, set to true if you use the Obsidian Advanced URI plugin.
  \-- https://github.com/Vinzent03/obsidian-advanced-uri
  use\_advanced\_uri \= false,

  \-- Optional, set to true to force ':ObsidianOpen' to bring the app to the foreground.
  open\_app\_foreground \= false,

  picker \= {
    \-- Set your preferred picker. Can be one of 'telescope.nvim', 'fzf-lua', or 'mini.pick'.
    name \= "telescope.nvim",
    \-- Optional, configure key mappings for the picker. These are the defaults.
    \-- Not all pickers support all mappings.
    note\_mappings \= {
      \-- Create a new note from your query.
      new \= "<C-x>",
      \-- Insert a link to the selected note.
      insert\_link \= "<C-l>",
    },
    tag\_mappings \= {
      \-- Add tag(s) to current note.
      tag\_note \= "<C-x>",
      \-- Insert a tag at the current location.
      insert\_tag \= "<C-l>",
    },
  },

  \-- Optional, sort search results by "path", "modified", "accessed", or "created".
  \-- The recommend value is "modified" and \`true\` for \`sort\_reversed\`, which means, for example,
  \-- that \`:ObsidianQuickSwitch\` will show the notes sorted by latest modified time
  sort\_by \= "modified",
  sort\_reversed \= true,

  \-- Set the maximum number of lines to read from notes on disk when performing certain searches.
  search\_max\_lines \= 1000,

  \-- Optional, determines how certain commands open notes. The valid options are:
  \-- 1. "current" (the default) - to always open in the current window
  \-- 2. "vsplit" - to open in a vertical split if there's not already a vertical split
  \-- 3. "hsplit" - to open in a horizontal split if there's not already a horizontal split
  open\_notes\_in \= "current",

  \-- Optional, define your own callbacks to further customize behavior.
  callbacks \= {
    \-- Runs at the end of \`require("obsidian").setup()\`.
    \---@param client obsidian.Client
    post\_setup \= function(client) end,

    \-- Runs anytime you enter the buffer for a note.
    \---@param client obsidian.Client
    \---@param note obsidian.Note
    enter\_note \= function(client, note) end,

    \-- Runs anytime you leave the buffer for a note.
    \---@param client obsidian.Client
    \---@param note obsidian.Note
    leave\_note \= function(client, note) end,

    \-- Runs right before writing the buffer for a note.
    \---@param client obsidian.Client
    \---@param note obsidian.Note
    pre\_write\_note \= function(client, note) end,

    \-- Runs anytime the workspace is set/changed.
    \---@param client obsidian.Client
    \---@param workspace obsidian.Workspace
    post\_set\_workspace \= function(client, workspace) end,
  },

  \-- Optional, configure additional syntax highlighting / extmarks.
  \-- This requires you have \`conceallevel\` set to 1 or 2. See \`:help conceallevel\` for more details.
  ui \= {
    enable \= true,  \-- set to false to disable all additional syntax features
    update\_debounce \= 200,  \-- update delay after a text change (in milliseconds)
    max\_file\_length \= 5000,  \-- disable UI features for files with more than this many lines
    \-- Define how various check-boxes are displayed
    checkboxes \= {
      \-- NOTE: the 'char' value has to be a single character, and the highlight groups are defined below.
      \[" "\] \= { char \= "󰄱", hl\_group \= "ObsidianTodo" },
      \["x"\] \= { char \= "", hl\_group \= "ObsidianDone" },
      \["\>"\] \= { char \= "", hl\_group \= "ObsidianRightArrow" },
      \["~"\] \= { char \= "󰰱", hl\_group \= "ObsidianTilde" },
      \["!"\] \= { char \= "", hl\_group \= "ObsidianImportant" },
      \-- Replace the above with this if you don't have a patched font:
      \-- \[" "\] = { char = "☐", hl\_group = "ObsidianTodo" },
      \-- \["x"\] = { char = "✔", hl\_group = "ObsidianDone" },

      \-- You can also add more custom ones...
    },
    \-- Use bullet marks for non-checkbox lists.
    bullets \= { char \= "•", hl\_group \= "ObsidianBullet" },
    external\_link\_icon \= { char \= "", hl\_group \= "ObsidianExtLinkIcon" },
    \-- Replace the above with this if you don't have a patched font:
    \-- external\_link\_icon = { char = "", hl\_group = "ObsidianExtLinkIcon" },
    reference\_text \= { hl\_group \= "ObsidianRefText" },
    highlight\_text \= { hl\_group \= "ObsidianHighlightText" },
    tags \= { hl\_group \= "ObsidianTag" },
    block\_ids \= { hl\_group \= "ObsidianBlockID" },
    hl\_groups \= {
      \-- The options are passed directly to \`vim.api.nvim\_set\_hl()\`. See \`:help nvim\_set\_hl\`.
      ObsidianTodo \= { bold \= true, fg \= "#f78c6c" },
      ObsidianDone \= { bold \= true, fg \= "#89ddff" },
      ObsidianRightArrow \= { bold \= true, fg \= "#f78c6c" },
      ObsidianTilde \= { bold \= true, fg \= "#ff5370" },
      ObsidianImportant \= { bold \= true, fg \= "#d73128" },
      ObsidianBullet \= { bold \= true, fg \= "#89ddff" },
      ObsidianRefText \= { underline \= true, fg \= "#c792ea" },
      ObsidianExtLinkIcon \= { fg \= "#c792ea" },
      ObsidianTag \= { italic \= true, fg \= "#89ddff" },
      ObsidianBlockID \= { italic \= true, fg \= "#89ddff" },
      ObsidianHighlightText \= { bg \= "#75662e" },
    },
  },

  \-- Specify how to handle attachments.
  attachments \= {
    \-- The default folder to place images in via \`:ObsidianPasteImg\`.
    \-- If this is a relative path it will be interpreted as relative to the vault root.
    \-- You can always override this per image by passing a full path to the command instead of just a filename.
    img\_folder \= "assets/imgs",  \-- This is the default

    \-- Optional, customize the default name or prefix when pasting images via \`:ObsidianPasteImg\`.
    \---@return string
    img\_name\_func \= function()
      \-- Prefix image names with timestamp.
      return string.format("%s-", os.time())
    end,

    \-- A function that determines the text to insert in the note when pasting an image.
    \-- It takes two arguments, the \`obsidian.Client\` and an \`obsidian.Path\` to the image file.
    \-- This is the default implementation.
    \---@param client obsidian.Client
    \---@param path obsidian.Path the absolute path to the image file
    \---@return string
    img\_text\_func \= function(client, path)
      path \= client:vault\_relative\_path(path) or path
      return string.format("!\[%s\](%s)", path.name, path)
    end,
  },
}

### Notes on configuration

[](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#notes-on-configuration)

#### Workspaces

[](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#workspaces)

For most Obsidian users, each workspace you configure in your obsidian.nvim config should correspond to a unique Obsidian vault, in which case the `path` of each workspace should be set to the corresponding vault root path.

For example, suppose you have an Obsidian vault at `~/vaults/personal`, then the `workspaces` field in your config would look like this:

config \= {
  workspaces \= {
    {
      name \= "personal",
      path \= "~/vaults/personal",
    },
  }
}

However obsidian.nvim's concept of workspaces is a little more general than that of vaults, since it's also valid to configure a workspace that doesn't correspond to a vault, or to configure multiple workspaces for a single vault. The latter case can be useful if you want to segment a single vault into multiple directories with different settings applied to each directory. For example:

config \= {
  workspaces \= {
    {
      name \= "project-1",
      path \= "~/vaults/personal/project-1",
      \-- \`strict=true\` here tells obsidian to use the \`path\` as the workspace/vault root,
      \-- even though the actual Obsidian vault root may be \`~/vaults/personal/\`.
      strict \= true,
      overrides \= {
        \-- ...
      },
    },
    {
      name \= "project-2",
      path \= "~/vaults/personal/project-2",
      strict \= true,
      overrides \= {
        \-- ...
      },
    },
  }
}

obsidian.nvim also supports "dynamic" workspaces. These are simply workspaces where the `path` is set to a Lua function (that returns a path) instead of a hard-coded path. This can be useful in several scenarios, such as when you want a workspace whose `path` is always set to the parent directory of the current buffer:

config \= {
  workspaces \= {
    {
      name \= "buf-parent",
      path \= function()
        return assert(vim.fs.dirname(vim.api.nvim\_buf\_get\_name(0)))
      end,
    },
  }
}

Dynamic workspaces are also useful when you want to use a subset of this plugin's functionality on markdown files outside of your "fixed" vaults. See [using obsidian.nvim outside of a workspace / Obsidian vault](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#usage-outside-of-a-workspace-or-vault).

#### Completion

[](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#completion)

obsidian.nvim will set itself up as an nvim-cmp source automatically when you enter a markdown buffer within your vault directory, you do **not** need to specify this plugin as a cmp source manually.

Note that in order to trigger completion for tags *within YAML frontmatter* you still need to type the "#" at the start of the tag. obsidian.nvim will remove the "#" when you hit enter on the tag completion item.

#### Syntax highlighting

[](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#syntax-highlighting)

If you're using [nvim-treesitter](https://github.com/nvim-treesitter/nvim-treesitter/blob/master/README.md) you're configuration should include both "markdown" and "markdown\_inline" sources:

require("nvim-treesitter.configs").setup({
  ensure\_installed \= { "markdown", "markdown\_inline", ... },
  highlight \= {
    enable \= true,
  },
})

If you use `vim-markdown` you'll probably want to disable its frontmatter syntax highlighting (`vim.g.vim_markdown_frontmatter = 1`) which I've found doesn't work very well.

#### Concealing characters

[](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#concealing-characters)

If you wish to use the formatting concealment features, you will need to have `conceallevel` set to a value that allows it (either `1` or `2`), for example: `set conceallevel=1` in viml or `vim.opt.conceallevel = 1` in a lua config.

#### Note naming and location

[](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#note-naming-and-location)

The `notes_subdir` and `note_id_func` options are not mutually exclusive. You can use them both. For example, using a combination of both of the above settings, a new note called "My new note" will assigned a path like `notes/1657296016-my-new-note.md`.

#### `gf` passthrough

[](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#gf-passthrough)

If you want the `gf` passthrough functionality but you've already overridden the `gf` keybinding, just change your `gf` mapping definition to something like this:

vim.keymap.set("n", "gf", function()
  if require("obsidian").util.cursor\_on\_markdown\_link() then
    return "<cmd>ObsidianFollowLink<CR>"
  else
    return "gf"
  end
end, { noremap \= false, expr \= true })

Then make sure to comment out the `gf` keybinding in your obsidian.nvim config:

mappings \= {
  \-- \["gf"\] = ...
},

Or alternatively you could map obsidian.nvim's follow functionality to a different key:

mappings \= {
  \["fo"\] \= {
    action \= function()
      return require("obsidian").util.gf\_passthrough()
    end,
    opts \= { noremap \= false, expr \= true, buffer \= true },
  },
},

### Using templates

[](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#using-templates)

To insert a template in the current note, run the command `:ObsidianTemplate`. This will open a list of available templates in your templates folder with your preferred picker. Select a template and hit `<CR>` to insert. To create a new note from a template, run the command `:ObsidianNewFromTemplate`. This will prompt you for an optional path for the new note and will open a list of available templates in your templates folder with your preferred picker. Select a template and hit `<CR>` to create the new note with the selected template. Substitutions for `{{id}}`, `{{title}}`, `{{path}}`, `{{date}}`, and `{{time}}` are supported out-of-the-box. For example, with the following configuration

{
  \-- other fields ...

  templates \= {
      folder \= "my-templates-folder",
      date\_format \= "%Y-%m-%d-%a",
      time\_format \= "%H:%M",
  },
}

and the file `~/my-vault/my-templates-folder/note template.md`:

\# {{title}}

Date created: {{date}}

creating the note `Configuring Neovim.md` and executing `:ObsidianTemplate` will insert

\# Configuring Neovim

Date created: 2023-03-01-Wed

above the cursor position.

You can also define custom template substitutions with the configuration field `templates.substitutions`. For example, to automatically substitute the template variable `{{yesterday}}` when inserting a template, you could add this to your config:

{
\-- other fields ...
templates \= {
  substitutions \= {
    yesterday \= function()
      return os.date("%Y-%m-%d", os.time() \- 86400)
    end
  }
}

### Usage outside of a workspace or vault

[](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#usage-outside-of-a-workspace-or-vault)

It's possible to configure obsidian.nvim to work on individual markdown files outside of a regular workspace / Obsidian vault by configuring a "dynamic" workspace. To do so you just need to add a special workspace with a function for the `path` field (instead of a string), which should return a *parent* directory of the current buffer. This tells obsidian.nvim to use that directory as the workspace `path` and `root` (vault root) when the buffer is not located inside another fixed workspace.

For example, to extend the configuration above this way:

{
  workspaces = {
     {
       name = "personal",
       path = "~/vaults/personal",
     },
     ...
+    {
+      name = "no-vault",
+      path = function()
+        -- alternatively use the CWD:
+        -- return assert(vim.fn.getcwd())
+        return assert(vim.fs.dirname(vim.api.nvim\_buf\_get\_name(0)))
+      end,
+      overrides = {
+        notes\_subdir = vim.NIL,  -- have to use 'vim.NIL' instead of 'nil'
+        new\_notes\_location = "current\_dir",
+        templates = {
+          folder = vim.NIL,
+        },
+        disable\_frontmatter = true,
+      },
+    },
+  },
   ...
}

With this configuration, anytime you enter a markdown buffer outside of "~/vaults/personal" (or whatever your configured fixed vaults are), obsidian.nvim will switch to the dynamic workspace with the path / root set to the parent directory of the buffer.

Please note that in order to avoid unexpected behavior (like a new directory being created for `notes_subdir`) it's important to carefully set the workspace `overrides` options. And keep in mind that to reset a configuration option to `nil` you'll have to use `vim.NIL` there instead of the builtin Lua `nil` due to the way Lua tables work.

## Contributing

[](https://github.com/epwalsh/obsidian.nvim?tab=readme-ov-file#contributing)

Please read the [CONTRIBUTING](https://github.com/epwalsh/obsidian.nvim/blob/main/.github/CONTRIBUTING.md) guide before submitting a pull request.

And if you're feeling especially generous I always appreciate some coffee funds! ❤️

[![BuyMeACoffee](https://camo.githubusercontent.com/af57548d9718bcbbfbc814feb621e5d19ae10aa23cf7b297b55c26d0a8a55470/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4275792532304d6525323061253230436f666665652d6666646430303f7374796c653d666f722d7468652d6261646765266c6f676f3d6275792d6d652d612d636f66666565266c6f676f436f6c6f723d626c61636b)](https://www.buymeacoffee.com/epwalsh)