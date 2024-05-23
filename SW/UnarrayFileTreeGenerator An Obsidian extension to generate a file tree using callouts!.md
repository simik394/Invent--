---
page-title: "Unarray/FileTreeGenerator: An Obsidian extension to generate a file tree using callouts!"
url: https://github.com/Unarray/FileTreeGenerator
date: "2024-04-08 20:11:16"
tags: 
- A/sw/plugin
- F/homepage
- C/
- P/
about: "[[Obsidian]]"
aliases: 
- 7dd5f90c-9aea-4ad8-80e9-ecfa7fa1c469
- Unarray/FileTreeGenerator: An Obsidian extension to generate a file tree using callouts!
by: 
length: 924
dir: 
---

## File Tree Generator

[](https://github.com/Unarray/FileTreeGenerator#file-tree-generator)

An Obsidian plugin allow you to generate file trees using [Obsidian Callouts](https://help.obsidian.md/Editing+and+formatting/Callouts)!

[![obsidian dark-mode example](https://github.com/Unarray/FileTreeGenerator/raw/main/meta/example-dark.png)](https://github.com/Unarray/FileTreeGenerator/blob/main/meta/example-dark.png) [![obsidian light-mode example](https://github.com/Unarray/FileTreeGenerator/raw/main/meta/example-light.png)](https://github.com/Unarray/FileTreeGenerator/blob/main/meta/example-light.png)

## How to use?

[](https://github.com/Unarray/FileTreeGenerator#how-to-use)

When editing an Obsidian note, you can use `generate file tree` command or use the generate file tree Ribbon Icon.  

[![generate file tree pannel](https://github.com/Unarray/FileTreeGenerator/raw/main/meta/pannel.png)](https://github.com/Unarray/FileTreeGenerator/blob/main/meta/pannel.png)

Note

if you are on desktop, you can import a folder by pressing the extra button next to your files paths input

---

As you see, you can ignore patterns of files/folders in the setting tabs.  
This patterns follow the [gitignore spec 2.22.1](https://git-scm.com/docs/gitignore/2.22.1)

[![generate file tree pannel](https://github.com/Unarray/FileTreeGenerator/raw/main/meta/settings.png)](https://github.com/Unarray/FileTreeGenerator/blob/main/meta/settings.png)

## Note

[](https://github.com/Unarray/FileTreeGenerator#note)

This plugin use FS *(desktop only)* to load files from your local directory.

## Installation

[](https://github.com/Unarray/FileTreeGenerator#installation)

In your vault folder, go to `./.obsidian/plugins/file-tree-generator/` Then you can:

Clone this REPO and run `npm run build` or directly download latest plugin release containing `main.js`, `manifest.json` and `styles.css`.

Note

If you are a developer, clone this repo -> run `npm i` -> start coding with `npm run dev` *(to hot-reload the plugin in obsidian, install [Hot-Reload plugin](https://github.com/pjeby/hot-reload))*