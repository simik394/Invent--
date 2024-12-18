---
page-title: "max-niederman/ttyper: Terminal-based typing test."
url: https://github.com/max-niederman/ttyper
date: "2024-12-11 03:58:02"
about: ["[[rychlé a byzchybné psaní na klávesnici bez koukání]]"]
tags: [f/homepage/repo, c/examples/usage, c/examples/config]
---
## ttyper

[](https://github.com/max-niederman/ttyper#ttyper)

[![Crates.io](https://camo.githubusercontent.com/1bed7c7511be1a873ad30261ba8043481d5129c876c6c6e24efb2cf1f95b8306/68747470733a2f2f696d672e736869656c64732e696f2f6372617465732f762f747479706572)](https://crates.io/crates/ttyper) [![GitHub Stars](https://camo.githubusercontent.com/c6d5d8bb99e300425b910b510c9da7db842b81987d5e98d1d32b762688f14e8d/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f73746172732f6d61782d6e69656465726d616e2f747479706572)](https://github.com/max-niederman/ttyper) [![GitHub Workflow Status](https://camo.githubusercontent.com/11465e40a5b561a00309d68cf7eaa5b1104077cb3a98e5a50a8334fe208e8777/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f616374696f6e732f776f726b666c6f772f7374617475732f6d61782d6e69656465726d616e2f7474797065722f727573742e796d6c)](https://github.com/max-niederman/ttyper/actions) [![GitHub commit activity](https://camo.githubusercontent.com/57fa9b464b803b573b3232c1d8cd978be5f9ac827c2af5e2238a2df21d646ec3/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f636f6d6d69742d61637469766974792f6d2f6d61782d6e69656465726d616e2f747479706572)](https://camo.githubusercontent.com/57fa9b464b803b573b3232c1d8cd978be5f9ac827c2af5e2238a2df21d646ec3/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f636f6d6d69742d61637469766974792f6d2f6d61782d6e69656465726d616e2f747479706572) [![Discord](https://camo.githubusercontent.com/14fbc31bab831fbb607e6e1856c6429662819b1e2a565c536f15752b38561a05/68747470733a2f2f696d672e736869656c64732e696f2f646973636f72642f313233333236373031313936333036303237353f6c6f676f3d646973636f7264)](https://discord.gg/3wJyrBsKXu) [![License](https://camo.githubusercontent.com/a93950d5360752e23db93cbc4beb3a8913f9160080b9ad9098c16770a42492bf/68747470733a2f2f696d672e736869656c64732e696f2f6372617465732f6c2f747479706572)](https://github.com/max-niederman/ttyper/blob/main/LICENSE.md)

ttyper is a terminal-based typing test built with Rust and Ratatui.

[![Recording](https://github.com/max-niederman/ttyper/raw/main/resources/recording.gif)](https://github.com/max-niederman/ttyper/blob/main/resources/recording.gif)

## chat

[](https://github.com/max-niederman/ttyper#chat)

If you're interested in contributing to ttyper, need help with an issue, or just want to hang out, you should join [the development Discord server](https://discord.gg/3wJyrBsKXu).

## installation

[](https://github.com/max-niederman/ttyper#installation)

### pre-built binaries

[](https://github.com/max-niederman/ttyper#pre-built-binaries)

Pre-built binaries are available for most architectures on [GitHub releases](https://github.com/max-niederman/ttyper/releases). If your system is not supported or you have another problem, feel free to open an issue.

### cargo

[](https://github.com/max-niederman/ttyper#cargo)

### arch linux

[](https://github.com/max-niederman/ttyper#arch-linux)

### nix

[](https://github.com/max-niederman/ttyper#nix)

nix-env -iA nixpkgs.ttyper # or nixos.ttyper on NixOS

### scoop

[](https://github.com/max-niederman/ttyper#scoop)

## usage

[](https://github.com/max-niederman/ttyper#usage)

For usage instructions, you can run `ttyper --help`:

```
ttyper 1.5.0
Terminal-based typing test.

USAGE:
    ttyper [FLAGS] [OPTIONS] [contents]

FLAGS:
    -d, --debug             
    -h, --help              Prints help information
        --list-languages    List installed languages
        --no-backtrack      Disable backtracking to completed words
        --sudden-death      Enable sudden death mode to restart on first error
    -V, --version           Prints version information

OPTIONS:
    -c, --config <config>                  Use config file
    -l, --language <language>              Specify test language
        --language-file <language-file>    Specify test language in file
    -w, --words <words>                    Specify word count [default: 50]

ARGS:
    <contents>
```

### examples

[](https://github.com/max-niederman/ttyper#examples)

| command | test contents |
| --- | --- |
| `ttyper` | 50 of the 200 most common english words |
| `ttyper -w 100` | 100 of the 200 most common English words |
| `ttyper -w 100 -l english1000` | 100 of the 1000 most common English words |
| `ttyper --language-file lang` | 50 random words from the file `lang` |
| `ttyper text.txt` | contents of `text.txt` split at newlines |

## languages

[](https://github.com/max-niederman/ttyper#languages)

The following languages are available by default:

| name | description |
| --- | --- |
| `c` | The C programming language |
| `csharp` | The C# programming language |
| `english100` | 100 most common English words |
| `english200` | 200 most common English words |
| `english1000` | 1000 most common English words |
| `english-advanced` | Advanced English words |
| `english-pirate` | 50 pirate speak English words |
| `french100` | 100 most common French words |
| `french200` | 200 most common French words |
| `french1000` | 1000 most common French words |
| `german` | 207 most common German words |
| `german1000` | 1000 most common German words |
| `german10000` | 10000 most common German words |
| `go` | The Go programming language |
| `html` | HyperText Markup Language |
| `java` | The Java programming language |
| `javascript` | The Javascript programming language |
| `norwegian` | 200 most common Norwegian words |
| `php` | The PHP programming language |
| `portuguese` | 100 most common Portuguese words |
| `portuguese200` | 200 most common Portuguese words |
| `portuguese1000` | 1000 most common Portuguese words |
| `portuguese-advanced` | Advanced Portuguese words |
| `python` | The Python programming language |
| `qt` | The QT GUI framework |
| `ruby` | The Ruby programming language |
| `rust` | The Rust programming language |
| `spanish` | 100 most common Spanish words |
| `ukrainian` | 100 most common Ukrainian words |

Additional languages can be added by creating a file in `TTYPER_CONFIG_DIR/language` with a word on each line. On Linux, the config directory is `$HOME/.config/ttyper`; on Windows, it's `C:\Users\user\AppData\Roaming\ttyper`; and on macOS it's `$HOME/Library/Application Support/ttyper`.

## config

[](https://github.com/max-niederman/ttyper#config)

Configuration is specified by the `config.toml` file in the config directory (e.g. `$HOME/.config/ttyper/config.toml`).

The default values with explanations are below:

# the language used when one is not manually specified
default\_language = "english200"

\[theme\]
# default style (this includes empty cells)
default = "none"

# title text styling
title = "white;bold"

#\# test styles ##

# input box border
input\_border = "cyan"
# prompt box border
prompt\_border = "green"

# border type
border\_type = "rounded"

# correctly typed words
prompt\_correct = "green"
# incorrectly typed words
prompt\_incorrect = "red"
# untyped words
prompt\_untyped = "gray"

# correctly typed letters in current word
prompt\_current\_correct = "green;bold"
# incorrectly typed letters in current word
prompt\_current\_incorrect = "red;bold"
# untyped letters in current word
prompt\_current\_untyped = "blue;bold"

# cursor character
prompt\_cursor = "none;underlined"

#\# results styles ##

# overview text
results\_overview = "cyan;bold"
# overview border
results\_overview\_border = "cyan"

# worst keys text
results\_worst\_keys = "cyan;bold"
# worst keys border
results\_worst\_keys\_border = "cyan"

# results chart default (includes plotted data)
results\_chart = "cyan"
# results chart x-axis label
results\_chart\_x = "cyan"
# results chart y-axis label
results\_chart\_y = "gray;italic"

# restart/quit prompt in results ui
results\_restart\_prompt = "gray;italic"

### style format

[](https://github.com/max-niederman/ttyper#style-format)

The configuration uses a custom style format which can specify most [ANSI escape styling codes](https://en.wikipedia.org/wiki/ANSI_escape_code#SGR_\(Select_Graphic_Rendition\)_parameters), encoded as a string.

Styles begin with the color specification, which can be a single color (the foreground), or two colors seperated by a colon (the foreground and background). Colors can be one of sixteen specified by your terminal, a 24-bit hex color code, `none`, or `reset`.

After the colors, you can optionally specify modifiers seperated by a semicolon. A list of modifiers is below:

-   `bold`
-   `crossed_out`
-   `dim`
-   `hidden`
-   `italic`
-   `rapid_blink`
-   `slow_blink`
-   `reversed`
-   `underlined`

Some examples:

-   `blue:white;italic` specifies italic blue text on a white background.
-   `none;italic;bold;underlined` specifies underlined, italicized, and bolded text with no set color or background.
-   `00ff00:000000` specifies text of color `#00ff00` (pure green) on a background of `#000000` (pure black).

In [extended Backus-Naur form](https://en.wikipedia.org/wiki/Extended_Backus%E2%80%93Naur_form):

style     \= colors, { ";", modifier }, \[ ";" \] ;
colors    \= color, \[ ":", color \] ;
color     \= "none"
          | "reset"
          | "black"
          | "white"
          | "red"
          | "green"
          | "yellow"
          | "blue"
          | "magenta"
          | "cyan"
          | "gray"
          | "darkgray"
          | "lightred"
          | "lightgreen"
          | "lightyellow"
          | "lightblue"
          | "lightmagenta"
          | "lightcyan"
          | 6 \* hex digit ;
hex digit \= ? hexadecimal digit; 1-9, a-z, and A-Z ? ;
modifier  \= "bold"
          | "crossed\_out"
          | "dim"
          | "hidden"
          | "italic"
          | "rapid\_blink"
          | "slow\_blink"
          | "reversed"
          | "underlined" ;

### border types

[](https://github.com/max-niederman/ttyper#border-types)

The following border types are supported in the config file.

-   `plain`
-   `rounded` (default)
-   `double`
-   `thick`
-   `quadrantinside`
-   `quadrantoutside`

If you're familiar with [serde](https://serde.rs/), you can also read [the deserialization code](https://github.com/max-niederman/ttyper/blob/main/src/config.rs).