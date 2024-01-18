---
page-title: "rodrez/obsidian-harpoon"
url: https://github.com/rodrez/obsidian-harpoon
date: "2024-01-16 08:31:31"
---
# Obsidian Harpoon Plugin

An Obsidian plugin to manage and quickly navigate to your favorite files. This is a port of Harpoon (github.com/theprimeagen/harpoon) plugin for Obsidian.

[![Example Usage](https://github.com/rodrez/obsidian-harpoon/raw/main/sample.gif)](https://github.com/rodrez/obsidian-harpoon/blob/main/sample.gif)

If you find value in this plugin, I'd greatly appreciate it if you could show your support by giving a star to this repository. Alternatively, if you're feeling generous, you can also treat me to a coffee using the link below. Your contribution means a lot and helps in further development. Thank you!

[![Buy Me A Coffee](https://camo.githubusercontent.com/4412aa44a78a18c03862fd7da2de5bd81e3817a3adec90fdd41671170a206abd/68747470733a2f2f63646e2e6275796d6561636f666665652e636f6d2f627574746f6e732f64656661756c742d6f72616e67652e706e67)](https://www.buymeacoffee.com/devmask)

### [](https://github.com/rodrez/obsidian-harpoon#installation)Installation

Note: This assumes that you're already familiar with installing Obsidian plugins.

- Download the Harpoon Plugin
- Install it in your Obsidian vault as you would with any other plugin.

### [](https://github.com/rodrez/obsidian-harpoon#inital-setup)Inital Setup

I recommend for you to use your favorite keybindings to add/navigate files. After installation, the plugin will create a default configuration file named harpoon-config.json in your vault.

### [](https://github.com/rodrez/obsidian-harpoon#usage)Usage

- Open File List: This command opens a modal that lists the files you've hooked with Harpoon.
- Add File to List: Add the currently active file to the Harpoon list. Note: There's a limit of 4 files that can be added.
- Go To File: You can use one of the Go To File x commands (where x is a number from 1 to 4) to quickly jump to one of your hooked files.

### [](https://github.com/rodrez/obsidian-harpoon#keyboard-shortcuts)Keyboard Shortcuts

> Ctrl + Shift + D: Opens the modal.

While the Harpoon modal is open:

**Ctrl + Shift + D**: Close the modal.

**Enter**: Choose the file corresponding to the currently highlighted index.

**dd**: Quickly press twice to remove a file from the list.

**p**: Insert the last removed file just after the currently highlighted file.

**Shift + p**: Insert the last removed file just before the currently highlighted file

**ArrowDown or J**: Navigate downwards in the list. **ArrowUp or K**: Navigate upwards in the list.

### [](https://github.com/rodrez/obsidian-harpoon#tips)Tips

- Make sure not to manually delete the harpoon-config.json unless you're sure about it. It holds the configuration and list of hooked files for the plugin.
- The plugin is designed for quick navigation, so make use of keyboard shortcuts for efficient usage.

## [](https://github.com/rodrez/obsidian-harpoon#todos)Todos

- [ ]  Add scroll to pos (includes on initial load/refresh)
- [ ]  Add adjustable keybindings for Harpoon Modal? (maybe)