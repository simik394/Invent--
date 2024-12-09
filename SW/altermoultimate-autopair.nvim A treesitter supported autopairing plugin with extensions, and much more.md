---
page-title: "altermo/ultimate-autopair.nvim: A treesitter supported autopairing plugin with extensions, and much more"
url: https://github.com/altermo/ultimate-autopair.nvim
date: "2024-06-23 01:05:24"
tags: [A/sw/plugin, F/prod/homepage, C/, P/pwf]
about: ["[[NeoVim]]"]
aliases: 
- 
by: 
length: 2164
dir: 
---

**❗ Ultimate-autopair is at the moment in the *beta* stage of development. ([versioning system](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6/CONTRIBUTING.md#version))**

## Ultimate-autopair.nvim 0.6.1

[](https://github.com/altermo/ultimate-autopair.nvim#ultimate-autopairnvim-061)

[Ultimate-autopair](https://github.com/altermo/ultimate-autopair.nvim) plugin aims to always work as you expect and be ultra customizable, while making it easy to configure. It has features which other auto-pairing plugins lack: multiline support, treesitter-node filtering and treesitter-filetype detection.

For development version, which is sometimes up to date with default branch, check out [development](https://github.com/altermo/ultimate-autopair.nvim/tree/development)  
Requires **neovim 0.9** (for older versions of neovim, check previous versions of plugin)  
For some features, including string filtering, requires **treesitter**.

For new users, check out starter documentation (`:help ultimate-autopair`)

## Installation

[](https://github.com/altermo/ultimate-autopair.nvim#installation)

**Lazy**

{
    'altermo/ultimate-autopair.nvim',
    event\={'InsertEnter','CmdlineEnter'},
    branch\='v0.6', \--recommended as each new version will have breaking changes
    opts\={
        \--Config goes here
    },
}

**Packer**

use{
    'altermo/ultimate-autopair.nvim',
    event\={'InsertEnter','CmdlineEnter'},
    branch\='v0.6', \--recommended as each new version will have breaking changes
    config\=function ()
        require('ultimate-autopair').setup({
                \--Config goes here
                })
    end,
}

## Default configuration

[](https://github.com/altermo/ultimate-autopair.nvim#default-configuration)

For the default configuration, refer to the documentation (`:help ultimate-autopair-default-config`).

## Demo

[](https://github.com/altermo/ultimate-autopair.nvim#demo)

**demo**

[![demo](https://private-user-images.githubusercontent.com/107814000/265192623-a30ba4fd-0a3b-49af-bcd8-67413c9a86d1.gif?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTkwOTc3OTAsIm5iZiI6MTcxOTA5NzQ5MCwicGF0aCI6Ii8xMDc4MTQwMDAvMjY1MTkyNjIzLWEzMGJhNGZkLTBhM2ItNDlhZi1iY2Q4LTY3NDEzYzlhODZkMS5naWY_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwNjIyJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDYyMlQyMzA0NTBaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT03NGVlNDdkOWE2OGFjYjQyMmZkYjYxOWJjODMzNTE2NGM0ZTcyYmQzMWU5YWM1MjYyZmI0M2IwMmZlMjM0OTYxJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.s8JDPIS7HmriptT0PfZVg6BQBRZwajIgv4ljSIO1Tzk)](https://private-user-images.githubusercontent.com/107814000/265192623-a30ba4fd-0a3b-49af-bcd8-67413c9a86d1.gif?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTkwOTc3OTAsIm5iZiI6MTcxOTA5NzQ5MCwicGF0aCI6Ii8xMDc4MTQwMDAvMjY1MTkyNjIzLWEzMGJhNGZkLTBhM2ItNDlhZi1iY2Q4LTY3NDEzYzlhODZkMS5naWY_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwNjIyJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDYyMlQyMzA0NTBaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT03NGVlNDdkOWE2OGFjYjQyMmZkYjYxOWJjODMzNTE2NGM0ZTcyYmQzMWU5YWM1MjYyZmI0M2IwMmZlMjM0OTYxJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.s8JDPIS7HmriptT0PfZVg6BQBRZwajIgv4ljSIO1Tzk)

### Other plugins to supercharge auto-pairing

[](https://github.com/altermo/ultimate-autopair.nvim#other-plugins-to-supercharge-auto-pairing)

These are some other plugins which are related to pairing which have features that ultimate-autopair does not have.

-   [endwise](https://github.com/RRethy/nvim-treesitter-endwise) wisely add `end` in lua, ruby, etc... (Note: doesn't get broken by ultimate-autopair's newline)
-   [tabout](https://github.com/abecodes/tabout.nvim) tab out of treesitter nodes
-   [surround](https://github.com/kylechui/nvim-surround) delete, change surrounding parentheses and much more...
-   [autotag](https://github.com/windwp/nvim-ts-autotag) auto pair html tags

If you want to use this together with [nvim-autopairs](https://github.com/windwp/nvim-autopairs) read `:h ultimate-autopair-use-with-npairs`

### Donate

[](https://github.com/altermo/ultimate-autopair.nvim#donate)

If you want to donate then you need to find the correct link (hint: 50₁₀):

-   [0a](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [0b](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [0c](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [0d](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [0e](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [0f](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [0g](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [0h](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6)
-   [1a](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [1b](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [1c](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [1d](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [1e](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [1f](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [1g](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [1h](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6)
-   [2a](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [2b](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [2c](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [2d](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [2e](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [2f](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [2g](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [2h](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6)
-   [3a](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [3b](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [3c](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [3d](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [3e](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [3f](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [3g](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [3h](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6)
-   [4a](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [4b](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [4c](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [4d](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [4e](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [4f](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [4g](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [4h](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6)
-   [5a](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [5b](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [5c](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [5d](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [5e](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [5f](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [5g](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [5h](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6)
-   [6a](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [6b](https://www.buymeacoffee.com/altermo) [6c](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [6d](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [6e](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [6f](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [6g](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [6h](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6)
-   [7a](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [7b](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [7c](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [7d](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [7e](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [7f](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [7g](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6) [7h](https://github.com/altermo/ultimate-autopair.nvim/blob/v0.6)

### Chat

[](https://github.com/altermo/ultimate-autopair.nvim#chat)

-   [github discussions](https://github.com/altermo/ultimate-autopair.nvim/discussions)