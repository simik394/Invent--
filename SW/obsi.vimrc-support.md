---
page-title: "esm7/obsidian-vimrc-support: A plugin for the Obsidian.md note-taking software"
url: https://github.com/esm7/obsidian-vimrc-support
date: 2024-01-16 22:03:08
tags:
  - A/sw/obsi/plugin
qual.README: 75
---

# README
## Obsidian Vimrc Support Plugin

[!["Buy Me A Coffee"](https://camo.githubusercontent.com/12f516d86d600c89a6abd2326256045c27325ad7c8532c0d36772965a4923be0/68747470733a2f2f7777772e6275796d6561636f666665652e636f6d2f6173736574732f696d672f637573746f6d5f696d616765732f6f72616e67655f696d672e706e67)](https://www.buymeacoffee.com/esm7)

This plugin loads a file of Vim commands from `VAULT_ROOT/.obsidian.vimrc`. For users of the Obsidian.md Vim mode, this is very useful for making various settings (most notably keymaps) persist.

Note that this plugin is **not** the Vim support of Obsidian -- that support is built-in and you can perfectly use Obsidian in Vim mode without this plugin. This plugin merely implements the ability to load a persistent configuration and adds a few extras.

## Maintainer Needed

While I am still around for some urgent fixes, especially when the plugin stops working due to Obsidian API changes API, I am no longer able to give it the attention it deserves.

Anyone who wishes to take over, please message me.

## Usage

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

## Supported Commands

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

## Installation

In the Obsidian.md settings under "Community plugins", click on "Turn on community plugins", then browse to this plugin.

Alternatively (and less recommended), you can install it manually: just copy `main.js` and `manifest.json` to your vault `VaultFolder/.obsidian/plugins/obsidian-vimrc-support/`.

## Support the Development

If you want to support the development of this plugin, please consider to [buy me a coffee](https://www.buymeacoffee.com/esm7).

## "Please implement \[some Vim feature here\]..."

I'd like to emphasize again that this plugin is a tweak to Obsidian's built-in Vim mode, which is in turn mostly the [Vim mode of CodeMirror](https://codemirror.net/demo/vim.html). And while I am personally very fond of helping everybody make use of Vim modes everywhere, this plugin is often not the best place to implement some types of features.

1.  Vim editor features (e.g. new motions) would best be implemented in CodeMirror, so other editors using this component would enjoy them too! Please consider submitting issues or pull requests [there](https://github.com/codemirror/CodeMirror/) first.
2.  Features that are already implemented by other Obsidian plugins are best to stay in these plugins. Please consider asking these plugin authors to add Vim support for their features (using the CodeMirror API), or even better -- help them out :)

Having said that, adding features here in this plugin is often very easy thanks to the CodeMirror [API for extending its Vim mode](https://codemirror.net/doc/manual.html#vimapi_extending), so as the path of least resistance I will occassionally implement some requested Vim features and be happy to accept PRs.

Things I'd love to add:

-   Implement some standard `vim-markdown` motions for Obsidian, e.g. `[[`, or implement for CodeMirror the 1-2 missing Ex commands required to define these keymaps in the Vimrc.

## Change Vimrc File Location/Name

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

## Some Help with Binding Space Chords (Doom and Spacemacs fans)

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

## Fixed Keyboard Layout in Normal Mode

In many languages and keyboard layouts it becomes problematic or plain impossible to use Vim keys. The Vim keys are located in different positions on some keyboard layouts, which could be confusing when switching layouts, and on some layouts (e.g. non-Western languages) the keys for Vim movements just don't exist. To be able to use Vim mode with those layouts & languages, you can turn on the "fixed keyboard layout" feature in the plugin settings.

When turned on for the first time, or when you click "capture current layout", your current keyboard layout is saved, and that will be the layout that is used when you are in Vim normal or visual mode. When you enter insert mode, you will type in your actual current system layout/language.

**This feature is experimental and may have unintended side-effects relating to Obsidian or editor shortcuts.**

## Relative Line Numbers

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

### Custom Styles for Status Bar

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

## Changelog

