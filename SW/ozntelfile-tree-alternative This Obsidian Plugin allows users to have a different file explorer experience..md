---
page-title: "ozntel/file-tree-alternative: This Obsidian Plugin allows users to have a different file explorer experience."
url: https://github.com/ozntel/file-tree-alternative
date: "2024-04-08 20:09:48"
tags: 
- A/sw/plugin
- F/homepage
- C/
- P/
about: "[[Obsidian]]"
aliases: 
- 656e5c66-51ca-48d8-8b21-8ef80859b70f
- ozntel/file-tree-alternative: This Obsidian Plugin allows users to have a different file explorer experience.
by: 
length: 4083
dir: 
---

## Obsidian File Tree Alternative Plugin

[](https://github.com/ozntel/file-tree-alternative#obsidian-file-tree-alternative-plugin)

[![GitHub release (latest SemVer)](https://camo.githubusercontent.com/097c91d37f96932de81f37e925e89276aeb1f0591c2d7d0119b6c1f1c5a6f7c1/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f762f72656c656173652f6f7a6e74656c2f66696c652d747265652d616c7465726e61746976653f7374796c653d666f722d7468652d6261646765)](https://camo.githubusercontent.com/097c91d37f96932de81f37e925e89276aeb1f0591c2d7d0119b6c1f1c5a6f7c1/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f762f72656c656173652f6f7a6e74656c2f66696c652d747265652d616c7465726e61746976653f7374796c653d666f722d7468652d6261646765) [![GitHub all releases](https://camo.githubusercontent.com/c51333e3a584bece245b56ada2d7e1e78e08b04b868fb6613e57ceec63aeffba/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f646f776e6c6f6164732f6f7a6e74656c2f66696c652d747265652d616c7465726e61746976652f746f74616c3f7374796c653d666f722d7468652d6261646765)](https://camo.githubusercontent.com/c51333e3a584bece245b56ada2d7e1e78e08b04b868fb6613e57ceec63aeffba/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f646f776e6c6f6164732f6f7a6e74656c2f66696c652d747265652d616c7465726e61746976652f746f74616c3f7374796c653d666f722d7468652d6261646765)

The default file explorer of Obsidian has all files and folders in a single view. The File Tree Alternative plugin helps you to have separate views for folders and files.

The plugin is updated quiet regularly. You can see the details of each release using the following link [Release Updates](https://github.com/ozntel/file-tree-alternative/blob/main/Releases.md)

## Plugin Features

[](https://github.com/ozntel/file-tree-alternative#plugin-features)

### General

[](https://github.com/ozntel/file-tree-alternative#general)

-   You can use `Evernote` view, which shows folders and file list at the same time. Or simply turn it off to have separate views. The plugin supports splitting the view `horizontally` or `vertically`. Make sure that you adjust the plugin settings accordingly.
-   You can use `Ribbon Icon` to activate the `File Tree Leaf` in case you close by mistake. You can turn off `ribbon icon` from the plugin settings. It will only work if you closed the plugin view accidentaly or on purpose to build it back.

### Folder Pane Features

[](https://github.com/ozntel/file-tree-alternative#folder-pane-features)

-   You can see the `number of notes` under each folder within the `folders` view. You have an option if you want to see the number for notes or `number of all files`. You can also turn this function off completely to remove counts from the display.
    
    [![](https://raw.githubusercontent.com/ozntel/file-tree-alternative/main/images/number-of-notes.png)](https://raw.githubusercontent.com/ozntel/file-tree-alternative/main/images/number-of-notes.png)
    
-   You can also `focus in and out` to a certain folder, which will help you to save space in the folder pane by either double clicking the folder name or using the context menu items:
    
    [![](https://raw.githubusercontent.com/ozntel/file-tree-alternative/main/images/focus-in-folder.png)](https://raw.githubusercontent.com/ozntel/file-tree-alternative/main/images/focus-in-folder.png)
    
    [![](https://raw.githubusercontent.com/ozntel/file-tree-alternative/main/images/focus-out-from-folder.png)](https://raw.githubusercontent.com/ozntel/file-tree-alternative/main/images/focus-out-from-folder.png)
    

Double Clicking again on the focused folder name will move focus to the parent folder.

-   The plugin remembers `last expanded folders` and `last focused folder` state to load for the following session in case you relaunch your vault.
    
-   You can define certain `folder paths` in plugin settings to exclude from main folder list. All subfolders are going to be excluded, as well.
    
-   You can turn on/off `root folder` within the file tree.
    
-   You can customize the `folder icons`. Check the available options from plugin settings:
    
    [![](https://raw.githubusercontent.com/ozntel/file-tree-alternative/main/images/folder-icons.png)](https://raw.githubusercontent.com/ozntel/file-tree-alternative/main/images/folder-icons.png)
    
-   You can expand/collapse all folders using the navigation buttons on the top.
    

### File List Pane Features

[](https://github.com/ozntel/file-tree-alternative#file-list-pane-features)

-   The plugin lists all files including the `files under sub-folders`. You can turn off this option from plugin settings if you want to see only the files under the folder you selected. You can also turn on `toggle button` from the plugin settings and it'll include an additional button (looks like an eye) to toggle `files under sub-folders`. You can also toggle viewing direct or all files under a folder.
    
-   The plugin allows you to `Pin` your favorite files to the top. They are saved for the following sessions.
    
-   You can define certain `file extensions` in plugin settings to exclude from listing in file explorer.
    
-   You can `star`/`unstar` your files in case you have `Starred` plugin turned on.
    
-   You can drop `external files` into file list to add the files into current active folder path.
    
-   You can turn on `Search` feature from plugin settings to filter files with their names.
    
    -   You can use `all:` syntax in search box to search files from all folders rather than the active folder.
    -   You can use `tag:` syntax in search box to search files with tag. It will show all files with full or partial match.
-   You can fix the buttons and the header on the top of the file list. Not all themes are compatible with this option. You might need to add custom CSS to use this option effectively:
    
    [![](https://raw.githubusercontent.com/ozntel/file-tree-alternative/main/images/fixed-top-files.png)](https://raw.githubusercontent.com/ozntel/file-tree-alternative/main/images/fixed-top-files.png)
    
-   You can sort your files depending on your needs. Current options are `File Name`, `File Size`, `Creation Time` and `Update Time`. You can sort from both sides using `Reverse Order` button.
    

## Style Settings

[](https://github.com/ozntel/file-tree-alternative#style-settings)

As of version 2.3.2, the plugin supports Custom Style Setings. To be able to use it, you need to install [Style Settings](https://github.com/mgmeyers/obsidian-style-settings) plugin. You can customize the size, colors etc.

## Sample Images

[](https://github.com/ozntel/file-tree-alternative#sample-images)

-   Single Folder View:
    
    [![](https://github.com/ozntel/file-tree-alternative/raw/main/images/folders-view.png)](https://github.com/ozntel/file-tree-alternative/raw/main/images/folders-view.png)
-   Pin to Top:
    
    [![](https://github.com/ozntel/file-tree-alternative/raw/main/images/files-pinned.png)](https://github.com/ozntel/file-tree-alternative/raw/main/images/files-pinned.png)

## Sample Record

[](https://github.com/ozntel/file-tree-alternative#sample-record)

[![](https://github.com/ozntel/file-tree-alternative/raw/main/images/obsidian-plugin.png)](https://youtu.be/fbz8IZtXuUE)

You can also checkout the Youtube video created by Antone Heyward explaining the functionalities of the plugin: [Enhance The File Explorer File Tree Alternative Plugin](https://youtu.be/KBzE_BT0rtQ)

## Contact

[](https://github.com/ozntel/file-tree-alternative#contact)

If you have any issue or you have any suggestion, please feel free to reach me out directly using contact page of my website [ozan.pl/contact/](https://www.ozan.pl/contact/) or directly to [me@ozan.pl](mailto:me@ozan.pl).

## Support

[](https://github.com/ozntel/file-tree-alternative#support)

If you are enjoying the plugin then you can support my work and enthusiasm by buying me a coffee:

[![Buy Me a Coffee at ko-fi.com](https://camo.githubusercontent.com/9da29a4ab68783c46db3229ef632988f93d14cffaebf3c7710c37454f3180ce9/68747470733a2f2f63646e2e6b6f2d66692e636f6d2f63646e2f6b6f6669312e706e673f763d32)](https://ko-fi.com/L3L356V6Q)