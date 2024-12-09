---
page-title: "m4xshen/autoclose.nvim: A minimalist Neovim plugin that auto pairs & closes brackets"
url: https://github.com/m4xshen/autoclose.nvim
date: "2024-06-23 00:56:03"
tags: [A/sw/plugin, F/prod/homepage, C/, P/pwf]
about: ["[[NeoVim]]"]
aliases: 
- 
by: 
length: 4299
dir: 
---

## autoclose.nvim

[](https://github.com/m4xshen/autoclose.nvim#autoclosenvim)

 [![Stargazers](https://camo.githubusercontent.com/4d262bba798c1dce4088e38b0a3e17bd3a38308ae05187a7dd9f3fb0c0adcac4/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f73746172732f6d34787368656e2f6175746f636c6f73652e6e76696d3f7374796c653d666f722d7468652d6261646765266c6f676f3d737461727368697026636f6c6f723d666165336230266c6f676f436f6c6f723d643965306565266c6162656c436f6c6f723d323832613336)](https://github.com/m4xshen/autoclose.nvim/stargazers)[![Issues](https://camo.githubusercontent.com/048d349696de63d2233e77c71c2d39fba76751b817e320ec07136a41fabf3bcf/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6973737565732f6d34787368656e2f6175746f636c6f73652e6e76696d3f7374796c653d666f722d7468652d6261646765266c6f676f3d676974626f6f6b26636f6c6f723d646462366632266c6f676f436f6c6f723d643965306565266c6162656c436f6c6f723d323832613336) ](https://github.com/m4xshen/autoclose.nvim/issues)[![Contributors](https://camo.githubusercontent.com/f78614df65cbb043c94f390d85cc0c2ad315089edd0292fb75ff18c126fcc884/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f636f6e7472696275746f72732f6d34787368656e2f6175746f636c6f73652e6e76696d3f7374796c653d666f722d7468652d6261646765266c6f676f3d6f70656e736f75726365696e697469617469766526636f6c6f723d616265396233266c6f676f436f6c6f723d643965306565266c6162656c436f6c6f723d323832613336)](https://github.com/m4xshen/autoclose.nvim/contributors)

## 📃 Introduction

[](https://github.com/m4xshen/autoclose.nvim#-introduction)

A minimalist [Neovim](https://neovim.io/) plugin that auto pairs & closes brackets written in 100% Lua.

## ⚙️ Functions

[](https://github.com/m4xshen/autoclose.nvim#%EF%B8%8F-functions)

Most functions work in both insert and command-line mode.

### Auto-close

[](https://github.com/m4xshen/autoclose.nvim#auto-close)

[![](https://user-images.githubusercontent.com/74842863/208931426-4f171094-e1c8-4f85-918a-92250d92c933.gif)](https://user-images.githubusercontent.com/74842863/208931426-4f171094-e1c8-4f85-918a-92250d92c933.gif)

### Auto-delete

[](https://github.com/m4xshen/autoclose.nvim#auto-delete)

(works in `<BS>` and `<C-W>`)

[![](https://user-images.githubusercontent.com/74842863/208931458-0ed78f76-0080-4aa9-a36e-e55881090a0c.gif)](https://user-images.githubusercontent.com/74842863/208931458-0ed78f76-0080-4aa9-a36e-e55881090a0c.gif)

### Auto-escape

[](https://github.com/m4xshen/autoclose.nvim#auto-escape)

[![](https://user-images.githubusercontent.com/74842863/208931512-6f06036a-267a-42d7-9d3e-58a7ddfab1a6.gif)](https://user-images.githubusercontent.com/74842863/208931512-6f06036a-267a-42d7-9d3e-58a7ddfab1a6.gif)

### Auto-indent

[](https://github.com/m4xshen/autoclose.nvim#auto-indent)

(works in `<CR>` and `<S-CR>`, only in insert mode)

[![](https://user-images.githubusercontent.com/74842863/208931561-b9170d08-0697-49b4-90fb-6d432e03c393.gif)](https://user-images.githubusercontent.com/74842863/208931561-b9170d08-0697-49b4-90fb-6d432e03c393.gif)

## ⚡ Requirements

[](https://github.com/m4xshen/autoclose.nvim#-requirements)

-   Neovim >= [v0.7.0](https://github.com/neovim/neovim/releases/tag/v0.7.0)

## 📦 Installation

[](https://github.com/m4xshen/autoclose.nvim#-installation)

1.  Install via your favorite package manager.

-   [vim-plug](https://github.com/junegunn/vim-plug)

Plug 'm4xshen/autoclose.nvim'

-   [packer.nvim](https://github.com/wbthomason/packer.nvim)

use 'm4xshen/autoclose.nvim'

2.  Setup the plugin in your `init.lua`.

require("autoclose").setup()

## 🔧 Configuration

[](https://github.com/m4xshen/autoclose.nvim#-configuration)

You can pass your config table into the `setup()` function.

### Keys

[](https://github.com/m4xshen/autoclose.nvim#keys)

The available options in `keys`:

-   `close`: If set to true, pressing the character will insert both the opening and closing characters, and place the cursor in between them.
-   `escape`: If set to true, pressing the character again will escape it instead of inserting a closing character.
-   `pair`: The string that represents the pair of opening and closing characters. This should be a two-character string, with the opening character first and the closing character second.
-   `disabled_filetypes`: Table of filetypes where the specific key should not be autoclosed.
-   `enabled_filetypes`: Only autoclose the key under these filetypes. This option takes precedence over `disabled_filetypes`.
-   `disable_command_mode`: If set to true, the character will be disabled in command-line mode.

Example: Add a `$$` pair.

require("autoclose").setup({
   keys \= {
      \["$"\] \= { escape \= true, close \= true, pair \= "$$", disabled\_filetypes \= {} },
   },
})

You can also overwrite the default config.

Example: Remove the escape function of `>`.

require("autoclose").setup({
   keys \= {
      \["\>"\] \= { escape \= false, close \= false, pair \= "<>", disabled\_filetypes \= {} },
   },
})

### Options

[](https://github.com/m4xshen/autoclose.nvim#options)

The available options in `options`:

-   `disabled_filetypes`: The plugin will be disabled under the filetypes in this table.
    -   type of the value: table of strings
    -   default value: `{ "text" }`

Example: Disable the plugin in text and markdown file.

require("autoclose").setup({
   options \= {
      disabled\_filetypes \= { "text", "markdown" },
   },
})

-   `disable_when_touch`: Set this to true will disable the auto-close function when the cursor touches character that matches `touch_regex`.
    
    -   type of the value: boolean
    -   default value: `false`
-   `touch_regex`
    
    -   type of the value: string
    -   default value: `"[%w(%[{]"` (alphanumeric characters or `(` or `[` or `{`)

Example:

Your current file: ( `^` points to your cursor position)

You press `(` and the file will become

It doesn't autoclose for you because your cursor touches `w`.

-   `pair_spaces`: Pair the spaces when cursor is inside a pair of `keys`.
    -   type of the value: boolean
    -   default value: `false`

Example:

The `|` is your cursor in insert mode.

after inserting a space:

-   `auto_indent`: Enable auto-indent feature
    
    -   type of the value: boolean
    -   default value: `true`
-   `disable_command_mode`: Disable autoclose for command mode globally
    
    -   type of the value: boolean
    -   default value: `false`

### Default config

[](https://github.com/m4xshen/autoclose.nvim#default-config)

local config \= {
   keys \= {
      \["("\] \= { escape \= false, close \= true, pair \= "()" },
      \["\["\] \= { escape \= false, close \= true, pair \= "\[\]" },
      \["{"\] \= { escape \= false, close \= true, pair \= "{}" },

      \["\>"\] \= { escape \= true, close \= false, pair \= "<>" },
      \[")"\] \= { escape \= true, close \= false, pair \= "()" },
      \["\]"\] \= { escape \= true, close \= false, pair \= "\[\]" },
      \["}"\] \= { escape \= true, close \= false, pair \= "{}" },

      \['"'\] \= { escape \= true, close \= true, pair \= '""' },
      \["'"\] \= { escape \= true, close \= true, pair \= "''" },
      \["\`"\] \= { escape \= true, close \= true, pair \= "\`\`" },
   },
   options \= {
      disabled\_filetypes \= { "text" },
      disable\_when\_touch \= false,
      touch\_regex \= "\[%w(%\[{\]",
      pair\_spaces \= false,
      auto\_indent \= true,
      disable\_command\_mode \= false,
   },
}

### `autoclose.nvim` vs other plugins

[](https://github.com/m4xshen/autoclose.nvim#autoclosenvim-vs-other-plugins)

Some plugins such as `nvim-autopairs` and `ultimate-autopair.nvim` provide a wider range of features such as fast wrap, treesitter pair checking, etc., but some users may not need all of them. If you just want the basic functionality of editing with pairs, you can use autoclose.nvim to achieve the same thing in a simpler and faster way.