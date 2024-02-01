---
page-title: "kelszo/obsidian-file-explorer-plus: A plugin for https://obsidian.md, which enables the ability to hide and pin specific files and folders in the file explorer by applying custom filters."
url: https://github.com/kelszo/obsidian-file-explorer-plus
date: "2024-01-18 08:19:52"
tags: A/sw/plugin
purpose:
extends: "[[Obsidian]]"
---

## File Explorer++ Plugin for [Obsidian.md](https://obsidian.md/)

**File Explorer++** enhances the built-in file explorer in [Obsidian.md](https://obsidian.md/). This plugin enables users to efficiently hide and pin files and folders. You can utilize custom wildcard or regex filters based on file/folder names, paths, and tags. Additionally, a simple click in the file menu lets you hide or pin specific files or folders.

[![](https://github.com/kelszo/obsidian-file-explorer-plus/raw/master/assets/example.png)](https://github.com/kelszo/obsidian-file-explorer-plus/blob/master/assets/example.png)

## **Usage**

1.  Set up filters either via the plugin settings tab in Obsidian or by right-clicking on a file/folder and choosing "Hide/Pin file".
2.  Toggle filters on/off in settings or using the `Toggle all pin/hide filters` command. For individual filters, use the `Toggle pin/hide filter` command.

## **Features**

-   **Flexibility in Filtering**: Hide and pin files and folders using wildcard or regex filters for names, paths, and tags.
-   **Quick Action**: Instantly hide or pin specific files and folders with a right-click.
-   **Efficiency**: Through monkey patching, the plugin only runs during Obsidian folder sorting or when a filter changes.
-   **Transparency**: View the paths hidden or pinned and understand the filter behind each.
-   **Mobile Compatibility**: This plugin supports mobile devices.

## **Feature Requests and Bug Reporting**

Though the plugin is in its initial stages, we're open to enhancement suggestions. If you encounter any bugs or have a feature in mind, kindly open an issue for discussion.

## **License**

File Explorer++ is under the GNU [AGPL-3.0](https://www.gnu.org/licenses/agpl-3.0.en.html) license. For more details, see the `LICENSE` file.