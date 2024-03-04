---
page-title: "GitHub - gapmiss/badges: A light-weight plugin for displaying inline \"badges\" in Obsidian.md"
url: https://github.com/gapmiss/badges
date: "2024-03-03 17:08:51"
tags: 
- A/sw/plugin
- F/homepage
- C/
- P/
about: "[[Obsidian]]"
uuid: 108ba8c4-2b67-4485-a091-15afb226a3f8
---

## Badges

[](https://github.com/gapmiss/badges#badges)

### Introduction

[](https://github.com/gapmiss/badges#introduction)

A light-weight plugin for displaying inline "badges" in [Obsidian.md](https://github.com/obsidianmd) which acts similarly to a key-value store(database) for querying via default search or [Dataview](https://github.com/blacksmithgu/obsidian-dataview) plugin.

-   [Usage](https://github.com/gapmiss/badges#usage)
    -   [Github styled badges](https://github.com/gapmiss/badges#Github)
    -   [Plain-text](https://github.com/gapmiss/badges#Plain-text)
    -   [custom](https://github.com/gapmiss/badges#custom)
-   [Installation](https://github.com/gapmiss/badges#Installation)
-   [CSS styles](https://github.com/gapmiss/badges#CSS)
-   [Dataview plugin](https://github.com/gapmiss/badges#Dataview)
-   [Development](https://github.com/gapmiss/badges#Development)
-   [Notes](https://github.com/gapmiss/badges#Notes)

### Usage

[](https://github.com/gapmiss/badges#usage)

###### default syntax

[](https://github.com/gapmiss/badges#default-syntax)

syntax

details

`KEY`

the type and name of the `ICON`

`VAL`

the value and text displayed

Important

the `VAL` cannot contain either the `|` pipe or the `:` colon symbols, as they are used as delimiters for the custom syntax

###### example

[](https://github.com/gapmiss/badges#example)

\`\[!!note:note\]\`
\`\[!!info:info\]\`
\`\[!!todo:todo\]\`
...
\`\[!!cite:cite\]\`

###### results

[](https://github.com/gapmiss/badges#results)

[![](https://github.com/gapmiss/badges/raw/master/assets/Badges-demo-Obsidian-v1.3.7-20230709144540.png)](https://github.com/gapmiss/badges/blob/master/assets/Badges-demo-Obsidian-v1.3.7-20230709144540.png)

[![](https://github.com/gapmiss/badges/raw/master/assets/Badges-demo-Obsidian-v1.3.7-20230709144545.png)](https://github.com/gapmiss/badges/blob/master/assets/Badges-demo-Obsidian-v1.3.7-20230709144545.png)

###### example

[](https://github.com/gapmiss/badges#example-1)

\`\[!!emergency: emergency\]\`
\`\[!!prohibit: prohibit\]\`
\`\[!!stop:stop\]\`
…
\`\[!!reward: reward\]\`
\`\[!!vault: vault\]\`

###### results

[](https://github.com/gapmiss/badges#results-1)

[![](https://github.com/gapmiss/badges/raw/master/assets/Badges-demo-Obsidian-v1.3.7-20230709170950.png)](https://github.com/gapmiss/badges/blob/master/assets/Badges-demo-Obsidian-v1.3.7-20230709170950.png)

[![](https://github.com/gapmiss/badges/raw/master/assets/Badges-demo-Obsidian-v1.3.7-20230709170943.png)](https://github.com/gapmiss/badges/blob/master/assets/Badges-demo-Obsidian-v1.3.7-20230709170943.png)

#### Github

[](https://github.com/gapmiss/badges#github)

###### syntax

[](https://github.com/gapmiss/badges#syntax)

syntax

details

`|`

start pipe symbol

`GHX`

Github style, either `ghb` for the blue style or `ghs` for the green success style

`>`

greater than symbol (delimiter)

`KEY:VAL`

`KEY` is the type or label, `VAL` is the value text displayed. e.g. `release:1.0.0`

###### example

[](https://github.com/gapmiss/badges#example-2)

\`\[!!|ghb>release:1.2.1\]\`
\`\[!!|ghb>issues:2\]\`
\`\[!!|ghb>open issues:0\]\`
\`\[!!|ghb>closed issues:2\]\`
\`\[!!|ghb>contributors:3\]\`
\`\[!!|ghb>license:MIT\]\`
\`\[!!|ghs>checks:success\]\`
\`\[!!|ghs>build:success\]\`

###### results

[](https://github.com/gapmiss/badges#results-2)

[![](https://github.com/gapmiss/badges/raw/master/assets/Badges-demo-Obsidian-v1.3.7-20230709171043.png)](https://github.com/gapmiss/badges/blob/master/assets/Badges-demo-Obsidian-v1.3.7-20230709171043.png)

[![](https://github.com/gapmiss/badges/raw/master/assets/Badges-demo-Obsidian-v1.3.7-20230709171053.png)](https://github.com/gapmiss/badges/blob/master/assets/Badges-demo-Obsidian-v1.3.7-20230709171053.png)

### Plain-text

[](https://github.com/gapmiss/badges#plain-text)

###### syntax

[](https://github.com/gapmiss/badges#syntax-1)

syntax

details

`|`

start pipe symbol

`KEY:VAL`

`KEY` is the type, `VAL` is the value

###### example

[](https://github.com/gapmiss/badges#example-3)

###### results

[](https://github.com/gapmiss/badges#results-3)

[![](https://github.com/gapmiss/badges/raw/master/assets/Badges-demo-Obsidian-v1.3.7-20230709171707.png)](https://github.com/gapmiss/badges/blob/master/assets/Badges-demo-Obsidian-v1.3.7-20230709171707.png)

[![](https://github.com/gapmiss/badges/raw/master/assets/Badges-demo-Obsidian-v1.3.7-20230709171713.png)](https://github.com/gapmiss/badges/blob/master/assets/Badges-demo-Obsidian-v1.3.7-20230709171713.png)

### custom

[](https://github.com/gapmiss/badges#custom)

###### syntax

[](https://github.com/gapmiss/badges#syntax-2)

\`\[!!|ICON|KEY:VAL|COLOR-RGB\]\`

syntax

details

`|`

start pipe symbol

`ICON`

name of icon. e.g. `lucide-dice`

`|`

pipe symbol

`KEY:VAL`

`KEY` is the type or label, `VAL` is the value text displayed. e.g. `release:1.0.0`

`|`

pipe symbol

`COLOR-RGB`  
(optional, defaults to currentColor)

3 (R.G.B.) numeric (0-255) values, separated by commas. e.g. `144,144,144` or CSS variable e.g. `var(--color-red-rgb)`

###### example

[](https://github.com/gapmiss/badges#example-4)

\`\[!!|message-square|comment:edited by j.d.|var(--color-cyan-rgb)\]\`
\`\[!!|dice|roll:eleven|120,82,238\]\`
\`\[!!|gem|mineral:emerald|var(--my-custom-rgb)\]\`
\`\[!!|apple|fruit:snack|var(--color-red-rgb)\]\`
\`\[!!|brain|brain:pkm|var(--color-purple-rgb)\]\`
\`\[!!|sun|weather:sunny|var(--color-yellow-rgb)\]\`
\`\[!!|cloudy|weather:cloudy|var(--mono-rgb-100)\]\`
\`\[!!|sunset|weather:8.44pm|var(--color-orange-rgb)\]\`
\`\[!!|dumbbell|reps:3 sets of 50|var(--mono-rgb-00)\]\`
\`\[!!|gift|event:wedding|var(--color-blue-rgb)\]\`
\`\[!!|plus-square|credit:$100|var(--color-green-rgb)\]\`
\`\[!!|minus-square|debit:$10|var(--color-pink-rgb)\]\`

###### results

[](https://github.com/gapmiss/badges#results-4)

[![](https://github.com/gapmiss/badges/raw/master/assets/Badges-demo-Obsidian-v1.3.7-20230709171541.png)](https://github.com/gapmiss/badges/blob/master/assets/Badges-demo-Obsidian-v1.3.7-20230709171541.png) [![](https://github.com/gapmiss/badges/raw/master/assets/Badges-demo-Obsidian-v1.3.7-20230709171534.png)](https://github.com/gapmiss/badges/blob/master/assets/Badges-demo-Obsidian-v1.3.7-20230709171534.png)

### Installation

[](https://github.com/gapmiss/badges#installation)

From Obsidian's settings or preferences:

1.  Open in Obsidian.md

or:

1.  Community Plugins > Browse
2.  Search for "Badges"

Manually:

1.  download the latest [release archive](https://github.com/gapmiss/badges/releases/download/1.1.0/badges-v1.1.0.zip)
2.  uncompress the downloaded archive
3.  move the `badges` folder to `/path/to/vault/.obsidian/plugins/`
4.  Settings > Community plugins > reload **Installed plugins**
5.  enable plugin

or:

1.  download `main.js`, `manifest.json` & `styles.css`
2.  create a new folder `/path/to/vault/.obsidian/plugins/badges`
3.  move all 3 files to `/path/to/vault/.obsidian/plugins/badges`
4.  Settings > Community plugins > reload **Installed plugins**
5.  enable plugin

### CSS

[](https://github.com/gapmiss/badges#css)

Custom `CSS` styles can be applied via CSS snippets. All colors and styles can be over-written just the same.

See [CSS snippets - Obsidian Help](https://help.obsidian.md/Extending+Obsidian/CSS+snippets)

##### variables

[](https://github.com/gapmiss/badges#variables)

body {
	/\* border \*/
	\--inline-badge-border-color: transparent;
	\--inline-badge-border-radius: var(\--radius-s);
	\--inline-badge-border: 1px solid var(\--inline-badge-border-color);
	/\* example custom color \*/
	\--my-custom-rgb: var(\--color-green-rgb);
}
/\* example CSS customization \*/
.inline-badge\[data-inline-badge^="vault"\] {
	\--badge-color: var(\--my-custom-rgb);
	color: rgba(var(\--badge-color), .88);
	background-color: rgba(var(\--badge-color),.22);
}

### Dataview

[](https://github.com/gapmiss/badges#dataview)

View and copy example dataview queries: [badges-dataview](https://github.com/gapmiss/badges/blob/master/assets/badges-dataview.md)

### Development

[](https://github.com/gapmiss/badges#development)

###### Clone this repo

[](https://github.com/gapmiss/badges#clone-this-repo)

cd /path/to/vault/.obsidian/plugins
git clone https://github.com/gapmiss/badges.git
cd badges

###### Install packages and run

[](https://github.com/gapmiss/badges#install-packages-and-run)

###### Enable plugin

[](https://github.com/gapmiss/badges#enable-plugin)

1.  open `Settings` → `Community plugins`
2.  enable the `Badges` plugin.

### Notes

[](https://github.com/gapmiss/badges#notes)

Thanks to [Markdown Furigana Plugin](https://github.com/steven-kraft/obsidian-markdown-furigana) as an example implementation of Live Preview.

[Lucide](https://github.com/lucide-icons/lucide) Icons: [https://lucide.dev](https://lucide.dev/)

Lucide Icons LICENSE: [https://lucide.dev/license](https://lucide.dev/license)