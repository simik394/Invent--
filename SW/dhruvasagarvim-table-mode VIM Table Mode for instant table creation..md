---
page-title: "dhruvasagar/vim-table-mode: VIM Table Mode for instant table creation."
url: https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file
date: 2024-06-21 03:33:43
tags:
  - A/sw/plugin
  - F/prod/homepage
  - C/
  - P/pwf
about:
  - "[[NeoVim]]"
  - "[[Inv/SW/Vim]]"
aliases:
  - 
by: 
length: 11379
dir: 
---

## VIM Table Mode v4.8.1 [![Build](https://github.com/dhruvasagar/vim-table-mode/actions/workflows/ci.yml/badge.svg)](https://github.com/dhruvasagar/vim-table-mode/actions/workflows/ci.yml)

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#vim-table-mode-v481-)

An awesome automatic table creator & formatter allowing one to create neat tables as you type.

## Getting Started

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#getting-started)

### Installation

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#installation)

#### [Vim 8+ native package manager](https://www.danielfranklin.id.au/vim-8-package-management/)

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#vim-8-native-package-manager)

clone into `.vim/pack/plugins/start` (the `plugins` folder can have any name)

Add `packloadall` in your `~/.vimrc`.

#### [NeoBundle](https://github.com/Shougo/neobundle.vim)

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#neobundle)

Add `NeoBundle 'dhruvasagar/vim-table-mode'` to your `~/.vimrc`.

#### [pathogen.vim](https://github.com/tpope/vim-pathogen)

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#pathogenvim)

Add a git submodule for your plugin:

$ cd ~/.vim
$ git submodule add git@github.com:dhruvasagar/vim-table-mode.git bundle/table-mode

Copy all files under `autoload/`, `plugin/`, and `doc/` to respective `~/.vim/autoload/`, `~/.vim/plugin` and `~/.vim/doc` under UNIX, or `vimfiles/autoload/`, `vimfiles/plugin/` and `vimfiles/doc` under WINDOWS and restart Vim.

#### [vim-plug](https://github.com/junegunn/vim-plug)

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#vim-plug)

Add `Plug 'dhruvasagar/vim-table-mode'` to your `~/.vimrc`.

### Creating table on-the-fly

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#creating-table-on-the-fly)

