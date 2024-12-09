---
page-title: "windwp/nvim-autopairs: autopairs for neovim written in lua"
url: https://github.com/windwp/nvim-autopairs
date: "2024-06-23 01:04:14"
tags: [A/sw/plugin, F/prod/homepage, C/, P/pwf]
about: ["[[NeoVim]]"]
aliases: 
- 
by: 
length: 9987
dir: 
---

## nvim-autopairs

[](https://github.com/windwp/nvim-autopairs#nvim-autopairs)

A super powerful autopair plugin for Neovim that supports multiple characters.

Requires neovim 0.7

## Installation

[](https://github.com/windwp/nvim-autopairs#installation)

Install the plugin with your preferred package manager:

### [lazy.nvim](https://github.com/folke/lazy.nvim)

[](https://github.com/windwp/nvim-autopairs#lazynvim)

{
    'windwp/nvim-autopairs',
    event \= "InsertEnter",
    config \= true
    \-- use opts = {} for passing setup options
    \-- this is equalent to setup({}) function
}

### [vim-plug](https://github.com/junegunn/vim-plug)

[](https://github.com/windwp/nvim-autopairs#vim-plug)

Plug 'windwp/nvim-autopairs'

lua << EOF
require("nvim-autopairs").setup {}
EOF

### [packer](https://github.com/wbthomason/packer.nvim)

[](https://github.com/windwp/nvim-autopairs#packer)

use {
    "windwp/nvim-autopairs",
    event \= "InsertEnter",
    config \= function()
        require("nvim-autopairs").setup {}
    end
}

## Default values

[](https://github.com/windwp/nvim-autopairs#default-values)

{
    disable\_filetype \= { "TelescopePrompt", "spectre\_panel" }
    disable\_in\_macro \= true  \-- disable when recording or executing a macro
    disable\_in\_visualblock \= false \-- disable when insert after visual block mode
    disable\_in\_replace\_mode \= true
    ignored\_next\_char \= \[=\[\[%w%%%'%\[%"%.%\`%$\]\]=\]
    enable\_moveright \= true
    enable\_afterquote \= true  \-- add bracket pairs after quote
    enable\_check\_bracket\_line \= true  \--- check bracket in same line
    enable\_bracket\_in\_quote \= true \--
    enable\_abbr \= false \-- trigger abbreviation
    break\_undo \= true \-- switch for basic rule break undo sequence
    check\_ts \= false
    map\_cr \= true
    map\_bs \= true  \-- map the <BS> key
    map\_c\_h \= false  \-- Map the <C-h> key to delete a pair
    map\_c\_w \= false \-- map <c-w> to delete a pair if possible
}

### Override default values

[](https://github.com/windwp/nvim-autopairs#override-default-values)

require('nvim-autopairs').setup({
  disable\_filetype \= { "TelescopePrompt" , "vim" },
})

#### Mapping `<CR>`

[](https://github.com/windwp/nvim-autopairs#mapping-cr)

```
Before        Input         After
------------------------------------
{|}           <CR>          {
                                |
                            }
------------------------------------
```

**nvim-cmp**

### You need to add mapping \`CR\` on nvim-cmp setup. Check readme.md on nvim-cmp repo.

[](https://github.com/windwp/nvim-autopairs#you-need-to-add-mapping-cr-on-nvim-cmp-setupcheck-readmemd-on-nvim-cmp-repo)

\-- If you want insert \`(\` after select function or method item
local cmp\_autopairs \= require('nvim-autopairs.completion.cmp')
local cmp \= require('cmp')
cmp.event:on(
  'confirm\_done',
  cmp\_autopairs.on\_confirm\_done()
)

You can customize the kind of completion to add `(` or any character.

local handlers \= require('nvim-autopairs.completion.handlers')

cmp.event:on(
  'confirm\_done',
  cmp\_autopairs.on\_confirm\_done({
    filetypes \= {
      \-- "\*" is a alias to all filetypes
      \["\*"\] \= {
        \["("\] \= {
          kind \= {
            cmp.lsp.CompletionItemKind.Function,
            cmp.lsp.CompletionItemKind.Method,
          },
          handler \= handlers\["\*"\]
        }
      },
      lua \= {
        \["("\] \= {
          kind \= {
            cmp.lsp.CompletionItemKind.Function,
            cmp.lsp.CompletionItemKind.Method
          },
          \---@param char string
          \---@param item table item completion
          \---@param bufnr number buffer number
          \---@param rules table
          \---@param commit\_character table<string>
          handler \= function(char, item, bufnr, rules, commit\_character)
            \-- Your handler function. Inspect with print(vim.inspect{char, item, bufnr, rules, commit\_character})
          end
        }
      },
      \-- Disable for tex
      tex \= false
    }
  })
)

Don't use `nil` to disable a filetype. If a filetype is `nil` then `*` is used as fallback.

**coq\_nvim**

local remap \= vim.api.nvim\_set\_keymap
local npairs \= require('nvim-autopairs')

npairs.setup({ map\_bs \= false, map\_cr \= false })

vim.g.coq\_settings \= { keymap \= { recommended \= false } }

\-- these mappings are coq recommended mappings unrelated to nvim-autopairs
remap('i', '<esc>', \[\[pumvisible() ? "<c-e><esc>" : "<esc>"\]\], { expr \= true, noremap \= true })
remap('i', '<c-c>', \[\[pumvisible() ? "<c-e><c-c>" : "<c-c>"\]\], { expr \= true, noremap \= true })
remap('i', '<tab>', \[\[pumvisible() ? "<c-n>" : "<tab>"\]\], { expr \= true, noremap \= true })
remap('i', '<s-tab>', \[\[pumvisible() ? "<c-p>" : "<bs>"\]\], { expr \= true, noremap \= true })

\-- skip it, if you use another global object
\_G.MUtils\= {}

MUtils.CR \= function()
  if vim.fn.pumvisible() ~= 0 then
    if vim.fn.complete\_info({ 'selected' }).selected ~= \-1 then
      return npairs.esc('<c-y>')
    else
      return npairs.esc('<c-e>') .. npairs.autopairs\_cr()
    end
  else
    return npairs.autopairs\_cr()
  end
end
remap('i', '<cr>', 'v:lua.MUtils.CR()', { expr \= true, noremap \= true })

MUtils.BS \= function()
  if vim.fn.pumvisible() ~= 0 and vim.fn.complete\_info({ 'mode' }).mode \== 'eval' then
    return npairs.esc('<c-e>') .. npairs.autopairs\_bs()
  else
    return npairs.autopairs\_bs()
  end
end
remap('i', '<bs>', 'v:lua.MUtils.BS()', { expr \= true, noremap \= true })

**without completion plugin**

\-- add option map\_cr
npairs.setup({ map\_cr \= true })

[another completion plugin](https://github.com/windwp/nvim-autopairs/wiki/Completion-plugin)

If you have a problem with indent after you press `<CR>` please check the settings of treesitter indent or install a plugin that has indent support for your filetype.

### Rule

[](https://github.com/windwp/nvim-autopairs#rule)

nvim-autopairs uses rules with conditions to check pairs.

local Rule \= require('nvim-autopairs.rule')
local npairs \= require('nvim-autopairs')

npairs.add\_rule(Rule("$$","$$","tex"))

\-- you can use some built-in conditions

local cond \= require('nvim-autopairs.conds')
print(vim.inspect(cond))

npairs.add\_rules({
  Rule("$", "$",{"tex", "latex"})
    \-- don't add a pair if the next character is %
    :with\_pair(cond.not\_after\_regex("%%"))
    \-- don't add a pair if  the previous character is xxx
    :with\_pair(cond.not\_before\_regex("xxx", 3))
    \-- don't move right when repeat character
    :with\_move(cond.none())
    \-- don't delete if the next character is xx
    :with\_del(cond.not\_after\_regex("xx"))
    \-- disable adding a newline when you press <cr>
    :with\_cr(cond.none())
  },
  \-- disable for .vim files, but it work for another filetypes
  Rule("a","a","\-vim")
)

npairs.add\_rules({
  Rule("$$","$$","tex")
    :with\_pair(function(opts)
        print(vim.inspect(opts))
        if opts.line\=="aa $$" then
        \-- don't add pair on that line
          return false
        end
    end)
   }
)

\-- you can use regex
\-- press u1234 => u1234number
npairs.add\_rules({
    Rule("u%d%d%d%d$", "number", "lua")
      :use\_regex(true)
})

\-- press x1234 => x12341234
npairs.add\_rules({
    Rule("x%d%d%d%d$", "number", "lua")
      :use\_regex(true)
      :replace\_endpair(function(opts)
          \-- print(vim.inspect(opts))
          return opts.prev\_char:sub(#opts.prev\_char \- 3,#opts.prev\_char)
      end)
})

\-- you can do anything with regex +special key
\-- example press tab to uppercase text:
\-- press b1234s<tab> => B1234S1234S

npairs.add\_rules({
  Rule("b%d%d%d%d%w$", "", "vim")
    :use\_regex(true,"<tab>")
    :replace\_endpair(function(opts)
          return
              opts.prev\_char:sub(#opts.prev\_char \- 4,#opts.prev\_char)
              .."<esc>viwU"
    end)
})

\-- you can exclude filetypes
npairs.add\_rule(
  Rule("$$","$$")
    :with\_pair(cond.not\_filetypes({"lua"}))
)
\--- check ./lua/nvim-autopairs/rules/basic.lua

[Rules API](https://github.com/windwp/nvim-autopairs/wiki/Rules-API)

### Treesitter

[](https://github.com/windwp/nvim-autopairs#treesitter)

You can use treesitter to check for a pair.

local npairs \= require("nvim-autopairs")
local Rule \= require('nvim-autopairs.rule')

npairs.setup({
    check\_ts \= true,
    ts\_config \= {
        lua \= {'string'},\-- it will not add a pair on that treesitter node
        javascript \= {'template\_string'},
        java \= false,\-- don't check treesitter on java
    }
})

local ts\_conds \= require('nvim-autopairs.ts-conds')

\-- press % => %% only while inside a comment or string
npairs.add\_rules({
  Rule("%", "%", "lua")
    :with\_pair(ts\_conds.is\_ts\_node({'string','comment'})),
  Rule("$", "$", "lua")
    :with\_pair(ts\_conds.is\_not\_ts\_node({'function'}))
})

### Don't add pairs if it already has a close pair in the same line

[](https://github.com/windwp/nvim-autopairs#dont-add-pairs-if-it-already-has-a-close-pair-in-the-same-line)

if **next character** is a close pair and it doesn't have an open pair in same line, then it will not add a close pair

```
Before        Input         After
------------------------------------
(  |))         (            (  (|))

```

require('nvim-autopairs').setup({
  enable\_check\_bracket\_line \= false
})

### Don't add pairs if the next char is alphanumeric

[](https://github.com/windwp/nvim-autopairs#dont-add-pairs-if-the-next-char-is-alphanumeric)

You can customize how nvim-autopairs will behave if it encounters a specific character

require('nvim-autopairs').setup({
  ignored\_next\_char \= "\[%w%.\]" \-- will ignore alphanumeric and \`.\` symbol
})

```
Before        Input         After
------------------------------------
|foobar        (            (|foobar
|.foobar       (            (|.foobar
```

### Plugin Integration

[](https://github.com/windwp/nvim-autopairs#plugin-integration)

  require('nvim-autopairs').disable()
  require('nvim-autopairs').enable()
  require('nvim-autopairs').remove\_rule('(') \-- remove rule (
  require('nvim-autopairs').clear\_rules() \-- clear all rules
  require('nvim-autopairs').get\_rules('"')

-   Sample

\-- remove add single quote on filetype scheme or lisp
require("nvim-autopairs").get\_rules("'")\[1\].not\_filetypes \= { "scheme", "lisp" }
require("nvim-autopairs").get\_rules("'")\[1\]:with\_pair(cond.not\_after\_text("\["))

### FastWrap

[](https://github.com/windwp/nvim-autopairs#fastwrap)

```
Before        Input                    After         Note
-----------------------------------------------------------------
(|foobar      <M-e> then press $       (|foobar)
(|)(foobar)   <M-e> then press q       (|(foobar))
(|foo bar     <M-e> then press qh      (|foo) bar
(|foo bar     <M-e> then press qH      (foo|) bar
(|foo bar     <M-e> then press qH      (foo)| bar    if cursor_pos_before = false
```

\-- put this to setup function and press <a-e> to use fast\_wrap
npairs.setup({
    fast\_wrap \= {},
})

\-- change default fast\_wrap
npairs.setup({
    fast\_wrap \= {
      map \= '<M-e>',
      chars \= { '{', '\[', '(', '"', "'" },
      pattern \= \[=\[\[%'%"%>%\]%)%}%,\]\]=\],
      end\_key \= '$',
      before\_key \= 'h',
      after\_key \= 'l',
      cursor\_pos\_before \= true,
      keys \= 'qwertyuiopzxcvbnmasdfghjkl',
      manual\_position \= true,
      highlight \= 'Search',
      highlight\_grey\='Comment'
    },
})

### autotag html and tsx

[](https://github.com/windwp/nvim-autopairs#autotag-html-and-tsx)

[autotag](https://github.com/windwp/nvim-ts-autotag)

### Endwise

[](https://github.com/windwp/nvim-autopairs#endwise)

[endwise](https://github.com/windwp/nvim-autopairs/wiki/Endwise)

### Custom rules

[](https://github.com/windwp/nvim-autopairs#custom-rules)

[rules](https://github.com/windwp/nvim-autopairs/wiki/Custom-rules)

## Sponsors

[](https://github.com/windwp/nvim-autopairs#sponsors)

Thanks to everyone who sponsors my projects and makes continued development maintenance possible!

[![](https://github.com/t4t5.png)](https://github.com/t4t5)