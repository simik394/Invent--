---
page-title: "RyotaUshio/obsidian-quick-preview: An Obsidian plugin to quickly preview a suggestion before selecting it in link suggestions & quick switcher."
url: https://github.com/RyotaUshio/obsidian-quick-preview
date: "2024-01-18 22:24:23"
tags: A/sw/plugin
purpose:
extends: "[[Obsidian]]"
---

## Obsidian Quick Preview

This [Obsidian.md](https://obsidian.md/) plugin adds a ***quick preview*** functionality to

-   [Link suggestions](https://help.obsidian.md/Linking+notes+and+files/Internal+links),
-   [Quick switcher](https://help.obsidian.md/Plugins/Quick+switcher),
-   and even [Quick switcher++](https://github.com/darlal/obsidian-switcher-plus).
-   ***New in 0.6.0***: Canvas's note/media suggestion is now supported as well!

Hold down `Alt`/`Option` (by default) to quickly preview a suggestion before actually selecting it.

### Link suggestions ([file](https://help.obsidian.md/Linking+notes+and+files/Internal+links#Link%20to%20a%20file)/[heading](https://help.obsidian.md/Linking+notes+and+files/Internal+links#Link%20to%20a%20heading%20in%20a%20note)/[block](https://help.obsidian.md/Linking+notes+and+files/Internal+links#Link%20to%20a%20block%20in%20a%20note))

[![Screen Recording 2023-12-13 at 18 27 42](https://private-user-images.githubusercontent.com/72342591/290140907-3dec5c7d-e74e-4f8d-a0f3-43e424dbbee9.gif?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDU2MDc0NDUsIm5iZiI6MTcwNTYwNzE0NSwicGF0aCI6Ii83MjM0MjU5MS8yOTAxNDA5MDctM2RlYzVjN2QtZTc0ZS00ZjhkLWEwZjMtNDNlNDI0ZGJiZWU5LmdpZj9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAxMTglMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMTE4VDE5NDU0NVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWZjMTRiMmZhZTMwNTEzM2E3YTU1MDA5OGI2NGE5OTExNDlmZWI4ZWYzMmJjZGMwZmE4YTQwNzQyMDc4NWI2ZjMmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.xXRuJPYS1OcwZUTgwsqI0fCxESA_lwzROg_xCdywHfg)](https://private-user-images.githubusercontent.com/72342591/290140907-3dec5c7d-e74e-4f8d-a0f3-43e424dbbee9.gif?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDU2MDc0NDUsIm5iZiI6MTcwNTYwNzE0NSwicGF0aCI6Ii83MjM0MjU5MS8yOTAxNDA5MDctM2RlYzVjN2QtZTc0ZS00ZjhkLWEwZjMtNDNlNDI0ZGJiZWU5LmdpZj9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAxMTglMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMTE4VDE5NDU0NVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWZjMTRiMmZhZTMwNTEzM2E3YTU1MDA5OGI2NGE5OTExNDlmZWI4ZWYzMmJjZGMwZmE4YTQwNzQyMDc4NWI2ZjMmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.xXRuJPYS1OcwZUTgwsqI0fCxESA_lwzROg_xCdywHfg)

### Quick switcher / Quick switcher++

[![Screen Recording 2023-12-13 at 18 24 34](https://private-user-images.githubusercontent.com/72342591/290139810-4eaae76b-b0fa-425f-a3ff-857b70e9a02a.gif?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDU2MDc0NDUsIm5iZiI6MTcwNTYwNzE0NSwicGF0aCI6Ii83MjM0MjU5MS8yOTAxMzk4MTAtNGVhYWU3NmItYjBmYS00MjVmLWEzZmYtODU3YjcwZTlhMDJhLmdpZj9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAxMTglMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMTE4VDE5NDU0NVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWUzMzRlNzE1YmE5ZWYxYWRkMjZiOWVmMGY3ODE0NTBmMDUzZDFkMTI1ZGM0OTNlMjU1MTY3ODRkOGIyNGFkMTYmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.r0Hwbw2bGhrfpVTqwNihq0SBrwHzB-zcpMxNivUDKkg)](https://private-user-images.githubusercontent.com/72342591/290139810-4eaae76b-b0fa-425f-a3ff-857b70e9a02a.gif?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDU2MDc0NDUsIm5iZiI6MTcwNTYwNzE0NSwicGF0aCI6Ii83MjM0MjU5MS8yOTAxMzk4MTAtNGVhYWU3NmItYjBmYS00MjVmLWEzZmYtODU3YjcwZTlhMDJhLmdpZj9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAxMTglMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMTE4VDE5NDU0NVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWUzMzRlNzE1YmE5ZWYxYWRkMjZiOWVmMGY3ODE0NTBmMDUzZDFkMTI1ZGM0OTNlMjU1MTY3ODRkOGIyNGFkMTYmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.r0Hwbw2bGhrfpVTqwNihq0SBrwHzB-zcpMxNivUDKkg)

Tip

-   You can adjust the font size for quick preview via [Style Settings](https://github.com/mgmeyers/obsidian-style-settings).
-   **Other plugins also can utilize the quick preview feature via the API**. See [below](https://github.com/RyotaUshio/obsidian-quick-preview#using-the-api) for more details.

## Installation

You can find this plugin in the community plugin browser within Obsidian.

You can also install the latest beta release using [BRAT](https://github.com/TfTHacker/obsidian42-brat):

1.  Install the latest version of BRAT and enable it.
2.  Open the following URL in browser: `obsidian://brat?plugin=RyotaUshio/obsidian-quick-preview`.
3.  Click the "Add Plugin" button.
4.  *(Optional but highly recommended)* In the BRAT settings, turn on `Auto-update plugins at startup` at the top of the page.

## Reporting problems

If you find a problem about this plugin, please report it by filing an issue from [here](https://github.com/RyotaUshio/obsidian-quick-preview/issues).

It'd be helpful if you could attatch the following information:

-   Result of the "Show debug info" command
-   Screenshot of the plugin settings

## Using the API

This plugin provides an API to allow other plugins to add the quick preview functionality to their custom suggesters. Supported suggester types are:

-   [`SuggestModal`](https://docs.obsidian.md/Reference/TypeScript+API/SuggestModal)
-   [`PopoverSuggest`](https://docs.obsidian.md/Reference/TypeScript+API/PopoverSuggest), including:
    -   [`EditorSuggest`](https://docs.obsidian.md/Reference/TypeScript+API/EditorSuggest)
    -   [`AbstractInputSuggest`](https://docs.obsidian.md/Reference/TypeScript+API/AbstractInputSuggest)

### Installation

```
npm install -D obsidian-quick-preview
```

### Usage examples

import { Plugin, EditorSuggest, SuggestModal, TFile, SectionCache } from "obsidian";
import { registerQuickPreview } from "obsidian-quick-preview";

class MyCustomEditorSuggest extends EditorSuggest<{ file: TFile }\> { ... }

class MyCustomSuggestModal extends SuggestModal<{ path: string, cache: SectionCache }\> { ... }

export default MyPlugin extends Plugin {
    excludedFiles: string\[\];

    onload() {
        registerQuickPreview(this.app, this, MyCustomEditorSuggest, (item) \=> {
            // - \`linktext\` can be any string representing a proper internal link,
            //   e.g. "note", "note.md", "folder/note", "folder/note.md", "note#heading", "note#^block-id" etc
            // - \`sourcePath\` is used to resolve relative links. In many cases, you can just pass an empty string.
            return { linktext: item.file.path, sourcePath: "" };
        });
        // or
        registerQuickPreview(this.app, this, MyCustomSuggestModal, (item) \=> {
            if (this.excludedFiles.contains(item.path)) {
                // Return \`null\` when you don't want to show a quick preview for the item.
                return null;
            }
            // Add a \`line\` parameter to focus on a specific line.
            return { linktext: item.path, sourcePath: "", line: item.cache.position.start.line };
        });
    }
}

## Support development

If you find my plugins useful, please support my work by buying me a coffee!

[![Buy Me A Coffee](https://camo.githubusercontent.com/cace41b0afc90c68d0207e2bd809ee121f9ff4f72ac032e8ced972aee7adbb23/68747470733a2f2f63646e2e6275796d6561636f666665652e636f6d2f627574746f6e732f76322f64656661756c742d79656c6c6f772e706e67)](https://www.buymeacoffee.com/ryotaushio)