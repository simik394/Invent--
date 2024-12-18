---
page-title: "Fevol/obsidian-criticmarkup: Annotate notes with comments and suggestions using CriticMarkup in Obsidian"
url: https://github.com/Fevol/obsidian-criticmarkup
date: "2024-06-21 00:00:57"
tags: 
- A/sw/plugin
- F/homepage
- C/
- P/
about: 
- "[[Obsidian]]"
aliases: 
- bcc7f501-74fe-4dae-afb1-696a921b9136
- Fevolobsidian-criticmarkup Annotate notes with comments and suggestions using CriticMarkup in Obsidian
by: 
length: 3196
dir: 
---

## CriticMarkup plugin for Obsidian

[](https://github.com/Fevol/obsidian-criticmarkup#criticmarkup-plugin-for-obsidian)

A [CriticMarkup](https://github.com/CriticMarkup/CriticMarkup-toolkit) renderer for [Obsidian](https://obsidian.md/) for collaborative editing and reviewing your notes. Includes a suggestion mode for keeping track of changes, and a comment mode for easily leaving comments.

This plugin was built upon the excellent work and advice of @kometenstaub, the original repositories can be found here: [CriticMarkup plugin](https://github.com/kometenstaub/obsidian-criticmarkup) and [CriticMarkup parser](https://github.com/kometenstaub/lang-criticmarkup).

Roadmap for full product can be found below. No timeline will be given for when (and in which order) these features will be implemented. If features prove to be completely infeasible to implement, they will be removed from the roadmap.

The plugin *is* available for beta testing, but please keep in mind that you should not use this plugin in your main vault. There is a non-zero risk of text being removed when using e.g. the suggestion mode.

Please report any errors or bug you encounter, especially when these result in loss of data or cause crashes/malfuctions in Obsidian. In the [Obsidian Discord](https://discord.com/invite/obsidianmd), there is a thread under `Extensions > Plugin Advanced > Commentator`, you can report bugs there, or in the [Github issues page](https://github.com/Fevol/obsidian-criticmarkup/issues).

### Parser

[](https://github.com/Fevol/obsidian-criticmarkup#parser)

-   Parsing of CriticMarkup syntax (see [CriticMarkup parser library](https://github.com/Fevol/criticmarkup-parser/))
-   Parsing of annotations and extended syntax (see **Syntax**)
-   Improving resilience to invalid markup

### UIX

[](https://github.com/Fevol/obsidian-criticmarkup#uix)

#### Commands

[](https://github.com/Fevol/obsidian-criticmarkup#commands)

-   Mark selection as `Insertion`/`Deletion`/...
-   Accepting/Rejecting all changes in document
    -   Via command palette (entire document/selection)
    -   Via context menu (selection)
    -   Via gutter markings (line)

#### Extensions

[](https://github.com/Fevol/obsidian-criticmarkup#extensions)

-   Auto-close critic-markup brackets when typing
-   Automatically correct invalid markup
-   Automatically simplify dangling and (partially) empty markup

#### Suggestion View

[](https://github.com/Fevol/obsidian-criticmarkup#suggestion-view)

-   Vault-wide index of all suggestions and comments
    -   Automatically create/re-synchronize on vault opening
    -   Keep up-to-date with immediate changes in vault
-   Custom view for viewing suggestions and comments over entire vault
    -   Metadata rendering
    -   Filter by recency
    -   Filter by author (see also custom syntax)
    -   Performance improvements
    -   UIX/Scrolling improvements
    -   Accept/Close selection of suggestions and comments

#### Editor

[](https://github.com/Fevol/obsidian-criticmarkup#editor)

-   Preview of `Accept/Reject` commands in editor
-   Toggling suggestion mode on/off in editor
-   Toggling comment mode on/off in editor
-   Integration of toggles for suggestion mode, preview and comment mode with other community plugins
-   Specify suggestion/comment-only mode in frontmatter (based on authorship)

### Rendering

[](https://github.com/Fevol/obsidian-criticmarkup#rendering)

-   Rendering of markup in Live Preview
-   Rendering of markup in Reading View (Postprocessor)
-   Rendering comments
    -   In right-side gutter of document
    -   On hover in document

### Syntax

[](https://github.com/Fevol/obsidian-criticmarkup#syntax)

-   Extend CriticMarkup syntax to allow for authorship and timestamp annotation
-   Extend `Comment` markup to support comment threads
-   Allow custom highlight colours for `Highlight` markup

### Suggestion Mode

[](https://github.com/Fevol/obsidian-criticmarkup#suggestion-mode)

-   Converting edit operations into appropriate markings
-   Correct cursor placement through edit and cursor operations
    -   Support different options for cursor movement (always stop when markup encountered, ...)
    -   Full Vim Support
-   Toggle sequential CM state updating for improved multi-cursor support when inserting/deleting

### Comment Mode

[](https://github.com/Fevol/obsidian-criticmarkup#comment-mode)

-   Add comments to selection
-   Smooth cursor movement through markup