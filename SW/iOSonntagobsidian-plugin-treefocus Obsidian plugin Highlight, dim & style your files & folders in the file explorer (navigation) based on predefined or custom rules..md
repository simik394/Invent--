---
page-title: "iOSonntag/obsidian-plugin-treefocus: Obsidian plugin: Highlight, dim & style your files & folders in the file explorer (navigation) based on predefined or custom rules."
url: https://github.com/iOSonntag/obsidian-plugin-treefocus
date: "2024-04-08 20:11:30"
tags: 
- A/sw/plugin
- F/homepage
- C/
- P/
about: "[[Obsidian]]"
aliases: 
- db2253c5-f8ae-444a-ab85-87fd1aa58736
- iOSonntag/obsidian-plugin-treefocus: Obsidian plugin: Highlight, dim & style your files & folders in the file explorer (navigation) based on predefined or custom rules.
by: 
length: 2554
dir: 
---

## Obsidian Plugin: TreeFocus

[](https://github.com/iOSonntag/obsidian-plugin-treefocus#obsidian-plugin-treefocus)

[![Dynamic JSON Badge](https://camo.githubusercontent.com/5137d4777783fbc5d962b1da1ef853a580ddbf7a62e878ffbf94882f30861dd2/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f64796e616d69632f6a736f6e3f75726c3d68747470732533412532462532467261772e67697468756275736572636f6e74656e742e636f6d253246694f536f6e6e7461672532466f6273696469616e2d706c7567696e2d74726565666f6375732532466d61737465722532467061636b6167652e6a736f6e2671756572793d2532342e76657273696f6e266c6162656c3d76657273696f6e)](https://camo.githubusercontent.com/5137d4777783fbc5d962b1da1ef853a580ddbf7a62e878ffbf94882f30861dd2/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f64796e616d69632f6a736f6e3f75726c3d68747470732533412532462532467261772e67697468756275736572636f6e74656e742e636f6d253246694f536f6e6e7461672532466f6273696469616e2d706c7567696e2d74726565666f6375732532466d61737465722532467061636b6167652e6a736f6e2671756572793d2532342e76657273696f6e266c6162656c3d76657273696f6e) [![Dynamic JSON Badge](https://camo.githubusercontent.com/673ba039685865fd1f38bc6863d4a72cfab6920712e80bcf963ec6ae5c415a8f/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f64796e616d69632f6a736f6e3f75726c3d68747470732533412532462532467261772e67697468756275736572636f6e74656e742e636f6d253246694f536f6e6e7461672532466f6273696469616e2d706c7567696e2d74726565666f6375732532466d61737465722532466d616e69666573742e6a736f6e2671756572793d2532342e6964266c6162656c3d6f6273696469616e2d706c7567696e26636f6c6f723d72676228313234253243253230353825324325323032333729)](https://camo.githubusercontent.com/673ba039685865fd1f38bc6863d4a72cfab6920712e80bcf963ec6ae5c415a8f/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f64796e616d69632f6a736f6e3f75726c3d68747470732533412532462532467261772e67697468756275736572636f6e74656e742e636f6d253246694f536f6e6e7461672532466f6273696469616e2d706c7567696e2d74726565666f6375732532466d61737465722532466d616e69666573742e6a736f6e2671756572793d2532342e6964266c6162656c3d6f6273696469616e2d706c7567696e26636f6c6f723d72676228313234253243253230353825324325323032333729) [![Static Badge](https://camo.githubusercontent.com/981f0611678c6b006dafb3622a7fbaa81557214ce872d1a547e9b3b8287d4412/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f7374726963742d643f6c6162656c3d54797065536372697074)](https://camo.githubusercontent.com/981f0611678c6b006dafb3622a7fbaa81557214ce872d1a547e9b3b8287d4412/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f7374726963742d643f6c6162656c3d54797065536372697074) [![build](https://github.com/iOSonntag/obsidian-plugin-treefocus/actions/workflows/release.yml/badge.svg?branch=master)](https://github.com/iOSonntag/obsidian-plugin-treefocus/actions/workflows/release.yml)

### Ever wanted to (*dim*) a `File` or `Folder`?

[](https://github.com/iOSonntag/obsidian-plugin-treefocus#ever-wanted-to-dim-a-file-or-folder)

*For rarely used or unimportant `Files` or `Folders`.*

**Example:**

[![](https://github.com/iOSonntag/obsidian-plugin-treefocus/raw/master/resources/treefocus_dim_01.png?raw=true)](https://github.com/iOSonntag/obsidian-plugin-treefocus/blob/master/resources/treefocus_dim_01.png?raw=true)

-   `/_SYS/` (maybe for your template and attachment Folders)
-   `/some_dir/not_in_use/` (storing some irrelevant data)

### Or maybe **HIGHLIGHT** some `Files` and `Folders`?

[](https://github.com/iOSonntag/obsidian-plugin-treefocus#or-maybe-highlight-some-files-and-folders)

*For the good stuff.*

**Example:**

[![](https://github.com/iOSonntag/obsidian-plugin-treefocus/raw/master/resources/treefocus_highlight_01.png?raw=true)](https://github.com/iOSonntag/obsidian-plugin-treefocus/blob/master/resources/treefocus_highlight_01.png?raw=true)

-   `/Main/`
-   `/VeryImportantFolder_DoNotDelete_Plz/`

### Or any other imaginable config for your file explorer items?

[](https://github.com/iOSonntag/obsidian-plugin-treefocus#or-any-other-imaginable-config-for-your-file-explorer-items)

*✅ This plugin might do the trick!*

## TreeFocus - Intro

[](https://github.com/iOSonntag/obsidian-plugin-treefocus#treefocus---intro)

**Highlight**, **dim** & **style** your `Files` & `Folders` in the file explorer based on predefined or custom rules.

All your vault items in the left navigation panel can be styled. Either via

-   **matching rules** *or*
-   **explicitly set** via the item context menu

Every item in the file explorer evaluates to one of the following **TreeFocusModes**™ :

-   💡 `HIGHLIGHT`
-   🥱 `DIM`
-   🍆 `DEFAULT` (Obsidian default)

Then each item will be styled based on that **TreeFocusMode**™.

## Combine with other Plugins

[](https://github.com/iOSonntag/obsidian-plugin-treefocus#combine-with-other-plugins)

You like the **`Icon Folder`** plugin?  
Me too that is why this plugin is fully compatible with the plugin [Icon Folder (`obsidian-iconize`)](https://github.com/FlorianWoelki/obsidian-iconize).

> Hurray 🕺 🎊 🎉 !!!  
> Big shout out @ [FlorianWoelki](https://github.com/FlorianWoelki) for his awesome plugin.

## How it all works

[](https://github.com/iOSonntag/obsidian-plugin-treefocus#how-it-all-works)

*Example config result:*

[![](https://github.com/iOSonntag/obsidian-plugin-treefocus/raw/master/resources/treefocus_01.png?raw=true)](https://github.com/iOSonntag/obsidian-plugin-treefocus/blob/master/resources/treefocus_01.png?raw=true)

The screenshot is the result of choosing the

-   **Style Transformation Preset:** `Fancy`

and applying the following rules:

1.  **TreeFocusMode**™ - `DIM`  
    on all `Files` and `Folders` starting with `'_'`
    
2.  **TreeFocusMode**™ - `HIGHLIGHT`  
    on explicit selected items:
    
    -   `/Backend`
    -   `/More`

## Settings

[](https://github.com/iOSonntag/obsidian-plugin-treefocus#settings)

You can configure the behavior of this plugin by either defining general rules or explicitly set the **TreeFocusMode**™ per `File` / `Folder`.

[![](https://github.com/iOSonntag/obsidian-plugin-treefocus/raw/master/resources/settings_01.png?raw=true)](https://github.com/iOSonntag/obsidian-plugin-treefocus/blob/master/resources/settings_01.png?raw=true)

## Explicit Transformations: Configurations On Item Level

[](https://github.com/iOSonntag/obsidian-plugin-treefocus#explicit-transformations-configurations-on-item-level)

Right click on an item in the file explorer gives you options to explicitly apply **TreeFocusModes**™. This overwrites all defined rules and can be reset at any time.

[![](https://github.com/iOSonntag/obsidian-plugin-treefocus/raw/master/resources/context_menu_01.png?raw=true)](https://github.com/iOSonntag/obsidian-plugin-treefocus/blob/master/resources/context_menu_01.png?raw=true)

## Bugs

[](https://github.com/iOSonntag/obsidian-plugin-treefocus#bugs)

Please report any issues at: [TreeFocus - GitHub Repository](https://github.com/iOSonntag/obsidian-plugin-treefocus/issues)

## Contribution

[](https://github.com/iOSonntag/obsidian-plugin-treefocus#contribution)

Pull requests are **WELCOME** !

If you have improvements or feel like you can solve a bug, please do not hesitate to submit a pull requests.

**Even if you think you might not be skilled enough. That is pure bullsh\*t. We are all beginners - all the time :)**

## Support This Plugin

[](https://github.com/iOSonntag/obsidian-plugin-treefocus#support-this-plugin)

If you like this plugin and want to support it - submit a feature request, a pull request or simply buy me a little coffee :) - Thank You.

[![Buy Me A
Coffee](https://camo.githubusercontent.com/cace41b0afc90c68d0207e2bd809ee121f9ff4f72ac032e8ced972aee7adbb23/68747470733a2f2f63646e2e6275796d6561636f666665652e636f6d2f627574746f6e732f76322f64656661756c742d79656c6c6f772e706e67)](https://www.buymeacoffee.com/iOSonntag)

or direct via

-   [Buy Me A Coffee](https://www.buymeacoffee.com/iOSonntag)
-   [GitHub Sponsor](https://github.com/sponsors/iOSonntag)
-   [PayPal](https://paypal.com/paypalme/iOSonntag/20)
-   [Homepage](https://iosonntag.com/buy-me-a-coffe)

## DISCLAIMER

[](https://github.com/iOSonntag/obsidian-plugin-treefocus#disclaimer)

I do not own the **TreeFocusMode**™ nor the **TreeFocusModes**™ trade mark. This is pure parody on the stupidity of that trade mark. Developers do these kind of jokes :D - Have a great day!