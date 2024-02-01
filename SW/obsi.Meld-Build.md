---
page-title: "meld-cp/obsidian-build: Write and execute (sandboxed) JavaScript to render templates, query DataView and create dynamic notes."
url: https://github.com/meld-cp/obsidian-build
date: 2024-01-18 08:29:41
tags:
  - A/sw/plugin
  - ⭐/interesting
purpose:
  - scripting
extends:
  - "[[Obsidian]]"
---

-   Watch 3
    
    ### Notifications
    
-   [Fork 0](https://github.com/meld-cp/obsidian-build/fork) Fork your own copy of meld-cp/obsidian-build
    
-   #### Lists
    
    #### Lists
    

[Open in github.dev](https://github.dev/) [Open in a new github.dev tab](https://github.dev/) [Open in codespace](https://github.com/codespaces/new/meld-cp/obsidian-build?resume=1)

## meld-cp/obsidian-build

## Add file

## Add file

## Meld Build - An Obsidian Plugin

Write and execute (sandboxed) JavaScript to render templates, query DataView and create dynamic notes.

Basically, turn a note into a small, simple, runnable thing.

[![](https://camo.githubusercontent.com/d6a41ff4647ea2e8e10365d32da78dc3b9bb3a521b42c5dd777149993b22393b/68747470733a2f2f696d672e6275796d6561636f666665652e636f6d2f627574746f6e2d6170692f3f746578743d26656d6f6a693d26736c75673d6d656c642d6275696c6426627574746f6e5f636f6c6f75723d46464444303026666f6e745f636f6c6f75723d30303030303026666f6e745f66616d696c793d417269616c266f75746c696e655f636f6c6f75723d30303030303026636f666665655f636f6c6f75723d666666666666)](https://www.buymeacoffee.com/cleon)

## Quick Start

-   Install and enable the plugin
-   Paste the Markdown below into a new note.
-   If you are in Reading or Live Preview modes, click the 'Run' button. If you are in Source mode, choose `Meld Build: Run` from the command pallette.

\`\`\`meld-build-toolbar
\`\`\`

\`\`\`js meld-build
const ans \= await $.ui.ask('What should I call you?');
await $.ui.message( \`From this day forth you shall be known as ${ans}\` );
\`\`\`

## Documentation

-   [User Guide](https://github.com/meld-cp/obsidian-build/blob/master/docs/user-guide.md)
-   [API](https://github.com/meld-cp/obsidian-build/blob/master/docs/api.md)

### Examples

-   [Guess The Number Game](https://github.com/meld-cp/obsidian-build/blob/master/docs/examples/guess-the-number.md)
-   [Guess The Number Game (Using Markers)](https://github.com/meld-cp/obsidian-build/blob/master/docs/examples/guess-the-number-marker.md)
-   [Simple Invoice Builder](https://github.com/meld-cp/obsidian-build/blob/master/docs/examples/invoice-builder.md)

## Manually installing the plugin

-   Copy over `main.js`, `styles.css`, `manifest.json` to your vault `VaultFolder/.obsidian/plugins/meld-build/`.

## About

Write and execute (sandboxed) JavaScript to render templates, query DataView and create dynamic notes.

### Resources

[Readme](https://github.com/meld-cp/obsidian-build#readme-ov-file)

### License

[MIT license](https://github.com/meld-cp/obsidian-build#MIT-1-ov-file)

[Activity](https://github.com/meld-cp/obsidian-build/activity)

### Stars

[**22** stars](https://github.com/meld-cp/obsidian-build/stargazers)

### Watchers

[**3** watching](https://github.com/meld-cp/obsidian-build/watchers)

### Forks

[**0** forks](https://github.com/meld-cp/obsidian-build/forks)