To start using the plugin in the on-the-fly mode use `:TableModeToggle` mapped to <Leader>tm by default (which means \\ t m if you didn't override the by `:let mapleader = ','` to have , t m).

Tip: You can use the following to quickly enable / disable table mode in insert mode by using `||` or `__`:

> function! s:isAtStartOfLine(mapping)
>   let text\_before\_cursor \= getline('.')\[0 : col('.')\-1\]
>   let mapping\_pattern \= '\\V' . escape(a:mapping, '\\')
>   let comment\_pattern \= '\\V' . escape(substitute(&l:commentstring, '%s.\*$', '', ''), '\\')
>   return (text\_before\_cursor \=~? '^' . ('\\v(' . comment\_pattern . '\\v)?') . '\\s\*\\v' . mapping\_pattern . '\\v$')
> endfunction
> 
> inoreabbrev <expr> <bar><bar>
>           \\ <SID>isAtStartOfLine('\\|\\|') ?
>           \\ '<c-o>:TableModeEnable<cr><bar><space><bar><left><left>' : '<bar><bar>'
> inoreabbrev <expr> \_\_
>           \\ <SID>isAtStartOfLine('\_\_') ?
>           \\ '<c-o>:silent! TableModeDisable<cr>' : '\_\_'

Enter the first line, delimiting columns by the `|` symbol. The plugin reacts by inserting spaces between the text and the separator if you omit them:

```
| name | address | phone |
```

In the second line (without leaving Insert mode), enter `|` twice. The plugin will write a properly formatted horizontal line:

```
| name | address | phone |
|------+---------+-------|
```

When you enter the subsequent lines, the plugin will automatically adjust the formatting to match the text you’re entering every time you press `|`:

```
| name       | address | phone |
|------------+---------+-------|
| John Adams |
```

Go on until the table is ready:

```
| name            | address                  | phone      |
|-----------------+--------------------------+------------|
| John Adams      | 1600 Pennsylvania Avenue | 0123456789 |
|-----------------+--------------------------+------------|
| Sherlock Holmes | 221B Baker Street        | 0987654321 |
|-----------------+--------------------------+------------|
```

Then you can return to the first line and above it enter `||`:

```
|-----------------+--------------------------+------------|
| name            | address                  | phone      |
|-----------------+--------------------------+------------|
| John Adams      | 1600 Pennsylvania Avenue | 0123456789 |
|-----------------+--------------------------+------------|
| Sherlock Holmes | 221B Baker Street        | 0987654321 |
|-----------------+--------------------------+------------|
```

Corner separators are adjustable:

For Markdown-compatible tables use

```
let g:table_mode_corner='|'


|-----------------|--------------------------|------------|
| name            | address                  | phone      |
|-----------------|--------------------------|------------|
| John Adams      | 1600 Pennsylvania Avenue | 0123456789 |
|-----------------|--------------------------|------------|
| Sherlock Holmes | 221B Baker Street        | 0987654321 |
|-----------------|--------------------------|------------|
```

To get ReST-compatible tables use

```
let g:table_mode_corner_corner='+'
let g:table_mode_header_fillchar='='


+-----------------+--------------------------+------------+
| name            | address                  | phone      |
+=================+==========================+============+
| John Adams      | 1600 Pennsylvania Avenue | 0123456789 |
+-----------------+--------------------------+------------+
| Sherlock Holmes | 221B Baker Street        | 0987654321 |
+-----------------+--------------------------+------------+
```

Markdown and ReST filetypes have automatically configured corners.

> If you wish to override their configurations, it should be done in an after plugin, for example :
> 
> In a `$VIM/after/ftplugin/markdown/custom.vim` you can add the following :
> 
> let b:table\_mode\_corner\='+'

You can also define in a table header border how its content should be aligned, whether center, right or left by using a `:` character defined by `g:table_mode_align_char` option.

If you manipulate the table when table mode is disabled or copy paste a table from clipboard from outside and it ends up being misaligned, you can realign it using `:TableModeRealign` or using the default mapping <Leader>tr (defined by the option `g:table_mode_relign_map`).

### Formatting existing content into a table

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#formatting-existing-content-into-a-table)

Table Mode wouldn't justify its name if it didn't allow formatting existing content into a table. And it does as promised. Like table creation typing on the fly, formatting existing content into a table is equally simple. You can visually select multiple lines and call `:Tableize` on it. Alternatively, the mapping <Leader>tt can be used (defined by the option `g:table_mode_tableize_map`). This converts CSV (Comma-separated Values) data into a table.

If however you wish to use a different delimiter, you can use the command `:Tableize/{pattern}` in a similar fashion as you tabulate (e.g. `:Tableize/;` uses ';' as the delimiter) or use the mapping <Leader>T (defined by the option `g:table_mode_tableize_op_map`) which takes input in the cmd-line and uses the `{pattern}` input as the delimiter.

`:Tableize` also accepts a range. Call it by giving lines manually like `:line1,line2Tableize`. However this may not be intuitive. You can use the mapping <Leader>T with a `[count]` to apply it to the next `[count]` lines in standard vim style.

### Moving around

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#moving-around)

Now you can move between cells using table mode motions \[|, \]|, {| & }| to move left | right | up | down cells respectively. The left | right motions wrap around the table and move to the next | previous row after the last | first cell in the current row if one exists.

### Manipulating Table

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#manipulating-table)

-   **Cell Text Object** :
    
    Tableize provides a text object for manipulating table cells. Following the vim philosophy the you have i| & a| for the inner and around (including the immediate right table separator) the table cell.
    
-   **Delete Row** :
    
    You can use the <Leader>tdd mapping (defined by the option `g:table_mode_delete_row_map`) to delete the current table row (provided you are within a table row). This can be preceeded with a `[count]` to delete multiple rows as per Vim command grammar.
    
-   **Delete Column** :
    
    You can use the <Leader>tdc mapping (defined by the option `g:table_mode_delete_column_map`) to delete the entire current column (provided you are within a table row), this can also be preceeded with a `[count]` to delete multiple columns.
    
-   **Insert Column** :
    
    You can use the <Leader>tic mapping (defined by the option `g:table_mode_insert_column_after_map`) to insert a column after the cursor (provided you are within a table row). Of course you can use the <Leader>tiC mapping defined by `g:table_mode_insert_column_before_map` to insert a column before the cursor. Both can also be preceeded with a \[count\] to insert multiple columns.
    

### Highlight cells based on content

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#highlight-cells-based-on-content)

You can highlight cells based on content by setting `let g:table_mode_color_cells` : - cells starting with `yes` will use the `yesCell` highlight group. - cells starting with `no` will use the `noCell` highlight group. - cells starting with `?` will use the `maybeCell` hightlight group.

You can overwrite any highlight group. For exemple use `hi yesCell ctermfg=2` to remove the background color.

## Advanced Usage: Spreadsheet Capabilities

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#advanced-usage-spreadsheet-capabilities)

### Table Formulas

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#table-formulas)

Table Mode now has support for formulas like a spreadsheet. There are 2 ways of defining formulas :

-   You can add formulas using `:TableAddFormula` or the mapping <Leader>tfa (defined by the option `g:table_mode_add_formula_map`) from within a table cell, which will ask for input on the cmd-line with a `f=` prompt. The input formula will be appended to the formula line if one exists or a new one will be created with the input formula taking the current cell as the target cell. The formula line is evaluated immidiately to reflect the results.
    
-   You can directly add / manipulate formula expressions in the formula line. The formula line is a commented line right after the table, or optionally separated from the table by a single empty line. It begins with 'tmf:' (table mode formula). eg) `# tmf: $3=$2*$1`. You can add multiple formulas on the line separated with a ';' eg) `# tmf: $3=$2*$1;$4=$3/3.14`
    

