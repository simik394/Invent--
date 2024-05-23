---
page-title: "joshuakto/obsidian-cardify: plugin to create individual pages for line separated elements"
url: https://github.com/joshuakto/obsidian-cardify
date: "2024-04-12 00:52:52"
tags: 
- A/sw/plugin/structure-mgmt
- F/homepage
- C/
- P/
about: "[[Obsidian]]"
aliases: 
- 0f6a9316-69fe-41a9-b489-7b4a837d8ecb
- joshuakto/obsidian-cardify: plugin to create individual pages for line separated elements
by: 
length: 2036
dir: 
---

## Obsidian Cardify Plugin [![copy-plus](https://github.com/joshuakto/obsidian-cardify/assets/34743132/4ecabc7b-2498-4128-94a3-a3e5b1ddd82d)](https://github.com/joshuakto/obsidian-cardify/assets/34743132/4ecabc7b-2498-4128-94a3-a3e5b1ddd82d)

[](https://github.com/joshuakto/obsidian-cardify#obsidian-cardify-plugin-)

[![Obsidian Downloads](https://camo.githubusercontent.com/04ee25edabb9e6f523ab71aa30fdab4f45c98433476376ad20e36e478c8004e7/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f64796e616d69632f6a736f6e3f6c6f676f3d6f6273696469616e26636f6c6f723d253233343833363939266c6162656c3d646f776e6c6f6164732671756572793d253234253542253232636172646966792532322535442e646f776e6c6f6164732675726c3d68747470732533412532462532467261772e67697468756275736572636f6e74656e742e636f6d2532466f6273696469616e6d642532466f6273696469616e2d72656c65617365732532466d6173746572253246636f6d6d756e6974792d706c7567696e2d73746174732e6a736f6e)](https://camo.githubusercontent.com/04ee25edabb9e6f523ab71aa30fdab4f45c98433476376ad20e36e478c8004e7/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f64796e616d69632f6a736f6e3f6c6f676f3d6f6273696469616e26636f6c6f723d253233343833363939266c6162656c3d646f776e6c6f6164732671756572793d253234253542253232636172646966792532322535442e646f776e6c6f6164732675726c3d68747470732533412532462532467261772e67697468756275736572636f6e74656e742e636f6d2532466f6273696469616e6d642532466f6273696469616e2d72656c65617365732532466d6173746572253246636f6d6d756e6974792d706c7567696e2d73746174732e6a736f6e)

Separates contents in a markdown, assign internal links to each separated content, and generate subsequent linked markdowns. Making it easy to drag and drop individual linked markdown files onto canvas.

## Demo

[](https://github.com/joshuakto/obsidian-cardify#demo)

### Desktop (Mac)

[](https://github.com/joshuakto/obsidian-cardify#desktop-mac)

obsidian.demo.mov

### iPadOS

[](https://github.com/joshuakto/obsidian-cardify#ipados)

Adding cardify generate card command to toolbar and using added shortcut.

RPReplay\_Final1708955498.MP4

### Android

[](https://github.com/joshuakto/obsidian-cardify#android)

Using ribbon bar icon to trigger generation of cards on android app.

screen-20240226-213336.2.mp4

Cardify has these basic functionalities

-   Selection of separator (currently only supports two new lines or ---).
-   Detect whether an internal link exists in the content, if not assign automatically.
-   Create a markdown for each separated content (while preserving the frontmatter).
    -   Give an index for the created page based on the position of the separated contents.
    -   Extract comment from content to use as title for the created page
-   Create a folder to store the created markdown.
-   Generate and insert an internal link to replace the current selection.

Planned functionalities

-   Switch for toggling function to automatically assign internal links.
-   List of regex arranged in order of priority to use as title of the created markdown.
-   Allow users to view instruction for using the plugin in a popup modal.
-   Allow users to see the preview for the cards to be generated from the active file.

## How to use

[](https://github.com/joshuakto/obsidian-cardify#how-to-use)

1.  Upon installation, [![an icon with overlapping squares(copy-plus)](https://private-user-images.githubusercontent.com/34743132/308150893-a1c0a848-f8da-4f67-a7a7-8458f0f9320e.svg?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTI4NzYyMTgsIm5iZiI6MTcxMjg3NTkxOCwicGF0aCI6Ii8zNDc0MzEzMi8zMDgxNTA4OTMtYTFjMGE4NDgtZjhkYS00ZjY3LWE3YTctODQ1OGYwZjkzMjBlLnN2Zz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA0MTElMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNDExVDIyNTE1OFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTAxY2M1MzFkNmQ5ODg3ZTc1MTg5NTZlNGVmZGI1MzA4ODAwOTBmOWI2ZDY4MWJjYzFmODBlNThlMDhlZTNmNTcmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.nQT9Om-KCH-_IVJ3GG-gY8jmcs2MMZxiOrUVRLXyjjk)](https://private-user-images.githubusercontent.com/34743132/308150893-a1c0a848-f8da-4f67-a7a7-8458f0f9320e.svg?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTI4NzYyMTgsIm5iZiI6MTcxMjg3NTkxOCwicGF0aCI6Ii8zNDc0MzEzMi8zMDgxNTA4OTMtYTFjMGE4NDgtZjhkYS00ZjY3LWE3YTctODQ1OGYwZjkzMjBlLnN2Zz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA0MTElMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNDExVDIyNTE1OFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTAxY2M1MzFkNmQ5ODg3ZTc1MTg5NTZlNGVmZGI1MzA4ODAwOTBmOWI2ZDY4MWJjYzFmODBlNThlMDhlZTNmNTcmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.nQT9Om-KCH-_IVJ3GG-gY8jmcs2MMZxiOrUVRLXyjjk) will be visible on the ribbon.
2.  Navigate to the markdown file you want to Cardify.
3.  Clicking [![the icon with overlapping squares(copy-plus)](https://private-user-images.githubusercontent.com/34743132/308150893-a1c0a848-f8da-4f67-a7a7-8458f0f9320e.svg?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTI4NzYyMTgsIm5iZiI6MTcxMjg3NTkxOCwicGF0aCI6Ii8zNDc0MzEzMi8zMDgxNTA4OTMtYTFjMGE4NDgtZjhkYS00ZjY3LWE3YTctODQ1OGYwZjkzMjBlLnN2Zz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA0MTElMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNDExVDIyNTE1OFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTAxY2M1MzFkNmQ5ODg3ZTc1MTg5NTZlNGVmZGI1MzA4ODAwOTBmOWI2ZDY4MWJjYzFmODBlNThlMDhlZTNmNTcmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.nQT9Om-KCH-_IVJ3GG-gY8jmcs2MMZxiOrUVRLXyjjk)](https://private-user-images.githubusercontent.com/34743132/308150893-a1c0a848-f8da-4f67-a7a7-8458f0f9320e.svg?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTI4NzYyMTgsIm5iZiI6MTcxMjg3NTkxOCwicGF0aCI6Ii8zNDc0MzEzMi8zMDgxNTA4OTMtYTFjMGE4NDgtZjhkYS00ZjY3LWE3YTctODQ1OGYwZjkzMjBlLnN2Zz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA0MTElMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNDExVDIyNTE1OFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTAxY2M1MzFkNmQ5ODg3ZTc1MTg5NTZlNGVmZGI1MzA4ODAwOTBmOWI2ZDY4MWJjYzFmODBlNThlMDhlZTNmNTcmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.nQT9Om-KCH-_IVJ3GG-gY8jmcs2MMZxiOrUVRLXyjjk) will generate a folder named the same as the active file and store created markdowns in it. **Note:** Currently, the plugin will change the content of the markdown when inserting internal link. If the spacing of the document is important, do not use this plugin for now. In the future there will be an option to choose whether you want to modify content of existing files.

[!["Buy Me A Coffee"](https://camo.githubusercontent.com/52867c19b7dfad6776f2d60ae248692873ae6bdcb9a3df2bfca2f1f2ffdfd15d/68747470733a2f2f63646e2e6275796d6561636f666665652e636f6d2f627574746f6e732f76322f64656661756c742d626c75652e706e67)](https://www.buymeacoffee.com/joshuakto)

## Acknowledgements

[](https://github.com/joshuakto/obsidian-cardify#acknowledgements)

This plugin is built using [Obsidian Sample Plugin](https://github.com/obsidianmd/obsidian-sample-plugin) as a template.