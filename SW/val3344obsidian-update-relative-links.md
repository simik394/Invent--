---
page-title: "val3344/obsidian-update-relative-links"
url: https://github.com/val3344/obsidian-update-relative-links
date: "2024-03-20 14:41:54"
tags: 
- A/sw/plugin
- F/homepage
- C/
- P/
about: "[[Obsidian]]"
aliases: 
- d9596b68-a404-4690-a303-980bf835cc79
- val3344/obsidian-update-relative-links
by: 
length: 1841
dir: 
---

## Update Relative Links

[](https://github.com/val3344/obsidian-update-relative-links#update-relative-links)

[中文](https://github.com/val3344/obsidian-update-relative-links/blob/master/README_zh.md)

## Plugin function

[](https://github.com/val3344/obsidian-update-relative-links#plugin-function)

Obsidian's implementation of the "Automatically update internal links" option is buggy. After the file is moved, only the links to this file will be automatically updated, and the links to other files in this file will not be updated. This plugin is used to solve this problem. There is also a command to batch fix all existing links.

For example, there are two files as follows:

`dirA/fileA`:

\[fileB\](../dirB/fileB.md)

`dirB/fileB`:

\[fileA\](../dirA/fileA.md)

After moving `fileA` from `dirA` to `dirB`:

`dirB/fileA`:

\[fileB\](../dirB/fileB.md)

`dirB/fileB`:

The function of this plugin is to fix `[fileB](../dirB/fileB.md)` in `dirB/fileA` to `[fileB](fileB.md)`.

## Instructions

[](https://github.com/val3344/obsidian-update-relative-links#instructions)

The plugin contains two functions:

The first function: After the file is moved, the relative path of the link is automatically fixed. Once the plugin is installed and enabled, moving files is triggered automatically, no further action is required.

The second function: batch fix links in all files to relative paths. Open the command palette (the default shortcut is `Ctrl + P`), search for "Update all relative links", and press Enter to execute.

## Plugin restrictions

[](https://github.com/val3344/obsidian-update-relative-links#plugin-restrictions)

The `Use [[Wikilinks]]` option must be turned off to use Markdown's link syntax. The point of using relative paths is also to make notes more generic, and if you are also using Wiki Links, there is no need to use relative paths.

## Why use relative paths

[](https://github.com/val3344/obsidian-update-relative-links#why-use-relative-paths)

One of the great advantages of Obsidian is that the notes are composed entirely of Markdown files, so there is no need to worry about migration. Use relative paths to make notes more versatile. For example, use other Markdown editors to view and edit notes. If you sync your notes with Git, you can also view your notes directly on the web. If you don't use relative paths, links in notes will only be recognized in Obsidian.