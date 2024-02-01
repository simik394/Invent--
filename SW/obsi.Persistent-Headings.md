---
page-title: "ivan-lednev/obsidian-persistent-links: More robust internal links for Obsidian!"
url: https://github.com/ivan-lednev/obsidian-persistent-links
date: "2024-01-18 02:46:50"
tags: A/sw/obsi/plugin
purpose: headings
---

## Persistent Links

## Purpose

Suppose you have a file with backlinks to some of its headings or blocks. Normally if you move these linked-to headings and blocks, the links are going to break. The plugin tries to automatically update such links.

## How to use it

Once you've enabled the plugin, it will automatically update links when you cut and paste headings and blocks. Here is a demo: [![](https://github.com/ivan-lednev/obsidian-persistent-links/raw/master/persistent-links-demo.gif)](https://github.com/ivan-lednev/obsidian-persistent-links/blob/master/persistent-links-demo.gif)

If a file got updated in some other way, and you've noticed some broken links, you can use the "Repair links in file" command to fix them. The plugin will search through the metadata cache and try to find a file that contains the block or heading in the link.

## Limitations

-   Partially relies on internal Obsidian APIs, so it may break. If you noticed that, please create an issue
-   Automatically works only with cut & paste events
-   Only works with Wiki links

If you'd like the plugin to support other workflows, don't hesitate to create an issue: [https://github.com/ivan-lednev/obsidian-persistent-links/issues](https://github.com/ivan-lednev/obsidian-persistent-links/issues).

## Contribution

If you noticed a bug or thought of some way to improve the plugin, feel free to create an issue: [https://github.com/ivan-lednev/obsidian-persistent-links/issues](https://github.com/ivan-lednev/obsidian-persistent-links/issues).

Pull-requests are also welcome! If you want to contribute but don't know where to start, you can create an issue or write me an email: [bishop1860@gmail.com](mailto:bishop1860@gmail.com).

You can also support me by buying me a coffee:

[![Buy Me A Coffee](https://camo.githubusercontent.com/cace41b0afc90c68d0207e2bd809ee121f9ff4f72ac032e8ced972aee7adbb23/68747470733a2f2f63646e2e6275796d6561636f666665652e636f6d2f627574746f6e732f76322f64656661756c742d79656c6c6f772e706e67)](https://www.buymeacoffee.com/machineelf)