---
page-title: vimsidian/plugin at main · kis9a/vimsidian
url: https://github.com/kis9a/vimsidian/tree/main/plugin
date: 2024-06-21 03:05:17
tags:
  - A/sw/plugin
  - F/prod/homepage
  - C/
  - P/pwf
about:
  - "[[Inv/SW/Vim]]"
aliases:
  - 
by: 
length: 9178
dir: 
---

## vimsidian

[](https://github.com/kis9a/vimsidian/tree/main/plugin#vimsidian)

[![](https://camo.githubusercontent.com/5392fb6b22a5aa0d362bcf336269628c8f9be07dd222fab7fe21c5ff73b42554/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f616374696f6e732f776f726b666c6f772f7374617475732f6b697339612f76696d73696469616e2f746573742e796d6c3f6272616e63683d6d61696e)](https://camo.githubusercontent.com/5392fb6b22a5aa0d362bcf336269628c8f9be07dd222fab7fe21c5ff73b42554/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f616374696f6e732f776f726b666c6f772f7374617475732f6b697339612f76696d73696469616e2f746573742e796d6c3f6272616e63683d6d61696e)

Vim plugin to help edit [Obsidian](https://obsidian.md/) notes in Vim. Links, backlink resolution and jumps, search and completion and highlighting, daily notes. Even if you don't use [Obsidian](https://obsidian.md/), you can use it to manage your notes locally.

This plugin was made for me, but I hope it will be useful for those who want to easily edit [Obsidian](https://obsidian.md/) notes with vim as I do. If you have trouble using it, please post an [issues](https://github.com/kis9a/vimsidian/issues) below. Contributions, edits and distribution are also welcome.

[![](https://raw.githubusercontent.com/kis9a/vimsidian/main/pictures/vimsidian.gif)](https://raw.githubusercontent.com/kis9a/vimsidian/main/pictures/vimsidian.gif)

## Motivation

[](https://github.com/kis9a/vimsidian/tree/main/plugin#motivation)

In my earlier days, I used to divide notes in directories and manage note relationships by describing relative paths. However, I had trouble categorizing notes and spent a lot of time resolving note paths. I needed to achieve the following.

-   Hierarchical structure is not suitable for classification of detailed personal knowledge.
-   Create atomic notes and link notes to each other.
-   Eliminate stress by unifying editing tasks and management of editing plugins in Vim.
-   \[\[Link\]\] format to integrate into [Obsidian](https://obsidian.md/).

For me, [vimsidian](https://github.com/kis9a/vimsidian) is the plugin that solves these issues and complements my PKM (personal knowledge managment).

## Features

[](https://github.com/kis9a/vimsidian/tree/main/plugin#features)

-   Insert mode completion of note names.
-   Find and move the link under the cursor.
-   Go to link before or afater current cursor.
-   Create a note with the name of the link under the cursor.
-   Search for notes and lines matching keywords.
-   Display notes in the quickfix window containing the tag string under the cursor.
-   Default syntax highlighting settings.
-   Custom formatting of link spacing.
-   Manage multiple `g:vimsidian_path` (Obsidian Vault).
-   Stack of link jump history in .
-   Daily note feature.
-   Highlighting broken links.
-   Fewer dependencies.

## Initialization

[](https://github.com/kis9a/vimsidian/tree/main/plugin#initialization)

### Requirements

[](https://github.com/kis9a/vimsidian/tree/main/plugin#requirements)

-   [ripgrep](https://github.com/BurntSushi/ripgrep) command
-   [fd](https://github.com/sharkdp/fd) command

### Installation

[](https://github.com/kis9a/vimsidian/tree/main/plugin#installation)

Use your favorite plugin manager.

-   Example: [vim-plug](https://github.com/junegunn/vim-plug)

## Configuration

[](https://github.com/kis9a/vimsidian/tree/main/plugin#configuration)

#### • Minimal

[](https://github.com/kis9a/vimsidian/tree/main/plugin#-minimal)

let g:vimsidian\_path \= $HOME . '/obsidian'
let g:vimsidian\_complete\_paths \= \[g:vimsidian\_path\]
let $VIMSIDIAN\_PATH\_PATTERN \= g:vimsidian\_path . '/\*.md'

function! s:vimsidianNewNoteAtNotesDirectory()
  execute ':VimsidianNewNote ' . g:vimsidian\_path . '/notes'
endfunction

augroup vimsidian\_augroup
  au!
  au BufNewFile,BufReadPost $VIMSIDIAN\_PATH\_PATTERN nn <buffer> sl :VimsidianFdLinkedNotesByThisNote<CR>
  au BufNewFile,BufReadPost $VIMSIDIAN\_PATH\_PATTERN nn <buffer> sg :VimsidianRgNotesLinkingThisNote<CR>
  au BufNewFile,BufReadPost $VIMSIDIAN\_PATH\_PATTERN nn <buffer> sm :VimsidianRgNotesWithMatchesInteractive<CR>
  au BufNewFile,BufReadPost $VIMSIDIAN\_PATH\_PATTERN nn <buffer> si :VimsidianRgLinesWithMatchesInteractive<CR>
  au BufNewFile,BufReadPost $VIMSIDIAN\_PATH\_PATTERN nn <buffer> st :VimsidianRgTagMatches<CR>
  au BufNewFile,BufReadPost $VIMSIDIAN\_PATH\_PATTERN nn <buffer> <C-k> :VimsidianMoveToLink<CR>
  au BufNewFile,BufReadPost $VIMSIDIAN\_PATH\_PATTERN nn <buffer> <2-LeftMouse> :VimsidianMoveToLink<CR>
  au BufNewFile,BufReadPost $VIMSIDIAN\_PATH\_PATTERN nn <buffer> sk :VimsidianMoveToPreviousLink<CR>
  au BufNewFile,BufReadPost $VIMSIDIAN\_PATH\_PATTERN nn <buffer> sj :VimsidianMoveToNextLink<CR>
  au BufNewFile,BufReadPost $VIMSIDIAN\_PATH\_PATTERN nn <buffer> sN :call <SID>vimsidianNewNoteAtNotesDirectory()<CR>
  au BufNewFile,BufReadPost $VIMSIDIAN\_PATH\_PATTERN nn <buffer> sO :VimsidianNewNoteInteractive<CR>
  au BufNewFile,BufReadPost $VIMSIDIAN\_PATH\_PATTERN nn <buffer> sd :VimsidianDailyNote<CR>
  au BufNewFile,BufReadPost $VIMSIDIAN\_PATH\_PATTERN nn <buffer> sf :VimsidianFormatLink<CR>
  au WinEnter,BufEnter $VIMSIDIAN\_PATH\_PATTERN silent! call vimsidian#MatchBrokenLinks()
  au CursorMoved $VIMSIDIAN\_PATH\_PATTERN silent! call vimsidian#MatchCursorLink()
augroup END

#### • Advance, ideas

[](https://github.com/kis9a/vimsidian/tree/main/plugin#-advance-ideas)

Multiple g:vimsidian\_path

Multiple vimsidian\_paths can be managed. The `$VIMSIDIAN_PATH_PATTERN` is the autocmd path-pattern (:h autocmd-pattern). `g:vimsidian_path` variable is the path where notes and completion suggestions are searched.

let g:vimsidian\_path\_main \= $HOME . '/obsidian'
let g:vimsidian\_path\_sub \= $HOME . '/Nsidian'
let g:vimsidian\_path \= g:vimsidian\_path\_main
let $VIMSIDIAN\_PATH\_PATTERN \= g:vimsidian\_path\_main . '/\*.md,' . g:vimsidian\_path\_sub . '/\*.md'

function! s:vimsidianSwitchVault()
  if stridx(expand('%:p'), g:vimsidian\_path\_main) !=# '\-1'
    let g:vimsidian\_path \= g:vimsidian\_path\_main
    let g:vimsidian\_complete\_paths \= \[g:vimsidian\_path\_main . '/notes', g:vimsidian\_path\_main  . '/images'\]
  elseif stridx(expand('%:p'), g:vimsidian\_path\_sub) !=# '\-1'
    let g:vimsidian\_path \= g:vimsidian\_path\_sub
    let g:vimsidian\_complete\_paths \= \[g:vimsidian\_path\_sub . '/Nnotes'\]
  endif
endfunction

augroup vimsidian\_augroup
  au!
  au VimEnter,BufNewFile,BufReadPost,WinEnter,BufEnter \*.md call s:vimsidianSwitchVault()
" ry ...

Use link stack

Keep a stack of link jump history in each window (w:vimsidian\_link\_stack)  
Provides jump and jumpback functionality to entries in the link stack.  
Like CTRL+t/CTRL+\] for tags using ctags in vim. (:h tags)

Detials: [#10](https://github.com/kis9a/vimsidian/pull/10), [#9](https://github.com/kis9a/vimsidian/issues/9)

let g:vimsidian\_enable\_link\_stack \= 1

" Example mapping like ctags jump
augroup vimsidian\_augroup
  au!
  au BufNewFile,BufReadPost $VIMSIDIAN\_PATH\_PATTERN nn <buffer> <C-\]> :VimsidianMoveToLink<CR>
  au BufNewFile,BufReadPost $VIMSIDIAN\_PATH\_PATTERN nn <silent> <C-t> :VimsidianMoveToPreviousEntryInLinkStack<CR>
  au BufNewFile,BufReadPost $VIMSIDIAN\_PATH\_PATTERN nn <silent> sn :VimsidianMoveToNextEntryInLinkStack<CR>
  au BufNewFile,BufReadPost $VIMSIDIAN\_PATH\_PATTERN nn <silent> ss :VimsidianLinkStack<CR>
" ry ...

Use fzf to list note names

Open listings using fzf instead of quick fix window. See fzf installation at [https://github.com/junegunn/fzf.vim#installation](https://github.com/junegunn/fzf.vim#installation)

\# e.g
Plug 'junegunn/fzf', { 'do': { \-\> fzf#install() } }
Plug 'junegunn/fzf.vim'

if executable('fzf')
  let g:vimsidian\_use\_fzf \= 1
endif

Change link open mode

Change the way the buffer opens when opening a new note.

" default
let g:vimsidian\_link\_open\_mode \= 'e!'

" newtab
let g:vimsidian\_link\_open\_mode \= 'newtab'

" vsplit
let g:vimsidian\_link\_open\_mode \= 'vnew'

" hsplit
let g:vimsidian\_link\_open\_mode \= 'new'

Define the colors yourself  

let g:vimsidian\_color\_definition\_use\_default \= 0

hi def VimsidianLinkColor term\=NONE ctermfg\=42 guifg\=#00df87
hi def VimsidianLinkMediaColor term\=NONE ctermfg\=208 guifg\=#ff8700
hi def VimsidianLinkHeaderColor term\=NONE ctermfg\=142 guifg\=#b8bb26
hi def VimsidianLinkBlockColor term\=NONE ctermfg\=142 guifg\=#b8bb26
hi def VimsidianLinkBlockFlagColor term\=NONE ctermfg\=142 guifg\=#b8bb26
hi def VimsidianTagColor term\=NONE ctermfg\=214 guifg\=#ffaf00
hi def VimsidianCalloutColor term\=NONE ctermfg\=117 guifg\=#87dfff
hi def VimsidianPromptColor term\=NONE ctermfg\=109 guifg\=#076678
hi def VimsidianCursorLinkColor term\=NONE ctermfg\=47 guifg\=#00ff5f
hi def VimsidianBrokenLinkColor term\=NONE ctermfg\=29 guifg\=#00875f

Custom daily note template  

let g:vimsidian\_daily\_note\_path \= g:vimsidian\_path . "/daily/" . strftime("%Y-%m")
let g:vimsidian\_daily\_note\_template\_path \= g:vimsidian\_path . "/daily/Daily template.md"

The template file can use some parameters. (:h g:vimsidian\_daily\_note\_template\_path)

```
[[{{date}}]]

< [[{{previous_date}}]] | [[{{next_date}}]] >

[[{{year}}-{{month}}]] [[{{day}}]] [[{{day_of_week}}]]
```
Create new note same directory as current file  

function! s:vimsidianNewNoteSameDirectoryAsCurrentFile()
  execute ':VimsidianNewNote ' . fnamemodify(expand('%:p'), ':h')
endfunction

au BufNewFile,BufReadPost $VIMSIDIAN\_PATH\_PATTERN nn <silent> sC :call <SID>vimsidianNewNoteSameDirectoryAsCurrentFile()<CR>

Refine complete\_paths to speed up search for completions  

" vimsidian complete paths search use ls command
let g:vimsidian\_complete\_paths\_search\_use\_fd \= 0
let g:vimsidian\_complete\_paths \= \[g:vimsidian\_path . '/notes/foo', g:vimsidian\_path . '/notes/b'\]

Disable required commands checks to make plugins load a bit faster  

" It is assumed that the following commands are already installed
" :echo g:vimsidian\_required\_commands
let g:vimsidian\_check\_required\_commands\_executable \= 0

#vimsidian functions  

function! s:MocByFd(noteKeyword)
  let files \= split(vimsidian#unit#Fd(g:vimsidian\_path, \[\]), '\\n')
  for f in files
    if f \=~# '\\v^.\*' . a:noteKeyword
      put\='\[\[' . fnamemodify(f, ':t:r') . '\]\]'
    endif
  endfor
  return vimsidian#unit#Find(files, '^.\*/' . a:noteKeyword)
endfunction

command! -nargs\=1 VimsidianMocByFd call s:MocByFd(<q-args>)

function! s:MocByRg(keyword)
  for path in vimsidian#unit#RgNotes(a:keyword)
    put\='\[\[' . fnamemodify(path, ':t:r') . '\]\]'
  endfor"
endfunction

command! -nargs\=1 VimsidianMocByRg call s:MocByRg(<q-args>)

function! s:HiCursorLink()
  let link \= vimsidian#unit#CursorLink()
  if link !=# v:null
    normal! "zyiw:let @/ = '\\<' . @z . '\\>'<CR>:set hlsearch<CR>
  endif
endfunction

command! VimsidianHiCursorLink call s:HiCursorLink()

## Help

[](https://github.com/kis9a/vimsidian/tree/main/plugin#help)

See [Vim doc - Syntax highlight, Variables and Commands help](https://github.com/kis9a/vimsidian/blob/main/doc/vimsidian.txt)

## Developments

[](https://github.com/kis9a/vimsidian/tree/main/plugin#developments)

If you contribute to this repository, please use the following tools for linting and testing

### Linting

[](https://github.com/kis9a/vimsidian/tree/main/plugin#linting)

Use [vim-parser](https://github.com/ynkdir/vim-vimlparser), [vim-vimlint](https://github.com/syngan/vim-vimlint)

When using [vint](https://github.com/Vimjas/vint)

```
make vint-int
make lint-vint
```

### Testing

[](https://github.com/kis9a/vimsidian/tree/main/plugin#testing)

Use [vim-themis](https://github.com/thinca/vim-themis/issues), CI [.github/workflows/test.yml](https://github.com/kis9a/vimsidian/blob/main/.github/workflows/test.yml)

## LICENSE

[](https://github.com/kis9a/vimsidian/tree/main/plugin#license)

[WTFPL license - Do What The F\*ck You Want To Public License](https://github.com/kis9a/vimsidian/blob/main/LICENSE.md)