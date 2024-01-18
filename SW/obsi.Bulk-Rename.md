---
page-title: "OlegLustenko/obsidian-bulk-rename"
url: https://github.com/OlegLustenko/obsidian-bulk-rename
date: "2024-01-18 00:06:25"
tags: obsi/plugin
purpose: 
---

## Obsidian Bulk Rename Plugin

[![](https://github.com/OlegLustenko/obsidian-bulk-rename/actions/workflows/CI.yml/badge.svg)](https://github.com/OlegLustenko/obsidian-bulk-rename/actions/workflows/CI.yml) [![Release Obsidian plugin](https://github.com/OlegLustenko/obsidian-bulk-rename/actions/workflows/release.yml/badge.svg)](https://github.com/OlegLustenko/obsidian-bulk-rename/actions/workflows/release.yml) [![GitHub license](https://camo.githubusercontent.com/9ebeb9918c3c1cbde8ebc3eaec4e5f5bbcd87d82f1f30ed02a2b4c41fdf609f5/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6c6963656e73652f4f6c65674c757374656e6b6f2f6f6273696469616e2d62756c6b2d72656e616d65)](https://https//github.com/OlegLustenko/obsidian-bulk-rename/master/LICENSE) [![Github all releases](https://camo.githubusercontent.com/0f94bb6304ac18b06851796cfe6d3f4b4cc3eac3551e05413f3d720b40dcca65/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f646f776e6c6f6164732f4f6c65674c757374656e6b6f2f6f6273696469616e2d62756c6b2d72656e616d652f746f74616c2e737667)](https://github.com/OlegLustenko/obsidian-bulk-rename/releases/) [![GitLab latest release](https://camo.githubusercontent.com/d967dd1a75a77e294e0d8fe57fde946aef8788aad07e4ba03c39afa080b644a9/68747470733a2f2f62616467656e2e6e65742f6769746875622f72656c656173652f4f6c65674c757374656e6b6f2f6f6273696469616e2d62756c6b2d72656e616d652f)](https://github.com/OlegLustenko/obsidian-bulk-rename/releases)

## Introduction

Now you can rename a bunch of files from the directory and all references also will be updated across the vault.

[![](https://github.com/OlegLustenko/obsidian-bulk-rename/raw/master/documentation/assets/Animation.gif)](https://github.com/OlegLustenko/obsidian-bulk-rename/blob/master/documentation/assets/Animation.gif)

> Under the hood this plugin is using obsidian API for renaming, but we just applying it for many files

## Features

> Whenever we're updating **Replacement Symbols** you can set new *Directory Location* too so, you can also move files to *another directory*

## Rename/Move files based on folder location

Click *Search By Folder*

Update **Folder Location** where are you wanting to get files from, put **Existing Characters** from the file path later on update **Replacement Symbols** those symbols will be used for in a new path.

## Rename/Move files based on tags

Click *Search By Tags*

Put tags in **Tags names** field search will be completed across the vault, use coma separator if you need more than 1 tag Click Refresh Update **Existing Characters** field with a pattern you are looking for in existing notes, set **Replacement Symbols**

## Search By RegExp

Usage of Search By RegExp You have two fields, RegExp pattern, and RegExp Flags

RegExp pattern will be wrapped into `/ /`

## Supported flags:

-   **g** - global
-   **i** - ignore case
-   **m** - multiline anchors
-   **s** - dot matches all (aka singleline) - works even when not natively supported
-   **u** - unicode (ES6)
-   **y** - sticky (Firefox 3+, ES6)
-   **n** - explicit capture
-   **x** - free-spacing and line comments (aka extended)
-   **A** - astral (requires the Unicode Base addon)

---

Click Preview or `Enter` to see intermediate results(nothing will be changed/moved/renamed).

Click `Rename` whenever you're done

## API

-   **folder location** - Files from which folder you need to rename
-   **Symbols in existing files** - the symbols/characters that we have in the files
-   **Replacement Symbols** - a new symbols that will be pasted instead
-   **Files within the folder** - this is for information purpose
-   **RegExp pattern** - pattern of RegExp to match
-   **RegExp flags** - flags that will be applied to RegExp pattern

Rename Button will start renaming all files by respective path.

## Motivation

This plugin was developed to cover my needs. Originally I've started to use my daily files with **\_** delimiter. So my files looked like this: 2022\_01\_01, over the time I realized other platform out of the box configured to prefer dashes, like this 2022-01-01

Here is many guides on how to rename files, what kind of script we need to run, what version of python or Node.js we need to install and so on.

Why Not to have this functionality build-in into Obsidian?

And rename a **bunch of files** and update their reference in code base respectively. So now you can rename a bunch of files at once and all imports also will be updated in the vault

## Installation

Follow the steps below to install Tasks.

1.  Search for "Bulk Rename" in Obsidian's community plugins browser
2.  Enable the plugin in your Obsidian settings (find "Bulk Rename" under "Community plugins").
3.  Welcome on board! Follow the guides above, share your findings!

## Support development

If you enjoy Bulk Rename, consider [buying me a coffee](https://www.buymeacoffee.com/oleglustenko), and following me on twitter [@oleglustenko](https://twitter.com/oleglustenko) [!["Buy Me A Coffee"](https://camo.githubusercontent.com/12f516d86d600c89a6abd2326256045c27325ad7c8532c0d36772965a4923be0/68747470733a2f2f7777772e6275796d6561636f666665652e636f6d2f6173736574732f696d672f637573746f6d5f696d616765732f6f72616e67655f696d672e706e67)](https://www.buymeacoffee.com/oleglustenko)