---
page-title: "liamcain/obsidian-creases: 👕 Tools for effectively folding markdown sections in Obsidian"
url: https://github.com/liamcain/obsidian-creases
date: "2024-02-21 00:56:08"
tags: A/sw/plugin
purpose:
---
[[Obsidian]]
## Creases 👕

Tools for efficiently folding markdown sections in Obsidian.

[![creases-overview](https://user-images.githubusercontent.com/693981/156103767-33f311de-39ac-422d-b8ea-987ea9c63f7b.png)](https://user-images.githubusercontent.com/693981/156103767-33f311de-39ac-422d-b8ea-987ea9c63f7b.png)

Add `%% fold %%` markers to "crease" your markdown. Then run **Fold along creases** to get your file into the state you want.

## ⚙️ Commands

### General Folding

-   **Fold headings by level** – Fold all headings in the correct document that match a given level (H1 - H6)
-   **Fold More** - Finds and folds the closest heading or list item.
-   **Fold less** - Finds and unfolds the closest heading or list item.

### Fold Levels

Creases also borrows the concept of a "fold level" from vim. The fold level is inferred from the current folds in the note. If have you have your `## Heading Level 2` headings folded, *decreasing* the fold level will unfold all headings up to `# Heading Level 1`. *Increasing* the fold level will unfold up to your `### Heading Level 3`.

-   **Increase heading fold level** - Increase the fold level by 1
-   **Decrease heading fold level** - Decrease the fold level by 1

### Working with "creases"

-   **Toggle Crease** – Crease/uncrease the current section that you're in
-   **Crease the current folds** – Applies a crease to the current folds in the file, allowing you to easily get back to these current folds using **fold along creases**.
-   **Fold along creases** – Fold all the creased sections of your file
-   **Iron out the creases** – Remove all the creases from the current file

## ➕ Additional Features

-   **Templates support** – If you use the *Templates* core plugin, any creases included in your template will automatically be folded.
-   **Templater support** – Add creases to your [Templater](https://github.com/SilentVoid13/Templater) templates to have content automatically folded.

## ⚡️ Example Workflows (aka "Has this ever happened to you?")

### Create a "save state" for your folds

If you're working on a long document, you might find yourself folding sections as you go. Now you want to do a "Find" in the fold. Uh oh, it found a match but now all your folded away content is unfolded.

Instead, save your folds as creases:

1.  Run "Crease the current folds" to mark all your current folds as *creased*.
2.  Search the document to your heart's content, unfolding without a care in the world.
3.  Run "Fold along creases" to restore all your folds to exactly how they were before.
4.  *Optional* Now that you're back to your ideal document origami, you can run "Iron out the creases" to get rid of the fold markers.

### You want content in your template to be folded by default.

Whether you use the core **Templates** plugin or **Templater**, you might find yourself wishing that some sections start folded since you don't look at them often.

1.  In your template file, just make sure that `%% fold %%` appears on the same line as the heading or list item that you want folded. You can also run the "Toggle crease" command from within the template to insert the crease automatically.

### You want to fold all the `### Level 3 Heading`s in your document

Folding all the headings at a given depth can be a tedious process. Well, no longer.

1.  Just run "Toggle fold for H3."

## 🎞 Credits

Special thanks **@mleo2003** on Discord for the plugin name.

## Say Thanks 🙏

If you like this plugin and would like to buy me a coffee, you can!

[![BuyMeACoffee](https://camo.githubusercontent.com/d01e495f6bfec179e89e34a7f60f1e1085cac9980774465403dacd2df175de16/68747470733a2f2f63646e2e6275796d6561636f666665652e636f6d2f627574746f6e732f76322f64656661756c742d76696f6c65742e706e67)](https://www.buymeacoffee.com/liamcain)

Like my work and want to see more like it? You can sponsor me.

[![GitHub Sponsors](https://camo.githubusercontent.com/649cc08cbe345e4f1aa8d4ed2c65baeb2728703d5195093b7eace324db035880/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f73706f6e736f72732f6c69616d6361696e3f7374796c653d736f6369616c)](https://github.com/sponsors/liamcain)