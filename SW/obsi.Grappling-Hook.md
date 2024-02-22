---
page-title: "chrisgrieser/grappling-hook: Obsidian Plugin for blazingly fast file switching. For those who find the Quick Switcher still too slow."
url: https://github.com/chrisgrieser/grappling-hook
date: "2024-01-18 00:12:31"
tags: 
    - A/sw/obsi/plugin
    - M/⭐
purpose: speed
---

## 🪝 Grappling Hook

[![Obsidian Downloads](https://camo.githubusercontent.com/e8e5a6346b2cf1345ae3c07c03f6f8bf697e47d83d035504c47681b0f64a72c0/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f64796e616d69632f6a736f6e3f6c6f676f3d6f6273696469616e26636f6c6f723d253233343833363939266c6162656c3d646f776e6c6f6164732671756572793d25323425354225323267726170706c696e672d686f6f6b2532322535442e646f776e6c6f6164732675726c3d68747470732533412532462532467261772e67697468756275736572636f6e74656e742e636f6d2532466f6273696469616e6d642532466f6273696469616e2d72656c65617365732532466d6173746572253246636f6d6d756e6974792d706c7567696e2d73746174732e6a736f6e267374796c653d706c6173746963)](https://camo.githubusercontent.com/e8e5a6346b2cf1345ae3c07c03f6f8bf697e47d83d035504c47681b0f64a72c0/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f64796e616d69632f6a736f6e3f6c6f676f3d6f6273696469616e26636f6c6f723d253233343833363939266c6162656c3d646f776e6c6f6164732671756572793d25323425354225323267726170706c696e672d686f6f6b2532322535442e646f776e6c6f6164732675726c3d68747470732533412532462532467261772e67697468756275736572636f6e74656e742e636f6d2532466f6273696469616e6d642532466f6273696469616e2d72656c65617365732532466d6173746572253246636f6d6d756e6974792d706c7567696e2d73746174732e6a736f6e267374796c653d706c6173746963) [![Last Release](https://camo.githubusercontent.com/93c94538f1ab721bb01c32ac005655d6fa43765a2712108f253f73a0a7806e17/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f762f72656c656173652f6368726973677269657365722f67726170706c696e672d686f6f6b3f6c6162656c3d4c617465737425323052656c65617365267374796c653d706c6173746963)](https://camo.githubusercontent.com/93c94538f1ab721bb01c32ac005655d6fa43765a2712108f253f73a0a7806e17/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f762f72656c656173652f6368726973677269657365722f67726170706c696e672d686f6f6b3f6c6162656c3d4c617465737425323052656c65617365267374796c653d706c6173746963)

Obsidian Plugin for blazingly fast file switching. For those who find the Quick Switcher still too slow. [Endorsed by Nick Milo.](https://youtu.be/mcrcRXp5d8A?t=462)

-   [Features](https://github.com/chrisgrieser/grappling-hook#features)
    -   [Bookmark Cycler](https://github.com/chrisgrieser/grappling-hook#bookmark-cycler)
    -   [Alternate Note](https://github.com/chrisgrieser/grappling-hook#alternate-note)
-   [Installation](https://github.com/chrisgrieser/grappling-hook#installation)
-   [About the developer](https://github.com/chrisgrieser/grappling-hook#about-the-developer)

## Features

### Bookmark Cycler

Goes to your most recently modified bookmarked note. If you are already at a bookmarked note, goes to the next bookmarked note, in order of the last modification date. This allows you to quickly cycle between a core set of files that are important. The command works well for workflows where you work with a dynamic core set of main notes and many auxiliary notes.

When you have text selected, the bookmark cycler switches to its alternative mode, and copies the selected text to the last modified bookmarked note, regardless the note you are.

> **Note**  
> Only bookmarked *files* are considered. Bookmarked *blocks* or *headers* are ignored.

[![Illustration bookmark cycler](https://github.com/chrisgrieser/grappling-hook/raw/main/illustration/bookmark-cycler.png)](https://github.com/chrisgrieser/grappling-hook/blob/main/illustration/bookmark-cycler.png) *This command is inspired by the [Harpoon plugin for neovim](https://github.com/ThePrimeagen/harpoon).*

### Alternate Note

Go to the last file you were at. As opposed to the `Navigate Back` command, using the `Switch to Alternate Note` command moves you forward in history when you press it the second time. This allows you to rapidly switch between two files with only one hotkey. The name of the alternate file is also displayed in the status bar.

[![Illustration alt-file](https://github.com/chrisgrieser/grappling-hook/raw/main/illustration/alt-file.png)](https://github.com/chrisgrieser/grappling-hook/blob/main/illustration/alt-file.png) *This command is an emulation of vim's `:buffer #`.*

## Installation

The plugin is available in Obsidian's Community Plugin Browser via: `Settings` → `Community Plugins` → `Browse` → Search for *"🪝 Grappling Hook"*

## About the developer

In my day job, I am a sociologist studying the social mechanisms underlying the digital economy. For my PhD project, I investigate the governance of the app economy and how software ecosystems manage the tension between innovation and compatibility. If you are interested in this subject, feel free to get in touch.

-   [Academic Website](https://chris-grieser.de/)
-   [ResearchGate](https://www.researchgate.net/profile/Christopher-Grieser)
-   [Discord](https://discordapp.com/users/462774483044794368/)
-   [GitHub](https://github.com/chrisgrieser/)
-   [Twitter](https://twitter.com/pseudo_meta)
-   [LinkedIn](https://www.linkedin.com/in/christopher-grieser-ba693b17a/)

[![Buy Me a Coffee at ko-fi.com](https://camo.githubusercontent.com/938f57e4b1f4ee91d585cbf7cb943e60b2381cc9a07317e2c18086b89fceb77c/68747470733a2f2f63646e2e6b6f2d66692e636f6d2f63646e2f6b6f6669312e706e673f763d33)](https://ko-fi.com/Y8Y86SQ91)