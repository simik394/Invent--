---
page-title: "deathau/cm-typewriter-scroll-obsidian: Typewriter Scroll Obsidian Plugin"
url: https://github.com/deathau/cm-typewriter-scroll-obsidian
date: "2024-01-18 00:30:04"
tags: A/sw/obsi/plugin
purpose:
---

## Typewriter Scroll Obsidian Plugin

[![GitHub release (latest SemVer)](https://camo.githubusercontent.com/0fbe5e11ee158ed354141f2b5e4d5d66e5f062cc2b839eefe1b011a36d21cfad/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f762f72656c656173652f646561746861752f636d2d747970657772697465722d7363726f6c6c2d6f6273696469616e3f7374796c653d666f722d7468652d626164676526736f72743d73656d766572)](https://github.com/deathau/cm-typewriter-scroll-obsidian/releases/latest) [![GitHub All Releases](https://camo.githubusercontent.com/394f8d5e01b20f63b621bcf4a8479631829bfa304d8b0b05a96ff8f9cedb4244/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f646f776e6c6f6164732f646561746861752f636d2d747970657772697465722d7363726f6c6c2d6f6273696469616e2f746f74616c3f7374796c653d666f722d7468652d6261646765)](https://camo.githubusercontent.com/394f8d5e01b20f63b621bcf4a8479631829bfa304d8b0b05a96ff8f9cedb4244/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f646f776e6c6f6164732f646561746861752f636d2d747970657772697465722d7363726f6c6c2d6f6273696469616e2f746f74616c3f7374796c653d666f722d7468652d6261646765)

A plugin for [Obsidian](https://obsidian.md/) to enable typewriter-style scrolling, which keeps the view centered in the editor.

[![Screenshot](https://github.com/deathau/cm-typewriter-scroll-obsidian/raw/main/screenshot.gif)](https://github.com/deathau/cm-typewriter-scroll-obsidian/raw/main/screenshot.gif)

### Compatibility

Custom plugins are only available for Obsidian v0.9.7+.

The current API of this repo targets Obsidian **v0.10.0**.

### Notes

This is all very experimental at the moment, so parts might not work, etc.

## Installation

### From within Obsidian

From Obsidian v0.9.8, you can activate this plugin within Obsidian by doing the following:

-   Open Settings > Third-party plugin
-   Make sure Safe mode is **off**
-   Click Browse community plugins
-   Search for this plugin
-   Click Install
-   Once installed, close the community plugins window and activate the newly installed plugin

#### Updates

You can follow the same procedure to update the plugin

### From GitHub

-   Download the Latest Release from the Releases section of the GitHub Repository
-   Extract the plugin folder from the zip to your vault's plugins folder: `<vault>/.obsidian/plugins/`  
    Note: On some machines the `.obsidian` folder may be hidden. On MacOS you should be able to press `Command+Shift+Dot` to show the folder in Finder.
-   Reload Obsidian
-   If prompted about Safe Mode, you can disable safe mode and enable the plugin. Otherwise head to Settings, third-party plugins, make sure safe mode is off and enable the plugin from there.

## Security

> Third-party plugins can access files on your computer, connect to the internet, and even install additional programs.

The source code of this plugin is available on GitHub for you to audit yourself, but installing plugins into Obsidian is currently a matter of trust.

I can assure you here that I do nothing to collect your data, send information to the internet or otherwise do anything nefarious with your system. However, be aware that I *could*, and you only have my word that I don't.

This plugin does contain code copied from [this repository](https://github.com/azu/codemirror-typewriter-scrolling/blob/b0ac076d72c9445c96182de87d974de2e8cc56e2/typewriter-scrolling.js), which I have modified for this plugin.

## Development

This project uses Typescript to provide type checking and documentation.  
The repo depends on the latest [plugin API](https://github.com/obsidianmd/obsidian-api) in Typescript Definition format, which contains TSDoc comments describing what it does.

**Note:** The Obsidian API is still in early alpha and is subject to change at any time!

If you want to contribute to development and/or just customize it with your own tweaks, you can do the following:

-   Clone this repo.
-   `npm i` or `yarn` to install dependencies
-   `npm run build` to compile.
-   Copy `manifest.json`, `main.js` and `styles.css` to a subfolder of your plugins folder (e.g, `<vault>/.obsidian/plugins/<plugin-name>/`)
-   Reload obsidian to see changes

Alternately, you can clone the repo directly into your plugins folder and once dependencies are installed use `npm run dev` to start compilation in watch mode.  
You may have to reload obsidian (`ctrl+R`) to see changes.

## Pricing

Huh? This is an open-source plugin I made *for fun*. It's completely free. However, if you absolutely *have* to send me money because you like it that much, feel free to throw some coins in my hat via the following:

[![GitHub Sponsors](https://camo.githubusercontent.com/7a9f821f43afe107e636092c2071dca576b517542f75373c527a95b21dce6b4e/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f73706f6e736f72732f646561746861753f7374796c653d736f6369616c)](https://github.com/sponsors/deathau) [![Paypal](https://camo.githubusercontent.com/4436978ff0e502ebb4a7c62d5ca162728e73561d0d7932492bdf15f6a134dd72/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f70617970616c2d646561746861752d79656c6c6f773f7374796c653d736f6369616c266c6f676f3d70617970616c)](https://paypal.me/deathau)

## Version History

## 0.2.2

-   Added a setting to adjust the typewriter mode offset (more towards the top or bottom of the page).
-   Fixed a bug preventing the typewriter mode from being disabled without reloading Obsidian.

## 0.2.1

-   Added padding to centre the top in live preview

## 0.2.0

-   CM6 (Live Preview) support!

## 0.1.1

-   Modified scroll so it won't work on mouse selection.
    -   Instead, it specifically only works on 'up', 'down', 'left' and 'right' keyboard presses (alongside any typing edits).
-   Also, changed the cursor position used for the calculation so that shift+arrow selection is visible.
-   Fixed unexpected line jumping.

## 0.1.0

-   Updated APIs so toggling on and off should work again.

## 0.0.2

-   Added a basic 'Zen Mode' which dims non-active lines in the editor
    -   "Active Line" will include an entire paragraph at this stage
    -   Togglable in settings and via a command
-   Fixed some minor issues around disabling / enabling

## 0.0.1

Initial Release