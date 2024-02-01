---
page-title: "LilaRest/obsidian-custom-classes: A minimal Obsidian plugin that allows you to add your own HTML classes to chosen Markdown elements directly from your notes."
url: https://github.com/LilaRest/obsidian-custom-classes
date: "2024-01-18 08:18:32"
tags: A/sw/plugin
purpose:
extends: "[[Obsidian]]"
---

## Obsidian Custom Classes

[![GitHub Workflow Status](https://camo.githubusercontent.com/b20333c99716b43827634636026d2c4e727f3127b3286bb30350412c466fa682/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f616374696f6e732f776f726b666c6f772f7374617475732f4c696c61526573742f6f6273696469616e2d637573746f6d2d636c61737365732f73656d616e7469632d72656c656173652e796d6c)](https://camo.githubusercontent.com/b20333c99716b43827634636026d2c4e727f3127b3286bb30350412c466fa682/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f616374696f6e732f776f726b666c6f772f7374617475732f4c696c61526573742f6f6273696469616e2d637573746f6d2d636c61737365732f73656d616e7469632d72656c656173652e796d6c) [![GitHub Downloads](https://camo.githubusercontent.com/28cf1ba0943a4b4f415225ed3e695d5303604956ec8e12ac4841b40afa54630f/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f646f776e6c6f6164732f4c696c61526573742f6f6273696469616e2d637573746f6d2d636c61737365732f746f74616c3f636f6c6f723d253233646463636565)](https://camo.githubusercontent.com/28cf1ba0943a4b4f415225ed3e695d5303604956ec8e12ac4841b40afa54630f/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f646f776e6c6f6164732f4c696c61526573742f6f6273696469616e2d637573746f6d2d636c61737365732f746f74616c3f636f6c6f723d253233646463636565) [![GitHub License](https://camo.githubusercontent.com/24b5774c39d88d74910d7aa9022999db1b7dd525862d0275ce8945ce4e1fbb67/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6c6963656e73652f4c696c61526573742f6f6273696469616e2d637573746f6d2d636c61737365733f636f6c6f723d253233353538386666)](https://camo.githubusercontent.com/24b5774c39d88d74910d7aa9022999db1b7dd525862d0275ce8945ce4e1fbb67/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6c6963656e73652f4c696c61526573742f6f6273696469616e2d637573746f6d2d636c61737365733f636f6c6f723d253233353538386666) [![Semantic-release: angular](https://camo.githubusercontent.com/2822a3edae66f3b3d4a0406c07496f401ee4986e07bec802df29b290a288d7fb/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f73656d616e7469632d2d72656c656173652d616e67756c61722d6531303037393f6c6f676f3d73656d616e7469632d72656c65617365)](https://camo.githubusercontent.com/2822a3edae66f3b3d4a0406c07496f401ee4986e07bec802df29b290a288d7fb/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f73656d616e7469632d2d72656c656173652d616e67756c61722d6531303037393f6c6f676f3d73656d616e7469632d72656c65617365)

**A minimal Obsidian plugin that allows you to add your own HTML  
classes to chosen Markdown blocks directly from your notes.**

## Usage

You can add custom classes to :

-   **entire blocks** (e.g. a whole list) → By inserting `` `class: <customClass>` `` on the line right before it
    
    **This markdown**  
    (Edit mode)
    
    **Will be rendered**  
    (Live Preview / Read mode)
    
    \`class: fancy-list\`
    \- Lorem ipsum
    \- Dolor
    \- Amet consectetur             
    
    <div class\="fancy-list"\>
      <ul\>
        <li\>Lorem ipsum</li\>
        <li\>Dolor sit</li\>
        <li\>Amet consectetur</li\>            
      </ul\>
    </div\>
    
  
-   **specific elements** (e.g. a list item) → By inserting `` `class: <customClass>` `` inside of it
    
    **This markdown**  
    (Edit mode)
    
    **Will be rendered**  
    (Live Preview / Read mode)
    
    \- Lorem ipsum
    \- Dolor sit \`class: fancy-item\`
    \- Amet consectetur
    
    <div\>
      <ul\>
        <li\>Lorem ipsum</li\>
        <li class\="fancy-item"\>Dolor sit</li\>
        <li\>Amet consectetur</li\>
      </ul\>
    </div\>
    
  
-   **or even both :**
    
    **This markdown**  
    (Edit mode)
    
    **Will be rendered**  
    (Live Preview / Read mode)
    
    \`class: fancy-list\`
    \- Lorem ipsum
    \- Dolor \`class: fancy-item\` sit 
    \- Amet consectetur
    
    <div class\="fancy-list"\>
      <ul\>
        <li\>Lorem ipsum</li\>
        <li class\="fancy-item"\>Dolor sit</li\>
        <li\>Amet consectetur</li\>
      </ul\>
    </div\>
    

  

> #### ℹ️   For advanced usages and/or informations see the [FAQ section](https://github.com/LilaRest/obsidian-custom-classes#-FAQ).

## Demonstrations

Here are some ways to use this plugin that may inspire you for your workflows.

**Add a class to :**

1.  **A whole table**  
    
    **This markdown**  
    (Edit mode)
    
    **Will be rendered**  
    (Live Preview / Read mode)
    
    \`class: mytable\`
    | AAA | BBB | CCC |
    | --- | --- | --- |
    | 111 | 222 | 333 |
    
    <div class\="mytable"\>
    <table\>
      <thead\>
        <tr\>
          <th\>AAA</th\>
          <th\>BBB</th\>
          <th\>CCC</th\>
        </tr\>
      </thead\>
      <tbody\>
        <tr\>
          <td\>111</td\>
          <td\>222</td\>
          <td\>333</td\>
        </tr\>
      </tbody\>
    </table\>
    </div\>  
2.  **A table cell**  
    
    **This markdown**  
    (Edit mode)
    
    **Will be rendered**  
    (Live Preview / Read mode)
    
    | AAA | BBB                  | CCC |
    | --- | -------------------- | --- |
    | 111 | 222 \`class: my-cell\` | 333 |
    
    <div\>
    <table\>
      <thead\>
        <tr\>
          <th\>AAA</th\>
          <th\>BBB</th\>
          <th\>CCC</th\>
        </tr\>
      </thead\>
      <tbody\>
        <tr\>
          <td\>111</td\>
          <td class\="my-cell"\>222</td\>
          <td\>333</td\>
        </tr\>
      </tbody\>
    </table\>
    </div\>  
3.  **A Dataview query**  
    
    **This markdown**  
    (Edit mode)
    
    **Will be rendered**  
    (Live Preview / Read mode)
    
    \`class: my-dv-list\`
    \`\`\`dataview
    LIST
    WHERE creation
    \`\`\`
    
    <div class\="my-dv-list"\>
      <div class\="block-language-dataview"\>
        <ul class\="dataview list-view-ul"\>
          // The results of your query 
          // <li\>...</li\>
          // ...
        </ul\>
      </div\>
    </div\>
    
      
    
4.  **A heading**  
    
    **This markdown**  
    (Edit mode)
    
    **Will be rendered**  
    (Live Preview / Read mode)
    
    \`class: important-title\`
    \### My super heading
    
    <div class\="important-title"\>
      <h3\>My super heading</h3\>
    </div\>
    
      
    
5.  **A blockquote**  
    
    **This markdown**  
    (Edit mode)
    
    **Will be rendered**  
    (Live Preview / Read mode)
    
    \`class: interesting-quote\`
    \> Lorem ipsum dolor sit amet
    
    <div class\="interesting-quote"\>
      <blockquote\>
        <p\>Lorem ipsum dolor sit amet</p\>
      </blockquote\>
    </div\>
    
      
    
6.  **An inline formatting**  
    
    **This markdown**  
    (Edit mode)
    
    **Will be rendered**  
    (Live Preview / Read mode)
    
    I'm a \*\*bold text \`class: big\`\*\* and \_\`.small\` me an italic one\_
    
    <p\>I'm a <strong class\="big"\>bold text</strong\> and <em class\="small"\>me an italic one</em\></p\>
    
      
    

## Showcase / Integrations

That section displays some example of how people have integrated the *Custom Classes* plugin in their workflows. Feel free to share yours by [opening an issue](https://github.com/LilaRest/obsidian-custom-classes/issues/new).

1.  ### The Lila's frontmatter 🌸
    
    Here the *Custom Classes* plugin is used to render a Markdown unordered list (`ul`) as a clean frontmatter block.
    
    → Source: [https://forum.obsidian.md/t/a-frontmatter-that-finally-supports-links-lilas-frontmatter/53087](https://forum.obsidian.md/t/a-frontmatter-that-finally-supports-links-lilas-frontmatter/53087)
    
    **This markdown**  
    (Edit mode)
    
    **Will be rendered**  
    (Live Preview / Read mode)
    
    \`class:meta\`
    \- creation:: 2023-01-21T18:55:12
    \- author:: \[\[John Doe\]\]
    \- parents:: \[\[Note\]\], \[\[Another note\]\]
    \- status:: `#MayBePartial`
    
    Theme
    
    Dark
    
    [![](https://camo.githubusercontent.com/e44e335d871d668d8a4f26b3c540245cae1418e6e23c16a936fcd7c3e92787ad/68747470733a2f2f666f72756d2e6f6273696469616e2e6d642f75706c6f6164732f64656661756c742f6f726967696e616c2f33582f312f342f313431386133363539623033336663663864393235313035643661336461336336623939383466632e676966)](https://camo.githubusercontent.com/e44e335d871d668d8a4f26b3c540245cae1418e6e23c16a936fcd7c3e92787ad/68747470733a2f2f666f72756d2e6f6273696469616e2e6d642f75706c6f6164732f64656661756c742f6f726967696e616c2f33582f312f342f313431386133363539623033336663663864393235313035643661336461336336623939383466632e676966)
    
    Light
    
    [![](https://camo.githubusercontent.com/3c6287a9fe4e7a17c356fe8e78f98b4e1529f828dd5c717445ebd6b9203483e2/68747470733a2f2f666f72756d2e6f6273696469616e2e6d642f75706c6f6164732f64656661756c742f6f726967696e616c2f33582f332f352f333562323039646661373961326233646631333136366539646464366431623230383438306663612e676966)](https://camo.githubusercontent.com/3c6287a9fe4e7a17c356fe8e78f98b4e1529f828dd5c717445ebd6b9203483e2/68747470733a2f2f666f72756d2e6f6273696469616e2e6d642f75706c6f6164732f64656661756c742f6f726967696e616c2f33582f332f352f333562323039646661373961326233646631333136366539646464366431623230383438306663612e676966)
    

## ❔ FAQ

**Why not to use `<div class="my-custom-class">` instead ?**

> In Obsidian, wrapping a Markdown element in a `div` will break its render in Live Preview and Read modes, and prevent links from being clicked in Edit mode. Also, writing HTML into your notes makes them less readable.
> 
> **Thanks to the *Custom Classes* plugin you're able to add a custom classes to Markdown elements without breaking anything and using plain-markdown format !** 🎉

  
**Will it works in other Markdown editors ?**

> Since this plugin is exclusive to Obsidian, the custom classes will not be applied in other editors.
> 
> However since the custom classes blocks (`` `class: ...` ``) are simple Markdown inline code-blocks, they will properly render as code blocks in other Markdown editors.

  
**Is it possible to add multiple classes at once ?**

> Yes, just separate each class by a comma :
> 
> **This markdown**  
> (Edit mode)
> 
> **Will be rendered**  
> (Live Preview / Read mode)
> 
> \`class: first, second, third-one\`
> I'm the paragraph and you ?          
> 
> <div class\="first second third-one"\>
>   <p\>I'm the paragraph and you ?</p\>
> </div\>

  
**Does it works in Live Preview mode ?**

> Yes the Live Preview mode is fully supported by this plugin.
> 
> By the way, elements targetted by a *Custom Classes* block are rendered in the exact same way in both Read and LP modes, allowing you to write CSS that will work everywhere.

  
**The `class:` prefix is too long, is there any shorthand version ?**

> Yes the *Custom Classes* plugin will also consider as custom classes block every inline code-block that starts with `cls:`or with `.`
> 
> So `` `cls: wow` `` and `` `.wow` `` are equivalent to `` `class: wow` ``.

  

## Installation

1.  Go to **Community Plugins** section of your Obsidian's settings
2.  Click on **Browse** and search for "Custom classes"
3.  Select the *Custom Classes* plugin and click on **Install**
4.  Once installed, click on **Enable**
5.  Enjoy !

## Inspiration

This plugin is originally inspired by the [Obsidian Stylist](https://github.com/ixth/obsidian-stylist) plugin but has been entirely rewritten to :

-   focus exclusively on adding custom HTML classes,
-   support the Live Preview mode,
-   fix some majors bugs (e.g. classes were not properly appended if the targetted block was modified and then re-rendered).

## Contributing

See [CONTRIBUTING.md](https://github.com/LilaRest/obsidian-custom-classes/blob/main/CONTRIBUTING.md).