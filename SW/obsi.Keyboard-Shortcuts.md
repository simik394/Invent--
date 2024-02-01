---
page-title: "ieviev/obsidian-keyboard-shortcuts: Quick snippets and navigation for Obsidian"
url: https://github.com/ieviev/obsidian-keyboard-shortcuts
date: "2024-01-18 02:46:14"
tags: A/sw/obsi/plugin
purpose: headings
---

## Quick snippets and navigation for Obsidian

-   Keyboard navigation up/down for headings
-   Configurable default code block and callout shortcuts
-   Copy code block via keyboard shortcut
-   Quick Switcher extensions

no keybinds are set on install, you have to configure them yourself

## List of commands:

-   Go to previous heading
-   Go to next heading
-   Select current heading block
-   Go to previous empty line
-   Go to next empty line
-   Copy Next Code Block
-   Copy Code Block
-   Search by Tag
-   Insert heading 4
-   Insert heading 5
-   Increase Heading level
-   Decrease Heading level
-   Insert Default Callout
-   Insert Code Block
-   Open Switcher with Tag 1

### Go to previous/next heading and Go to previous/next empty line

-   note: only works in edit mode

[![](https://github.com/ieviev/obsidian-keyboard-shortcuts/raw/main/_resources/obs-go-to-heading.gif?raw=true)](https://github.com/ieviev/obsidian-keyboard-shortcuts/blob/main/_resources/obs-go-to-heading.gif?raw=true)

### Select current heading block

-   Select current heading block: selects text until the next heading or end of document

[![](https://github.com/ieviev/obsidian-keyboard-shortcuts/raw/main/_resources/select-current-block.gif?raw=true)](https://github.com/ieviev/obsidian-keyboard-shortcuts/blob/main/_resources/select-current-block.gif?raw=true)

### Copy code block / Copy next code block

-   Copy code block: shows a list of code blocks and allows you to search and copy one of them
-   Copy next code block: copies the next code block, closest to the cursor

[![](https://github.com/ieviev/obsidian-keyboard-shortcuts/raw/main/_resources/obs-copying-codeblocks.gif?raw=true)](https://github.com/ieviev/obsidian-keyboard-shortcuts/blob/main/_resources/obs-copying-codeblocks.gif?raw=true)

### Switcher extensions

> NOTE: these require you to configure `Default modal command` in the plugin settings:

> For the following demos i used the [Another Quick Switcher plugin](https://github.com/tadashi-aikawa/obsidian-another-quick-switcher) which supports tags and set `Default modal command` to:

```
obsidian-another-quick-switcher:search-command_recent-search
```

#### Switcher extensions / Search by tag

Allows performing a 2-step search, first filtering notes by tag.

[![](https://github.com/ieviev/obsidian-keyboard-shortcuts/raw/main/_resources/obs-search-by-tag.gif?raw=true)](https://github.com/ieviev/obsidian-keyboard-shortcuts/blob/main/_resources/obs-search-by-tag.gif?raw=true)

#### Switcher extensions / Folded search by Tag

Tag search with:

-   Unfolding tags
-   AND queries

[![](https://github.com/ieviev/obsidian-keyboard-shortcuts/raw/main/_resources/folded-search-by-tag.gif?raw=true)](https://github.com/ieviev/obsidian-keyboard-shortcuts/blob/main/_resources/folded-search-by-tag.gif?raw=true)

#### Switcher extensions / Open switcher with Tag 1

Opens the switcher with the first tag in the file already added to the query.

[![](https://github.com/ieviev/obsidian-keyboard-shortcuts/raw/main/_resources/obs-with-tag-1.gif?raw=true)](https://github.com/ieviev/obsidian-keyboard-shortcuts/blob/main/_resources/obs-with-tag-1.gif?raw=true)

> NOTE 2: if you want to find the command id for another switcher command press ctrl+shift+i to open the developer console and run this line.

```
app.commands.listCommands().map(x => x.id);
```

[![](https://github.com/ieviev/obsidian-keyboard-shortcuts/raw/main/_resources/command-ids.png)](https://github.com/ieviev/obsidian-keyboard-shortcuts/blob/main/_resources/command-ids.png)

### Insert heading 4/5 / Insert code block / Insert callout

-   also moves the cursor inside the code block / to the title after using
-   the default language of the code block is configurable in settings
-   the default callout type is also configurable in settings

[![](https://github.com/ieviev/obsidian-keyboard-shortcuts/raw/main/_resources/obs-inserting-codeblocks-headings.gif?raw=true)](https://github.com/ieviev/obsidian-keyboard-shortcuts/blob/main/_resources/obs-inserting-codeblocks-headings.gif?raw=true)

## development

### dependencies

-   dotnet 6.0 sdk
-   npm

### \---

installing node and dotnet dependencies

compiling F# to js

publishing to dist/