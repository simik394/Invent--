---
page-title: "voldikss/coc-todolist: [Deprecated due to an unfixable bug and crappy design]🕐 Todolist/task manager extension for (Neo)Vim"
url: https://github.com/voldikss/coc-todolist
date: "2024-06-24 00:09:11"
tags: [a/sw/plugin/todos, f/prod/homepage, c/, p/pwf]
about: ["[[NeoVim]]"]
aliases: 
- 
by: 
length: 1676
dir: 
---

## coc-todolist

[](https://github.com/voldikss/coc-todolist#coc-todolist)

[![publish](https://github.com/voldikss/coc-todolist/workflows/publish/badge.svg)](https://github.com/voldikss/coc-todolist/workflows/publish/badge.svg) [![npm version](https://camo.githubusercontent.com/1345e9fbbed7b82b7f5e113ee3c20ba9f7103de53742a7621006d3bc789bdcf8/68747470733a2f2f62616467652e667572792e696f2f6a732f636f632d746f646f6c6973742e737667)](https://badge.fury.io/js/coc-todolist)

Todolist manager extension for [coc.nvim](https://github.com/neoclide/coc.nvim)

[![](https://user-images.githubusercontent.com/20282795/61593014-d1be3780-ac0c-11e9-96cc-e3b787a27f46.png)](https://user-images.githubusercontent.com/20282795/61593014-d1be3780-ac0c-11e9-96cc-e3b787a27f46.png)

## Install

[](https://github.com/voldikss/coc-todolist#install)

## Features

[](https://github.com/voldikss/coc-todolist#features)

-   Allow to set a reminder for a todo item
-   Auto upload/download todolists with gist
-   Manage your todolist with CocList

## Configuration

[](https://github.com/voldikss/coc-todolist#configuration)

"todolist.dateFormat": {
  "type": "string",
  "default": "YYYY-MM-DD HH:mm",
  "description": "dates format"
},
"todolist.monitor": {
  "type": "boolean",
  "default": false,
  "description": "monitor the todolist and remind you at the time"
}

## Commands

[](https://github.com/voldikss/coc-todolist#commands)

-   `:CocCommand todolist.create`: create a new todo
-   `:CocCommand todolist.upload`: upload todolist to gist
-   `:CocCommand todolist.download`: download todolist from gist
-   `:CocCommand todolist.export`: export todolist as a json/yaml file
-   `:CocCommand todolist.clear`: clear all todos
-   `:CocCommand todolist.gist.openBrowser`: open todolist gist in [gist.github.com](https://gist.github.com/)
-   `:CocCommand todolist.gist.genToken`: generate a token used to update gist

## CocList

[](https://github.com/voldikss/coc-todolist#coclist)

run `:CocList todolist` to open the todolist

-   Filter your todo items and perform operations via `<Tab>`
-   Use `toggle` to toggle todo status between `active` and `completed`
-   Use `edit` to edit a todo item
-   Use `preview` to preview a todo item
-   Use `delete` to delete a todo item

## F.A.Q

[](https://github.com/voldikss/coc-todolist#faq)

Q: Where is the todolist data stored?

A: Normally the data is saved in `~/.config/coc/extensions/coc-todolist-data/`, but if you set `g:coc_extension_root` to another location, it will change as well

Q: coc-todolist is not loaded after upgrading

A: Remove `todolist.json`(normally `~/.config/coc/extensions/coc-todolist-data/todolist.json`). Don't forget to backup it if necessary.

Q: I want to create a persistent todolist item

A: Leave `due` value empty or let `due` be the same as `date` value(default)

## TODO

[](https://github.com/voldikss/coc-todolist#todo)

-   sync
-   Log
-   UI

## License

[](https://github.com/voldikss/coc-todolist#license)

MIT