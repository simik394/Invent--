---
page-title: "ennioitaliano/obsidian-auto-glossary: Obsidian plugin that allows user to create a glossary of notes or a MOC from a selected folder."
url: https://github.com/ennioitaliano/obsidian-auto-glossary
date: "2024-01-18 00:09:52"
tags: A/sw/obsi/plugin
purpose:
---

## Obsidian Auto Glossary

[![Obsidian Downloads](https://camo.githubusercontent.com/a6d9b603272407e8ab9fecc2d7c381545f3eb7290100a2a24bb194fcfea4aa21/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f64796e616d69632f6a736f6e3f6c6f676f3d6f6273696469616e26636f6c6f723d253233343833363939266c6162656c3d646f776e6c6f6164732671756572793d2532342535422532326175746f2d676c6f73736172792532322535442e646f776e6c6f6164732675726c3d68747470732533412532462532467261772e67697468756275736572636f6e74656e742e636f6d2532466f6273696469616e6d642532466f6273696469616e2d72656c65617365732532466d6173746572253246636f6d6d756e6974792d706c7567696e2d73746174732e6a736f6e)](https://camo.githubusercontent.com/a6d9b603272407e8ab9fecc2d7c381545f3eb7290100a2a24bb194fcfea4aa21/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f64796e616d69632f6a736f6e3f6c6f676f3d6f6273696469616e26636f6c6f723d253233343833363939266c6162656c3d646f776e6c6f6164732671756572793d2532342535422532326175746f2d676c6f73736172792532322535442e646f776e6c6f6164732675726c3d68747470732533412532462532467261772e67697468756275736572636f6e74656e742e636f6d2532466f6273696469616e6d642532466f6273696469616e2d72656c65617365732532466d6173746572253246636f6d6d756e6974792d706c7567696e2d73746174732e6a736f6e)

Auto Glossary is an Obsidian plugin to generate a [glossary](https://en.wikipedia.org/wiki/Glossary) or a [MOC](https://notes.linkingyourthinking.com/Cards/MOCs+Overview) (or a combination of both) from a selected folder.

[![](https://private-user-images.githubusercontent.com/47503625/266801360-64f06472-88ba-4b09-828c-73fb1aa0cf5f.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDU1MzMyODYsIm5iZiI6MTcwNTUzMjk4NiwicGF0aCI6Ii80NzUwMzYyNS8yNjY4MDEzNjAtNjRmMDY0NzItODhiYS00YjA5LTgyOGMtNzNmYjFhYTBjZjVmLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAxMTclMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMTE3VDIzMDk0NlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTQyMWE4OWQ4NjU5OTVjZTZhZjM1ZjYyM2YwZTJhN2UyZjcyN2JiNzk1MWY1ZTVjNGQ5YzQxMGU2MjZmNmZjZjEmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.2wbfthZISy1WByBsVIpkBoFNNrjsO1KFXxXOZLCS9es)](https://private-user-images.githubusercontent.com/47503625/266801360-64f06472-88ba-4b09-828c-73fb1aa0cf5f.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDU1MzMyODYsIm5iZiI6MTcwNTUzMjk4NiwicGF0aCI6Ii80NzUwMzYyNS8yNjY4MDEzNjAtNjRmMDY0NzItODhiYS00YjA5LTgyOGMtNzNmYjFhYTBjZjVmLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAxMTclMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMTE3VDIzMDk0NlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTQyMWE4OWQ4NjU5OTVjZTZhZjM1ZjYyM2YwZTJhN2UyZjcyN2JiNzk1MWY1ZTVjNGQ5YzQxMGU2MjZmNmZjZjEmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.2wbfthZISy1WByBsVIpkBoFNNrjsO1KFXxXOZLCS9es)

## How to install

You can install this plugin directly within Obsidian or you can copy over `main.js`, `styles.css`, `manifest.json` to your vault `VaultFolder/.obsidian/plugins/obsidian-auto-glossary/`.

## Usage

You can create the file you want by right-clicking on a folder in Obsidian.

## ⚠️ Contribute

I stopped working on this project. Feel free to contribute to the code of this plugin, since there are more features to be implemented (and it needs a nice refactoring too). You can also share feedback, issues, and ideas.