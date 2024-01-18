---
page-title: "shap-po/obsidian-party: An implementation of party.js for Obsidian"
url: https://github.com/shap-po/obsidian-party
date: "2024-01-18 08:19:36"
tags: sw/plugin
purpose:
extends: "[[Obsidian]]"
---

## [![](https://raw.githubusercontent.com/yiliansource/party-js/main/.github/banner.svg)](https://raw.githubusercontent.com/yiliansource/party-js/main/.github/banner.svg)

[Installation](https://github.com/shap-po/obsidian-party#installation) • [Usage](https://github.com/shap-po/obsidian-party#usage) • [Documentation](https://party.js.org/docs)

[![](https://camo.githubusercontent.com/13fb820c9e22434870d488c32d6e22b4b1d362a69dd80355002422b205b03bd5/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f446f6e6174652d50617950616c2d626c75652e737667)](https://www.paypal.com/donate/?hosted_button_id=89AG7T2HQA8K6) [![](https://camo.githubusercontent.com/5561ed0ee663e23f487ebfccea1bc66d458ad84a5efaa0a84064e1014261f45e/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f446f6e6174652d4275792532304d6525323041253230436f666665652d6f72616e67652e737667)](https://www.buymeacoffee.com/shap)

## Party🎉

An implementation of the [party.js](https://party.js.org/) library for the [Obsidian](https://obsidian.md/).

## Features

-   Create confetti and sparkles effects

 [![](https://raw.githubusercontent.com/shap-po/obsidian-party/master/images/confetti.gif)](https://raw.githubusercontent.com/shap-po/obsidian-party/master/images/confetti.gif)[![](https://raw.githubusercontent.com/shap-po/obsidian-party/master/images/sparkles.gif)](https://raw.githubusercontent.com/shap-po/obsidian-party/master/images/sparkles.gif)

-   Add effects to checkboxes (also supports dataview tasks and a tasks plugin)

 [![](https://raw.githubusercontent.com/shap-po/obsidian-party/master/images/checkbox.gif)](https://raw.githubusercontent.com/shap-po/obsidian-party/master/images/checkbox.gif)[![](https://raw.githubusercontent.com/shap-po/obsidian-party/master/images/snowflakes.gif)](https://raw.githubusercontent.com/shap-po/obsidian-party/master/images/snowflakes.gif)

-   A lot of customization options

[![](https://raw.githubusercontent.com/shap-po/obsidian-party/master/images/customization.png)](https://raw.githubusercontent.com/shap-po/obsidian-party/master/images/customization.png)

-   Custom shapes

[![](https://raw.githubusercontent.com/shap-po/obsidian-party/master/images/custom-shapes.png)](https://raw.githubusercontent.com/shap-po/obsidian-party/master/images/custom-shapes.png)

-   Kanban compatibility
    
-   What else do you want? (I'm open to suggestions!)
    

## Installation

Search for the "Party🎉" in the Obsidian plugin list.

## Manual Installation

1.  Go to [Releases](https://github.com/shap-po/obsidian-party/releases) and download the latest release
2.  Enable plugins in the Obsidian settings
3.  Extract the contents of the zip file to obsidian plugins folder
4.  You should have a folder named "obsidian-party", containing "main.js" and "manifest.json" files
5.  Restart Obsidian and enable the plugin in the plugin list

## Manual build

1.  Clone the repository
2.  Run `npm i` or `yarn` to install dependencies
3.  `npm run dev` to build the plugin

## Examples

## Checkbox effects

1.  Open plugin settings
2.  Select effect type
3.  Enjoy!

## Custom elements / API

Either add a `confetti` or `sparkles` class for an element, or make use of all features of the [party module](https://party.js.org/docs), which can be accessed through `window.party`! Also, you'd better to not spam particles, because it can cause performance issues.

## Simple confetti button

<button class\="confetti"\>Click me!</button\>

Click me! (This button will launch confetti on click if you have this plugin enabled)

## DataView JS support

````
```dataviewjs
const buttonMaker = (text) => {
  const btn = this.container.createEl('button', {"text": text});
  btn.addEventListener('click', async (evt) => {
    evt.preventDefault();
    party.confetti(evt); // <---- creating confetti
    party.sparkles(evt); // <---- creating sparkles
  });
  return btn;
}

dv.table(["File", "Button"],
	dv.pages('"Dataview"')
    .map(t => [
      t.file.link,
      buttonMaker("Let's start the party!")
    ]
  )
)
```
````

## Custom shapes

Any HTML code can be used as a shape. For example, you can use an SVG image as a shape.

<svg viewBox\="0 0 2 2" width\="10" height\="10"\><circle cx\="1" cy\="1" r\="1"/></svg\>

Put the code in the "Shape HTML" field in the custom shapes section of the plugin settings, give it a name and you're good to go! Now you can select custom shapes in the "Shapes" field of the effect settings.