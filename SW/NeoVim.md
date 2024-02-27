---
tags:
  - M/⭐
url: https://neovim.io/
---

> [!NOTE]- purposeless
> ```dataview
> table
> from #nvim/plugin 
> where !purpose
> ```
> 

| command | effect |
| ---- | ---- |
| :Ex | open FS_current directory view in buffer |
| :Sex! | splitscreen current-dir \| buffer |
| :S | split window horizontally |
| :S! | split window vertically |
| vim . | open the FS_current directory |
| u | undo |
| ctrl+r | redo |
| crtl+d | jump 1/2 of page down |
| ctrl+u | jump 1/2 of page up |
| { | 1 paragraph up |
| } | 1 paragraph down |
| :... | jump to line ... |
| /... + n;shift+N | najdi ... + navigace tam a zpátky |
| ?... | search upwards |
| (kurzor na daném slově) + * | automatically switches to searching mode |
| (kurzor před závorkami) + vi'závorka' | označí celý text mezi danými závorkami |
| (kurzor před závorkami) + va'závorka' | označí celý text včetně daných závorek |
gj - by 1 visual line down 

![[delete-examples.commands.nvim]]



# Tutorial
[Overview - Practicalli Neovim](https://practical.li/neovim/) 
- [Overview - Practicalli Neovim](onenote:https://d.docs.live.net/a3e7ec4e2a2bbe83/Documents/OneNote%20Notebooks/Projects/BP/latest.one#Overview%20-%20Practicalli%20Neovim&section-id={CA37B6A0-3ECD-407A-AB93-01DEFA2ADAEA}&page-id={1EA27FD7-DEDF-451D-9E53-6974C2E13743}&end)  ([Web view](https://onedrive.live.com/view.aspx?resid=A3E7EC4E2A2BBE83%2150469&id=documents&wd=target%28BP%2Flatest.one%7CCA37B6A0-3ECD-407A-AB93-01DEFA2ADAEA%2FOverview%20-%20Practicalli%20Neovim%7C1EA27FD7-DEDF-451D-9E53-6974C2E13743%2F%29))

[vim tutorial - Hledat](https://www.bing.com/search?pglt=675&q=vim+tutorial&cvid=87484be5d582449c897edb000f7e4c7e&gs_lcrp=EgZjaHJvbWUqBggAEEUYOzIGCAAQRRg7MgYIARAAGEAyBggCEAAYQDIGCAMQABhAMgYIBBAAGEAyBggFEAAYQDIGCAYQABhAMgYIBxBFGDwyBggIEEUYPNIBCDcxODBqMGoxqAIAsAIA&FORM=ANNTA1&PC=EDBBAN)

> [!NOTE]- on windows guides
> ```dataview
> list from [[NeoVim]] and [[windows.os]]
> ```

> [!NOTE]- nvim lua guides
> ```dataview
> list from [[NeoVim]] and [[Lua]]
> ```

> [!NOTE]- javascript (web-dev) in neovim
> ```dataview
> list from [[NeoVim]] and [[JavaScript]]
> ```

## config
* [nvim configuration - Hledat](https://www.bing.com/search?q=nvim+configuration&qs=n&form=QBRE&sp=-1&ghc=1&lq=0&pq=nvim+configuration&sc=11-18&sk=&cvid=26AF47F03FA0436F848CD31E4C8850C2&ghsh=0&ghacc=0&ghpl=)
* [neovim-configuration · GitHub Topics](https://github.com/topics/neovim-configuration)
# Plugins
[[awesome-neovimREADME.md at main · rockerBOOawesome-neovim f6fdb144-d106-4068-b518-df29b0847781|awsome neovim - collection of plugins]]
## Distributions
[[myDM/Websites/homepage.LazyVim.distributions.nvim|LazyVim]]
[[homepage.AstroNvim.distributions.nvim]]
[[homepage.NvChad.distributions.nvim]]
[[homepage.LunarVim.distributions.nvim]]
[[homepage.nix-config.distributions.nvim]]
[[homepage.Neelfrost_nvim-config.distributions.nvim]]
[[homepage.utfeight_vimacs.distributions.nvim]]
- [CosmicNvim/CosmicNvim: CosmicNvim is a lightweight and opinionated Neovim config for web development, specifically designed to provide a 💫 COSMIC programming experience! (github.com)](https://github.com/CosmicNvim/CosmicNvim)


[[nixvim.distributions.nvim |nixvim]]
fn gg{                                    }


Color themes
- [rebelot/kanagawa.nvim: NeoVim dark colorscheme inspired by the colors of the famous painting by Katsushika Hokusai. (github.com)](https://github.com/rebelot/kanagawa.nvim)
- [artanikin/vim-synthwave84: The port of SynthWave '84 - VS Code theme to Vim (github.com)](https://github.com/artanikin/vim-synthwave84)
- [folke/tokyonight.nvim: 🏙 A clean, dark Neovim theme written in Lua, with support for lsp, treesitter and lots of plugins. Includes additional themes for Kitty, Alacritty, iTerm and Fish. (github.com)](https://github.com/folke/tokyonight.nvim)


