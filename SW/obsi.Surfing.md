---
page-title: "PKM-er/Obsidian-Surfing: An Obsidian plugin that lets you browse the web within Obsidian."
url: https://github.com/PKM-er/Obsidian-Surfing
date: "2024-01-18 00:51:43"
tags: obsi/plugin
purpose: 
    - web
    - integration
---

## Surfing

[中文文档](https://github.com/PKM-er/Obsidian-Surfing/blob/main/README-ZH.md) ｜ [English Doc](https://github.com/PKM-er/Obsidian-Surfing/blob/main/README.md)

## Introduction

An [Obsidian](https://obsidian.md/) plugin that allows you to browse the web within Obsidian using v1.0 tabs.

The core functionality of the plugin, rendering a web view, is greatly influenced by [Ellpeck's Obsidian Custom Frames](https://github.com/Ellpeck/ObsidianCustomFrames) plugin and this plugin wouldn't have be possible without it.

[![](https://github.com/PKM-er/Obsidian-Surfing/raw/main/assets/obsidian-web-browser.png)](https://github.com/PKM-er/Obsidian-Surfing/blob/main/assets/obsidian-web-browser.png)

## TODO

-   Support extensions
-   Support custom CSS
-   Support custom JS

## Feature

-   Core Feature
    -   Browse arbitrary web pages: The plugin hijacks Obsidian's file, http, https protocols, enabling links to be opened directly in Obsidian, rather than in external browsers. Yes, local HTML and other resources are also supported.
    -   Editor web search: You can select keywords in the editor and then right-click to open them in web-browser and search using the default search engine.
    -   In-page web search: Again, you can right-click within a web page to use the default search engine search.
    -   Copy links pointing to highlights: As with the browser, you can select text and copy the links pointing to it.
    -   Use BookmarkLets in your browser to open the URL directly in Obsidian.
    -   Copy video timestamp (experimental feature: currently only bilibili is supported): right click on the text to pop up the menu to copy the timestamp, currently there are some bugs, it is known that sometimes the menu does not pop up.
-   Auxiliary Feature
    -   Open current URL with external browser: right-click menu
    -   Default search engine: setting item
    -   Default copy highlighted template: setting item (currently only supports very simple templates), please avoid using some special characters
    -   Support browsing history: Jump back and forth to the page
    -   Clear browsing history: command panel
    -   All links are opened in the same panel on the right: Settings
    -   Toggle whether to open in the same panel on the right: command panel
    -   Simple dark mode: just simple

## Usage

### Use BookmarkLets Open URL

The plugin registers an Obsidain uri protocol that allows you to open eb-broswer in Obsidian using the URL `obsidian://web-open?url=<url>`. Where `<url>` refers to the web address link. Match [bookmarklets](https://en.wikipedia.org/wiki/Bookmarklet) will be able to click a bookmark in the browser to open the current browser URL within Obsidain.

1.  Open the `Open URL In Obsidian Web` option in the plugin settings.
2.  Under this option there is a link of bookmarklets, drag this link into your browser's bookmark bar. You can also click this link(will copy bookmarklets code), then create bookmarklets by yourself.
3.  Now you can click on the bookmark to open the current page of your browser in Obsidian.

### Use Quickadd to search selection in ChatGPT in Surfing

1.  Create a macro based on this script: [search-in-surfing](https://gist.github.com/Quorafind/c70c6c698feeed66465d59efc39e4e1c)
2.  Open ChatGPT in surfing, and select some text, then run the macro.

## Installation

-   Not ready for market yet
-   Can be installed via the [Brat](https://github.com/TfTHacker/obsidian42-brat) plugin
-   Manual installation

1.  Find the release page on this github page and click
2.  Download the latest release zip file
3.  Unzip it, copy the unzipped folder to the obsidian plugin folder, make sure there are main.js and manifest.json files in the folder
4.  Restart obsidian (do not restart also, you have to refresh plugin list), in the settings interface to enable the plugin
5.  Done!

## Contribution

-   [Windily-cloud(皮皮)](https://github.com/windily-cloud) - Chinese translation && Features

## Support

If you are enjoying this plugin then please support my work and enthusiasm by buying me a coffee on [https://www.buymeacoffee.com/boninall](https://www.buymeacoffee.com/boninall). .

[![](https://camo.githubusercontent.com/4f14ae44a18f549610befa76f90619771fbc3a219d1e37537ae981191cb831b9/68747470733a2f2f696d672e6275796d6561636f666665652e636f6d2f627574746f6e2d6170692f3f746578743d427579206d65206120636f6666656526656d6f6a693d26736c75673d626f6e696e616c6c26627574746f6e5f636f6c6f75723d36343935454426666f6e745f636f6c6f75723d66666666666626666f6e745f66616d696c793d4c61746f266f75746c696e655f636f6c6f75723d30303030303026636f666665655f636f6c6f75723d464644443030)](https://www.buymeacoffee.com/boninall)