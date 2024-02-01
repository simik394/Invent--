---
page-title: "SkepticMystic/adjacency-matrix-maker: Creative an interactive adjacency matrix of your Obsidian vault"
url: https://github.com/SkepticMystic/adjacency-matrix-maker
date: 2024-01-18 12:05:22
tags:
  - A/sw/plugin
purpose: 
extends:
  - "[[Obsidian]]"
last-commit:
---

## Adjacency Matrix Maker

An adjacency matrix is a different way to represent an Obsidian graph.

It starts with a square grid of cells, where each **row** of cells represents a single note in your vault, and so does each **column**. If note `i` is linked to note `j`, then the cell in row `i` and column `j` will be coloured in.

You can think of it as a grid of all the **links** in your vault. Each row is a *node* in your graph, and each cell is an *edge*.

## Examples

This graph conveys the same information as this adjacency matrix:

[![](https://camo.githubusercontent.com/c3066fa98a12e06315c4fdfd34123a623acfd9635db934282088676eb4a5ab0d/68747470733a2f2f692e696d6775722e636f6d2f565a75764168712e706e67)](https://camo.githubusercontent.com/c3066fa98a12e06315c4fdfd34123a623acfd9635db934282088676eb4a5ab0d/68747470733a2f2f692e696d6775722e636f6d2f565a75764168712e706e67)

[![](https://camo.githubusercontent.com/902f4c75c83139af84d588f31c6e3bb2304c95219b86e8075e05537f222b435d/68747470733a2f2f692e696d6775722e636f6d2f676c4c346d47632e706e67)](https://camo.githubusercontent.com/902f4c75c83139af84d588f31c6e3bb2304c95219b86e8075e05537f222b435d/68747470733a2f2f692e696d6775722e636f6d2f676c4c346d47632e706e67)

## Functionality

### Pan & Zoom

When you run the `Make Adjacency Matrix` command, you will see a modal pop up with an image of your matrix. This can be panned (by holding down left-click and dragging), and zoomed (using the middle mouse wheel). If you want to reset the zoom level to it's initial state, you can use the right mouse btton, or click the `Reset Scale` button above the image.

[![](https://camo.githubusercontent.com/562568057866d5ad85a9166b3e240594c8b90d35cdbd8b69d3887f15106f03f9/68747470733a2f2f692e696d6775722e636f6d2f694a6f684444692e706e67)](https://camo.githubusercontent.com/562568057866d5ad85a9166b3e240594c8b90d35cdbd8b69d3887f15106f03f9/68747470733a2f2f692e696d6775722e636f6d2f694a6f684444692e706e67)

### Interactive Tooltip

If you hoiver your cursor over a coloured-in cell (representing two linked notes), you will see a tooltip appear showing which two notes are linked `A → B`

[![](https://camo.githubusercontent.com/28293998ec640d13ed848e34d04fe756f906d8faf4fa6f78ef47062d85b539bf/68747470733a2f2f692e696d6775722e636f6d2f777536697645372e706e67)](https://camo.githubusercontent.com/28293998ec640d13ed848e34d04fe756f906d8faf4fa6f78ef47062d85b539bf/68747470733a2f2f692e696d6775722e636f6d2f777536697645372e706e67)

You can hold down `Ctrl` to see this tooltip anywhere, even if the two notes aren't linked.

If you click on a cell, it will open the note with the outgoing link (Note `A`).

### Folder Squares

There is an option to show "folder squares" on the image of your adjacency matrix. These squares show which folder each note is in. You can also see subfolders based on colours:

-   Level-1 folders → **Red**
-   Level-2 folders → **Orange**
-   Level-3 folders → **Yellow**
-   Level-4 folders → **Green**
-   Level-5 folders → **Blue**
-   Level-6 folders → **Indigo**
-   Level-7 folders → **Violet**

[![](https://camo.githubusercontent.com/abeb893849959bb91c262edc34524eea9e0316b60b22fe805bd750343cb4434f/68747470733a2f2f692e696d6775722e636f6d2f523778476c62342e706e67)](https://camo.githubusercontent.com/abeb893849959bb91c262edc34524eea9e0316b60b22fe805bd750343cb4434f/68747470733a2f2f692e696d6775722e636f6d2f523778476c62342e706e67)

### Save Image

You can save the image of the adjacency matrix to your vault by clicking on the `Save Image` button. If successful, you will see a notice appear in the top-right corner saying `Image Saved`. The defualt name and path of the image can be configured in [image settings](https://github.com/SkepticMystic/adjacency-matrix-maker/blob/master/README.md#save-image-configuration)

## Settings

There are a few settings you can change. These can be found under the settings tab for the plugin.

### Colours

You can change the main and background colour of the image. The main colour is used to colour-in cells when two notes are linked. The background colour fills in the rest of the cells.

These settings:

[![](https://camo.githubusercontent.com/8c46ed9c65ba8accdd3c3e1544fedb686f5addd915d48656a2dc0a739e07cdee/68747470733a2f2f692e696d6775722e636f6d2f67463047395a732e706e67)](https://camo.githubusercontent.com/8c46ed9c65ba8accdd3c3e1544fedb686f5addd915d48656a2dc0a739e07cdee/68747470733a2f2f692e696d6775722e636f6d2f67463047395a732e706e67)

give me this matrix:

[![](https://camo.githubusercontent.com/a65591bbe9124b8ff3b8ca51b985059bd7a6f9eff44ef9b5696d1091a7e31703/68747470733a2f2f692e696d6775722e636f6d2f34753678674f362e706e67)](https://camo.githubusercontent.com/a65591bbe9124b8ff3b8ca51b985059bd7a6f9eff44ef9b5696d1091a7e31703/68747470733a2f2f692e696d6775722e636f6d2f34753678674f362e706e67)

### Show Folders

There is also the option to toggle [folder squares](https://github.com/SkepticMystic/adjacency-matrix-maker/blob/master/README.md#folder-squares) on or off.

[![](https://camo.githubusercontent.com/0ae231c7ba87668d0326af3b3ed4a49fe1933f76a5a41687ca8aa502af4dbb97/68747470733a2f2f692e696d6775722e636f6d2f7045576d3936342e706e67)](https://camo.githubusercontent.com/0ae231c7ba87668d0326af3b3ed4a49fe1933f76a5a41687ca8aa502af4dbb97/68747470733a2f2f692e696d6775722e636f6d2f7045576d3936342e706e67)

### Image Scale

Using the `Image Scale` option, you can change how detialed the image is. A higher scale means longer waiting time, but also a crisper image. By default, the scale is chosen based on the size of your vault.

#### `Image scale = 1`

[![](https://camo.githubusercontent.com/b50de73df941218981f471bdb7310b921dfd9b91be6e8c0308c363299adc218a/68747470733a2f2f692e696d6775722e636f6d2f306675343139522e706e67)](https://camo.githubusercontent.com/b50de73df941218981f471bdb7310b921dfd9b91be6e8c0308c363299adc218a/68747470733a2f2f692e696d6775722e636f6d2f306675343139522e706e67)

#### `Image Scale = 100`

[![](https://camo.githubusercontent.com/ae5b559d3b75471ccf70e237b82c9bb4c4060522ef606a97b87b66cc320c1ab4/68747470733a2f2f692e696d6775722e636f6d2f316752443768562e706e67)](https://camo.githubusercontent.com/ae5b559d3b75471ccf70e237b82c9bb4c4060522ef606a97b87b66cc320c1ab4/68747470733a2f2f692e696d6775722e636f6d2f316752443768562e706e67)

### Save Image Configuration

When saving the image to your vault, you can change the following properties.

#### Image Name

The name prepended to the current datetime. For example, if `Image Name = Adj`, then the saved image will be called `Adj 2021-06-15 2223`.

#### Image Path

You can also choose where the image is saved. By default, it is saved to the root of your vault. To change it, just write the path to the folder youw ant it to be saved in. For example, `Image path = Attachments/Images/Adjacency Matrices`.