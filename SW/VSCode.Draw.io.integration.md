---
page-title: Draw.io Integration - Visual Studio Marketplace
url: https://marketplace.visualstudio.com/items?itemName=hediet.vscode-drawio
date: 2024-01-18 02:32:00
tags:
  - sw/extension
purpose:
  - integration
integrates: "[[draw.io]]"
integrates_to: "[[VSCode]]"
---
## Draw.io VS Code Integration

[![](https://img.shields.io/static/v1?style=social&label=Sponsor&message=%E2%9D%A4&logo=GitHub&color&link=%3curl%3e)](https://github.com/sponsors/hediet) [![](https://img.shields.io/static/v1?style=social&label=Donate&message=%E2%9D%A4&logo=Paypal&color&link=%3curl%3e)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=ZP5F38L4C88UY&source=url) [![](https://img.shields.io/twitter/follow/hediet_dev.svg?style=social)](https://twitter.com/intent/follow?screen_name=hediet_dev)

This unofficial extension integrates [Draw.io](https://app.diagrams.net/) (also known as [diagrams.net](https://github.com/hediet/vscode-drawio/blob/HEAD/diagrams.net)) into VS Code.  
Mentioned in the official diagrams.net [blog](https://www.diagrams.net/blog/embed-diagrams-vscode).

## Features

-   Edit `.drawio`, `.dio`, `.drawio.svg` or `.drawio.png` files in the Draw.io editor.
    -   To create a new diagram, simply create an empty `*.drawio`, `*.drawio.svg` or `*.drawio.png` file and open it.
    -   `.drawio.svg` are valid `.svg` files that can be embedded in Github readme files! No export needed.
    -   `.drawio.png` are valid `.png` files! No export needed. You should use `.svg` though whenever possible - they look much better!
    -   To convert between different formats, use the `Draw.io: Convert To...` command.
-   Uses an offline version of Draw.io by default.
-   Multiple Draw.io themes are available.
-   Use Liveshare to collaboratively edit a diagram with others.
-   Nodes/edges can be linked with code spans.

## Demo

![](https://github.com/hediet/vscode-drawio/raw/HEAD/docs/demo.gif)

## Like it so far? You might also like my [open source](https://github.com/hediet/chrome-ext-github-monaco) [Chrome extension that enhances the Github markdown editor](https://chrome.google.com/webstore/detail/monaco-markdown-editor-fo/mmpbdjdnmhgkpligeniippcgfmkgkpnf)!

## Editing .drawio.svg/.drawio.png Files

You can directly edit and save `.drawio.svg` and `.drawio.png` files. These files are perfectly valid svg/png-images that contain an embedded Draw.io diagram. Whenever you edit such a file, the svg/png part of that file is kept up to date.

The logo of this extension is such a `.drawio.png` file that has been created with the extension itself!

![](https://github.com/hediet/vscode-drawio/raw/HEAD/docs/drawio-png.gif)

If diffs are important for you, you should prefer `.drawio` and avoid `.drawio.png` diagrams.

## Collaboratively Edit Or Present Diagrams

With version 1.0 of this extension, extensive support for [VS Code Liveshare](https://visualstudio.microsoft.com/de/services/live-share/) has been added. You can now edit or present your Draw.io diagrams remotely, while seeing each participant's cursor and selection! This can be used for discussing, reviewing or brainstorming diagrams. With Draw.io's freehand drawing tool and integrated LaTeX support, this extension becomes an advanced whiteboard solution that can be used for remote code interviews!

![](https://github.com/hediet/vscode-drawio/raw/HEAD/docs/liveshare-demo.gif)

*Internally, this extension synchronizes Draw.io diagrams with text documents. These text documents are shared by Liveshare. As Liveshare has no understanding of the text, modification conflicts might occur on simultaneous modifications.*

## Code Link Feature

In the status bar, you can enable or disable the code link feature. If it is enabled and you double click on a node whose label starts with `#`, you will perform a workspace search for a symbol matching the rest of the label.

If you have a node labeled `#MyClass` and a class of name `MyClass`, you will jump to its source if you double click the node!

**Please note that you have to open at least one file of the project that contains the symbol.** Otherwise, VS Code will not consider this project when searching for symbols. This file itself does not have to contain the symbol though.

Thanks to my latest github sponsors, this feature is open source and freely available now.

*TIP*: If you open the draw.io editor to the right side (i.e. the second editor column) and navigate to a symbol, the diagram will stay visible.

![](https://github.com/hediet/vscode-drawio/raw/HEAD/docs/demo-code-link.gif)

## Themes

**Available Draw.io Themes**

-   Theme "atlas"
    
    ![atlas](https://github.com/hediet/vscode-drawio/raw/HEAD/docs/theme-atlas.png)
-   Theme "Kennedy"
    
    ![Kennedy](https://github.com/hediet/vscode-drawio/raw/HEAD/docs/theme-Kennedy.png)
-   Theme "min"
    
    ![min](https://github.com/hediet/vscode-drawio/raw/HEAD/docs/theme-min.png)
-   Theme "dark"
    
    ![dark](https://github.com/hediet/vscode-drawio/raw/HEAD/docs/theme-dark.png)

## Associate `.svg` Files With The Draw.io Editor

By default, this extension only handles `*.drawio.svg` files. Add this to your VS Code `settings.json` file if you want to associate it with `.svg` files:

```
"workbench.editorAssociations": {
    "*.svg": "hediet.vscode-drawio-text",
}
```

You won't be able to edit arbitrary SVG files though - only those that have been created with Draw.io or this extension!

## Editing the Diagram and its XML Side by Side

You can open the same `*.drawio` file with the Draw.io editor and as xml file. They are synchronized, so you can switch between them as you like it. This is super practical if you want to use find/replace to rename text or other features of VS Code to speed up your diagram creation/edit process. Use the `View: Reopen Editor With...` command to toggle between the text or the Draw.io editor. You can open multiple editors for the same file. This does not make much sense for SVG files though, as the draw.io diagram is stored in its metadata.

![](https://github.com/hediet/vscode-drawio/raw/HEAD/docs/drawio-xml.gif)

## Contributors

-   Henning Dieterichs, [hediet](https://github.com/hediet) on Github (Main Contributor / Author)
-   Vincent Rouillé, [Speedy37](https://github.com/Speedy37) on Github

## See Also / Similar Extensions

-   [Draw.io](https://app.diagrams.net/) - This extension relies on the giant work of Draw.io. Their embedding feature enables this extension! This extension bundles a recent version of Draw.io.
-   [vscode-drawio](https://github.com/eightHundreds/vscode-drawio) by eightHundreds.

## Other Cool Extensions

If you like this extension, you might like [my other extensions](https://marketplace.visualstudio.com/search?term=henning%20dieterichs&target=VSCode) too:

-   **[Debug Visualizer](https://marketplace.visualstudio.com/items?itemName=hediet.debug-visualizer)**: An extension for visualizing data structures while debugging.
-   **[Real-Time Debugging](https://marketplace.visualstudio.com/items?itemName=hediet.realtime-debugging)**: This extension visualizes how your code is being executed.