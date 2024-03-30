---
page-title: Features - Wez's Terminal Emulator
url: https://wezfurlong.org/wezterm/features.html
date: 2024-03-26 02:38:13
tags:
  - F/homepage
  - C/features
  - P/pwf
  - A/sw/terminal
about:
  - terminal emulators
aliases:
  - ab4243e2-9084-497d-b1fd-472fdaba3a30
  - Features - Wez's Terminal Emulator
by: 
length: 1689
dir:
---

[](https://github.com/wez/wezterm/edit/main/docs/features.md "Edit this page")[](https://github.com/wez/wezterm/raw/main/docs/features.md "View source of this page")

## Features

## Available Features[¶](https://wezfurlong.org/wezterm/features.html#available-features "Permanent link")

-   Runs on Linux, macOS, Windows 10 and FreeBSD
-   [Multiplex terminal panes, tabs and windows on local and remote hosts, with native mouse and scrollback](https://wezfurlong.org/wezterm/multiplexing.html)
-   [Ligatures](https://github.com/tonsky/FiraCode#fira-code-monospaced-font-with-programming-ligatures), Color Emoji and font fallback, with true color and [dynamic color schemes](https://wezfurlong.org/wezterm/config/appearance.html#colors).
-   [Hyperlinks](https://wezfurlong.org/wezterm/hyperlinks.html)
-   [Searchable Scrollback](https://wezfurlong.org/wezterm/scrollback.html) (use mouse wheel and `Shift-PageUp` and `Shift PageDown` to navigate, Ctrl-Shift-F to activate search mode)
-   xterm style selection of text with mouse; paste selection via `Shift-Insert` (bracketed paste is supported!)
-   SGR style mouse reporting (works in vim and tmux)
-   Render underline, double-underline, italic, bold, strikethrough (most other terminal emulators do not support as many render attributes)
-   Configuration via a [configuration file](https://wezfurlong.org/wezterm/config/files.html) with hot reloading
-   Multiple Windows (Hotkey: `Super-N`)
-   Splits/Panes (Split horizontally/vertically: `Ctrl-Shift-Alt-%` and `Ctrl-Shift-Alt-"`, move between panes: `Ctrl-Shift-ArrowKey`)
-   Tabs (Hotkey: `Super-T`, next/prev: `Super-Shift-[` and `Super-Shift-]`, go-to: `Super-[1-9]`)  
    
-   [SSH client with native tabs](https://wezfurlong.org/wezterm/ssh.html)
    
-   [Connect to serial ports for embedded/Arduino work](https://wezfurlong.org/wezterm/serial.html)
-   Connect to a local multiplexer server over unix domain sockets
-   Connect to a remote multiplexer using SSH or TLS over TCP/IP
-   iTerm2 compatible image protocol support, and built-in [imgcat command](https://wezfurlong.org/wezterm/imgcat.html)
-   Kitty graphics support
-   Sixel graphics support (experimental: starting in `20200620-160318-e00b076c`)