You can evaluate the formula line using `:TableEvalFormulaLine` or the mapping <Leader>tfe (defined by the option `g:table_mode_eval_expr_map`) from anywhere inside the table or while on the formula line.

NOTE: You can now use the mapping <Leader>t?

### Formula Expressions

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#formula-expressions)

Expressions are of the format `$target = formula`.

-   The `target` can be of 2 forms :
    
    -   `$n`: This matches the table column number `n`. So the `formula` would be evaluated for each cell in that column and the result would be placed in it. You can use negative indice to represent column relative to the last, -1 being the last.
        
    -   `$n,m`: This matches the table cell n,m (row, column). So in this case the formula would be evaluated and the result will be placed in this cell. You can also use negative values to refer to cells relative to the size, -1 being the last (row or column).
        
-   The `formula` can be a simple mathematical expression involving cells which are also defined by the same format as that of the target cell. You can use all native vim functions within the formula. Apart from that table mode also provides 2 special functions `Sum` and `Average`. Both these functions take a range as input. A range can be of two forms:
    
    -   `r1:r2`: This represents cells in the current column from row `r1` through `r2`. If `r2` is negative it represents `r2` rows above the current row (of the target cell).
        
    -   `r1,c1:r2,c2`: This represents cells in the table from cell r1,c1 through cell r2,c2 (row, column).
        
-   Examples :
    
    -   `$2 = $1 * $1`
    -   `$2 = pow($1, 5)` NOTE: Remember to put space between the $1, and 5 here otherwise it will be treated like a table cell.
    -   `$2 = $1 / $1,3`
    -   `$1,2 = $1,1 * $1,1`
    -   `$5,1 = Sum(1:-1)`
    -   `$5,1 = float2nr(Sum(1:-1))`
    -   `$5,3 = Sum(1,2:5,2)`
    -   `$5,3 = Sum(1,2:5,2)/$5,1`
    -   `$5,3 = Average(1,2:5,2)/$5,1`

## Demo

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#demo)

