---
page-title: "HoBeedzc/obsidian-header-enhancer-plugin: Level up your headers, customize your notes. Header Enhancer makes your notes header better and more useful."
url: https://github.com/HoBeedzc/obsidian-header-enhancer-plugin
date: "2024-01-18 08:16:07"
tags: sw/plugin
purpose:
extends: "[[Obsidian]]"
---

## Obsidian Header Enhancer

This plugin is designed to enhance the header of [Obsidian](https://obsidian.md/). The plugin will auto-detect the header level and add the number to the header.

**Warning:**

-   This plugin is still in the early stage of development, so there may be some bugs. If you find any bugs, please feel free to report them in the [issue](https://github.com/HoBeedzc/obsidian-header-enhancer-plugin/issues)
-   Data is invaluable, so please remember to create backups when using the beta plugin (which version number like 0.x.x).

## Core Features

### 1\. Header Auto Numbering

Header auto numbering provides the ability to add numbers to the header. The number will be added to the header when you press `Enter` key to create a new line and it will be updated when you change the header level.

**Example:**

[![header-auto-numbering-example](https://github.com/HoBeedzc/obsidian-header-enhancer-plugin/raw/main/doc/img/header-auto-numbering-example.gif)](https://github.com/HoBeedzc/obsidian-header-enhancer-plugin/blob/main/doc/img/header-auto-numbering-example.gif)

**Warning:**

-   Header Auto Numbering use `\t` split auto-number and your header. If your header contains `\t`, Header Auto Numbering may not work properly.
-   Header Auto Numbering will modify your Markdown source file directly, so that can be rendered in other Markdown editors.
-   Please make sure your header not inculde space if you set `Space` as separator.

### 2\. Isolate Title Font \[W.I.P\]

Isolate title font provides the ability to isolate the title font from the content.

## Installation

### From Obsidian \[Recommended\]

1.  Open Settings -> Third-party plugins
2.  Disable Safe mode
3.  Click Browse community plugins
4.  Search for "Header Enhancer"
5.  Click Install
6.  Once installed, close the community plugins window and enable the newly installed plugin

### From GitHub

1.  Download the [Latest release](https://github.com/HoBeedzc/obsidian-header-enhancer-plugin/releases/latest)
2.  Extract the zip archive in `<vault>/.obsidian/plugins/` so that the `main.js` file is within the folder `<vault>/.obsidian/plugins/header-enhancer/`.
3.  Reload Obsidian
4.  If prompted about Safe Mode, you can disable safe mode and enable the plugin.

## Usage

### Header Auto Numbering

Header auto-numbering is enabled by default. You can disable it in the plugin settings.

#### a. Change auto number start header level

You can change the auto number start header level in the plugin settings. The default value is `1` which means auto number start from H1 or `#`.

#### b. Custom your numbering style

You can customize your numbering style and observe the style preview in the plugin settings. Currently, only custom separator are supported.

#### c. Use Yaml to Control Header Numbering

You can use Yaml to control header numbering in the plugin settings. The default value is `false` which means use auto numbering. If you set it to `true`, you can use Yaml to control header numbering.

**Example:** [![yaml-example](https://github.com/HoBeedzc/obsidian-header-enhancer-plugin/raw/main/doc/img/yaml-example.gif)](https://github.com/HoBeedzc/obsidian-header-enhancer-plugin/blob/main/doc/img/yaml-example.gif)[](https://github.com/HoBeedzc/obsidian-header-enhancer-plugin/blob/main/doc/img/yaml-example.gif)

## Known bugs

Here are some known bugs, I will fix them as soon as possible.

-   When you change the header level, the auto number will not be updated immediately. You need move cursor to header line and press `Enter` key to update it.

## Todo list

-   Setting support Chinese. - Header Enhancer

## ChangeLog

Full changelog can be found [here](https://github.com/HoBeedzc/obsidian-header-enhancer-plugin/blob/main/doc/changelog.md).

## Acknowledgements

-   [https://github.com/Yaozhuwa/easy-typing-obsidian](https://github.com/Yaozhuwa/easy-typing-obsidian)
-   [https://github.com/lijyze/obsidian-state-switcher](https://github.com/lijyze/obsidian-state-switcher)
-   [https://github.com/onlyafly/number-headings-obsidian](https://github.com/onlyafly/number-headings-obsidian)

## Support

If you like this plugin, you can support me by:

[![](https://camo.githubusercontent.com/b18df8e71ef6bb985ccad26f5bd5c85b49bc44866b45b66957b2b9e4b3487db8/68747470733a2f2f696d672e6275796d6561636f666665652e636f6d2f627574746f6e2d6170692f3f746578743d427579206d65206120636f6666656526656d6f6a693d26736c75673d686f62656526627574746f6e5f636f6c6f75723d46464444303026666f6e745f636f6c6f75723d30303030303026666f6e745f66616d696c793d436f6f6b6965266f75746c696e655f636f6c6f75723d30303030303026636f666665655f636f6c6f75723d666666666666)](https://bmc.link/hobee)