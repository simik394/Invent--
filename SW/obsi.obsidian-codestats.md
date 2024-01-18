---
page-title: "Miskamyasa/obsidian-codestats: The Code::Stats plugin allows you to track your coding progress and earn XP for writing markdown in the Obsidian editor."
url: https://github.com/Miskamyasa/obsidian-codestats?tab=readme-ov-file
date: "2024-01-16 08:27:49"
---

# Obsidian Code::Stats Plugin

## [](https://github.com/Miskamyasa/obsidian-codestats?tab=readme-ov-file#description)Description

This is a Obsidian plugin to send updates to [https://codestats.net/api](https://codestats.net/api)

The Code::Stats plugin for Obsidian allows you to track your coding progress and earn XP for writing code in the Obsidian editor. With this plugin, you can send XP data to your Code::Stats account using the Code::Stats API.

To get started, simply install the plugin and enter your Code::Stats API key in the settings panel. The plugin will then listen for keyup events in the Obsidian editor and send XP data to Code::Stats every time you type a character.

Note that you will need a Code::Stats account and API key to use this plugin. You can sign up for a free account at [https://codestats.net/signup](https://codestats.net/signup) and API key can be found or created on [https://codestats.net/my/machines](https://codestats.net/my/machines) page.

This project uses Typescript to provide type checking and documentation. The repo depends on the latest plugin API (obsidian.d.ts) in Typescript Definition format, which contains TSDoc comments describing what it does.

## [](https://github.com/Miskamyasa/obsidian-codestats?tab=readme-ov-file#manually-installing-the-plugin)Manually installing the plugin

Copy over `main.js`, `styles.css`, `manifest.json` to your vault `VaultFolder/.obsidian/plugins/obsidian-codestats/`.

## [](https://github.com/Miskamyasa/obsidian-codestats?tab=readme-ov-file#api-documentation)API Documentation

See [https://github.com/obsidianmd/obsidian-api](https://github.com/obsidianmd/obsidian-api)

## [](https://github.com/Miskamyasa/obsidian-codestats?tab=readme-ov-file#summary)Summary

**Plugin ID:** codestats  
**Developer:** Denis (MiskaMyasa) Zaitsev  
**Mobile support:** No

\#codestats \#obsidian \#plugin

## [](https://github.com/Miskamyasa/obsidian-codestats?tab=readme-ov-file#license)License

[MIT License](https://github.com/Miskamyasa/obsidian-codestats/blob/main/LICENCE.md)