[![](https://camo.githubusercontent.com/aa9851b54d9e92f136ff997691cca7d504a60e8cd7647e7274267e4d8a8a6612/68747470733a2f2f7261772e6769746875622e636f6d2f6178696c2f76696d2d7461626c652d6d6f64652f6d61737465722f796f75747562652e706e67)](http://www.youtube.com/watch?v=9lVQ0VJY3ps)

## Change Log

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#change-log)

See [CHANGELOG.md](https://github.com/dhruvasagar/vim-table-mode/blob/master/CHANGELOG.md)

## Contributing

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#contributing)

### Reporting an Issue :

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#reporting-an-issue-)

-   Use [Github Issue Tracker](https://github.com/dhruvasagar/vim-table-mode/issues)

### Contributing to code :

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#contributing-to-code-)

-   Fork it.
-   Commit your changes and give your commit message some love.
-   Push to your fork on github.
-   Open a Pull Request.

## Credit

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#credit)

I must thank Tim Pope for inspiration. The initial concept was created by him named [cucumbertables.vim](https://gist.github.com/tpope/287147).

Also a shout out to godlygeek who developed the incredible [Tabular](http://github.com/godlygeek/tabular) plugin.

## Contributors

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#contributors)

### Code Contributors

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#code-contributors)

This project exists thanks to all the people who contribute. \[[Contribute](https://github.com/dhruvasagar/vim-table-mode/blob/master/CONTRIBUTING.md)\]. [![](https://camo.githubusercontent.com/f56fbba15235520d4f5a0e0745543c80fdc2ce35e7ef577701cbf90368a5a52a/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f76696d2d7461626c652d6d6f64652f636f6e7472696275746f72732e7376673f77696474683d38393026627574746f6e3d66616c7365)](https://github.com/dhruvasagar/vim-table-mode/graphs/contributors)

### Financial Contributors

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#financial-contributors)

Become a financial contributor and help us sustain our community. \[[Contribute](https://opencollective.com/vim-table-mode/contribute)\]

#### Individuals

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#individuals)

[![](https://camo.githubusercontent.com/bcf182b3f0cade00d986eaf1e18706a06723eb5de1514537db9af06f2c73d5f2/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f76696d2d7461626c652d6d6f64652f696e646976696475616c732e7376673f77696474683d383930)](https://opencollective.com/vim-table-mode)

#### Organizations

[](https://github.com/dhruvasagar/vim-table-mode?tab=readme-ov-file#organizations)

Support this project with your organization. Your logo will show up here with a link to your website. \[[Contribute](https://opencollective.com/vim-table-mode/contribute)\]

[![](https://camo.githubusercontent.com/c8e5cc675a5ff16f3c65c5b23a448bc13a4d5c3742797d6b435a64e69132e0f1/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f76696d2d7461626c652d6d6f64652f6f7267616e697a6174696f6e2f302f6176617461722e737667)](https://opencollective.com/vim-table-mode/organization/0/website) [![](https://camo.githubusercontent.com/9c52463cd1706862a1307a7e7db7593ed7821bfa87322ff31a47de3614e93de6/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f76696d2d7461626c652d6d6f64652f6f7267616e697a6174696f6e2f312f6176617461722e737667)](https://opencollective.com/vim-table-mode/organization/1/website) [![](https://camo.githubusercontent.com/ffded70fb22e46f2b2496fc3a00e37b946acadefc2265c0957107e42aa768db4/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f76696d2d7461626c652d6d6f64652f6f7267616e697a6174696f6e2f322f6176617461722e737667)](https://opencollective.com/vim-table-mode/organization/2/website) [![](https://camo.githubusercontent.com/3e3f5ef484c2553fc99607da0a287cfb6f2b377daf1d1f1a0d3b5307019c7ae0/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f76696d2d7461626c652d6d6f64652f6f7267616e697a6174696f6e2f332f6176617461722e737667)](https://opencollective.com/vim-table-mode/organization/3/website) [![](https://camo.githubusercontent.com/56d6cb3bbc743fe36699f57e9a2ce0328c9b3436aa846474a6b28f15d697e50f/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f76696d2d7461626c652d6d6f64652f6f7267616e697a6174696f6e2f342f6176617461722e737667)](https://opencollective.com/vim-table-mode/organization/4/website) [![](https://camo.githubusercontent.com/12b060ac114fae2ee6bb1ee6e8483ba70efac1bdc095ab8762eb633f35db2c8d/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f76696d2d7461626c652d6d6f64652f6f7267616e697a6174696f6e2f352f6176617461722e737667)](https://opencollective.com/vim-table-mode/organization/5/website) [![](https://camo.githubusercontent.com/25d76ccbef41ee4896ea8a1183cfd5dde29c98f4f31754489ae184c9a2ba4e77/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f76696d2d7461626c652d6d6f64652f6f7267616e697a6174696f6e2f362f6176617461722e737667)](https://opencollective.com/vim-table-mode/organization/6/website) [![](https://camo.githubusercontent.com/b227fb5eca1d4760a5d56c9b8387e75dbed3a5e2c10d1a86839cc7649e5916ee/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f76696d2d7461626c652d6d6f64652f6f7267616e697a6174696f6e2f372f6176617461722e737667)](https://opencollective.com/vim-table-mode/organization/7/website) [![](https://camo.githubusercontent.com/6d6e0ebbb14dae6d1d857d446c1df41c58fa889d648b32e12d7f207cc6278ae4/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f76696d2d7461626c652d6d6f64652f6f7267616e697a6174696f6e2f382f6176617461722e737667)](https://opencollective.com/vim-table-mode/organization/8/website) [![](https://camo.githubusercontent.com/6177cf291f21341370945edbf207b565d357035ccee844f1380852a0ec5e87ef/68747470733a2f2f6f70656e636f6c6c6563746976652e636f6d2f76696d2d7461626c652d6d6f64652f6f7267616e697a6174696f6e2f392f6176617461722e737667)](https://opencollective.com/vim-table-mode/organization/9/website)