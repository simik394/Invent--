---
page-title: "FlorianWoelki/obsidian-iconize: Simply add icons to anything you want in Obsidian."
url: https://github.com/FlorianWoelki/obsidian-iconize
date: "2024-04-08 20:10:00"
tags: 
- A/sw/plugin
- F/homepage
- C/
- P/
about: "[[Obsidian]]"
aliases: 
- 08690fc8-f99c-4399-9a9e-8ceddeaf50c0
- FlorianWoelki/obsidian-iconize: Simply add icons to anything you want in Obsidian.
by: 
length: 1417
dir: 
---

## Obsidian Iconize

[](https://github.com/FlorianWoelki/obsidian-iconize#obsidian-iconize)

[![Preview Image](https://github.com/FlorianWoelki/obsidian-iconize/raw/main/docs/preview-image.png)](https://github.com/FlorianWoelki/obsidian-iconize/blob/main/docs/preview-image.png)

## What is it?

[](https://github.com/FlorianWoelki/obsidian-iconize#what-is-it)

This obsidian plugin allows you to add **any** custom icon (of type `.svg`) or from an icon pack to anything you want.

Refer to the official documentation for more information: [https://florianwoelki.github.io/obsidian-iconize/](https://florianwoelki.github.io/obsidian-iconize/) about the plugin and its functionalities.

If you like this plugin, feel free to support the development by buying a coffee:

[![Buy Me A Coffee](https://camo.githubusercontent.com/cace41b0afc90c68d0207e2bd809ee121f9ff4f72ac032e8ced972aee7adbb23/68747470733a2f2f63646e2e6275796d6561636f666665652e636f6d2f627574746f6e732f76322f64656661756c742d79656c6c6f772e706e67)](https://www.buymeacoffee.com/florianwoelki)

## Key Highlights

[](https://github.com/FlorianWoelki/obsidian-iconize#key-highlights)

[Icons before file/folder name](https://florianwoelki.github.io/obsidian-iconize/files-and-folders/icon-before-file-or-folder.html), [Icons in notes](https://florianwoelki.github.io/obsidian-iconize/notes/icons-in-notes.html), [Icon above title](https://florianwoelki.github.io/obsidian-iconize/notes/title-icon.html), [Predefined icon packs](https://florianwoelki.github.io/obsidian-iconize/guide/icon-packs.html), [Icons in tabs](https://florianwoelki.github.io/obsidian-iconize/files-and-folders/icon-tabs.html), [Customizable settings](https://florianwoelki.github.io/obsidian-iconize/guide/settings.html), [Custom rules](https://florianwoelki.github.io/obsidian-iconize/files-and-folders/custom-rules.html), [Frontmatter integration](https://florianwoelki.github.io/obsidian-iconize/files-and-folders/use-frontmatter.html), [Change color of an individual icon](https://florianwoelki.github.io/obsidian-iconize/files-and-folders/individual-icon-color.html),

## Development

[](https://github.com/FlorianWoelki/obsidian-iconize#development)

To customize this project for your needs, you can clone it and then install all dependencies:

$ git clone https://github.com/FlorianWoelki/obsidian-iconize
$ cd obsidian-iconize
$ pnpm i

After the installation, you need to create a `env.js` file in the root directory. Fill the file with the following content:

export const obsidianExportPath \=
  '<path-to-obsidian-vault>/.obsidian/plugins/obsidian-iconize/';

Make sure you create the directory specified in that variable if it does not exist yet.

Afterwards, you can start the rollup dev server by using:

This command will automatically build the neccesary files for testing and developing on every change. Furthermore, it does copy all the necessary files to the plugin directory you specified.

Finally, you can customize the plugin and add it to your plugins.