---
page-title: "sissilab/obsidian-image-toolkit: An Obsidian plugin for viewing an image."
url: https://github.com/sissilab/obsidian-image-toolkit
date: "2024-01-18 00:19:40"
tags: A/sw/obsi/plugin
purpose: images
---

## Obsidian Image Toolkit

[![Release version](https://camo.githubusercontent.com/e9dc2425c0a8d4bf7c21d31e0eb5f9b5b1cccd0bee0e20040615f338a49a233e/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f762f72656c656173652f73697373696c61622f6f6273696469616e2d696d6167652d746f6f6c6b69743f7374796c653d666f722d7468652d6261646765)](https://camo.githubusercontent.com/e9dc2425c0a8d4bf7c21d31e0eb5f9b5b1cccd0bee0e20040615f338a49a233e/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f762f72656c656173652f73697373696c61622f6f6273696469616e2d696d6167652d746f6f6c6b69743f7374796c653d666f722d7468652d6261646765) [![Download count](https://camo.githubusercontent.com/47144df54f70d77a09919e64ed889a60080f8f8d404e66c38a32abdfb2233165/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f646f776e6c6f6164732f73697373696c61622f6f6273696469616e2d696d6167652d746f6f6c6b69742f746f74616c3f7374796c653d666f722d7468652d6261646765)](https://camo.githubusercontent.com/47144df54f70d77a09919e64ed889a60080f8f8d404e66c38a32abdfb2233165/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f646f776e6c6f6164732f73697373696c61622f6f6273696469616e2d696d6167652d746f6f6c6b69742f746f74616c3f7374796c653d666f722d7468652d6261646765)

An Obsidian plugin for providing some image viewing toolkit  
[简体中文](https://github.com/sissilab/obsidian-image-toolkit/blob/master/README_cn.md) · [English](https://github.com/sissilab/obsidian-image-toolkit/blob/master/README.md)

## About the Plugin

When you click an image, it will be popped up and you can preview, zoom, move, rotate, flip, invert and copy the image.

## Basic Features

-   Zoom in or out an image by mouse wheel or clicking toolbar zoom icons
-   Move an image by dragging mouse cursor or pressing keyboard arrow keys
-   Preview an image in full-screen mode
-   Rotate or flip an image by clicking footer toolbar icons
-   Invert the color of an image
-   Copy an image

## Normal Mode

When you turn off 'Pin an image' on the settings page, it's in **Normal Mode**.

[![normal_mode_screenshot](https://raw.githubusercontent.com/sissilab/obsidian-image-toolkit/master/example/normal_mode_screenshot.png)](https://raw.githubusercontent.com/sissilab/obsidian-image-toolkit/master/example/normal_mode_screenshot.png)

**Rule**:

-   After clicking the image, the image will be popped up with transparent mask layer on the background
-   You can only click and preview one image at a time
-   You cannot edit and look through your notes, or other operations except to view and operate the image in the Normal Mode

**Gallery Navbar**:

-   All the images in the current note will be displayed at the bottom, and you can switch these thumbs to view any image
-   To be able to use this functionality, you need to turn on 'display gallery navbar' on the plugin settings page
-   The background color of the gallery navbar and the border color the selected image can be set on the plugin settings page

**Exit**:

-   Click the outside of the image
-   Press Esc

> If it's in full-screen mode, you need to exit full-screen mode firstly, then exit the image preview page and close popup layer.

**Move the image**:

-   Put your mouse cursor on the image, and directly drag the image to move
-   Press configured arrow keys to move the image
    
    > If you set modifier keys (Ctrl, Alt, Shift) for moving the image, you need to hold the modifier keys and press arrow keys at the same time.
    

## Pin Mode

When you turn on 'Pin an image' on the settings page, it's in **Pin Mode**.

[![pin_mode_screenshot](https://raw.githubusercontent.com/sissilab/obsidian-image-toolkit/master/example/pin_mode_screenshot.png)](https://raw.githubusercontent.com/sissilab/obsidian-image-toolkit/master/example/pin_mode_screenshot.png)

**Rule**:

-   You can click and popped up 1 to 5 images at a time
-   Comparing with normal mode, the image will be popped up without mask layer after clicking the image
-   It's allowed to edit and look through your notes while images are being popped up and previewed

**Menu**:

-   When you right click on the popped image, it will show the menu at the right side of your cursor. The menu contains several functions, like zoom, full screen, refresh, rotate, flip, copy, close, etc.

**Exit**:

-   Press Esc to close the image where your mouse cursor is hovering
-   click 'close' button in the menu

**Move the image**:

-   Put your mouse cursor on the image, and directly drag the image to move
-   NOT SUPPORT moving image by arrow keys

## Installation

**Installation from Obsidian's community plugins**:

1.  Open Settings > community plugins
2.  Turn off 'Safe mode'
3.  Click 'Browse' button to browse plugins
4.  Search for 'Image Toolkit'
5.  Click 'Install' button
6.  Once installed, close the plugins browse window and go back community plugins window, and activate the newly installed plugin below installed plugins list

**Manual installation**:

1.  Download the [latest release](https://github.com/sissilab/obsidian-image-toolkit/releases/latest)
2.  Extract obsidian-image-toolkit folder from the zip to your vault's plugins folder `<vault>/.obsidian/plugins/` (Note: `.obsidian` folder may be hidden, you need to show it firstly)
3.  Open Settings > community plugins, and reload and activate the plugin below installed plugins list

## Contact

If you've got any kind of feedback or questions, feel free to reach out via [GitHub issues](https://github.com/sissilab/obsidian-image-toolkit/issues).