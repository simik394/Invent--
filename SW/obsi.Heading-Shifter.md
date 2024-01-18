---
page-title: "k4a-l/obsidian-heading-shifter: Easily Shift and Change markdown headings."
url: https://github.com/k4a-l/obsidian-heading-shifter
date: "2024-01-18 02:50:17"
tags: obsi/plugin
purpose: headings
---

## Obsidian Heading Shifter

[![github workflow](https://camo.githubusercontent.com/97a715b8e9c93db431f5d058b9e2219f2f40a92d07032c99aea6e82da42895de/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f776f726b666c6f772f7374617475732f6b34612d6465762f6f6273696469616e2d68656164696e672d736869667465722f6a6573743f7374796c653d666f722d7468652d6261646765)](https://camo.githubusercontent.com/97a715b8e9c93db431f5d058b9e2219f2f40a92d07032c99aea6e82da42895de/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f776f726b666c6f772f7374617475732f6b34612d6465762f6f6273696469616e2d68656164696e672d736869667465722f6a6573743f7374796c653d666f722d7468652d6261646765) [![github release](https://camo.githubusercontent.com/373165aea52b9f2b2bef3848f7f297e92c4b2bc62257ed71ef6a83496cc056d3/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f762f72656c656173652f6b34612d6465762f6f6273696469616e2d68656164696e672d736869667465723f7374796c653d666f722d7468652d6261646765)](https://camo.githubusercontent.com/373165aea52b9f2b2bef3848f7f297e92c4b2bc62257ed71ef6a83496cc056d3/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f762f72656c656173652f6b34612d6465762f6f6273696469616e2d68656164696e672d736869667465723f7374796c653d666f722d7468652d6261646765) [!["Buy Me A Coffee"](https://camo.githubusercontent.com/12f516d86d600c89a6abd2326256045c27325ad7c8532c0d36772965a4923be0/68747470733a2f2f7777772e6275796d6561636f666665652e636f6d2f6173736574732f696d672f637573746f6d5f696d616765732f6f72616e67655f696d672e706e67)](https://www.buymeacoffee.com/kasahala)

Easily Shift and Change markdown headings.

## Why use this plugin

Obsidian links numerous markdown files to form knowledge. Daily rearrangement of links is important to create a good knowledge base.

The following situations often occur in this process.

1.  Cut out A part of File 1 to an independent File 2 and linked.
    -   Heading3 in file 1 is changed to Heading1 in file 2
2.  Incorporated the content of File 3 into a part of File 4
    -   Heading2 in file 3 is changed to Heading4 in file 4

With this plugin, you can change the Heading size (the number of `#`) in a batch instead of changing it manually.

## How to install

### From within Obsidian

You can activate this plugin within Obsidian by doing the following:

-   Open Settings > Community plugin
-   Make sure `Restricted mode` is off
-   Click Browse `community plugins`
-   Search for `Heading Shifter`
-   Click `Install` -> `Enable`

### Manual installation

Download directory(includes `main.js, manifest.json, styles.css`) from the latest release and put them into `<vault>/.obsidian/plugins/` folder.

## Features

### Apply Headings

[![Applying Heading Demo](https://raw.githubusercontent.com/k4a-dev/obsidian-heading-shifter/main/doc/attachment/applyingHeading.gif)](https://raw.githubusercontent.com/k4a-dev/obsidian-heading-shifter/main/doc/attachment/applyingHeading.gif)

#### Commands

Command

Description

Hotkey

Apply Heading 0

Change Current line to no heading.

\-

Apply Heading 1~6

Change Current line to heading 1~6.

\-

> It is useful to assign a hotkey such as `Ctrl + 0 ~ 6`

### Shift Headings

[![Headings Shift Demo](https://raw.githubusercontent.com/k4a-dev/obsidian-heading-shifter/main/doc/attachment/shiftHeadings.gif)](https://raw.githubusercontent.com/k4a-dev/obsidian-heading-shifter/main/doc/attachment/shiftHeadings.gif)

#### Settings

Setting

Description

Value(Default)

Lower limit of Heading

The lower Heading Size that will be decreased by the Heading Shift

0~6(1)

Enable override tab behavior

If true, Tab execute "Increase Headings" and Shift-Tab execute "Decrease Headings" [1](https://github.com/k4a-l/obsidian-heading-shifter#user-content-fn-2-51919e9016bade2d8937f375daff0a22)

boolean(false)

#### Commands

Command

Description

Hotkey

Increase Headings

Increase heading of selected lines(with heading)

Decrease Headings

Decrease heading of selected lines(with heading)

> It is useful to assign a hotkey such as `Ctrl + Shift + Left/Right`

-   `Increase Headings` is ineffective if selected lines contains less than `Lower limit of Heading`.
-   `Decrease Headings` is ineffective if selected lines contains more than heading 6.

### Insert Headings

#### Commands

Command

Description

Hotkey

Insert Heading at current level

Change current line headings to current level

Insert Heading at one level deeper

Change current line headings to current level + 1

Insert Heading at one level higher

Change current line headings to current level - 1

## Common Settings

Setting

Description

Value(Default)

Style to remove

If this style is at the beginning of a line, remove it and make it Headin

boolean(All true)

#### Use Case

Operate headings like an outliner like the following,

\# The Festival Myster -> hit "Apply 1"

This is a great document.

\## Chapter One -> hit "Insert deeper"

\### Prologue -> hit "Insert deeper"

The sun was setting over the horizon...

\### The Summer Festival -> hit "Insert current"

As the townspeople gathered in the town square...

\## Chapter Two -> hit "Insert higher"

\### The Mystery of the Missing Prize -> hit "Insert deeper"

As the summer festival came to a close...

If you want to make headings deeper or higher than 2, use "shift" or "apply".

## Loadmap

Nothing specific at this time.

## Contribute

Feel free to report issues or request features.

1.  May conflict with other plugin behavior [↩](https://github.com/k4a-l/obsidian-heading-shifter#user-content-fnref-2-51919e9016bade2d8937f375daff0a22)