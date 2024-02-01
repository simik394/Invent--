---
page-title: "Pseudonium/Obsidian_to_Anki: Script to add flashcards from text/markdown files to Anki"
url: https://github.com/Pseudonium/Obsidian_to_Anki
date: "2024-01-18 00:28:46"
tags: A/sw/obsi/plugin
purpose: integration
---

## Obsidian\_to\_Anki

Plugin to add flashcards from a text or markdown file to Anki. Run in Obsidian as a plugin, or from the command-line as a python script. Built with [Obsidian](https://obsidian.md/) markdown syntax in mind. Supports **user-defined custom syntax for flashcards.**  
See the [Trello](https://trello.com/b/6MXEizGg/obsidiantoanki) for planned features.

## Getting started

Check out the [Wiki](https://github.com/Pseudonium/Obsidian_to_Anki/wiki)! It has a ton of information, including setup instructions for new users. I will include a copy of the instructions here:

## Setup

### All users

1.  Start up [Anki](https://apps.ankiweb.net/), and navigate to your desired profile.
2.  Ensure that you've installed [AnkiConnect](https://github.com/FooSoft/anki-connect).

### Obsidian plugin users

3.  Have [Obsidian](https://obsidian.md/) downloaded
4.  Search the 'Community plugins' list for this plugin
5.  Install the plugin.
6.  In Anki, navigate to Tools->Addons->AnkiConnect->Config, and change it to look like this:

{
    "apiKey": null,
    "apiLogPath": null,
    "webBindAddress": "127.0.0.1",
    "webBindPort": 8765,
    "webCorsOrigin": "http://localhost",
    "webCorsOriginList": \[
        "http://localhost",
        "app://obsidian.md"
    \]
}

7.  Restart Anki to apply the above changes
8.  With Anki running in the background, load the plugin. This will generate the plugin settings.

You shouldn't need Anki running to load Obsidian in the future, though of course you will need it for using the plugin!

To run the plugin, look for an Anki icon on your ribbon (the place where buttons such as 'open Graph view' and 'open Quick Switcher' are). For more information on use, please check out the [Wiki](https://github.com/Pseudonium/Obsidian_to_Anki/wiki)!

### Python script users

3.  Install the latest version of [Python](https://www.python.org/downloads/).
4.  If you are a new user, download `obstoanki_setup.py` from the [releases page](https://github.com/Pseudonium/Obsidian_to_Anki/releases), and place it in the folder you want the script installed (for example your notes folder).
5.  Run `obstoanki_setup.py`, for example by double-clicking it in a file explorer. This will download the latest version of the script and required dependencies automatically. Existing users should be able to run their existing `obstoanki_setup.py` to get the latest version of the script.
6.  Check the Permissions tab below to ensure the script is able to run.
7.  Run `obsidian_to_anki.py`, for example by double-clicking it in a file explorer. This will generate a config file, `obsidian_to_anki_config.ini`.

#### Permissions

The script needs to be able to:

-   Make a config file in the directory the script is installed.
-   Read the file in the directory the script is used.
-   Make a backup file in the directory the script is used.
-   Rename files in the directory the script is used.
-   Remove a backup file in the directory the script is used.
-   Change the current working directory temporarily (so that local image paths are resolved correctly).

## Features

Current features (check out the wiki for more details):

Note that **all custom syntax is off by default**, and must be programmed into the script via the config file - see the Wiki for more details.

[![Buy Me a Coffee at ko-fi.com](https://camo.githubusercontent.com/9da29a4ab68783c46db3229ef632988f93d14cffaebf3c7710c37454f3180ce9/68747470733a2f2f63646e2e6b6f2d66692e636f6d2f63646e2f6b6f6669312e706e673f763d32)](https://ko-fi.com/K3K52X4L6)