---
page-title: "HananoshikaYomaru/obsidian-run: Generate markdown from dataview query and javascript."
url: https://github.com/HananoshikaYomaru/obsidian-run
date: 2024-01-18 08:26:13
tags:
  - sw/plugin
  - ⭐/interesting
purpose:
  - gen-md
extends:
  - "[[Obsidian]]"
---

## Obsidian Run

Generate markdown from dataview query and javascript.

-   ✅ Powerful, Dead Simple
-   ✅ Markdown based, work with every markdown editor / render
-   ✅ Works well with Dataview, Templater, Obsidian publish

demo: [https://www.youtube.com/watch?v=\_UAr6e6hlVI&t=71s](https://www.youtube.com/watch?v=_UAr6e6hlVI&t=71s)

## Installation

### Plugin marketplace

You can download this from obsidian plugin store.

### Manual Installation

1.  cd to `.obsidian/plugins`
2.  git clone this repo
3.  `cd obsidian-run && bun install && bun run build`
4.  there you go 🎉

## Usage

1.  install this plugin and install [obsidian-custom-save](https://github.com/HananoshikaYomaru/obsidian-custom-save)
2.  add the `run: run file` command to the custom save actions
3.  define a starting tag

2.  save the file
3.  you markdown will become something like this

%% run start
3+4
%%
7
%% run end %%

### Syntax

Each block of run contains three parts: starting tag (required), generated content, ending tag

#### starting tag (required)

you define your expression in the starting tag. The expression will be used to calculate the content. It is the only required part for a run block.

%% run start <expression\> %%

or you can also write multiple line statements. Notice that if you write in multiple line you must return a value.

%% run start

\`\`\`ts|js
<your expression in codeblock>
\`\`\`

%%

You can use it with [CodeblockCustomizer](https://github.com/mugiwara85/CodeblockCustomizer), to have folding codeblock.

[![](https://user-images.githubusercontent.com/43137033/272329457-d278a370-63d6-4dc2-a3f4-68767745ac92.png)](https://user-images.githubusercontent.com/43137033/272329457-d278a370-63d6-4dc2-a3f4-68767745ac92.png)

#### Content

the generated content

#### Ending Tag

ending tag closes the run block.

## Options

1.  generate ending tag metadata: when enabled, the run block update time and error(if any) will be shown in the ending tag.
2.  ignore folders: the folder listed will be ignored by this plugin

## Advanced Usage

### Access file object

%% run start file.basename %%

the file object is the [TFile](https://docs.obsidian.md/Reference/TypeScript+API/TFile/TFile) but it is patched with `file.properties` which is the file yaml properties.

### Page level variable

\---
bar: "foo"
\---

%% run start file.properties.bar %%

### Dataview

you can access the `dv` object if you have dataview plugin installed and enabled.

%% run start

\`\`\`ts
return dv.markdownList(dv.pages("#ai/image").map((page) \=> page.file.link));
\`\`\`

%%

### Templater and Reusable user scripts

you can access the `tp` object if you have templater plugin installed and enabled.

> Then you need to go to the setting of template and manually set a startup template. The reason of doing this is that `tp` is not initialized by default by templater and it will be undefined. Learn more and see a video: [#14 (comment)](https://github.com/HananoshikaYomaru/obsidian-run/issues/14#issuecomment-1749945619). If you don't want to set a start up template, you can manually run templater once everytime you start up obsidian. As long as templater runs once, the `tp` object will be defined.

[![](https://camo.githubusercontent.com/ec5b9b08c189d6fd80498e863b3eaf6c6d901532d186388e30f583c98635d01d/68747470733a2f2f73686172652e636c65616e73686f742e636f6d2f71775459464362792b)](https://camo.githubusercontent.com/ec5b9b08c189d6fd80498e863b3eaf6c6d901532d186388e30f583c98635d01d/68747470733a2f2f73686172652e636c65616e73686f742e636f6d2f71775459464362792b)

Templater allows user to have their user defined functions and scripts. To learn more, checkout [https://silentvoid13.github.io/Templater/user-functions/script-user-functions.html](https://silentvoid13.github.io/Templater/user-functions/script-user-functions.html).

### Function

you can write complicated function in starting tag codeblock

### Async Function

You can do any kind of async operation in the run block. Async function is non-blocking. Results will be resolved after all sync operation are resolved. You can use the obsidian [request](https://docs.obsidian.md/Reference/TypeScript+API/request) function to fetch data.

[![](https://camo.githubusercontent.com/0601dddb72ed4ff20494019d073a9a9d6a331cd724a7275828d3d7c650505d0e/68747470733a2f2f73686172652e636c65616e73686f742e636f6d2f383368516c7444422b)](https://camo.githubusercontent.com/0601dddb72ed4ff20494019d073a9a9d6a331cd724a7275828d3d7c650505d0e/68747470733a2f2f73686172652e636c65616e73686f742e636f6d2f383368516c7444422b)

### Debug

you can use `console.log` in the starting tag codeblock. It will output in the developer tool.

## Note

1.  if you want to contribute, please star and open github issue.
2.  this plugin is powerful, but it is still under early development. The syntax is subject to change but will be backward compatible as much as possible
3.  you will want to use this with [CodeblockCustomizer](https://github.com/mugiwara85/CodeblockCustomizer) to collapse your code block.
4.  you will want to save the following codeblock as template so that you can use it easily.

%% run start

\`\`\`ts fold
return;
\`\`\`

%%

## Support

If you are enjoying this plugin then please support my work and enthusiasm by buying me a coffee on [https://www.buymeacoffee.com/yomaru](https://www.buymeacoffee.com/yomaru).

[![Buy Me A Coffee](https://camo.githubusercontent.com/cace41b0afc90c68d0207e2bd809ee121f9ff4f72ac032e8ced972aee7adbb23/68747470733a2f2f63646e2e6275796d6561636f666665652e636f6d2f627574746f6e732f76322f64656661756c742d79656c6c6f772e706e67)](https://www.buymeacoffee.com/yomaru)