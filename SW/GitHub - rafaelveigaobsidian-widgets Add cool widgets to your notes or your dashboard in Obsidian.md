---
page-title: "GitHub - rafaelveiga/obsidian-widgets: Add cool widgets to your notes or your dashboard in Obsidian"
url: https://github.com/rafaelveiga/obsidian-widgets
date: "2024-03-03 17:10:53"
tags: 
- A/sw/plugin
- F/homepage
- C/
- P/
about: "[[Obsidian]]"
uuid: 6135b134-d11c-48b6-b1e7-86d74ff9c0ed
---

## Obsidian Widgets

[](https://github.com/rafaelveiga/obsidian-widgets#obsidian-widgets)

Adds cool widgets within Obsidian notes

## Usage

[](https://github.com/rafaelveiga/obsidian-widgets#usage)

To insert a widget, simply add a code block with the language `widgets` and add your options to the body

Currently, the available widgets are:

## Clock

[](https://github.com/rafaelveiga/obsidian-widgets#clock)

[![Clock](https://github.com/rafaelveiga/obsidian-widgets/raw/master/public/clock.png)](https://github.com/rafaelveiga/obsidian-widgets/blob/master/public/clock.png)

#### Configuration Body

[](https://github.com/rafaelveiga/obsidian-widgets#configuration-body)

`type`: clock

#### Example

[](https://github.com/rafaelveiga/obsidian-widgets#example)

````
```widgets
type: clock
```
````

## Quote

[](https://github.com/rafaelveiga/obsidian-widgets#quote)

[![Quote](https://github.com/rafaelveiga/obsidian-widgets/raw/master/public/quote.png)](https://github.com/rafaelveiga/obsidian-widgets/blob/master/public/quote.png)

#### Configuration Body:

[](https://github.com/rafaelveiga/obsidian-widgets#configuration-body-1)

`type`: quote

`quote`: the quote you want to display

`author`: the author of the quote (optional)

#### Example

[](https://github.com/rafaelveiga/obsidian-widgets#example-1)

````
```widgets
type: quote
quote: Lorem ipsum dolor sit amet
author: Lorem Ipsum
```
````

## Countdown

[](https://github.com/rafaelveiga/obsidian-widgets#countdown)

[![Countdown](https://github.com/rafaelveiga/obsidian-widgets/raw/master/public/countdown.png)](https://github.com/rafaelveiga/obsidian-widgets/blob/master/public/countdown.png)

#### Configuration Body:

[](https://github.com/rafaelveiga/obsidian-widgets#configuration-body-2)

`type`: countdown

`date`: Must be in the format `YYYY-MM-DD HH:MM:SS`

`to`: Description of the countdown (optional)

#### Example

[](https://github.com/rafaelveiga/obsidian-widgets#example-2)

````
```widgets
type: countdown
date: 2024-01-01 00:00:00
to: New Year! 🎉
```
````

## Customizing your widgets

[](https://github.com/rafaelveiga/obsidian-widgets#customizing-your-widgets)

We currently do not support and don't plan to support customizing styles and colors of each widget via options in the widgets code block. Each widget is set to respect your theme's colors. That does not mean you can further customize the look of your widgets to your liking via CSS Snippets.

If you want to customize your widgets, please follow the [guide in our wiki](https://github.com/rafaelveiga/obsidian-widgets/wiki/Customizing-your-widgets-colors-styles)

## Command Pallete

[](https://github.com/rafaelveiga/obsidian-widgets#command-pallete)

Obsidian Widgets also comes with a handy command on the command pallete (Ctrl+P) to add widgets on the fly

[![Command Pallete](https://github.com/rafaelveiga/obsidian-widgets/raw/master/public/command-pallete.png)](https://github.com/rafaelveiga/obsidian-widgets/blob/master/public/command-pallete.png)

## Suggestions

[](https://github.com/rafaelveiga/obsidian-widgets#suggestions)

-   [Widget requests, bugs, new feature requests](https://github.com/rafaelveiga/obsidian-widgets/issues)

## Support

[](https://github.com/rafaelveiga/obsidian-widgets#support)

If you find this plugin useful and would like to support its development, you can sponsor me on Ko-Fi

[![ko-fi](https://camo.githubusercontent.com/ce32b4940b9ebf361cfd346ba0582815846406854cd2f701c11a85cb21eaa939/68747470733a2f2f6b6f2d66692e636f6d2f696d672f676974687562627574746f6e5f736d2e737667)](https://ko-fi.com/Z8Z0SNIS3)