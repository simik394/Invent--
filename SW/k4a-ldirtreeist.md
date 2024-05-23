---
page-title: "k4a-l/dirtreeist"
url: https://github.com/k4a-l/dirtreeist#description-of-options
date: "2024-04-08 20:10:41"
tags: 
- A/sw/plugin
- F/homepage
- C/
- P/
about: "[[Obsidian]]"
aliases: 
- e39e292b-6d06-4947-b3fb-34d2bbec861c
- k4a-l/dirtreeist
by: 
length: 2361
dir: 
---

## DirTreeist

[](https://github.com/k4a-l/dirtreeist#dirtreeist)

Create a directory Structure Diagram from a markdown lists.

## Installation

[](https://github.com/k4a-l/dirtreeist#installation)

#### yarn

[](https://github.com/k4a-l/dirtreeist#yarn)

yarn add @k4a\_l/dirtreeist

### npm

[](https://github.com/k4a-l/dirtreeist#npm)

npm install @k4a\_l/dirtreeist

## Demo

[](https://github.com/k4a-l/dirtreeist#demo)

[https://www.k4a.me/tools/dirtreeist](https://www.k4a.me/tools/dirtreeist)

## Example

[](https://github.com/k4a-l/dirtreeist#example)

### Basic

[](https://github.com/k4a-l/dirtreeist#basic)

#### Input

[](https://github.com/k4a-l/dirtreeist#input)

\- /components
  　- App.tsx
  　- App.css
\- config.json
\- /utils
  　- converter.ts
  　- parser.ts

#### Output

[](https://github.com/k4a-l/dirtreeist#output)

`├─/components │　├─App.tsx │　└─App.css ├─config.json └─/utils 　　└─converter.ts 　　└─parser.ts`

### Only one top

[](https://github.com/k4a-l/dirtreeist#only-one-top)

#### Input

[](https://github.com/k4a-l/dirtreeist#input-1)

\- /root
  \- /components
    　- App.tsx
    　- App.css
  \- config.json
  \- /utils
    　- converter.ts
    　- parser.ts

#### Output

[](https://github.com/k4a-l/dirtreeist#output-1)

`/root ├─/components │　├─App.tsx │　└─App.css ├─config.json └─/utils 　　├─converter.ts 　　└─parser.ts`

### Sequential listings

[](https://github.com/k4a-l/dirtreeist#sequential-listings)

Consecutive lists are connected.

#### Input

[](https://github.com/k4a-l/dirtreeist#input-2)

`- a   - b   - c - d  - 1   - 2     - 3       - 4`

#### Output

[](https://github.com/k4a-l/dirtreeist#output-2)

`├─ a │ 　 ├─ b │ 　 └─ c ├─ d └─ 1 　　 └─ 2 　　　　 └─ 3 　　　　　　 └─ 4`

### Another element comes in between

[](https://github.com/k4a-l/dirtreeist#another-element-comes-in-between)

If another element is sandwiched in between, a "only" split lists is output.

#### Input

[](https://github.com/k4a-l/dirtreeist#input-3)

`- a   - b   - c - d  sometext  - 1   - 2     - 3       - 4`

#### Output

[](https://github.com/k4a-l/dirtreeist#output-3)

## How to use

[](https://github.com/k4a-l/dirtreeist#how-to-use)

### TypeScript

[](https://github.com/k4a-l/dirtreeist#typescript)

const markdown \= \`
\- /components
　　- App.tsx
　　- App.css
\- config.json
\- /utils
　　- converter.ts
　　- parser.ts
\`

import dirtreeist, { Options } from '@k4a\_l/dirtreeist'

const options: Options \= {}
const outputs \= dirtreeist(markdown, options) // DirTree\[\] => output\[\]

console.log(outputs)

or

import { parse, convert, Options } from '@k4a\_l/dirtreeist'

const dirTrees \= parse(markdown) // markdown => DirTree\[\]

const options: Options \= {}
const outputs \= dirTrees.map((dirTree) \=> convert(dirTree, options)) // DirTree\[\] => output\[\]

console.log(outputs)

### Type

[](https://github.com/k4a-l/dirtreeist#type)

#### Structure

[](https://github.com/k4a-l/dirtreeist#structure)

type DirNode \= {
  name: string
  children: DirNode\[\]
}

type DirTree \= DirNode\[\]

#### Options

[](https://github.com/k4a-l/dirtreeist#options)

type Options \= {
  treeType?: 'normal' | 'bold' | 'ascii'
  emptyBeforeUpperHierarche?: boolean
  spaceBeforeName?: boolean
  spaceSize?: number
}

### Description of options

[](https://github.com/k4a-l/dirtreeist#description-of-options)

#### treeType

[](https://github.com/k4a-l/dirtreeist#treetype)

default:`normal`

##### normal

[](https://github.com/k4a-l/dirtreeist#normal)

##### bold

[](https://github.com/k4a-l/dirtreeist#bold)

##### ascii

[](https://github.com/k4a-l/dirtreeist#ascii)

#### emptyLineBeforeUpperHierarchy : boolean

[](https://github.com/k4a-l/dirtreeist#emptylinebeforeupperhierarchy--boolean)

default:`false`

##### true

[](https://github.com/k4a-l/dirtreeist#true)

`(true) ├─/components │　├─App.tsx │　└─App.css │ ├─config.json └─/utils 　　└─converter.ts 　　└─parser.ts`

#### spaceBeforeName : boolean

[](https://github.com/k4a-l/dirtreeist#spacebeforename--boolean)

default: `false`

##### true

[](https://github.com/k4a-l/dirtreeist#true-1)

`├─ /components │　├─ App.tsx │　└─ App.css ├─ config.json └─ /utils 　　└─ converter.ts 　　└─ parser.ts`

#### spaceSize : number

[](https://github.com/k4a-l/dirtreeist#spacesize--number)

default:`2`

##### 4

[](https://github.com/k4a-l/dirtreeist#4)

`├──/components │　　├──App.tsx │　　└──App.css ├──config.json └──/utils 　　　└──converter.ts 　　　└──parser.ts`