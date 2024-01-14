# cMenu Plugin

[![cMenu-Plugin Downloads](https://camo.githubusercontent.com/65f28bb3f2fa94f23a64cdef6d2a854f955d21ec096127445d276f3dd0fc23e3/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f646f776e6c6f6164732f6368657461636869657a696b65757a6f722f634d656e752d506c7567696e2f746f74616c2e737667)](https://camo.githubusercontent.com/65f28bb3f2fa94f23a64cdef6d2a854f955d21ec096127445d276f3dd0fc23e3/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f646f776e6c6f6164732f6368657461636869657a696b65757a6f722f634d656e752d506c7567696e2f746f74616c2e737667) [![cMenu-Plugin Releases](https://camo.githubusercontent.com/0afacec1fea3da1c956cd8ff8b63a27f04bafcd28304ba4fbd7ef1c8de3b51d8/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f762f72656c656173652f6368657461636869657a696b65757a6f722f634d656e752d506c7567696e)](https://camo.githubusercontent.com/0afacec1fea3da1c956cd8ff8b63a27f04bafcd28304ba4fbd7ef1c8de3b51d8/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f762f72656c656173652f6368657461636869657a696b65757a6f722f634d656e752d506c7567696e)

[![](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/cMenu%20Demo%20Header.png)](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/cMenu%20Demo%20Header.png)

### [](https://github.com/chetachiezikeuzor/cMenu-Plugin#status-this-plugin-is-now-available-in-obsidian-plugin-store)Status: This plugin is now available in Obsidian plugin store

cMenu is a plugin that adds a minimal and user friendly text editor modal for a smoother writing/editing experience ✍🏽. This plugin makes text editing and firing commands easier for those that don't wish to configure a multitude of hotkeys.

## [](https://github.com/chetachiezikeuzor/cMenu-Plugin#demo)Demo

[![](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/cMenu.gif)](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/cMenu.gif)

## [](https://github.com/chetachiezikeuzor/cMenu-Plugin#ease-of-use)Ease of Use

This plugin was specifically designed for note-takers that want to have a simple text editor to aid in marking up their notes. cMenu solves the issue of having to memorize numerous hotkeys and/or use multiple key presses to get the desired markup. When you use cMenu, you'll only have to focus on writing!

## [](https://github.com/chetachiezikeuzor/cMenu-Plugin#how-it-works)How it Works

With the newest update of cMenu, you can add just about any command from Obsidian's command library onto the menu bar. By default, the menu bar will have the following commands: Toggle bold, Toggle italics, Toggle strikethrough, cMenu: Toggle Underline, cMenu: Toggle Superscript, cMenu: Toggle Subscript, Toggle code, cMenu: Toggle codeblock, and Toggle blockquote.

```js
"menuCommands": [
    {
      id: "cmenu-plugin:editor:toggle-bold",
      name: "cMenu: Toggle bold",
      icon: "bold-glyph",
    },
    {
      id: "cmenu-plugin:editor:toggle-italics",
      name: "cMenu: Toggle italics",
      icon: "italic-glyph",
    },
    {
      id: "cmenu-plugin:editor:toggle-strikethrough",
      name: "cMenu: Toggle strikethrough",
      icon: "strikethrough-glyph",
    },
    {
      id: "cmenu-plugin:underline",
      name: "cMenu: Toggle underline",
      icon: "underline-glyph",
    },
    {
      id: "cmenu-plugin:superscript",
      name: "cMenu: Toggle superscript",
      icon: "superscript-glyph",
    },
    {
      id: "cmenu-plugin:subscript",
      name: "cMenu: Toggle subscript",
      icon: "subscript-glyph",
    },
    {
      id: "cmenu-plugin:editor:toggle-code",
      name: "cMenu: Toggle code",
      icon: "code-glyph",
    },
    {
      id: "cmenu-plugin:codeblock",
      name: "cMenu: Toggle codeblock",
      icon: "codeblock-glyph",
    },
    {
      id: "cmenu-plugin:editor:toggle-blockquote",
      name: "cMenu: Toggle blockquote",
      icon: "quote-glyph",
    }
  ],
```

As you can see, cMenu adds four new commands to Obsidian's command library and modifies fourteen of Obsidian's text editing commands. Those commands are added to an array of commands that are then read within the generation of the cMenu modal. If you would like to remove and/or add new commands, you can do so within the cMenu settings panel. Use the bright button (your accent color) to add a new command onto the menu. And use the gret button to remove them from the menu. When you add/remove a new command, you will see a message in your console, indicating the status of said command. With the newest update [1.1.2](https://github.com/chetachiezikeuzor/cMenu-Plugin/releases/tag/1.1.2), ycMenu will reload everytime a command is added or deleted. No need for closing out your current notes,

[![](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/cMenu.gif)](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/cMenu.gif)

The plugins [Templater](https://github.com/SilentVoid13/Templater) and [Hotkeys for Templates](https://github.com/Vinzent03/obsidian-hotkeys-for-templates) are strongly recommended to use with cMenu. For example: I have a template that spawns the chess opening "Alekhine's Defense." With Hotkeys for Templates, I can choose to add this template to Obsidian's command library. Now that it's in the command library, I can choose to append this command to cMenu. This means you can really add just about anything to cMenu now, which makes it much more powerful!

[![](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/chesser%20cMenu.gif)](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/chesser%20cMenu.gif)

cMenu also has a few stylistic changes that are also customizeable. For those that use the plugin [Sliding Panes](https://github.com/deathau/sliding-panes-obsidian), you can now change cMenu's append method to "body." That way, cMenu will no longer appends to the workspace area, but to the body of the app. This is a bit of a work around for the current issue with [Sliding Panes](https://github.com/deathau/sliding-panes-obsidian) but I'm actively looking into a better solution.

[![](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/cMenu-sliding-panes.gif)](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/cMenu-sliding-panes.gif)

With cMenu, you can change the design aesthetic. Glass morphism is a pretty popular design trend so I thought "why not add this to cMenu?!" You can choose to have a "glass" style for cMenu, which gives it a unique look.

[![](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/glass-cMenu.gif)](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/glass-cMenu.gif)

## [](https://github.com/chetachiezikeuzor/cMenu-Plugin#cmenu-status-bar-menu)cMenu Status Bar Menu

With the new [1.1.0](https://github.com/chetachiezikeuzor/cMenu-Plugin/releases/tag/1.1.0) update, you can control to bottom value of cMenu, as well as toggle to hide cMenu and add/delete new command items. The delete button will remove the most recently added command.

[![](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/cMenu%20status%20bar%20menu.gif)](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/cMenu%20status%20bar%20menu.gif)

[![](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/cMenu.png)](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/cMenu.png)

## [](https://github.com/chetachiezikeuzor/cMenu-Plugin#installation)Installation

This plugin is now available in the community plugin store. You can install it from there and enable it. For a manual installation, you can download the necessary files and place them within your plugins folder.

---

## [](https://github.com/chetachiezikeuzor/cMenu-Plugin#changelog)Changelog

### [](https://github.com/chetachiezikeuzor/cMenu-Plugin#010---jul-27-2021)[0.1.0](https://github.com/chetachiezikeuzor/cMenu-Plugin/releases/tag/0.1.0) - Jul 27, 2021

##### [](https://github.com/chetachiezikeuzor/cMenu-Plugin#changed)Changed

- Interfaces are renamed to match plugin info
- Now uses `workspace.getActiveViewOfType(MarkdownView)` instead of `activeLeaf` for menu creation

---

### [](https://github.com/chetachiezikeuzor/cMenu-Plugin#020---aug-02-2021)[0.2.0](https://github.com/chetachiezikeuzor/cMenu-Plugin/releases/tag/0.2.0) - Aug 02, 2021

##### [](https://github.com/chetachiezikeuzor/cMenu-Plugin#changed-1)Changed

- Now uses `workspace.getActiveViewOfType(MarkdownView)` to store text selection

##### [](https://github.com/chetachiezikeuzor/cMenu-Plugin#fixed)Fixed

- cMenu appends to `.mod-vertical.mod-root` parent instead of `body` parent.
- cMenu left positioning is set by function that finds width dynamically on menu creation. [![](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/cMenu-v020.gif)](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/cMenu-v020.gif)

---

### [](https://github.com/chetachiezikeuzor/cMenu-Plugin#030---aug-02-2021)[0.3.0](https://github.com/chetachiezikeuzor/cMenu-Plugin/releases/tag/0.3.0) - Aug 02, 2021

##### [](https://github.com/chetachiezikeuzor/cMenu-Plugin#fixed-1)Fixed

- Fixed small [bug](https://github.com/chetachiezikeuzor/cMenu-Plugin/issues/3#issuecomment-891371471) that causes an extra resize handle to be created.

---

### [](https://github.com/chetachiezikeuzor/cMenu-Plugin#100---aug-11-2021)[1.0.0](https://github.com/chetachiezikeuzor/cMenu-Plugin/releases/tag/1.0.0) - Aug 11, 2021

##### [](https://github.com/chetachiezikeuzor/cMenu-Plugin#fixed-2)Fixed

- Fixed issue with Sliding Panes with a toggle-able append method setting. [![](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/cMenu-sliding-panes.gif)](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/cMenu-sliding-panes.gif)

##### [](https://github.com/chetachiezikeuzor/cMenu-Plugin#added)Added

- Added new glass morphism setting. [![](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/glass-cMenu.gif)](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/glass-cMenu.gif)
- Added new custom commands setting [![](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/chesser%20cMenu.gif)](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/chesser%20cMenu.gif)

---

### [](https://github.com/chetachiezikeuzor/cMenu-Plugin#101---aug-11-2021)[1.0.1](https://github.com/chetachiezikeuzor/cMenu-Plugin/releases/tag/1.0.1) - Aug 11, 2021

##### [](https://github.com/chetachiezikeuzor/cMenu-Plugin#added-1)Added

- Added more icons to command icon chooser

---

### [](https://github.com/chetachiezikeuzor/cMenu-Plugin#102---aug-13-2021)[1.0.2](https://github.com/chetachiezikeuzor/cMenu-Plugin/releases/tag/1.0.2) - Aug 13, 2021

##### [](https://github.com/chetachiezikeuzor/cMenu-Plugin#changed-2)Changed

- Removed most !importants for better custom styling

##### [](https://github.com/chetachiezikeuzor/cMenu-Plugin#added-2)Added

- Added a few more icons
- Added updates to UI

---

### [](https://github.com/chetachiezikeuzor/cMenu-Plugin#103---aug-13-2021)[1.0.3](https://github.com/chetachiezikeuzor/cMenu-Plugin/releases/tag/1.0.3) - Aug 13, 2021

##### [](https://github.com/chetachiezikeuzor/cMenu-Plugin#added-3)Added

- Added feather icons

---

### [](https://github.com/chetachiezikeuzor/cMenu-Plugin#110---aug-27-2021)[1.1.0](https://github.com/chetachiezikeuzor/cMenu-Plugin/releases/tag/1.1.0) - Aug 27, 2021

##### [](https://github.com/chetachiezikeuzor/cMenu-Plugin#added-4)Added

- Added new status bar menu for extra cMenu setting: Hide/Show buttons, Bottom value change [![](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/cMenu%20status%20bar%20menu.gif)](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/cMenu%20status%20bar%20menu.gif)
- Added modified text editing commands
    - Commands will maintain focus in editor after execution

---

### [](https://github.com/chetachiezikeuzor/cMenu-Plugin#112---sep-14-2021)[1.1.2](https://github.com/chetachiezikeuzor/cMenu-Plugin/releases/tag/1.1.2) - Sep 14, 2021

##### [](https://github.com/chetachiezikeuzor/cMenu-Plugin#added-5)Added

- Added [remix icons](https://remixicon.com/) for command customization (makes it a bit slow :/)
- Added reload function (button to execute and execution after add/delete)
- Added custom columns setting
- Added command reordering in settings [![](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/reorder_commands.gif)](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/reorder_commands.gif)
- Added command to hide/show cMenu [![](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/hide_show_command.gif)](https://raw.githubusercontent.com/chetachiezikeuzor/cMenu-Plugin/master/assets/hide_show_command.gif)
- Added [remove tags](https://github.com/chetachiezikeuzor/cMenu-Plugin/pull/23) functionality

---

## [](https://github.com/chetachiezikeuzor/cMenu-Plugin#checklist)Checklist

- [x]  Glassmorphism setting
    - [x]  Setting to toggle for glass effect with cMenu
- [x]  Fix to work with Sliding Panes (workaround)
    - [x]  Setting to toggle for cMenu to toggle to body instead of modroot
- [x]  Add custom commands to cMenu
    - [x]  Choose icons for commands without
- [x]  [Modify](https://github.com/chetachiezikeuzor/cMenu-Plugin/issues/11#issue-973612232) text editing commands
    - [x]  Maintain focus in editor
- [x]  Change cMenu [bottom value](https://www.reddit.com/r/ObsidianMD/comments/owlaaf/new_obsidian_plugin_cmenu/h8vkn0v?utm_source=share&utm_medium=web2x&context=3)
- [x]  [Hide/show](https://github.com/chetachiezikeuzor/cMenu-Plugin/issues/10#issue-971519914) cMenu
- [x]  Add more command icons (Remix Icons)
- [x]  Custom cMenu columns
    - [x]  Setting to customize cMenu columns (control number of command buttons per row on cMenu)
- [x]  Reload cMenu
    - [x]  Add reload after new command added and command deletion functions.
    - [x]  Add general reload button (runs reload function)
- [ ]  Identify if text has been [selected](https://github.com/chetachiezikeuzor/cMenu-Plugin/issues/11#issuecomment-901091701)
- [x]  Easy command button [reordering](https://github.com/chetachiezikeuzor/cMenu-Plugin/issues/9#issue-969667944)
- [ ]  cMenu workspaces/nested menu
- [ ]  Follow the cursor setting
    - [ ]  Setting to toggle for cMenu to follow mouse cursor

---

## [](https://github.com/chetachiezikeuzor/cMenu-Plugin#support)Support

If you like this plugin and are considering donating to support continued development, use the button below!

Created with ❤️ by Chetachi