---
page-title: "chipsenkbeil/org-roam.nvim: Port of org-roam to neovim using orgmode"
url: https://github.com/chipsenkbeil/org-roam.nvim
date: "2024-06-21 02:56:53"
tags: [A/sw/plugin, F/prod/homepage, C/, P/pwf, a/org]
about: ["[[NeoVim]]"]
aliases: 
- 
by: 
length: 5251
dir: 
---

[![org-roam.nvim logo](https://github.com/chipsenkbeil/org-roam.nvim/raw/main/assets/org-roam-logo.png)](https://github.com/chipsenkbeil/org-roam.nvim/blob/main/assets/org-roam-logo.png)

## org-roam.nvim

[](https://github.com/chipsenkbeil/org-roam.nvim#org-roamnvim)

Port of [Org-roam](https://www.orgroam.com/) to [neovim](https://neovim.io/) using [nvim-orgmode](https://github.com/nvim-orgmode/orgmode).

Requires **neovim 0.9.2+**.

## Videos

[](https://github.com/chipsenkbeil/org-roam.nvim#videos)

[![](https://camo.githubusercontent.com/7eda176076132adf14389c2ef0a201d6bffe1ff09378967e111746096692b3ad/68747470733a2f2f696d672e796f75747562652e636f6d2f76692f30326c452d79474a5776632f6d617872657364656661756c742e6a7067)](https://youtu.be/02lE-yGJWvc)

## Installation

[](https://github.com/chipsenkbeil/org-roam.nvim#installation)

This plugin depends on [nvim-orgmode/orgmode](https://github.com/nvim-orgmode/orgmode) [0.3.4](https://github.com/nvim-orgmode/orgmode/releases/tag/0.3.4) or newer.

It is recommended to install and maintain the latest version of orgmode, or lock into the commit that this plugin needs, which is illustrated below.

Org Roam Version

Orgmode Version

0.1.0

0.3.4

### lazy.nvim (recommended)

[](https://github.com/chipsenkbeil/org-roam.nvim#lazynvim-recommended)

Code Example

{
  "chipsenkbeil/org-roam.nvim",
  tag \= "0.1.0",
  dependencies \= {
    {
      "nvim-orgmode/orgmode",
      tag \= "0.3.4",
    },
  },
  config \= function()
    require("org-roam").setup({
      directory \= "~/orgfiles",
    })
  end
}

### packer.nvim

[](https://github.com/chipsenkbeil/org-roam.nvim#packernvim)

Code Example

use {
  "chipsenkbeil/org-roam.nvim",
  tag \= "0.1.0",
  requires \= {
    {
      "nvim-orgmode/orgmode",
      tag \= "0.3.4",
    },
  },
  config \= function()
    require("org-roam").setup({
      directory \= "~/orgfiles",
    })
  end
}

## Bindings

[](https://github.com/chipsenkbeil/org-roam.nvim#bindings)

Name

Keybinding

Description

add\_alias

`<Leader>naa`

Adds an alias to the node under cursor.

add\_origin

`<Leader>noa`

Adds an origin to the node under cursor.

capture

`<Leader>nc`

Opens org-roam capture window.

complete\_at\_point

`<Leader>n.`

Completes the node under cursor.

find\_node

`<Leader>nf`

Finds node and moves to it, creating it if it does not exist.

goto\_next\_node

`<Leader>nn`

Goes to the next node in sequence (via origin) for the node under cursor.

goto\_prev\_node

`<Leader>np`

Goes to the prev node in sequence (via origin) for the node under cursor.

insert\_node

`<Leader>ni`

Inserts node at cursor position, creating it if it does not exist.

insert\_node\_immediate

`<Leader>nm`

Same as `insert_node`, but skips opening capture buffer.

quickfix\_backlinks

`<Leader>nq`

Opens the quickfix menu for backlinks to the current node under cursor.

remove\_alias

`<Leader>nar`

Removes an alias from the node under cursor.

remove\_origin

`<Leader>nor`

Removes the origin from the node under cursor.

toggle\_roam\_buffer

`<Leader>nl`

Toggles the org-roam node-view buffer for the node under cursor.

toggle\_roam\_buffer\_fixed

`<Leader>nb`

Toggles a fixed org-roam node-view buffer for a selected node.

### Dailies Extension

[](https://github.com/chipsenkbeil/org-roam.nvim#dailies-extension)

Name

Keybinding

Description

capture\_date

`<Leader>ndD`

Capture a specific date’s note.

capture\_today

`<Leader>ndN`

Capture today’s note.

capture\_tomorrow

`<Leader>ndT`

Capture tomorrow’s note.

capture\_yesterday

`<Leader>ndY`

Capture yesterday’s note.

find\_directory

`<Leader>nd.`

Navigate to dailies note directory.

goto\_date

`<Leader>ndd`

Navigate to specific date’s note.

goto\_next\_date

`<Leader>ndf`

Navigate to the next note in date sequence.

goto\_prev\_date

`<Leader>ndb`

Navigate to the previous note in date sequence.

goto\_today

`<Leader>ndn`

Navigate to today’s note.

goto\_tomorrow

`<Leader>ndt`

Navigate to tomorrow’s note.

goto\_yesterday

`<Leader>ndy`

Navigate to yesterday’s note.

## Documentation

[](https://github.com/chipsenkbeil/org-roam.nvim#documentation)

See [DOCS.org](https://github.com/chipsenkbeil/org-roam.nvim/blob/main/DOCS.org) for detailed guidance on the plugin.

The documentation is also generated in vimdoc help format, which can be accessed via `:h org-roam.txt`.

## Roadmap

[](https://github.com/chipsenkbeil/org-roam.nvim#roadmap)

A collection of features to implement in no particular order.

-   \[-\] Implement [org-roam buffer](https://www.orgroam.com/manual.html#The-Org_002droam-Buffer)
    -   \[X\] Implement **org-roam-buffer-toggle** (tracks current node at point)
    -   \[X\] Implement **org-roam-buffer-display-dedicated** (tracks specific node)
    -   \[X\] Implement **Backlinks** widget for buffer
        -   View (preview of) nodes that link to this node
    -   \[ \] Implement **Reference Links** widget for buffer
        -   Nodes that reference this node (see [Refs](https://www.orgroam.com/manual.html#Refs))
    -   \[ \] Implement **Unlinked references** widget for buffer
        -   View nodes that contain text that match the nodes title/alias but are not linked
    -   \[X\] Implement **Origin** widget for buffer (custom, not in Org Roam!)
        -   Displays the origin of the node as defined in `ROAM_ORIGIN`
-   \[ \] Support [citations](https://www.orgroam.com/manual.html#Citations)
    -   \[ \] As of orgmode 9.5, **org-cite** is built-in and has the form **\[cite:@key\]**
    -   \[ \] Alongside **org-cite**, there is also support for [org-ref](https://github.com/jkitchin/org-ref) (v2 & v3), which uses **cite:key** as its format
-   \[X\] Support [completion](https://www.orgroam.com/manual.html#Completion)
    -   \[X\] [Completing within Link Brackets](https://www.orgroam.com/manual.html#Completing-within-Link-Brackets)
    -   \[X\] [Completing anywhere](https://www.orgroam.com/manual.html#Completing-anywhere)
-   \[X\] Support [templating](https://www.orgroam.com/manual.html#The-Templating-System)
    -   \[X\] Implement **org-roam-node-insert**
    -   \[X\] Implement **org-roam-node-find**
    -   \[X\] Implement **org-roam-capture**
    -   \[X\] Implement **org-roam-node-insert-immediate**
-   \[X\] Support origin (custom, not in Org Roam!)
    -   \[X\] `ROAM_ORIGIN` available within node properties, containing org id
    -   \[X\] Ability to query database for nodes with origin matching an id
    -   \[X\] Keybinding to jump forward and backward across origins
-   \[X\] Miscellaneous Roam functions
    -   \[X\] Implement **org-roam-alias-add**
    -   \[X\] Implement **org-roam-alias-remove**
    -   \[X\] Implement **org-roam-origin-add** (custom, not in Org Roam!)
    -   \[X\] Implement **org-roam-origin-remove** (custom, not in Org Roam!)
-   \[-\] Implement extensions
    -   \[X\] [org-roam-dailies](https://www.orgroam.com/manual.html#org_002droam_002ddailies)
    -   \[ \] [org-roam-export](https://www.orgroam.com/manual.html#org_002droam_002dexport)
    -   \[ \] [org-roam-graph](https://www.orgroam.com/manual.html#org_002droam_002dgraph)
    -   \[ \] [org-roam-protocol](https://www.orgroam.com/manual.html#org_002droam_002dprotocol)

## Developer & Contributor Instructions

[](https://github.com/chipsenkbeil/org-roam.nvim#developer--contributor-instructions)

### Running tests

[](https://github.com/chipsenkbeil/org-roam.nvim#running-tests)

A *makefile* is provided to support running tests. It will download [plenary.nvim](https://github.com/nvim-lua/plenary.nvim) and [nvim-orgmode](https://github.com/nvim-orgmode/orgmode) into the *vendor* directory.