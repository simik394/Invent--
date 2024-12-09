---
page-title: "tversteeg/registers.nvim: 📑 Neovim plugin to preview the contents of the registers"
url: https://github.com/tversteeg/registers.nvim
date: "2024-06-20 21:12:16"
tags: 
- A/sw/plugin
- F/homepage
- C/
- P/pwf
about: 
- "[[NeoVim]]"
aliases: 
- ad4eda0c-8cd7-49f7-926c-71549dec27a0
- tversteegregisters.nvim 📑 Neovim plugin to preview the contents of the registers
by: 
length: 9900
dir: 
---

## registers.nvim

[](https://github.com/tversteeg/registers.nvim#registersnvim)

Show register content when you try to access it in Neovim. Written in Lua.

Warning

This plugin is not maintained actively by me anymore. Any pull requests will still be reviewed and merged but I'm not fixing any bugs or adding features myself. If someone is interested in taking over maintainership please contact me!

Requires Neovim 0.7.0+.

## Summary

[](https://github.com/tversteeg/registers.nvim#summary)

This plugin adds an interactive and visually pleasing UI for *selecting* what register item to paste or use next. It offers basic syntax highlighting, a preview, and an equally (if not more) efficient experience using Neovim registers. One simply uses " or CtrlR as one would normally, and then enjoys the benefit of seeing the contents of all filled registers *without having to use the `:reg` command beforehand*. It essentially removes an annoying step in using Neovim registers (checking where a specific item is, which register you might have used earlier, etc.), and lets you increase your efficiency while also increasing Neovim’s aesthetic.

## Features

[](https://github.com/tversteeg/registers.nvim#features)

-   Non-obtrusive, won't influence your workflow
-   Minimal interface, no visual noise
-   Configurable, there's a setting for almost all aspects of this plugin

## Use

[](https://github.com/tversteeg/registers.nvim#use)

The pop-up window showing the registers and their values can be opened in one of the following ways:

-   Call `:Registers`
-   Press " in *normal* or *visual* mode
-   Press CtrlR in *insert* mode

[![preview](https://github.com/tversteeg/registers.nvim/raw/main/.github/img/preview.png?raw=true)](https://github.com/tversteeg/registers.nvim/blob/main/.github/img/preview.png?raw=true)

Empty registers are not shown by default.

### Navigate

[](https://github.com/tversteeg/registers.nvim#navigate)

Use the Up and Down or CtrlP and CtrlN or CtrlJ and CtrlK keys to select the register you want to use and press Enter to apply it, or type the register you want to apply, which is one of the following:

" 0–9 a–z : . % # \= \* + \_ /

## Example Workflow

[](https://github.com/tversteeg/registers.nvim#example-workflow)

### With `registers.nvim`:

[](https://github.com/tversteeg/registers.nvim#with-registersnvim)

-   Copy item to system clipboard or Neovim register (this can also be achieved using `registers.nvim`);
-   In normal mode, type the " key. The `registers.nvim` pop-up will appear.
-   You can now use the arrow keys (or other navigation keys) to move to a specific item (representing an item in the Neovim register, i.e., what you see with `:reg`) in the list being displayed. Pressing enter on this item will ‘select’ it.
-   Alternatively, you can just type the highlighted character being displayed in the left margin of the pop-up, next to the register item you want to select. This resembles a workflow without `registers.nvim`, except that you get the visual feedback and confirmation of what is inside the register beforehand. It is also useful for remembering which register you placed something in ;) .
    -   I.e., type "+ to select from the system clipboard, **or** use the arrow keys to navigate to + and hit enter)
-   Once you have selected a register item, you can proceed to perform your desired action (e.g., yank, paste, etc.). To do this, simply use the usual keys: y, p, etc.

One can also call the `registers.nvim` pop-up through other means, not just ". For example, in insert mode, one can use CtrlR (this is default vim behaviour). If one does not want to use these key-binds (or bind your own keys), one can use the `:Registers` command.

### Without `registers.nvim`:

[](https://github.com/tversteeg/registers.nvim#without-registersnvim)

-   Copy item to system clipboard or vim register;
-   Use the `:reg` command to view registers. Make sure to remember the `Name` of the register item you want to use for future reference.
-   In normal mode, type ". You will get no visual feedback.
-   Now type the `Name` of the register item you want to select, as listed in the output of `:reg`.
-   Now perform the desired action (usually either yanking, y, or pasting, p)

### Using `registers.nvim` is definitely more aesthetically pleasing and probably makes registers easier for beginners to understand—but is it actually better for experienced Neovim users, too?

[](https://github.com/tversteeg/registers.nvim#using-registersnvim-is-definitely-more-aesthetically-pleasing-and-probably-makes-registers-easier-for-beginners-to-understandbut-is-it-actually-better-for-experienced-neovim-users-too)

[Well, users say ;)](https://github.com/tversteeg/registers.nvim/issues/102#issuecomment-1870503908)…

> I definitely think so. I use registers (and tmux buffers) extensively, and remembering a register’s name that I arbitrarily chose half an hour ago is not always the easiest for me. This means that I usually end up typing ", then realizing that I don’t know what to type next, opening `:reg`, finding the register I want (usually a quite difficult task), *trying* to remember its name, typing " *again*, forgetting the register’s name *again*, going back to `:reg`, and finally: typing "<register name>. This costs an excessive amount of time. `registers.nvim` has solved this problem for me because it previews the contents of a register, removing the need to remember arbitrary register names. In other words, I love the plugin :)

## Install

[](https://github.com/tversteeg/registers.nvim#install)

### Packer

[](https://github.com/tversteeg/registers.nvim#packer)

use {
	"tversteeg/registers.nvim",
	config \= function()
		require("registers").setup()
	end,
}

### Lazy.nvim

[](https://github.com/tversteeg/registers.nvim#lazynvim)

This configuration lazy-loads the plugin only when it’s invoked.

{
	"tversteeg/registers.nvim",
	cmd \= "Registers",
	config \= true,
	keys \= {
		{ "\\"",    mode \= { "n", "v" } },
		{ "<C-R>", mode \= "i" }
	},
	name \= "registers",
}

## Configuration

[](https://github.com/tversteeg/registers.nvim#configuration)

This plugin can be configured by passing a table to `require("registers").setup({})`. Configuration options can be found in Neovim’s documentation after installing with: [`:h registers`](https://github.com/tversteeg/registers.nvim/blob/main/doc/registers.txt).

### Default Values

[](https://github.com/tversteeg/registers.nvim#default-values)

use {
    "tversteeg/registers.nvim",
    config \= function()
        local registers \= require("registers")
        registers.setup({

        \-- Show these registers in the order of the string
        show \= "\*+\\"\-/\_=#%.0123456789abcdefghijklmnopqrstuvwxyz:",
        \-- Show a line at the bottom with registers that aren't filled
        show\_empty \= true,
        \-- Expose the :Registers user command
        register\_user\_command \= true,
        \-- Always transfer all selected registers to the system clipboard
        system\_clipboard \= true,
        \-- Don't show whitespace at the begin and end of the register's content
        trim\_whitespace \= true,
        \-- Don't show registers which are exclusively filled with whitespace
        hide\_only\_whitespace \= true,
        \-- Show a character next to the register name indicating how the register will be applied
        show\_register\_types \= true,
        bind\_keys \= {
            \-- Show the window when pressing " in normal mode, applying the selected register as part of a motion, which is the default behavior of Neovim
            normal    \= registers.show\_window({ mode \= "motion" }),
            \-- Show the window when pressing " in visual mode, applying the selected register as part of a motion, which is the default behavior of Neovim
            visual    \= registers.show\_window({ mode \= "motion" }),
            \-- Show the window when pressing <C-R> in insert mode, inserting the selected register, which is the default behavior of Neovim
            insert    \= registers.show\_window({ mode \= "insert" }),

            \-- When pressing the key of a register, apply it with a very small delay, which will also highlight the selected register
            registers \= registers.apply\_register({ delay \= 0.1 }),
            \-- Immediately apply the selected register line when pressing the return key
            \["<CR>"\]  \= registers.apply\_register(),
            \-- Close the registers window when pressing the Esc key
            \["<Esc>"\] \= registers.close\_window(),

            \-- Move the cursor in the registers window down when pressing <C-n>
            \["<C-n>"\] \= registers.move\_cursor\_down(),
            \-- Move the cursor in the registers window up when pressing <C-p>
            \["<C-p>"\] \= registers.move\_cursor\_up(),
            \-- Move the cursor in the registers window down when pressing <C-j>
            \["<C-j>"\] \= registers.move\_cursor\_down(),
            \-- Move the cursor in the registers window up when pressing <C-k>
            \["<C-k>"\] \= registers.move\_cursor\_up(),
            \-- Clear the register of the highlighted line when pressing <DeL>
            \["<Del>"\] \= registers.clear\_highlighted\_register(),
            \-- Clear the register of the highlighted line when pressing <BS>
            \["<BS>"\]  \= registers.clear\_highlighted\_register(),
        },
        events \= {
            \-- When a register line is highlighted, show a preview in the main buffer with how the register will be applied, but only if the register will be inserted or pasted
            on\_register\_highlighted \= registers.preview\_highlighted\_register({ if\_mode \= { "insert", "paste" } }),
        },
        symbols \= {
            \-- Show a special character for line breaks
            newline \= "⏎",
            \-- Show space characters without changes
            space \= " ",
            \-- Show a special character for tabs
            tab \= "·",
            \-- The character to show when a register will be applied in a char-wise fashion
            register\_type\_charwise \= "ᶜ",
            \-- The character to show when a register will be applied in a line-wise fashion
            register\_type\_linewise \= "ˡ",
            \-- The character to show when a register will be applied in a block-wise fashion
            register\_type\_blockwise \= "ᵇ",
        },
        window \= {
            \-- The window can't be wider than 100 characters
            max\_width \= 100,
            \-- Show a small highlight in the sign column for the line the cursor is on
            highlight\_cursorline \= true,
            \-- Don't draw a border around the registers window
            border \= "none",
            \-- Apply a tiny bit of transparency to the the window, letting some characters behind it bleed through
            transparency \= 10,
        },
        \-- Highlight the sign registers as regular Neovim highlights
        sign\_highlights \= {
            cursorlinesign \= "CursorLine",
            signcolumn \= "SignColumn",
            cursorline \= "Visual",
            selection \= "Constant",
            default \= "Function",
            unnamed \= "Statement",
            read\_only \= "Type",
            expression \= "Exception",
            black\_hole \= "Error",
            alternate\_buffer \= "Operator",
            last\_search \= "Tag",
            delete \= "Special",
            yank \= "Delimiter",
            history \= "Number",
            named \= "Todo",
        },