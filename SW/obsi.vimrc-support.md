---
page-title: "esm7/obsidian-vimrc-support: A plugin for the Obsidian.md note-taking software"
url: https://github.com/esm7/obsidian-vimrc-support
date: 2024-01-16 22:03:08
tags:
  - A/sw/obsi/plugin
qual.README: 75
---


Obsidian API: [obsidian-api/obsidian.d.ts at master · obsidianmd/obsidian-api · GitHub](https://github.com/obsidianmd/obsidian-api/blob/master/obsidian.d.ts)

obsi dev Docs: [Vault - Developer Documentation (obsidian.md)](https://docs.obsidian.md/Plugins/Vault)
# README %% fold %% 
## Obsidian Vimrc Support Plugin %% fold %%

[!["Buy Me A Coffee"](https://camo.githubusercontent.com/12f516d86d600c89a6abd2326256045c27325ad7c8532c0d36772965a4923be0/68747470733a2f2f7777772e6275796d6561636f666665652e636f6d2f6173736574732f696d672f637573746f6d5f696d616765732f6f72616e67655f696d672e706e67)](https://www.buymeacoffee.com/esm7)

This plugin loads a file of Vim commands from `VAULT_ROOT/.obsidian.vimrc`. For users of the Obsidian.md Vim mode, this is very useful for making various settings (most notably keymaps) persist.

Note that this plugin is **not** the Vim support of Obsidian -- that support is built-in and you can perfectly use Obsidian in Vim mode without this plugin. This plugin merely implements the ability to load a persistent configuration and adds a few extras.

## Maintainer Needed %% fold %%

While I am still around for some urgent fixes, especially when the plugin stops working due to Obsidian API changes API, I am no longer able to give it the attention it deserves.

Anyone who wishes to take over, please message me.

## Usage %% fold %%

First and foremost, make sure you have the Obsidian Vim key bindings turned on -- see Editor -> Vim key bindings.

Now to keep some of your Vim settings permanent, install this plugin and put a file named `.obsidian.vimrc` in your vault root. If you're using multiple vaults, you'll need this file on each one.

**For iOS/iPadOS users**, it's highly recommended to set "Paste from Other Apps" of Obsidian to Allow, so there won't be annoying popups.

Here's a simple & useful `.obsidian.vimrc` that I'm using:

" Have j and k navigate visual lines rather than logical ones
nmap j gj
nmap k gk
" I like using H and L for beginning/end of line
nmap H ^
nmap L $
" Quickly remove search highlights
`nmap <F9> :nohl`
" Yank to system clipboard
set clipboard=unnamed
" Go back and forward with Ctrl+O and Ctrl+I
" (make sure to remove default Obsidian shortcuts for these to work)
exmap back obcommand app:go-back
`nmap <C-o> :back`
exmap forward obcommand app:go-forward
`nmap <C-i> :forward`

## Supported Commands %% fold %%

The commands that can be used are whatever CodeMirror supports. I couldn't find a formal list anywhere but you can look for `defaultExCommandMap` in [the source code](https://github.com/replit/codemirror-vim/blob/master/src/vim.js), or play around with trying commands in Obsidian's Vim mode.

In addition to that:

-   The plugin skips blank lines and lines starting with Vimscript comments (`" ...`).
-   Special support for yanking to system clipboard can be activated by `set clipboard=unnamed` (`unnamedplus` will do the same thing).
-   Support for the `tabstop` Vim option (e.g. `set tabstop=4`).
-   Custom mapping/unmapping commands in addition to the defaults:
    -   `noremap`
    -   `iunmap`
    -   `nunmap`
    -   `vunmap`
    -   PRs are welcome to implement more :)
-   `exmap [commandName] [command...]`: a command to map Ex commands. This should basically be supported in regular `:map`, but doesn't work with multi-argument commands due to a CodeMirror bug, so this is a workaround.
-   `obcommand` - execute Obsidian commands, see more details below.
-   `cmcommand` - execute arbitrary CodeMirror commands, see details below.
-   `surround` - surround your selected text in visual mode or word in normal mode with text.
-   `pasteinto` - paste your current clipboard into your selected text in visual mode or word in normal mode. Useful for creating hyperlinks.
-   `jscommand` and `jsfile` - extend Vim mode using JavaScript snippets.
-   `source` - loads Vim commands from a file (relative to the vault root).

Commands that fail don't generate any visible error for now.

**Important tip!** Before adding commands to your Vimrc file, you should try them in Obsidian's normal mode (type '`:`' in the editor) to make sure they work as expected. CodeMirror's Vim mode has some limitations and bugs and not all commands will work like you'd expect. In some cases you can find workarounds by experimenting, and the easiest way to do that is by trying interactively rather than via the Vimrc file.

## Installation %% fold %%

In the Obsidian.md settings under "Community plugins", click on "Turn on community plugins", then browse to this plugin.

Alternatively (and less recommended), you can install it manually: just copy `main.js` and `manifest.json` to your vault `VaultFolder/.obsidian/plugins/obsidian-vimrc-support/`.

## Support the Development %% fold %%

If you want to support the development of this plugin, please consider to [buy me a coffee](https://www.buymeacoffee.com/esm7).

## "Please implement someVimfeaturehere..."

I'd like to emphasize again that this plugin is a tweak to Obsidian's built-in Vim mode, which is in turn mostly the [Vim mode of CodeMirror](https://codemirror.net/demo/vim.html). And while I am personally very fond of helping everybody make use of Vim modes everywhere, this plugin is often not the best place to implement some types of features.

1.  Vim editor features (e.g. new motions) would best be implemented in CodeMirror, so other editors using this component would enjoy them too! Please consider submitting issues or pull requests [there](https://github.com/codemirror/CodeMirror/) first.
2.  Features that are already implemented by other Obsidian plugins are best to stay in these plugins. Please consider asking these plugin authors to add Vim support for their features (using the CodeMirror API), or even better -- help them out :)

Having said that, adding features here in this plugin is often very easy thanks to the CodeMirror [API for extending its Vim mode](https://codemirror.net/doc/manual.html#vimapi_extending), so as the path of least resistance I will occassionally implement some requested Vim features and be happy to accept PRs.

Things I'd love to add:

-   Implement some standard `vim-markdown` motions for Obsidian, e.g. `[[`, or implement for CodeMirror the 1-2 missing Ex commands required to define these keymaps in the Vimrc.

## Change Vimrc File Location/Name %% fold %%

If you want the Vimrc file name or path to be different than the default, there is a plugin setting (under Settings | Plugin Options | Vimrc Support) to change that.

## Executing Obsidian Commands with `obcommand`

The plugin defines a custom Ex command named `obcommand` to execute various Obsidian commands as an Ex command. This is useful to map external functionality of Obsidian or other plugins to Vim shortcuts, but it's not as easy to use as one would hope.

If you just type `:obcommand` you'll get in the Developer Console (Ctrl+Shift+I) the list of commands that are currently defined by the app. The simple syntax `:obcommand [commandName]` will execute the named command.

Some useful examples:

-   `obcommand editor:insert-link`
-   `obcommand editor:toggle-comment`
-   `obcommand app:go-back`
-   `obcommand workspace:split-vertical`

And many more.

**WARNING:** this is not a formal API that Obsidian provides and is done in a rather hacky manner. It's definitely possible that some future version of Obsidian will break this functionality.

### Mapping Obsidian Commands Within Vim

Next thing you probably wanna ask is "how do I map the great Obsidian commands to Vim commands?"

The trivial answer should have been something along the line of `:nmap <C-o> :obcommand app:go-back`, but this **does not work** because of an annoying CodeMirror bug. Turns out that the various mapping commands of CodeMirror pass only the first argument, so when you execute your mapping if defined as above, `:obcommand` would execute with no arguments.

Here comes a custom command to the rescue, `exmap`, which you can use to "alias" Ex commands for longer Ex commands: `:exmap back obcommand app:go-back`. You now have a simple (0 argument) Ex command named `back` that goes back in Obsidian, and *that* is something you can map.

To summarize, here's how you map `C-o` to Back:

```
exmap back obcommand app:go-back
nmap <C-o> :back
```

Note how `exmap` lists command names without colons and in `nmap` the colon is required.

## Surround Text with `surround`

The plugin defines a custom Ex command named `surround` to surround either your currently selected text in visual mode or the word your cursor is over in normal mode with text. This is useful for Vim users who are used to the `vim-surround` plugin.

The syntax follows `:surround [prefixText] [postfixText]`.

Some examples:

-   `surround ( )`
-   `surround " "`
-   `surround [[ ]]`

Here's an example config that implements many of the features from vim-surround:

```
exmap surround_wiki surround [[ ]]
exmap surround_double_quotes surround " "
exmap surround_single_quotes surround ' '
exmap surround_backticks surround ` `
exmap surround_brackets surround ( )
exmap surround_square_brackets surround [ ]
exmap surround_curly_brackets surround { }

" NOTE: must use 'map' and not 'nmap'
map [[ :surround_wiki
nunmap s
vunmap s
map s" :surround_double_quotes
map s' :surround_single_quotes
map s` :surround_backticks
map sb :surround_brackets
map s( :surround_brackets
map s) :surround_brackets
map s[ :surround_square_brackets
map s[ :surround_square_brackets
map s{ :surround_curly_brackets
map s} :surround_curly_brackets
```

Usage:

1.  Select some text in visual mode, then press `s` and then the desired surround character. e.g. `s"` to surround the selected text with double quotes.
2.  Place your cursor over a word in normal mode, then press `s` and then the desired surround character. e.g. `s"` to surround the word with double quotes.

## Inserting Links/Hyperlinks with `pasteinto`

The plugin defines a custom Ex command named `pasteinto` to paste text into your currently selected text in visual mode, or the word your cursor is over in normal mode. This is particularly useful for creating links/hyperlinks `[selected-text](paste)`.

Here's my hyperlink config as an example:

```
" Maps pasteinto to Alt-p
map <A-p> :pasteinto
```

## Some Help with Binding Space Chords (Doom and Spacemacs fans) %% fold %%

`<Space>` can be bound to make chords, such as `<Space>fs` in conjunction with obcommand to save your current file and more. But first `<Space>` must be unbound with `unmap <Space>`. Afterwards `<Space>` can be mapped normally as any other key.

## Emulate Common Vim Commands via Obsidian commands

Using `obcommand`, it is possible to emulate some additional Vim commands that aren't included in Obsidian's Vim mode, like for example `gt` and `zo`.

" Emulate Folding https://vimhelp.org/fold.txt.html#fold-commands
exmap togglefold obcommand editor:toggle\-fold
nmap zo :togglefold
nmap zc :togglefold
nmap za :togglefold
exmap unfoldall obcommand editor:unfold-all
nmap zR :unfoldall
exmap foldall obcommand editor:fold-all
nmap zM :foldall
" Emulate Tab Switching https://vimhelp.org/tabpage.txt.html#gt
" requires Cycle Through Panes Plugins https://obsidian.md/plugins?id=cycle-through-panes
exmap tabnext obcommand cycle-through-panes:cycle-through-panes
nmap gt :tabnext
exmap tabprev obcommand cycle-through-panes:cycle-through-panes-reverse
nmap gT :tabprev

## Fixed Keyboard Layout in Normal Mode %% fold %%

In many languages and keyboard layouts it becomes problematic or plain impossible to use Vim keys. The Vim keys are located in different positions on some keyboard layouts, which could be confusing when switching layouts, and on some layouts (e.g. non-Western languages) the keys for Vim movements just don't exist. To be able to use Vim mode with those layouts & languages, you can turn on the "fixed keyboard layout" feature in the plugin settings.

When turned on for the first time, or when you click "capture current layout", your current keyboard layout is saved, and that will be the layout that is used when you are in Vim normal or visual mode. When you enter insert mode, you will type in your actual current system layout/language.

**This feature is experimental and may have unintended side-effects relating to Obsidian or editor shortcuts.**

## Relative Line Numbers %% fold %%

Relative line numbers work very nicely with [this](https://github.com/nadavspi/obsidian-relative-line-numbers) Obsidian plugin (thank you @piotryordanov for bringing it to my attention!)

## Extending Vim Commands with JavaScript Snippets

The plugin allows to define Vim commands that map to JavaScript snippets, which adds exciting new possibilities to what you can achieve with Vim key bindings. **But -- this comes with a price of a security risk, and is therefore disabled by default.**

> ⚠️ **Security Warning**
> 
> Before using this feature, you **must be sure** that you understand its potential security implications.
> 
> Running JavaScript snippets with Vim commands stored in your vault means that anyone who gains access to your notes can run arbitrary code inside your Obsidian app.

If you understand the risks and choose to use this feature, turn on "Support JS Commands" in the plugin settings and continue reading.

### JavaScript Command Usage

There are two ways to define JS-based commands.

**The `jscommand` Ex command** defines a JS function that has an `editor: Editor`, a `view: MarkdownView` and a `selection: EditorSelection` arguments (see the [Obsidian API](https://github.com/obsidianmd/obsidian-api/blob/master/obsidian.d.ts) if you're not sure what these are). You define only the body of the function, in a single line wrapped by curly braces, e.g.:

```
jscommand { console.log(editor.getCursor()); }
```

This will immediately log your current cursor position to the developer console. If you want, you can make this an Ex command using `exmap`:


```
exmap logCursor jscommand { console.log(editor.getCursor()); }
nmap <C-q> :logCursor
```

Another version of the same functionality is **the `jsfile` Ex command**, which executes code from a file you give as a parameter, then appends another optional piece of code to it (e.g. in case you want to store several helper methods in a file and launch different ones as part of different commands).

As above, the code running as part of `jsfile` has the arguments `editor: Editor`, `view: MarkdownView` and `selection: EditorSelection`.

Here's an example from my own `.obsidian.vimrc` that maps `]]` and `[[` to jump to the next/previous Markdown header:

```
exmap nextHeading jsfile mdHelpers.js {jumpHeading(true)}
exmap prevHeading jsfile mdHelpers.js {jumpHeading(false)}
nmap ]] :nextHeading
nmap [[ :prevHeading
```

See [here](https://github.com/esm7/obsidian-vimrc-support/blob/master/JsSnippets.md) for the full example, and please contribute your own!

### Custom Styles for Status Bar %% fold %% 

You may utilize the vim mode display prompt class and the `data-vim-mode` attribute to add styles to the status bar prompt (e.g. assign colors for different status). You can also toggle the setting in settings page to also apply the display prompt class to the entire status bar container if you want some customizations on it.

The display prompt class: `vimrc-support-vim-mode`

The `data-vim-mode` values:

Mode

Data Value (`data-vim-mode`)

normal

`normal`

insert

`insert`

visual

`visual`

replace

`replace`

#### Powerline Styling Snippet

**Screenshots**

[![Screen Shot 2023-04-09 at 19 19 53](https://user-images.githubusercontent.com/11176415/230812728-731e24d3-d667-478c-831c-14e0010e7973.png)](https://user-images.githubusercontent.com/11176415/230812728-731e24d3-d667-478c-831c-14e0010e7973.png)

[![Screen Shot 2023-04-09 at 19 20 09](https://user-images.githubusercontent.com/11176415/230812731-26ba0c02-1948-4a26-89d2-3e73a11076d1.png)](https://user-images.githubusercontent.com/11176415/230812731-26ba0c02-1948-4a26-89d2-3e73a11076d1.png)

[![Screen Shot 2023-04-09 at 19 20 22](https://user-images.githubusercontent.com/11176415/230812734-f51a01c9-5f80-4da7-b051-04018cc805cc.png)](https://user-images.githubusercontent.com/11176415/230812734-f51a01c9-5f80-4da7-b051-04018cc805cc.png)

[![Screen Shot 2023-04-09 at 19 20 37](https://user-images.githubusercontent.com/11176415/230812736-6fa688db-37b9-4b70-bacb-a6553b0762cb.png)](https://user-images.githubusercontent.com/11176415/230812736-6fa688db-37b9-4b70-bacb-a6553b0762cb.png)

```
div.status-bar-item.plugin-obsidian-vimrc-support {
  /\* Papercolor theme \*/
  \--text-color-normal: #585858;
  \--text-color-insert: #005f87;
  \--text-color-visual: white;
  \--text-color-replace: white;

  \--background-color-normal: #eeeeee;
  \--background-color-insert: #eeeeee;
  \--background-color-visual: #d75f00;
  \--background-color-replace: #d70087;
}

div.status-bar-item.plugin-obsidian-vimrc-support {
  /\* 
    Move to bottom left corner and discard top/left/bottom space
    from container paddings.
   \*/
  order: \-9999;
  margin: \-4px auto \-5px \-5px;

  /\* 
    We have the :after pseudo-element next, so padding-right
    is not needed
    \*/
  padding-right: 0px;
  padding-left: 1em;

  /\* Use Monospace font \*/
  font-family: 'MesloLGM Nerd Font Mono'; /\* !!! Needs to be a powerline font \*/
  font-weight: bold;
  font-size: 1.2em;

  /\* Clear spaces made from radius borders \*/
  border-top-right-radius: 0px;
  border-bottom-right-radius: 0px;
}

div.status-bar-item.plugin-obsidian-vimrc-support:after {
  /\* Powerline separator character \*/
  content: '';
  position: relative;
  font-size: 1.5rem;
  left: 0.9rem;

  /\* Fine adjust the position \*/
  margin-top: 0.1rem;
}

/\* Normal \*/
div.status-bar-item.vimrc-support-vim-mode\[data-vim-mode\="normal"\]:after {
  color: var(\--background-color-normal);
}
div.status-bar-item.vimrc-support-vim-mode\[data-vim-mode\="normal"\] {
  color: var(\--text-color-normal);
  background-color: var(\--background-color-normal);
}

/\* Insert \*/
div.status-bar-item.vimrc-support-vim-mode\[data-vim-mode\="insert"\]:after {
  color: var(\--background-color-insert);
}
div.status-bar-item.vimrc-support-vim-mode\[data-vim-mode\="insert"\] {
  color: var(\--text-color-insert);
  background-color: var(\--background-color-insert);
}

/\* Visual \*/
div.status-bar-item.vimrc-support-vim-mode\[data-vim-mode\="visual"\]:after {
  color: var(\--background-color-visual);
}
div.status-bar-item.vimrc-support-vim-mode\[data-vim-mode\="visual"\] {
  color: var(\--text-color-visual);
  background-color: var(\--background-color-visual);
}

/\* Replace \*/
div.status-bar-item.vimrc-support-vim-mode\[data-vim-mode\="replace"\]:after {
  color: var(\--background-color-replace);
}
div.status-bar-item.vimrc-support-vim-mode\[data-vim-mode\="replace"\] {
  color: var(\--text-color-replace);
  background-color: var(\--background-color-replace);
}
```

Note that the above snippet uses powerline glygh for the triangular shape, so you need to install a [powerline font](https://github.com/powerline/fonts) to display correctly. And of course, feel free to change the CSS variables to whatever color palette you want!

## Changelog %% fold %%


# js-snippets %% fold %% 
## obsidian-vimrc-support/JsSnippets.md at master · esm7/obsidian-vimrc-support · GitHub
[online](https://github.com/esm7/obsidian-vimrc-support/blob/master/JsSnippets.md)
date: "2024-03-04 19:33:38"

## Useful JS Snippets for `jscommand` and `jsfile`

[](https://github.com/esm7/obsidian-vimrc-support/blob/master/JsSnippets.md#useful-js-snippets-for-jscommand-and-jsfile)

In this document I will collect some of my and user-contributed ideas for how to utilize JS commands in the Vimrc plugin.

If you have interesting snippets, please contribute by opening a pull request!

## Jump to Next/Prev Markdown Header

[](https://github.com/esm7/obsidian-vimrc-support/blob/master/JsSnippets.md#jump-to-nextprev-markdown-header)

To map `]]` and `[[` to next/prev markdown header, I use the following.

In a file I call `mdHelpers.js`, put this:

// Taken from https://stackoverflow.com/questions/273789/is-there-a-version-of-javascripts-string-indexof-that-allows-for-regular-expr

function regexIndexOf(string, regex, startpos) {
    var indexOf \= string.substring(startpos || 0).search(regex);
    return (indexOf \>= 0) ? (indexOf + (startpos || 0)) : indexOf;
}

function regexLastIndexOf(string, regex, startpos) {
    regex \= (regex.global) ? regex : new RegExp(regex.source, "g" + (regex.ignoreCase ? "i" : "") + (regex.multiLine ? "m" : ""));
    if(typeof (startpos) \== "undefined") {
        startpos \= string.length;
    } else if(startpos < 0) {
        startpos \= 0;
    }
    var stringToWorkWith \= string.substring(0, startpos + 1);
    var lastIndexOf \= \-1;
    var nextStop \= 0;
    while((result \= regex.exec(stringToWorkWith)) != null) {
        lastIndexOf \= result.index;
        regex.lastIndex \= ++nextStop;
    }
    return lastIndexOf;
}

function jumpHeading(isForward) {
	const editor \= view.editor;
	let posToSearchFrom \= editor.getCursor();
	posToSearchFrom.line += isForward ? 1 : \-1;
	const cursorOffset \= editor.posToOffset(posToSearchFrom);
	const lookupToUse \= isForward ? regexIndexOf : regexLastIndexOf;
	let headingOffset \= lookupToUse(editor.getValue(), /^#(#\*) /gm, cursorOffset);
	// If not found from the cursor position, try again from the document beginning (or reverse beginning)
	if (headingOffset \=== \-1)
		headingOffset \= lookupToUse(editor.getValue(), /^#(#\*) /gm);
	const newPos \= editor.offsetToPos(headingOffset);
	editor.setCursor(newPos);
}

Then in your `.obsidian.vimrc` file add the following:

```
exmap nextHeading jsfile mdHelpers.js {jumpHeading(true)}
exmap prevHeading jsfile mdHelpers.js {jumpHeading(false)}
nmap ]] :nextHeading
nmap [[ :prevHeading
```

## Vimwiki-like link navigation

[](https://github.com/esm7/obsidian-vimrc-support/blob/master/JsSnippets.md#vimwiki-like-link-navigation)

This snippet allows to navigate next/previous links with Tab/Shift+Tab.

It mimicks the behaviour of vimwiki keybindings where you would press Tab several times to get to the link you want.

Append this function to the file mentioned above (after jumpHeading).

function jumpNextLink(isForward) {
	const editor \= view.editor;
	let posToSearchFrom \= editor.getCursor();
	posToSearchFrom.line += isForward ? 0 : \-1;
	const cursorOffset \= editor.posToOffset(posToSearchFrom);
	const lookupToUse \= isForward ? regexIndexOf : regexLastIndexOf;
	let headingOffset \= lookupToUse(editor.getValue(), /\\\[\\\[/g, cursorOffset);
	// If not found from the cursor position, try again from the document beginning (or reverse beginning)
	if (headingOffset \=== \-1)
		headingOffset \= lookupToUse(editor.getValue(), /\\\[\\\[/g);
	const newPos \= editor.offsetToPos(headingOffset+2);
	editor.setCursor(newPos);
}

Then put these lines in vimrc file to set the keybindings. Optionally (as in vimwiki) you can have ENTER bound to follow the link.

```
exmap nextLink jsfile mdHelpers.js {jumpNextLink(true)}
exmap prevLink jsfile mdHelpers.js {jumpNextLink(false)}
nmap <Tab> :nextLink
nmap <S-Tab> :prevLink

exmap followlink obcommand editor:follow-link
nmap <CR> :followlink
```
# obcommands 
## 1
advanced-paste:advpaste-debug
advanced-paste:default
advanced-paste:joinLines
advanced-paste:rawHTML
advanced-paste:removeBlankLines
advanced-paste:smartJoin
app:delete-file
app:go-back
app:go-forward
app:open-help
app:open-sandbox-vault
app:open-settings
app:open-vault
app:reload
app:show-debug-info
app:show-release-notes
app:toggle-default-new-pane-mode
app:toggle-left-sidebar
app:toggle-right-sidebar
auto-card-link:auto-card-link-enhance-selected-url
auto-card-link:auto-card-link-paste-and-enhance
Available commands: editor:save-file
backlink:open
backlink:open-backlinks
backlink:toggle-backlinks-in-document
bookmarks:bookmark-all-tabs
bookmarks:bookmark-current-heading
bookmarks:bookmark-current-search
bookmarks:bookmark-current-section
bookmarks:bookmark-current-view
bookmarks:open
bookmarks:unbookmark-current-view
boost-link-suggestions:add-file-link
breadcrumbs:global-index
breadcrumbs:jump-to-first-down
breadcrumbs:jump-to-first-next
breadcrumbs:jump-to-first-prev
breadcrumbs:jump-to-first-up
breadcrumbs:local-index
breadcrumbs:manipulate-hierarchy-notes
breadcrumbs:new-file-with-curr-as--> Project
breadcrumbs:new-file-with-curr-as-about
breadcrumbs:new-file-with-curr-as-answers_to
breadcrumbs:new-file-with-curr-as-down
breadcrumbs:new-file-with-curr-as-extends
breadcrumbs:new-file-with-curr-as-extensible_by
breadcrumbs:new-file-with-curr-as-for_Question
breadcrumbs:new-file-with-curr-as-how?
breadcrumbs:new-file-with-curr-as-info-shards
breadcrumbs:new-file-with-curr-as-loged_In
breadcrumbs:new-file-with-curr-as-looks_for
breadcrumbs:new-file-with-curr-as-next
breadcrumbs:new-file-with-curr-as-prev
breadcrumbs:new-file-with-curr-as-primary_use
breadcrumbs:new-file-with-curr-as-project-related
breadcrumbs:new-file-with-curr-as-reference
breadcrumbs:new-file-with-curr-as-ref_to_content
breadcrumbs:new-file-with-curr-as-same
breadcrumbs:new-file-with-curr-as-similar_to
breadcrumbs:new-file-with-curr-as-test
breadcrumbs:new-file-with-curr-as-tested
breadcrumbs:new-file-with-curr-as-tool_for_this
breadcrumbs:new-file-with-curr-as-up
breadcrumbs:new-file-with-curr-as-uses
breadcrumbs:open-vis-modal
breadcrumbs:Refresh-Breadcrumbs-Index
breadcrumbs:show-BC-ducks-view
breadcrumbs:show-BC-matrix-view
breadcrumbs:show-BC-tree-view
breadcrumbs:Toggle-trail-in-Edit&LP
breadcrumbs:Write-Breadcrumbs-to-All-Files
breadcrumbs:Write-Breadcrumbs-to-Current-File
buttons:button-maker
buttons:inline-button
callout-manager:manage-callouts
canvas:convert-to-file
canvas:export-as-image
canvas:jump-to-group
canvas:new-file
cmdr:macro-0
cmdr:open-commander-settings
cm-typewriter-scroll-obsidian:toggle-typewriter-sroll
cm-typewriter-scroll-obsidian:toggle-typewriter-sroll-zen
codeblock-customizer:codeblock-customizer-foldall-editor
codeblock-customizer:codeblock-customizer-restore-fold-editor
codeblock-customizer:codeblock-customizer-unfoldall-editor
codename:inject-codename
command-palette:open
creases:clear-creases
creases:crease-current-folds
creases:decrease-fold-level
creases:fold
creases:increase-fold-level
creases:toggle-crease
creases:toggle-fold-heading-level-1
creases:toggle-fold-heading-level-2
creases:toggle-fold-heading-level-3
creases:toggle-fold-heading-level-4
creases:toggle-fold-heading-level-5
creases:toggle-fold-heading-level-6
customjs:invokeScript
daily-notes
daily-notes:goto-next
daily-notes:goto-prev
darlal-switcher-plus:switcher-plus:open
darlal-switcher-plus:switcher-plus:open-commands
darlal-switcher-plus:switcher-plus:open-editors
darlal-switcher-plus:switcher-plus:open-headings
darlal-switcher-plus:switcher-plus:open-related-items
darlal-switcher-plus:switcher-plus:open-related-items-active
darlal-switcher-plus:switcher-plus:open-starred
darlal-switcher-plus:switcher-plus:open-symbols
darlal-switcher-plus:switcher-plus:open-symbols-active
darlal-switcher-plus:switcher-plus:open-vaults
darlal-switcher-plus:switcher-plus:open-workspaces
dataview:dataview-drop-cache
dataview:dataview-force-refresh-views
easy-toggle-sidebars:toggle-both-sidebars
editor:add-cursor-above
editor:add-cursor-below
editor:attach-file
editor:clear-formatting
editor:context-menu
editor:cycle-list-checklist
editor:delete-paragraph
editor:focus
editor:focus-bottom
editor:focus-left
editor:focus-right
editor:focus-top
editor:fold-all
editor:fold-less
editor:fold-more
editor:follow-link
editor:insert-callout
editor:insert-codeblock
editor:insert-embed
editor:insert-horizontal-rule
editor:insert-link
editor:insert-mathblock
editor:insert-table
editor:insert-tag
editor:insert-wikilink
editor:open-link-in-new-leaf
editor:open-link-in-new-split
editor:open-link-in-new-window
editor:open-search
editor:open-search-replace
editor:rename-heading
editor:set-heading
editor:set-heading-0
editor:set-heading-1
editor:set-heading-2
editor:set-heading-3
editor:set-heading-4
editor:set-heading-5
editor:set-heading-6
editor:swap-line-down
editor:swap-line-up
editor:table-col-after
editor:table-col-align-center
editor:table-col-align-left
editor:table-col-align-right
editor:table-col-before
editor:table-col-copy
editor:table-col-delete
editor:table-col-left
editor:table-col-right
editor:table-row-after
editor:table-row-before
editor:table-row-copy
editor:table-row-delete
editor:table-row-down
editor:table-row-up
editor:toggle-blockquote
editor:toggle-bold
editor:toggle-bullet-list
editor:toggle-checklist-status
editor:toggle-code
editor:toggle-comments
editor:toggle-fold
editor:toggle-fold-properties
editor:toggle-highlight
editor:toggle-inline-math
editor:toggle-italics
editor:toggle-numbered-list
editor:toggle-source
editor:toggle-spellcheck
editor:toggle-strikethrough
editor:unfold-all
excalibrain:excalibrain-addChildField
excalibrain:excalibrain-addLeftFriendField
excalibrain:excalibrain-addNextField
excalibrain:excalibrain-addParentField
excalibrain:excalibrain-addPreviousField
excalibrain:excalibrain-addRightFriendField
excalibrain:excalibrain-open-hover
excalibrain:excalibrain-selectOntology
excalibrain:excalibrain-start
excalibrain:excalibrain-start-popout
excel:excel-autocreate
execute-code:code-execute-open-manage-executors
execute-code:run-all-code-blocks-in-file
file-diff:compare
file-diff:compare-and-merge
file-diff:find-sync-conflicts-and-merge
file-explorer:duplicate-file
file-explorer:move-file
file-explorer:new-file
file-explorer:new-file-in-current-tab
file-explorer:new-file-in-new-pane
file-explorer:open
file-explorer:reveal-active-file
file-recovery:open
find-unlinked-files:create-files-of-broken-links
find-unlinked-files:delete-empty-files
find-unlinked-files:delete-unlinked-files
find-unlinked-files:find-empty-files
find-unlinked-files:find-files-without-tags
find-unlinked-files:find-unlinked-files
find-unlinked-files:find-unresolved-link
global-search:open
google-calendar:create-google-calendar-event
google-calendar:create-google-calendar-event-from-frontmatter 
google-calendar:create-google-calendar-event-view
google-calendar:delete-google-calendar-event-from-frontmatter 
google-calendar:google-calendar-create-event-note
google-calendar:google-calendar-create-event-note-current-event
google-calendar:google-calendar-get-todays-tasks
google-calendar:google-calendar-trigger-auto-import
google-calendar:insert-google-event-codeblock
google-calendar:insert-google-events
google-calendar:insert-google-event-template
google-calendar:list-google-calendars
google-calendar:list-google-events
google-calendar:open-google-calendar-event-from-frontmatter
google-calendar:open-google-calendar-month-view
google-calendar:open-google-calendar-schedule-view
google-calendar:open-google-calendar-timline-view
google-calendar:open-google-calendar-web-view
google-calendar:open-google-calendar-week-view
google-calendar:open-google-calendar-year-view
google-calendar:update-google-calendar-event-from-frontmatter 
google-photos:insert-album
google-photos:insert-google-photo
graph-analysis:open-Adamic Adar
graph-analysis:open-BoW
graph-analysis:open-Clustering Coefficient
graph-analysis:open-Co-Citations
graph-analysis:open-HITS
graph-analysis:open-Jaccard
graph-analysis:open-Label Propagation
graph-analysis:open-Louvain
graph-analysis:open-Otsuka-Chiai
graph-analysis:open-Overlap
graph-analysis:open-Sentiment
graph-analysis:refresh-analysis-view
graph-analysis:show-graph-analysis-view
graph:animate
graph:open
graph:open-local
header-enhancer:add-auto-numbering-yaml
header-enhancer:remove-auto-numbering-yaml
header-enhancer:reset-auto-numbering-yaml
header-enhancer:toggle-auto-numbering
highlightr-plugin:Blue
highlightr-plugin:Cyan
highlightr-plugin:Green
highlightr-plugin:Grey
highlightr-plugin:highlighter-plugin-menu
highlightr-plugin:Orange
highlightr-plugin:pink
highlightr-plugin:Purple
highlightr-plugin:Red
highlightr-plugin:unhighlight
highlightr-plugin:Yellow
hotkey-helper:browse-plugins
hotkey-helper:open-hotkeys
hotkey-helper:open-plugins
hotkey-helper:open-settings
html-server:start-server
html-server:stop-server
insert-current-date
insert-current-time
insert-template
json-table:generate-json-from-selected-table
json-table:generate-table-from-selected-json
json-table:generate-table-from-selected-json-url
juggl:open-vis
juggl:open-vis-global
juggl:show-nodes-pane
juggl:show-style-pane
link-exploder:link-exploder-canvas-builder
links:editor-convert-all-links-to-mdlinks
links:editor-convert-autolinks-to-mdlinks
links:editor-convert-link-to-autolink
links:editor-convert-link-to-mdlink
links:editor-convert-link-to-wikilink
links:editor-convert-urls-to-mdlinks
links:editor-convert-wikilinks-to-mdlinks
links:editor-copy-link-destination-to-clipboard
links:editor-create-link-from-clipboard
links:editor-create-link-from-selection
links:editor-delete-link05:19:20
links:editor-edit-link-destination
links:editor-edit-link-text
links:editor-embed-link
links:editor-remove-links-from-headings
links:editor-set-link-text
links:editor-unembed-link
links:editor-unlink-link
markdown:add-metadata-property
markdown:clear-metadata-properties
markdown:edit-metadata-property
markdown-importer:open
markdown:toggle-preview
mermaid-tools:open-toolbar
metadata-menu:add_fileclass_to_file
metadata-menu:field_at_cursor_options
metadata-menu:field_options
metadata-menu:fileClassAttr_options
metadata-menu:insert_field_at_cursor
metadata-menu:insert_fileClassAttr
metadata-menu:insert_missing_fields
metadata-menu:open_fields_modal
metadata-menu:open_fileclass_view
metadata-menu:update_all_lookups
metadata-menu:update_file_formulas
metadata-menu:update_file_lookups
metaedit:metaEditRun
mrj-crosslink-between-notes:add-link-from-quick-switcher
mrj-crosslink-between-notes:add-link-to-current
multiple-notes-outline:erase-all-fold-AOT-information
multiple-notes-outline:erase-non-favorite-fold-AOT-information
multiple-notes-outline:open-file-view
multiple-notes-outline:open-folder-view
nldates-obsidian:nlp-date-clean
nldates-obsidian:nlp-dates
nldates-obsidian:nlp-dates-link
nldates-obsidian:nlp-now
nldates-obsidian:nlp-parse-time
nldates-obsidian:nlp-picker
nldates-obsidian:nlp-time
nldates-obsidian:nlp-today
note-composer:extract-heading
note-composer:merge-file
note-composer:split-file
note-gallery:drop-database
note-refactor-obsidian:app:extract-selection-autogenerate-name
note-refactor-obsidian:app:extract-selection-content-only
note-refactor-obsidian:app:extract-selection-first-line
note-refactor-obsidian:app:split-note-by-heading-h1
note-refactor-obsidian:app:split-note-by-heading-h2
note-refactor-obsidian:app:split-note-by-heading-h3
note-refactor-obsidian:app:split-note-content-only
note-refactor-obsidian:app:split-note-first-line
novel-word-count:cycle-count-type
novel-word-count:recount-vault
novel-word-count:set-count-type-alias
novel-word-count:set-count-type-character
novel-word-count:set-count-type-created
novel-word-count:set-count-type-embed
novel-word-count:set-count-type-filesize
novel-word-count:set-count-type-link
novel-word-count:set-count-type-modified
novel-word-count:set-count-type-none
novel-word-count:set-count-type-note
novel-word-count:set-count-type-page
novel-word-count:set-count-type-pagedecimal
novel-word-count:set-count-type-percentgoal
novel-word-count:set-count-type-readtime
novel-word-count:set-count-type-word
novel-word-count:toggle-abbreviate
number-headings-obsidian:number-headings
number-headings-obsidian:number-headings-with-options
number-headings-obsidian:remove-number-headings
number-headings-obsidian:save-settings-to-front-matter
obsidian-advanced-new-file:advanced-new-file
obsidian-advanced-new-file:advanced-new-file-new-pane
obsidian-advanced-new-file:advanced-new-file-new-tab
obsidian-advanced-uri:copy-uri-block
obsidian-advanced-uri:copy-uri-command
obsidian-advanced-uri:copy-uri-current-file
obsidian-advanced-uri:copy-uri-current-file-simple
obsidian-advanced-uri:copy-uri-daily
obsidian-advanced-uri:copy-uri-search-and-replace
obsidian-apply-patterns:apply-pattern-to-clipboard-document
obsidian-apply-patterns:apply-pattern-to-clipboard-lines
obsidian-apply-patterns:apply-pattern-to-document
obsidian-apply-patterns:apply-pattern-to-lines
obsidian-apply-patterns:apply-pattern-to-selection
obsidian-chartsview-plugin:chartsview-wizard
obsidian-chartsview-plugin:import-chartsview-data-csv
obsidian-chartsview-plugin:insert-chartsview-template
obsidian-copy-block-link:copy-embed-to-block
obsidian-copy-block-link:copy-link-to-block
obsidian-custom-frames:open-custom-frames-google-keep
obsidian-diagrams-net:app:diagrams-net-new-diagram
obsidian-excalidraw-plugin:convert-excalidraw
obsidian-excalidraw-plugin:convert-to-excalidraw
obsidian-excalidraw-plugin:delete-file
obsidian-excalidraw-plugin:disable-binding
obsidian-excalidraw-plugin:disable-frameclipping
obsidian-excalidraw-plugin:disable-framerendering
obsidian-excalidraw-plugin:excalidraw-autocreate
obsidian-excalidraw-plugin:excalidraw-autocreate-and-embed
obsidian-excalidraw-plugin:excalidraw-autocreate-and-embed-new-tab
obsidian-excalidraw-plugin:excalidraw-autocreate-and-embed-on-current
obsidian-excalidraw-plugin:excalidraw-autocreate-and-embed-popout
obsidian-excalidraw-plugin:excalidraw-autocreate-newtab
obsidian-excalidraw-plugin:excalidraw-autocreate-on-current
obsidian-excalidraw-plugin:excalidraw-autocreate-popout
obsidian-excalidraw-plugin:excalidraw-disable-autosave
obsidian-excalidraw-plugin:excalidraw-download-lib
obsidian-excalidraw-plugin:excalidraw-enable-autosave
obsidian-excalidraw-plugin:excalidraw-insert-last-active-transclusion
obsidian-excalidraw-plugin:excalidraw-insert-transclusion
obsidian-excalidraw-plugin:excalidraw-open
obsidian-excalidraw-plugin:excalidraw-open-on-current
obsidian-excalidraw-plugin:export-image
obsidian-excalidraw-plugin:fullscreen
obsidian-excalidraw-plugin:import-svg
obsidian-excalidraw-plugin:insert-command
obsidian-excalidraw-plugin:insert-image
obsidian-excalidraw-plugin:insert-LaTeX-symbol
obsidian-excalidraw-plugin:insert-link
obsidian-excalidraw-plugin:insert-link-to-element
obsidian-excalidraw-plugin:insert-link-to-element-area
obsidian-excalidraw-plugin:insert-link-to-element-frame
obsidian-excalidraw-plugin:insert-link-to-element-group
obsidian-excalidraw-plugin:insert-md
obsidian-excalidraw-plugin:insert-pdf
obsidian-excalidraw-plugin:release-notes
obsidian-excalidraw-plugin:reset-image-to-100
obsidian-excalidraw-plugin:run-ocr
obsidian-excalidraw-plugin:save
obsidian-excalidraw-plugin:scriptengine-store
obsidian-excalidraw-plugin:search-text
obsidian-excalidraw-plugin:toggle-excalidraw-view
obsidian-excalidraw-plugin:toggle-lefthanded-mode
obsidian-excalidraw-plugin:toggle-lock
obsidian-excalidraw-plugin:tray-mode
obsidian-excalidraw-plugin:universal-add-file
obsidian-excel-to-markdown-table:excel-to-markdown-table
obsidian-export-to-tex:export-selection-tex-to-clipboard
obsidian-export-to-tex:export-selection-to-tex
obsidian-export-to-tex:export-tex-to-clipboard
obsidian-export-to-tex:export-to-tex
obsidian-file-cooker:Add-content-to
obsidian-file-cooker:add-dataview-results-to-canvas
obsidian-file-cooker:add-dataview-task-to-canvas
obsidian-file-cooker:add-files-in-clipboard-to-canvas
obsidian-file-cooker:add-files-in-searchresults-to-canvas
obsidian-file-cooker:add-links-to-canvas
obsidian-file-cooker:Add-selection-to
obsidian-file-cooker:copy-dataview-result-links
obsidian-file-cooker:create-links
obsidian-file-cooker:delete-dataview-results
obsidian-file-cooker:delete-files-in-clipboard
obsidian-file-cooker:delete-files-in-searchresults
obsidian-file-cooker:delete-links-in-current-file
obsidian-file-cooker:edit-front-matter-in-clipboard-files
obsidian-file-cooker:edit-front-matter-in-current-file-links
obsidian-file-cooker:edit-front-matter-in-dataview-results
obsidian-file-cooker:edit-front-matter-in-searchresults-files
obsidian-file-cooker:merge-dataview-results-to
obsidian-file-cooker:merge-files-in-clipboard-to
obsidian-file-cooker:merge-files-in-searchresults-to
obsidian-file-cooker:merge-links-to
obsidian-file-cooker:move-dataview-results-to
obsidian-file-cooker:move-files-in-clipboard-to
obsidian-file-cooker:move-files-in-searchresults-to
obsidian-file-cooker:move-links-to
obsidian-file-cooker:rename-files-in-clipboard
obsidian-file-cooker:rename-files-in-searchresults
obsidian-file-cooker:rename-in-current-file-links
obsidian-file-cooker:rename-in-dataview-results
obsidian-file-cooker:sync-content-to
obsidian-file-cooker:sync-dataview-results-to
obsidian-file-cooker:sync-files-in-clipboard-to-flomo
obsidian-file-cooker:sync-files-in-searchresults-to-flomo
obsidian-file-cooker:sync-links-to
obsidian-file-cooker:sync-selection-to
obsidian-google-tasks:copy-google-refresh-token
obsidian-google-tasks:create-google-task
obsidian-google-tasks:create-google-task-with-insert
obsidian-google-tasks:insert-google-tasks
obsidian-google-tasks:insert-uncompleted-google-tasks
obsidian-google-tasks:list-google-tasks
obsidian-heading-shifter:apply-heading0
obsidian-heading-shifter:apply-heading1
obsidian-heading-shifter:apply-heading2
obsidian-heading-shifter:apply-heading3
obsidian-heading-shifter:apply-heading4
obsidian-heading-shifter:apply-heading5
obsidian-heading-shifter:apply-heading6
obsidian-heading-shifter:decrease-heading
obsidian-heading-shifter:increase-heading
obsidian-heading-shifter:insert-heading-current
obsidian-heading-shifter:insert-heading-deeper
obsidian-heading-shifter:insert-heading-higher
obsidian-hider:toggle-app-ribbon
obsidian-hider:toggle-hider-status
obsidian-hider:toggle-tab-containers
obsidian-hover-editor:bounce-popovers
obsidian-hover-editor:convert-active-pane-to-popover
obsidian-hover-editor:dock-active-popover-to-workspace
obsidian-hover-editor:minimize-active-popover
obsidian-hover-editor:open-current-file-in-new-popover
obsidian-hover-editor:open-link-in-new-popover
obsidian-hover-editor:open-new-popover
obsidian-hover-editor:restore-active-popover
obsidian-hover-editor:snap-active-popover-to-left
obsidian-hover-editor:snap-active-popover-to-right
obsidian-hover-editor:snap-active-popover-to-viewport
obsidian-html-tags-autocomplete:html_autocomplete_tags-skip_over_tag_backward
obsidian-html-tags-autocomplete:html_autocomplete_tags-skip_over_tag_forward
obsidian-html-tags-autocomplete:html_autocomplete_tags-to_matching_tag
obsidian-hypothesis-plugin:hypothesis-resync-deleted
obsidian-hypothesis-plugin:hypothesis-sync
obsidian-importer:open-modal
obsidian-import-json:import-json
obsidian-markmind:Add brother node
obsidian-markmind:Add child node
obsidian-markmind:Cancel edit node
obsidian-markmind:Change basic mode to rich mode
obsidian-markmind:Change basic to outline mode
obsidian-markmind:Change basic to table mode
obsidian-markmind:Change layout to fishLeft
obsidian-markmind:Change layout to fishRight
obsidian-markmind:Change layout to left
obsidian-markmind:Change layout to mindmap
obsidian-markmind:Change layout to right
obsidian-markmind:Change layout to tree
obsidian-markmind:Change rich mode to basic mode
obsidian-markmind:Close theme change
obsidian-markmind:Copy Node
obsidian-markmind:Copy node link
obsidian-markmind:Create New MindMap
obsidian-markmind:Create New outline
obsidian-markmind:Delete node
obsidian-markmind:Edit node
obsidian-markmind:Expand to node level 1
obsidian-markmind:Expand to node level 2
obsidian-markmind:Expand to node level 3
obsidian-markmind:Expand to node level 4
obsidian-markmind:Expand to node level 5
obsidian-markmind:Expand to node level all
obsidian-markmind:Export mindmap to pdf
obsidian-markmind:Export mindmap to pdf (old version)
obsidian-markmind:Export to html
obsidian-markmind:Generate mind maps by chatGTP
obsidian-markmind:Generate mind maps by Q&A of chatGTP 
obsidian-markmind:Get vault path
obsidian-markmind:Paste Node
obsidian-markmind:Redo
obsidian-markmind:Set pdf js plugin folder path
obsidian-markmind:Theme change
obsidian-markmind:Toggle to markdown or mindmap
obsidian-markmind:Undo
obsidian-markmind:Use new version of pdfjs
obsidian-markmind:Use old version of pdfjs
obsidian-plaintext:new-plaintext-file
obsidian-shellcommands:re-execute-from-command-palette
obsidian-shellcommands:shell-command-c5pyvr0h5z
obsidian-sort-and-permute-lines:permute-reverse
obsidian-sort-and-permute-lines:permute-shuffle
obsidian-sort-and-permute-lines:sort-alphabetically
obsidian-sort-and-permute-lines:sort-alphabetically-with-checkboxes
obsidian-sort-and-permute-lines:sort-checkboxes
obsidian-sort-and-permute-lines:sort-headings
obsidian-sort-and-permute-lines:sort-length
obsidian-sort-and-permute-lines:sort-list-alphabetically
obsidian-sort-and-permute-lines:sort-list-alphabetically-with-checkboxes
obsidian-sort-and-permute-lines:sort-list-recursively
obsidian-sort-and-permute-lines:sort-list-recursively-with-checkboxes
obsidian-toggl-integration:start-timer
obsidian-toggl-integration:stop-timer
obsidian-tracker:add-bar-chart-tracker
obsidian-tracker:add-line-chart-tracker
obsidian-tracker:add-summary-tracker
oin-gotoheading:gotoheading-next
oin-gotoheading:gotoheading-previous
oin-gotoheading:gotoheading-switcher
oin-gotoheading:gotoheading-switcher-folder
open-with-default-app:open
open-with-default-app:show
outgoing-links:open
outgoing-links:open-for-current
outline:open
outline:open-for-current
oz-image-plugin:toggle-render-all
oz-image-plugin:toggle-render-excalidraw
oz-image-plugin:toggle-render-iframe
oz-image-plugin:toggle-render-images
oz-image-plugin:toggle-render-pdfs
oz-image-plugin:toggle-render-transclusion
pane-relief:focus-lock
pane-relief:go-1st
pane-relief:go-2nd
pane-relief:go-3rd
pane-relief:go-4th
pane-relief:go-5th
pane-relief:go-6th
pane-relief:go-7th
pane-relief:go-8th
pane-relief:go-last
pane-relief:go-next
pane-relief:go-prev
pane-relief:maximize
pane-relief:open-new-window
pane-relief:ordered-close
pane-relief:put-1st
pane-relief:put-2nd
pane-relief:put-3rd
pane-relief:put-4th
pane-relief:put-5th
pane-relief:put-6th
pane-relief:put-7th
pane-relief:put-8th
pane-relief:put-last
pane-relief:swap-next
pane-relief:swap-prev
pane-relief:toggle-sliding
pane-relief:win-1st
pane-relief:win-2nd
pane-relief:win-3rd
pane-relief:win-4th
pane-relief:win-5th
pane-relief:win-6th
pane-relief:win-7th
pane-relief:win-8th
pane-relief:win-last
pane-relief:win-next
pane-relief:win-prev
persistent-graph:restore-node-positions
persistent-graph:run-graph-simulation
persistent-graph:save-node-positions
persistent-graph:stop-graph-simulation
persistent-links:persistent-links:repair-links-in-file
properties:open
properties:open-local
quickadd:choice:11e142c8-0764-434a-8185-1944cee5375b
quickadd:choice:aac8b791-ed37-4b6c-81ba-a7aa142966da
quickadd:reloadQuickAdd
quickadd:runQuickAdd
quickadd:testQuickAdd
quick-latex:addAlignBlock
quick-latex:addCasesBlock
quick-latex:addMatrixBlock
quick-tagger:quick-add-tag
quick-tagger:quick-remove-tag
quick-tagger:repeat-last-tag
random-note
recent-files-obsidian:recent-files-open
run:run-file
slides:start
spotify-link:append-currently-playing-track
spotify-link:append-currently-playing-track-using-template
spotify-link:refresh-session
switcher:open
tag-pane:open
tag-summary-plugin:summary-modal
tag-word-cloud:recalcuate-word-distribution
templater-obsidian:create-new-note-from-template
templater-obsidian:insert-templater
templater-obsidian:jump-to-next-cursor-location
templater-obsidian:replace-in-file-templater
template-search-library:free-search
template-search-library:template-search
theme:switch
theme:use-dark
theme:use-light
typing:actions
typing:create-otl-file
typing:create-root-schema
typing:new
vantage-obsidian:build-search
various-complements:add-word-custom-dictionary
various-complements:copy-plugin-settings
various-complements:hide-suggestions
various-complements:predictable-complements
various-complements:reload-current-vault
various-complements:reload-custom-dictionaries
various-complements:show-suggestions
various-complements:toggle-complement-automatically
various-complements:toggle-match-strategy
vim-toggle:toggle-vim
window:reset-zoom
window:toggle-always-on-top
window:zoom-in
window:zoom-out
workspace:close
workspace:close-others
workspace:close-others-tab-group
workspace:close-tab-group
workspace:close-window
workspace:copy-path
workspace:copy-url
workspace:edit-file-title
workspace:export-pdf
workspace:goto-last-tab
workspace:goto-tab-1
workspace:goto-tab-2
workspace:goto-tab-3
workspace:goto-tab-4
workspace:goto-tab-5
workspace:goto-tab-6
workspace:goto-tab-7
workspace:goto-tab-8
workspace:move-to-new-window
workspace:new-tab
workspace:next-tab
workspace:open-in-new-window
workspace:previous-tab
workspace:show-trash
workspaces:load
workspaces:open-modal
workspace:split-horizontal
workspace:split-vertical
workspaces:save-and-load
workspace:toggle-pin
workspace:toggle-stacked-tabs
workspace:undo-close-pane
zk-prefixer
zotlit:import-note
zotlit:insert-markdown-citation
zotlit:note-quick-switcher
zotlit:overwrite-update-literature-note
zotlit:refresh-note-index
zotlit:refresh-zotero-data
zotlit:refresh-zotero-search-index
zotlit:update-literature-note
zotlit:zotero-annot-view

## obcommands 2
Available commands: editor:save-file
editor:follow-link
editor:open-link-in-new-leaf
editor:open-link-in-new-window
workspace:toggle-pin
editor:open-link-in-new-split
editor:focus-top
editor:focus-bottom
editor:focus-left
editor:focus-right
workspace:split-vertical
workspace:split-horizontal
workspace:toggle-stacked-tabs
workspace:edit-file-title
workspace:copy-path
workspace:copy-url
workspace:undo-close-pane
workspace:export-pdf
editor:rename-heading
workspace:open-in-new-window
workspace:move-to-new-window
workspace:next-tab
workspace:goto-tab-1
workspace:goto-tab-2
workspace:goto-tab-3
workspace:goto-tab-4
workspace:goto-tab-5
workspace:goto-tab-6
workspace:goto-tab-7
workspace:goto-tab-8
workspace:goto-last-tab
workspace:previous-tab
workspace:new-tab
workspace:show-trash
obsidian-export-to-tex:export-to-tex
obsidian-export-to-tex:export-tex-to-clipboard
obsidian-export-to-tex:export-selection-to-tex
obsidian-export-to-tex:export-selection-tex-to-clipboard
obsidian-plaintext:new-plaintext-file
dataview:dataview-force-refresh-views
dataview:dataview-drop-cache
dataview:dataview-rebuild-current-view
file-diff:compare
file-diff:compare-and-merge
file-diff:find-sync-conflicts-and-merge
obsidian-importer:open-modal
obsidian-copy-block-link:copy-link-to-block
obsidian-copy-block-link:copy-embed-to-block
quickadd:runQuickAdd
quickadd:reloadQuickAdd
quickadd:testQuickAdd
quickadd:choice:aac8b791-ed37-4b6c-81ba-a7aa142966da
quickadd:choice:11e142c8-0764-434a-8185-1944cee5375b
tag-summary-plugin:summary-modal
obsidian-tracker:add-line-chart-tracker
obsidian-tracker:add-bar-chart-tracker
obsidian-tracker:add-summary-tracker
boost-link-suggestions:add-file-link
obsidian-hypothesis-plugin:hypothesis-sync
obsidian-hypothesis-plugin:hypothesis-resync-deleted
mrj-crosslink-between-notes:add-link-to-current
mrj-crosslink-between-notes:add-link-from-quick-switcher
obsidian-import-json:import-json
callout-manager:manage-callouts
recent-files-obsidian:recent-files-open
links:editor-unlink-link
links:editor-delete-link
links:editor-convert-link-to-mdlink
links:editor-convert-link-to-wikilink
links:editor-convert-link-to-htmllink
links:editor-convert-link-to-autolink
links:editor-copy-link-to-clipboard
links:editor-copy-link-to-object-to-clipboard
links:editor-cut-link-to-clipboard
links:editor-copy-link-destination-to-clipboard
links:editor-remove-links-from-headings
links:editor-edit-link-text
links:editor-set-link-text
links:editor-edit-link-destination
links:editor-create-link-from-selection
links:editor-create-link-from-clipboard
links:editor-embed-unembed-link
links:editor-convert-all-links-to-mdlinks
links:editor-convert-wikilinks-to-mdlinks
links:editor-convert-urls-to-mdlinks
links:editor-convert-autolinks-to-mdlinks
links:editor-convert-htmllink-to-mdlinks
links:editor-extract-section
links:editor-set-link-text-from-clipboard
links:editor-set-link-destination-from-clipboard
links:note-wrap-in-folder
links:editor-convert-links-in-folder
obsidian-html-tags-autocomplete:html_autocomplete_tags-skip_over_tag_forward
obsidian-html-tags-autocomplete:html_autocomplete_tags-skip_over_tag_backward
obsidian-html-tags-autocomplete:html_autocomplete_tags-to_matching_tag
link-exploder:link-exploder-canvas-builder
obsidian-excalidraw-plugin:excalidraw-convert-image-from-url-to-local-file
obsidian-excalidraw-plugin:excalidraw-unzip-file
obsidian-excalidraw-plugin:excalidraw-publish-svg-check
obsidian-excalidraw-plugin:excalidraw-embeddable-poroperties
obsidian-excalidraw-plugin:excalidraw-embeddables-relative-scale
obsidian-excalidraw-plugin:open-image-excalidraw-source
obsidian-excalidraw-plugin:excalidraw-disable-autosave
obsidian-excalidraw-plugin:excalidraw-enable-autosave
obsidian-excalidraw-plugin:excalidraw-download-lib
obsidian-excalidraw-plugin:excalidraw-open
obsidian-excalidraw-plugin:excalidraw-open-on-current
obsidian-excalidraw-plugin:excalidraw-insert-transclusion
obsidian-excalidraw-plugin:excalidraw-insert-last-active-transclusion
obsidian-excalidraw-plugin:excalidraw-autocreate
obsidian-excalidraw-plugin:excalidraw-autocreate-newtab
obsidian-excalidraw-plugin:excalidraw-autocreate-on-current
obsidian-excalidraw-plugin:excalidraw-autocreate-popout
obsidian-excalidraw-plugin:excalidraw-autocreate-and-embed
obsidian-excalidraw-plugin:excalidraw-autocreate-and-embed-new-tab
obsidian-excalidraw-plugin:excalidraw-autocreate-and-embed-on-current
obsidian-excalidraw-plugin:excalidraw-autocreate-and-embed-popout
obsidian-excalidraw-plugin:run-ocr
obsidian-excalidraw-plugin:rerun-ocr
obsidian-excalidraw-plugin:run-ocr-selectedelements
obsidian-excalidraw-plugin:search-text
obsidian-excalidraw-plugin:fullscreen
obsidian-excalidraw-plugin:disable-binding
obsidian-excalidraw-plugin:disable-framerendering
obsidian-excalidraw-plugin:disable-frameclipping
obsidian-excalidraw-plugin:export-image
obsidian-excalidraw-plugin:save
obsidian-excalidraw-plugin:toggle-lock
obsidian-excalidraw-plugin:scriptengine-store
obsidian-excalidraw-plugin:delete-file
obsidian-excalidraw-plugin:convert-text2MD
obsidian-excalidraw-plugin:insert-link
obsidian-excalidraw-plugin:insert-command
obsidian-excalidraw-plugin:insert-link-to-element
obsidian-excalidraw-plugin:insert-link-to-element-group
obsidian-excalidraw-plugin:insert-link-to-element-frame
obsidian-excalidraw-plugin:insert-link-to-element-area
obsidian-excalidraw-plugin:toggle-lefthanded-mode
obsidian-excalidraw-plugin:flip-image
obsidian-excalidraw-plugin:reset-image-to-100
obsidian-excalidraw-plugin:convert-card-to-file
obsidian-excalidraw-plugin:insert-active-pdfpage
obsidian-excalidraw-plugin:crop-image
obsidian-excalidraw-plugin:annotate-image
obsidian-excalidraw-plugin:insert-image
obsidian-excalidraw-plugin:import-svg
obsidian-excalidraw-plugin:release-notes
obsidian-excalidraw-plugin:tray-mode
obsidian-excalidraw-plugin:insert-md
obsidian-excalidraw-plugin:insert-pdf
obsidian-excalidraw-plugin:universal-add-file
obsidian-excalidraw-plugin:universal-card
obsidian-excalidraw-plugin:insert-LaTeX-symbol
obsidian-excalidraw-plugin:toggle-excalidraw-view
obsidian-excalidraw-plugin:convert-to-excalidraw
obsidian-excalidraw-plugin:convert-excalidraw
template-search-library:free-search
template-search-library:template-search
vantage-obsidian:build-search
pane-relief:swap-prev
pane-relief:swap-next
pane-relief:go-prev
pane-relief:go-next
pane-relief:win-prev
pane-relief:win-next
pane-relief:go-1st
pane-relief:go-2nd
pane-relief:go-3rd
pane-relief:go-4th
pane-relief:go-5th
pane-relief:go-6th
pane-relief:go-7th
pane-relief:go-8th
pane-relief:go-last
pane-relief:win-1st
pane-relief:win-2nd
pane-relief:win-3rd
pane-relief:win-4th
pane-relief:win-5th
pane-relief:win-6th
pane-relief:win-7th
pane-relief:win-8th
pane-relief:win-last
pane-relief:put-1st
pane-relief:put-2nd
pane-relief:put-3rd
pane-relief:put-4th
pane-relief:put-5th
pane-relief:put-6th
pane-relief:put-7th
pane-relief:put-8th
pane-relief:put-last
pane-relief:maximize
pane-relief:ordered-close
pane-relief:open-new-window
pane-relief:toggle-sliding
pane-relief:focus-lock
obsidian-custom-frames:open-custom-frames-gkeep
obsidian-custom-frames:open-custom-frames-goffice
obsidian-custom-frames:open-custom-frames-github
obsidian-custom-frames:open-custom-frames-gtasks
obsidian-custom-frames:open-custom-frames-gemini
obsidian-custom-frames:open-custom-frames-discord
obsidian-custom-frames:open-custom-frames-bingnotebook
obsidian-custom-frames:open-custom-frames-gdoc
obsidian-custom-frames:open-custom-frames-gdrive
obsidian-custom-frames:open-custom-frames-notebooklm
obsidian-custom-frames:open-custom-frames-overleaf
obsidian-custom-frames:open-custom-frames-binancebtccross
juggl:open-vis
juggl:open-vis-global
juggl:show-nodes-pane
juggl:show-style-pane
google-calendar:open-google-calendar-timline-view
google-calendar:open-google-calendar-week-view
google-calendar:open-google-calendar-month-view
google-calendar:open-google-calendar-year-view
google-calendar:open-google-calendar-web-view
google-calendar:open-google-calendar-schedule-view
google-calendar:create-google-calendar-event
google-calendar:create-google-calendar-event-view
google-calendar:list-google-calendars
google-calendar:list-google-events
google-calendar:google-calendar-trigger-auto-import
google-calendar:google-calendar-create-event-note
google-calendar:google-calendar-get-todays-tasks
google-calendar:google-calendar-create-event-note-current-event
google-calendar:insert-google-event-codeblock
google-calendar:insert-google-event-template
google-calendar:insert-google-events
google-calendar:create-google-calendar-event-from-frontmatter 
google-calendar:update-google-calendar-event-from-frontmatter 
google-calendar:delete-google-calendar-event-from-frontmatter 
google-calendar:open-google-calendar-event-from-frontmatter
google-photos:insert-google-photo
google-photos:insert-album
spotify-link:append-currently-playing-episode-using-template
spotify-link:append-currently-playing-episode
spotify-link:append-currently-playing-track-using-template
spotify-link:append-currently-playing-track
spotify-link:refresh-session
obsidian-toggl-integration:start-timer
obsidian-toggl-integration:stop-timer
obsidian-google-tasks:list-google-tasks
obsidian-google-tasks:create-google-task
obsidian-google-tasks:create-google-task-with-insert
obsidian-google-tasks:insert-uncompleted-google-tasks
obsidian-google-tasks:insert-google-tasks
obsidian-google-tasks:copy-google-refresh-token
darlal-switcher-plus:switcher-plus:open
darlal-switcher-plus:switcher-plus:open-editors
darlal-switcher-plus:switcher-plus:open-symbols
darlal-switcher-plus:switcher-plus:open-symbols-active
darlal-switcher-plus:switcher-plus:open-workspaces
darlal-switcher-plus:switcher-plus:open-headings
darlal-switcher-plus:switcher-plus:open-starred
darlal-switcher-plus:switcher-plus:open-commands
darlal-switcher-plus:switcher-plus:open-related-items
darlal-switcher-plus:switcher-plus:open-related-items-active
darlal-switcher-plus:switcher-plus:open-vaults
json-table:generate-table-from-selected-json
json-table:generate-table-from-selected-json-url
json-table:generate-json-from-selected-table
obsidian-excel-to-markdown-table:excel-to-markdown-table
templater-obsidian:insert-templater
templater-obsidian:replace-in-file-templater
templater-obsidian:jump-to-next-cursor-location
templater-obsidian:create-new-note-from-template
templater-obsidian:Templates/Blocks/template.dataview.colapsable.md
obsidian-apply-patterns:apply-pattern-to-lines
obsidian-apply-patterns:apply-pattern-to-selection
obsidian-apply-patterns:apply-pattern-to-document
obsidian-apply-patterns:apply-pattern-to-clipboard-document
obsidian-apply-patterns:apply-pattern-to-clipboard-lines
obsidian-heading-shifter:apply-heading0
obsidian-heading-shifter:apply-heading1
obsidian-heading-shifter:apply-heading2
obsidian-heading-shifter:apply-heading3
obsidian-heading-shifter:apply-heading4
obsidian-heading-shifter:apply-heading5
obsidian-heading-shifter:apply-heading6
obsidian-heading-shifter:increase-heading
obsidian-heading-shifter:decrease-heading
obsidian-heading-shifter:insert-heading-current
obsidian-heading-shifter:insert-heading-deeper
obsidian-heading-shifter:insert-heading-higher
oin-gotoheading:gotoheading-previous
oin-gotoheading:gotoheading-next
oin-gotoheading:gotoheading-switcher
oin-gotoheading:gotoheading-switcher-folder
persistent-links:persistent-links:repair-links-in-file
various-complements:reload-custom-dictionaries
various-complements:reload-current-vault
various-complements:toggle-match-strategy
various-complements:toggle-complement-automatically
various-complements:show-suggestions
various-complements:hide-suggestions
various-complements:add-word-custom-dictionary
various-complements:predictable-complements
various-complements:copy-plugin-settings
buttons:button-maker
buttons:inline-button
obsidian-shellcommands:shell-command-c5pyvr0h5z
obsidian-shellcommands:re-execute-from-command-palette
excel:excel-autocreate
obsidian-advanced-new-file:advanced-new-file
obsidian-advanced-new-file:advanced-new-file-new-pane
obsidian-advanced-new-file:advanced-new-file-new-tab
obsidian-diagrams-net:app:diagrams-net-new-diagram
codename:inject-codename
obsidian-file-cooker:move-links-to
obsidian-file-cooker:sync-content-to
obsidian-file-cooker:sync-selection-to
obsidian-file-cooker:sync-links-to
obsidian-file-cooker:create-links
obsidian-file-cooker:merge-links-to
obsidian-file-cooker:delete-links-in-current-file
obsidian-file-cooker:edit-front-matter-in-current-file-links
obsidian-file-cooker:rename-in-current-file-links
obsidian-file-cooker:add-links-to-canvas
obsidian-file-cooker:Add-selection-to
obsidian-file-cooker:move-files-in-clipboard-to
obsidian-file-cooker:sync-files-in-clipboard-to-flomo
obsidian-file-cooker:merge-files-in-clipboard-to
obsidian-file-cooker:delete-files-in-clipboard
obsidian-file-cooker:edit-front-matter-in-clipboard-files
obsidian-file-cooker:rename-files-in-clipboard
obsidian-file-cooker:add-files-in-clipboard-to-canvas
obsidian-file-cooker:Add-content-to
obsidian-file-cooker:move-dataview-results-to
obsidian-file-cooker:sync-dataview-results-to
obsidian-file-cooker:merge-dataview-results-to
obsidian-file-cooker:delete-dataview-results
obsidian-file-cooker:copy-dataview-result-links
obsidian-file-cooker:edit-front-matter-in-dataview-results
obsidian-file-cooker:rename-in-dataview-results
obsidian-file-cooker:add-dataview-results-to-canvas
obsidian-file-cooker:add-dataview-task-to-canvas
obsidian-file-cooker:move-files-in-searchresults-to
obsidian-file-cooker:sync-files-in-searchresults-to-flomo
obsidian-file-cooker:merge-files-in-searchresults-to
obsidian-file-cooker:delete-files-in-searchresults
obsidian-file-cooker:edit-front-matter-in-searchresults-files
obsidian-file-cooker:rename-files-in-searchresults
obsidian-file-cooker:add-files-in-searchresults-to-canvas
obsidian-file-cooker:start-presentation
obsidian-file-cooker:stop-presentation
advanced-paste:smartJoin
advanced-paste:joinLines
advanced-paste:removeBlankLines
advanced-paste:rawHTML
advanced-paste:advpaste-debug
vim-toggle:toggle-vim
codeblock-customizer:codeblock-customizer-foldall-editor
codeblock-customizer:codeblock-customizer-unfoldall-editor
codeblock-customizer:codeblock-customizer-restore-fold-editor
execute-code:code-execute-open-manage-executors
execute-code:run-all-code-blocks-in-file
graph-analysis:show-graph-analysis-view
graph-analysis:refresh-analysis-view
graph-analysis:open-Co-Citations
graph-analysis:open-HITS
graph-analysis:open-Adamic Adar
graph-analysis:open-Jaccard
graph-analysis:open-Overlap
graph-analysis:open-Label Propagation
graph-analysis:open-Louvain
graph-analysis:open-Clustering Coefficient
graph-analysis:open-BoW
graph-analysis:open-Otsuka-Chiai
graph-analysis:open-Sentiment
obsidian-chartsview-plugin:insert-chartsview-template
obsidian-chartsview-plugin:chartsview-wizard
obsidian-chartsview-plugin:import-chartsview-data-csv
obsidian-advanced-uri:copy-uri-current-file
obsidian-advanced-uri:copy-uri-current-file-simple
obsidian-advanced-uri:copy-uri-daily
obsidian-advanced-uri:copy-uri-search-and-replace
obsidian-advanced-uri:copy-uri-command
obsidian-advanced-uri:copy-uri-block
obsidian-sort-and-permute-lines:sort-alphabetically-with-checkboxes
obsidian-sort-and-permute-lines:sort-list-alphabetically-with-checkboxes
obsidian-sort-and-permute-lines:sort-alphabetically
obsidian-sort-and-permute-lines:sort-list-alphabetically
obsidian-sort-and-permute-lines:sort-checkboxes
obsidian-sort-and-permute-lines:sort-length
obsidian-sort-and-permute-lines:sort-headings
obsidian-sort-and-permute-lines:permute-reverse
obsidian-sort-and-permute-lines:permute-shuffle
obsidian-sort-and-permute-lines:sort-list-recursively
obsidian-sort-and-permute-lines:sort-list-recursively-with-checkboxes
obsidian-icon-folder:iconize:set-icon-for-file
find-unlinked-files:find-unlinked-files
find-unlinked-files:find-unresolved-link
find-unlinked-files:delete-unlinked-files
find-unlinked-files:create-files-of-broken-links
find-unlinked-files:find-files-without-tags
find-unlinked-files:find-empty-files
find-unlinked-files:delete-empty-files
auto-card-link:auto-card-link-paste-and-enhance
auto-card-link:auto-card-link-enhance-selected-url
obsidian-hider:toggle-tab-containers
obsidian-hider:toggle-hider-status
cm-typewriter-scroll-obsidian:toggle-typewriter-sroll
cm-typewriter-scroll-obsidian:toggle-typewriter-sroll-zen
run:run-file
highlightr-plugin:highlighter-plugin-menu
highlightr-plugin:pink
highlightr-plugin:unhighlight
highlightr-plugin:Red
highlightr-plugin:Orange
highlightr-plugin:Yellow
highlightr-plugin:Cyan
highlightr-plugin:Blue
highlightr-plugin:Purple
highlightr-plugin:Grey
highlightr-plugin:Green
obsidian-hover-editor:bounce-popovers
obsidian-hover-editor:open-new-popover
obsidian-hover-editor:open-link-in-new-popover
obsidian-hover-editor:open-current-file-in-new-popover
obsidian-hover-editor:convert-active-pane-to-popover
obsidian-hover-editor:dock-active-popover-to-workspace
obsidian-hover-editor:restore-active-popover
obsidian-hover-editor:minimize-active-popover
obsidian-hover-editor:snap-active-popover-to-left
obsidian-hover-editor:snap-active-popover-to-right
obsidian-hover-editor:snap-active-popover-to-viewport
creases:fold
creases:toggle-crease
creases:crease-current-folds
creases:clear-creases
creases:increase-fold-level
creases:decrease-fold-level
creases:toggle-fold-heading-level-1
creases:toggle-fold-heading-level-2
creases:toggle-fold-heading-level-3
creases:toggle-fold-heading-level-4
creases:toggle-fold-heading-level-5
creases:toggle-fold-heading-level-6
quick-tagger:quick-add-tag
quick-tagger:quick-remove-tag
quick-tagger:repeat-last-tag
typing:new
typing:actions
typing:create-otl-file
typing:create-root-schema
nldates-obsidian:nlp-dates
nldates-obsidian:nlp-dates-link
nldates-obsidian:nlp-date-clean
nldates-obsidian:nlp-parse-time
nldates-obsidian:nlp-now
nldates-obsidian:nlp-today
nldates-obsidian:nlp-time
nldates-obsidian:nlp-picker
tag-word-cloud:recalcuate-word-distribution
persistent-graph:save-node-positions
persistent-graph:restore-node-positions
persistent-graph:run-graph-simulation
persistent-graph:stop-graph-simulation
oz-image-plugin:toggle-render-all
oz-image-plugin:toggle-render-images
oz-image-plugin:toggle-render-pdfs
oz-image-plugin:toggle-render-transclusion
oz-image-plugin:toggle-render-iframe
oz-image-plugin:toggle-render-excalidraw
obsidian-markmind:Create New MindMap
obsidian-markmind:Create New outline
obsidian-markmind:Generate mind maps by chatGTP
obsidian-markmind:Generate mind maps by Q&A of chatGTP 
obsidian-markmind:Toggle to markdown or mindmap
obsidian-markmind:Change basic to table mode
obsidian-markmind:Change basic to outline mode
obsidian-markmind:Copy Node
obsidian-markmind:Paste Node
obsidian-markmind:Change layout to mindmap
obsidian-markmind:Change layout to right
obsidian-markmind:Change layout to left
obsidian-markmind:Change layout to tree
obsidian-markmind:Change layout to fishRight
obsidian-markmind:Change layout to fishLeft
obsidian-markmind:Get vault path
obsidian-markmind:Set pdf js plugin folder path
obsidian-markmind:Change basic mode to rich mode
obsidian-markmind:Change rich mode to basic mode
obsidian-markmind:Export to html
obsidian-markmind:Export mindmap to pdf
obsidian-markmind:Export mindmap to pdf (old version)
obsidian-markmind:Use new version of pdfjs
obsidian-markmind:Use old version of pdfjs
obsidian-markmind:Expand to node level 1
obsidian-markmind:Expand to node level 2
obsidian-markmind:Expand to node level 3
obsidian-markmind:Expand to node level 4
obsidian-markmind:Expand to node level 5
obsidian-markmind:Expand to node level all
obsidian-markmind:Theme change
obsidian-markmind:Close theme change
obsidian-markmind:Copy node link
obsidian-markmind:Add child node
obsidian-markmind:Add brother node
obsidian-markmind:Edit node
obsidian-markmind:Cancel edit node
obsidian-markmind:Delete node
obsidian-markmind:Undo
obsidian-markmind:Redo
note-refactor-obsidian:app:extract-selection-first-line
note-refactor-obsidian:app:extract-selection-content-only
note-refactor-obsidian:app:extract-selection-autogenerate-name
note-refactor-obsidian:app:split-note-first-line
note-refactor-obsidian:app:split-note-content-only
note-refactor-obsidian:app:split-note-by-heading-h1
note-refactor-obsidian:app:split-note-by-heading-h2
note-refactor-obsidian:app:split-note-by-heading-h3
note-gallery:drop-database
multiple-notes-outline:open-file-view
multiple-notes-outline:open-folder-view
multiple-notes-outline:erase-all-fold-AOT-information
multiple-notes-outline:erase-non-favorite-fold-AOT-information
metadata-menu:fileClassAttr_options
metadata-menu:insert_fileClassAttr
metadata-menu:field_options
metadata-menu:insert_field_at_cursor
metadata-menu:field_at_cursor_options
metadata-menu:insert_missing_fields
metadata-menu:open_fields_modal
metadata-menu:update_file_lookups
metadata-menu:update_file_formulas
metadata-menu:open_fileclass_view
metadata-menu:add_fileclass_to_file
metadata-menu:update_all_lookups
metaedit:metaEditRun
runjs:open-codelist-modal
runjs:open-codelist-view
link-tree:activate-view
obsidian-task-archiver:archive-tasks
obsidian-task-archiver:archive-tasks-deeply
obsidian-task-archiver:delete-tasks
obsidian-task-archiver:archive-heading-under-cursor
obsidian-task-archiver:sort-tasks-in-list-under-cursor
obsidian-task-archiver:toggle-done-and-archive
canvas-mindmap:split-heading-into-mindmap
canvas-mindmap:create-floating-node
canvas-mindmap:create-child-node
canvas-mindmap:create-sibling-node
canvas-filter:show-all
canvas-filter:show-only-same-color
canvas-filter:show-hide
canvas-filter:show-hide-connected
canvas-filter:show-connected-nodes-from-to
canvas-filter:show-connected-nodes-from
canvas-filter:show-connected-nodes-to
canvas-filter:show-tags
link-nodes-in-canvas:link-between-selection-nodes
canvas-mindmap-helper:focus-down
canvas-mindmap-helper:focus-up
canvas-mindmap-helper:focus-left
canvas-mindmap-helper:focus-right
canvas-mindmap-helper:new-node
canvas-mindmap-helper:new-child-node
canvas-mindmap-helper:auto-layout
collapse-node:fold-all-nodes
collapse-node:expand-all-nodes
collapse-node:fold-selected-nodes
collapse-node:expand-selected-nodes
optimize-canvas-connections:optimize-preserve-axes-selection
optimize-canvas-connections:optimize-shortest-path-selection
obsidian-file-info-plugin:form-info-toggle-window
obsidian-file-info-plugin:form-info-show-window
obsidian-file-info-plugin:form-info-hide-window
novel-word-count:recount-vault
novel-word-count:cycle-count-type
novel-word-count:toggle-abbreviate
novel-word-count:set-count-type-none
novel-word-count:set-count-type-word
novel-word-count:set-count-type-page
novel-word-count:set-count-type-pagedecimal
novel-word-count:set-count-type-readtime
novel-word-count:set-count-type-percentgoal
novel-word-count:set-count-type-note
novel-word-count:set-count-type-character
novel-word-count:set-count-type-link
novel-word-count:set-count-type-embed
novel-word-count:set-count-type-alias
novel-word-count:set-count-type-created
novel-word-count:set-count-type-modified
novel-word-count:set-count-type-filesize
cmdr:open-commander-settings
zotlit:note-quick-switcher
zotlit:zotero-annot-view
zotlit:insert-markdown-citation
zotlit:update-literature-note
zotlit:overwrite-update-literature-note
zotlit:import-note
keyword-highlighter:kh-create-new-keyword
zotlit:refresh-zotero-data
zotlit:refresh-zotero-search-index
dbfolder:create-new-database-folder
dbfolder:active-database-folder-go-next-page
dbfolder:active-database-folder-go-previous-page
dbfolder:active-database-folder-add-new-row
dbfolder:active-database-folder-open-settings
dbfolder:active-database-folder-toggle-filters
dbfolder:active-database-folder-open-filters
perilous-writing:short-session
perilous-writing:long-session
perilous-writing:custom-session
perilous-writing:clear-session
tab-shifter:move-tab-next
tab-shifter:move-tab-prev
tab-shifter:focus-next-tab
tab-shifter:focus-prev-tab
vertical-tabs:open-vertical-tabs
app:go-back
app:go-forward
app:open-vault
theme:use-dark
theme:use-light
theme:switch
app:open-settings
app:show-release-notes
markdown:toggle-preview
markdown:add-metadata-property
markdown:add-alias
markdown:edit-metadata-property
markdown:clear-metadata-properties
workspace:close
workspace:close-window
workspace:close-others
workspace:close-tab-group
workspace:close-others-tab-group
app:delete-file
app:toggle-ribbon
app:toggle-left-sidebar
app:toggle-right-sidebar
app:toggle-default-new-pane-mode
app:open-help
app:reload
app:show-debug-info
app:open-sandbox-vault
window:toggle-always-on-top
window:zoom-in
window:zoom-out
window:reset-zoom
file-explorer:new-file
file-explorer:new-file-in-current-tab
file-explorer:new-file-in-new-pane
open-with-default-app:open
file-explorer:move-file
file-explorer:duplicate-file
open-with-default-app:show
editor:toggle-source
editor:open-search
editor:open-search-replace
editor:focus
editor:toggle-fold-properties
editor:toggle-fold
editor:fold-all
editor:unfold-all
editor:fold-less
editor:fold-more
editor:insert-wikilink
editor:insert-embed
editor:insert-link
editor:insert-tag
editor:set-heading
editor:set-heading-0
editor:set-heading-1
editor:set-heading-2
editor:set-heading-3
editor:set-heading-4
editor:set-heading-5
editor:set-heading-6
editor:toggle-bold
editor:toggle-italics
editor:toggle-strikethrough
editor:toggle-highlight
editor:toggle-code
editor:toggle-inline-math
editor:toggle-blockquote
editor:toggle-comments
editor:clear-formatting
editor:toggle-bullet-list
editor:toggle-numbered-list
editor:toggle-checklist-status
editor:cycle-list-checklist
editor:insert-callout
editor:insert-codeblock
editor:insert-horizontal-rule
editor:insert-mathblock
editor:insert-table
editor:swap-line-up
editor:swap-line-down
editor:attach-file
editor:delete-paragraph
editor:add-cursor-below
editor:add-cursor-above
editor:toggle-spellcheck
editor:table-row-before
editor:table-row-after
editor:table-row-up
editor:table-row-down
editor:table-row-copy
editor:table-row-delete
editor:table-col-before
editor:table-col-after
editor:table-col-left
editor:table-col-right
editor:table-col-copy
editor:table-col-delete
editor:table-col-align-left
editor:table-col-align-center
editor:table-col-align-right
editor:context-menu
file-explorer:open
file-explorer:reveal-active-file
file-explorer:new-folder
global-search:open
switcher:open
graph:open
graph:open-local
graph:animate
backlink:open
backlink:open-backlinks
backlink:toggle-backlinks-in-document
canvas:new-file
canvas:export-as-image
canvas:jump-to-group
canvas:convert-to-file
outgoing-links:open
outgoing-links:open-for-current
tag-pane:open
properties:open
properties:open-local
daily-notes
daily-notes:goto-prev
daily-notes:goto-next
insert-template
insert-current-date
insert-current-time
note-composer:merge-file
note-composer:split-file
note-composer:extract-heading
command-palette:open
bookmarks:open
bookmarks:bookmark-current-view
bookmarks:bookmark-current-search
bookmarks:unbookmark-current-view
bookmarks:bookmark-current-section
bookmarks:bookmark-current-heading
bookmarks:bookmark-all-tabs
markdown-importer:open
zk-prefixer
random-note
outline:open
outline:open-for-current
slides:start
workspaces:load
workspaces:save
workspaces:save-and-load
workspaces:open-modal
file-recovery:open
zotlit:refresh-note-index
easy-toggle-sidebars:toggle-both-sidebars
quick-latex:addAlignBlock
quick-latex:addMatrixBlock
quick-latex:addCasesBlock
excalibrain:excalibrain-addParentField
excalibrain:excalibrain-addChildField
excalibrain:excalibrain-addLeftFriendField
excalibrain:excalibrain-addRightFriendField
excalibrain:excalibrain-addPreviousField
excalibrain:excalibrain-addNextField
excalibrain:excalibrain-selectOntology
excalibrain:excalibrain-start
excalibrain:excalibrain-start-popout
excalibrain:excalibrain-open-hover
advanced-paste:default
hotkey-helper:open-plugins
hotkey-helper:browse-plugins
hotkey-helper:open-settings
hotkey-helper:open-hotkeys
cmdr:macro-0
html-server:start-server
html-server:stop-server
obsidian-meta-bind-plugin:open-docs
obsidian-meta-bind-plugin:open-playground
obsidian-meta-bind-plugin:open-help
obsidian-meta-bind-plugin:open-button-builder
obsidian-meta-bind-plugin:copy-command-id


# .obsidian.vimrc version
```
exmap back obcommand app:go-back
nmap <C-o> :back

exmap togglefold obcommand editor:toggle-fold
nmap zo :togglefold
nmap tf :togglefold

exmap creasesfold obcommand creases:fold
nmap fc :creasesfold

exmap togglecrease obcommand creases:toggle-crease
nmap yc :togglecrease
nmap zc :togglecrease

nmap ě @
nmap H ^
nmap L $

exmap nextHeading jsfile .mdHelpers.js {jumpHeading(true)}
exmap prevHeading jsfile .mdHelpers.js {jumpHeading(false)}
nmap ůů :nextHeading
nmap úú :prevHeading

exmap insCurrentTime obcommand insert-current-time
nmap tt :insCurrentTime

vnoremap L $
vnoremap H ^

```