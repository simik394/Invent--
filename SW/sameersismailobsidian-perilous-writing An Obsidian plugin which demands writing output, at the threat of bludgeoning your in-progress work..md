---
page-title: "sameersismail/obsidian-perilous-writing: An Obsidian plugin which demands writing output, at the threat of bludgeoning your in-progress work."
url: https://github.com/sameersismail/obsidian-perilous-writing
date: "2024-07-16 19:55:58"
tags: [a/sw/plugin, f/prod/homepage, c/, p/pwf/productivity/writing]
about: ["[[Obsidian]]"]
aliases: 
- 
by: 
length: 2007
dir: 
---

## Perilous Writing

[](https://github.com/sameersismail/obsidian-perilous-writing#perilous-writing)

An [Obsidian](https://obsidian.md/) plugin which *demands* writing output, at the threat of bludgeoning your in-progress work. Emulates [Manu Ebert's](https://github.com/maebert) excellent [The Most Dangerous Writing App](https://github.com/maebert/themostdangerouswritingapp).

[Try it out! ↗](https://perilous.sameerismail.org/) ☨

\[☨\] (Experimental—bug reports welcome.)

## Usage

[](https://github.com/sameersismail/obsidian-perilous-writing#usage)

> **Warning:** If a session is not completed successfully then your in-session work will be **irrevocably deleted**. Caveat emptor.

1.  Install the plugin. See below.
    
2.  Open the command palette and choose either a short session (default of five minutes), a long session (default of ten minutes), or a custom-length session. (The respective default durations can be changed in the settings tab.)
    
    [![image](https://user-images.githubusercontent.com/38896593/225518688-f0fbd6be-8662-4522-a1d1-e106ff67483e.png)](https://user-images.githubusercontent.com/38896593/225518688-f0fbd6be-8662-4522-a1d1-e106ff67483e.png)
3.  A light gray bar will appear at the top of the editor. It represents the session's progress. The session will begin after the next keypress.
    
    [![image](https://user-images.githubusercontent.com/38896593/225518790-aac26285-8583-4008-b003-535587f468df.png)](https://user-images.githubusercontent.com/38896593/225518790-aac26285-8583-4008-b003-535587f468df.png)
4.  Begin writing. If you stop writing for five seconds your in-session additions will be **deleted**. You'll be warned after two seconds of inactivity.
    
    [![image](https://user-images.githubusercontent.com/38896593/225519562-ac5493af-337f-4a50-b7d9-4e5cd71da019.png)](https://user-images.githubusercontent.com/38896593/225519562-ac5493af-337f-4a50-b7d9-4e5cd71da019.png) [![image](https://user-images.githubusercontent.com/38896593/225519715-6577f3ef-d437-4832-a8ee-e54cef18f9bb.png)](https://user-images.githubusercontent.com/38896593/225519715-6577f3ef-d437-4832-a8ee-e54cef18f9bb.png) [![image](https://user-images.githubusercontent.com/38896593/225519763-a2881d95-0c95-4446-9ead-fc74e99ac9f3.png)](https://user-images.githubusercontent.com/38896593/225519763-a2881d95-0c95-4446-9ead-fc74e99ac9f3.png)
5.  Only new characters reset the timer—backspace does *not*. Neither do normal-mode operations under Vim emulation. On completion of a successful session, progress is preserved.
    
    [![image](https://user-images.githubusercontent.com/38896593/225519961-fc73c74b-23f3-4801-a4b8-a87092a18e34.png)](https://user-images.githubusercontent.com/38896593/225519961-fc73c74b-23f3-4801-a4b8-a87092a18e34.png)
6.  Remove the progress bar with the “Clear session” command.
    

## Installation

[](https://github.com/sameersismail/obsidian-perilous-writing#installation)

## Community Plugins

[](https://github.com/sameersismail/obsidian-perilous-writing#community-plugins)

Search for [“Perilous Writing”](https://obsidian.md/plugins?search=perilous%20writing) in the community plugins tab.

## Manual

[](https://github.com/sameersismail/obsidian-perilous-writing#manual)

Download the latest release, and copy the `main.js`, `styles.css`, and `manifest.json` files into a new plugin directory, like (4) and (5) below.

## From source

[](https://github.com/sameersismail/obsidian-perilous-writing#from-source)

1.  Clone the repository.
    
2.  Install the dependencies. Through `yarn` or `npm install` in the directory root.
    
3.  Build the plugin with `yarn build` or `npm run build`. This will produce a `main.js` file.
    
4.  Create a directory for the plugin in your vault's directory.
    
    mkdir -p $VAULT\_SOURCE/.obsidian/plugins/perilous-writing
    
5.  Copy the `main.js`, `styles.css`, and `manifest.json` files into that directory.
    
    cp main.js styles.css manifest.json $VAULT\_SOURCE/.obsidian/perilous-writing
    
6.  Enable the plugin in Obsidian's settings tab.
    

## Acknowledgements

[](https://github.com/sameersismail/obsidian-perilous-writing#acknowledgements)

Inspired by [Manu Ebert's](https://github.com/maebert) [The Most Dangerous Writing App](https://github.com/maebert/themostdangerouswritingapp).