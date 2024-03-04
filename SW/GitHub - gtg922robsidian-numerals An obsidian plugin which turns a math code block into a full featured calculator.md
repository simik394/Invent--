---
page-title: "GitHub - gtg922r/obsidian-numerals: An obsidian plugin which turns a math code block into a full featured calculator"
url: https://github.com/gtg922r/obsidian-numerals
date: "2024-03-03 17:06:15"
tags: 
- A/sw/plugin
- F/homepage
- C/
- P/
about: "[[Obsidian]]"
uuid: cec6ac33-23b3-4fbc-ba04-58a94cdf2066
---

## Numerals Obsidian Plugin

[](https://github.com/gtg922r/obsidian-numerals#numerals-obsidian-plugin)

[![Obsidian Downloads](https://camo.githubusercontent.com/84817a783043ee8aea7fc9f23ae3c839ea9ee10867f8aea48a84599bece4fe22/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f64796e616d69632f6a736f6e3f6c6f676f3d6f6273696469616e26636f6c6f723d253233343833363939266c6162656c3d646f776e6c6f6164732671756572793d2532342535422532326e756d6572616c732532322535442e646f776e6c6f6164732675726c3d68747470732533412532462532467261772e67697468756275736572636f6e74656e742e636f6d2532466f6273696469616e6d642532466f6273696469616e2d72656c65617365732532466d6173746572253246636f6d6d756e6974792d706c7567696e2d73746174732e6a736f6e)](https://camo.githubusercontent.com/84817a783043ee8aea7fc9f23ae3c839ea9ee10867f8aea48a84599bece4fe22/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f64796e616d69632f6a736f6e3f6c6f676f3d6f6273696469616e26636f6c6f723d253233343833363939266c6162656c3d646f776e6c6f6164732671756572793d2532342535422532326e756d6572616c732532322535442e646f776e6c6f6164732675726c3d68747470732533412532462532467261772e67697468756275736572636f6e74656e742e636f6d2532466f6273696469616e6d642532466f6273696469616e2d72656c65617365732532466d6173746572253246636f6d6d756e6974792d706c7567696e2d73746174732e6a736f6e) [![GitHub release (latest by date)](https://camo.githubusercontent.com/7c88d9438024c17d31c1085f7f076f4fd46bde7350a7cf6571375fb56a323fa1/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f762f72656c656173652f677467393232722f6f6273696469616e2d6e756d6572616c733f636f6c6f723d253233343833363939)](https://camo.githubusercontent.com/7c88d9438024c17d31c1085f7f076f4fd46bde7350a7cf6571375fb56a323fa1/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f762f72656c656173652f677467393232722f6f6273696469616e2d6e756d6572616c733f636f6c6f723d253233343833363939)

*Numerals* gives you the power of an advanced calculator inside a `math` code block, complete with currencies, units, variables, and math functions! Now you can perform calculations inline with your notes, and see both the input and the evaluated result. *Numerals* works with Live Preview as well as Reader view, and offers TeX-style rendering or Syntax Highlighting as well as auto-completion suggestions. Comments or explanations can be added with `#`, and important results can be indicated with `=>` after the calculation. [![Numerals Lemonade Stand - Side by Side](https://user-images.githubusercontent.com/1195174/200186757-a71b5e7a-df96-4350-b6a4-366d758e696d.png)](https://user-images.githubusercontent.com/1195174/200186757-a71b5e7a-df96-4350-b6a4-366d758e696d.png) [![Numerals Tex Example](https://user-images.githubusercontent.com/1195174/201516487-75bb7a08-76ab-4ff3-bf6b-d654aa284ab7.png)](https://user-images.githubusercontent.com/1195174/201516487-75bb7a08-76ab-4ff3-bf6b-d654aa284ab7.png)

## Features

[](https://github.com/gtg922r/obsidian-numerals#features)

-   Units
    -   `1ft + 12in` → `2ft`
    -   `20 mi / 4 hr to m/s` → `2.235 m / s`
    -   `9.81 m/s^2 * 100 kg * 40 m` → `39.24 kJ`
-   Currency
    -   `$1,000 * 2` → `2,000 USD`
    -   `£10 + £0.75` → `10.75 GBP`
-   Math functions
    -   `sqrt`, `sin`, `cos`, `abs`, `log`, etc (see [mathjs](https://mathjs.org/docs/reference/functions.html) for full list)
-   Hex, Binary, Octal, and other bases
    -   `0xff + 0b100` → `259`
    -   `hex(0xff + 0b100)` → `"0x103"`
-   Natural Constants
    -   `e`, `i`, `pi`, `speedOfLight`, `gravitationConstant`, `vacuumImpedance`, `avogadro`
    -   And many more (see [mathjs: Constants](https://mathjs.org/docs/reference/constants.html) and [mathjs: Units](https://mathjs.org/docs/datatypes/units.html) for more)
-   Auto-complete suggestions
    -   By default will offer auto-complete suggestions for any variables defined in a math codeblock being edited
    -   Optional setting to include all available functions, constants, and physical constants
-   Fractions:
    -   `fraction(1/3) + fraction(1/4)` → `7/12`
-   Comments and Headings:
    -   `#` at the end of a line will be ignored, but rendered in faint text as a comment
    -   A line starting with `#` will be ignored by the math engine, but will be bolded when rendered
-   Result Annotation:
    -   `=>` at the end of a line (but before a comment) will tell *Numerals* that a result should be highlighted. Any line in that code block *without* a `=>` annotation will be rendered faintly (or hidden depending on settings).

*Numerals* utilizes the [mathjs](https://mathjs.org/) library for all calculations. *Numerals* implements a preprocessor to allow more human-friendly syntax, such as currency symbols and thousands separators. For all available functions and capabilities (which includes matrices, vectors, symbolic algebra and calculus, etc), see the [mathjs documentation](https://mathjs.org/docs/index.html)

## Styling Options

[](https://github.com/gtg922r/obsidian-numerals#styling-options)

*Numerals* has been tested with the default theme and most other top themes. It uses default values such that it should play nice with any other theme. There are also several configurable settings to modify how *Numerals* renders math blocks

### Render Style

[](https://github.com/gtg922r/obsidian-numerals#render-style)

*Numerals* supports rendering inputs/ouputs as either:

1.  Plain Text
2.  TeX
3.  Syntax Highlighting

One of these options can either be chosen as a default from *Numerals* settings, or then can be applied on a per-block basis by using `math-plain`, `math-tex`, or `math-highlight` rather than a `math` code block.

[![Numerals Render Style Side by Side](https://user-images.githubusercontent.com/1195174/201587645-5a79aafa-5008-49d0-b584-5c6a99c7edc5.png)](https://user-images.githubusercontent.com/1195174/201587645-5a79aafa-5008-49d0-b584-5c6a99c7edc5.png)

### Layout

[](https://github.com/gtg922r/obsidian-numerals#layout)

#### 2-panes

[](https://github.com/gtg922r/obsidian-numerals#2-panes)

-   Answer is shown to the right of the input with a background color and a seperator.
-   Distinctive style that seperates input from evaluated answers

[![Numerals 2 Panes](https://user-images.githubusercontent.com/1195174/200186692-0b6a0a7b-3f77-47f8-887f-d7d333b53967.png)](https://user-images.githubusercontent.com/1195174/200186692-0b6a0a7b-3f77-47f8-887f-d7d333b53967.png)

#### Answer to the Right

[](https://github.com/gtg922r/obsidian-numerals#answer-to-the-right)

-   Answer to the right: answer is shown in the same line as the input, but right-aligned
-   More subtle than 2-panes that works well with just a few calculations

[![Numerals answer right](https://user-images.githubusercontent.com/1195174/200186885-dedf1ccb-0464-4732-976e-0eaf54f5d098.png)](https://user-images.githubusercontent.com/1195174/200186885-dedf1ccb-0464-4732-976e-0eaf54f5d098.png)

#### Answer Below

[](https://github.com/gtg922r/obsidian-numerals#answer-below)

-   Answer is shown below the input, on the next line.
-   Less compact vertically, but more compact horizontally

[![Numerals answer below](https://user-images.githubusercontent.com/1195174/200186929-8e5bf0de-ab1e-47d0-a3f3-cf5164136c62.png)](https://user-images.githubusercontent.com/1195174/200186929-8e5bf0de-ab1e-47d0-a3f3-cf5164136c62.png)

### Alternating Row Colors

[](https://github.com/gtg922r/obsidian-numerals#alternating-row-colors)

Choose between a consistent code block background color (left), or alternating rows to help track from input to result (right).

[![Numerals Alternating Row Style Comparison](https://user-images.githubusercontent.com/1195174/200187338-24912a83-eb1e-4188-a843-e189f33e7133.png)](https://user-images.githubusercontent.com/1195174/200187338-24912a83-eb1e-4188-a843-e189f33e7133.png)

### Auto-completion Suggestions

[](https://github.com/gtg922r/obsidian-numerals#auto-completion-suggestions)

By default, *Numerals* will provide auto-completion suggestions for variables that have been defined in a particular `math` codeblock. Turning on *Include Functions and Constants in Suggestions* will also provide suggestions for all functions, math constants, and physical constants supported in *Numerals*.

[![Auto-completion of Functions](https://user-images.githubusercontent.com/1195174/215416147-68110298-0e10-44e5-9351-83efc3a17bba.png)](https://user-images.githubusercontent.com/1195174/215416147-68110298-0e10-44e5-9351-83efc3a17bba.png)

### Format of Numbers in Rendered Results

[](https://github.com/gtg922r/obsidian-numerals#format-of-numbers-in-rendered-results)

*Numerals* allows the user to specify the format of rendered results.

-   **System Formatted** (Default): Use your local system settings for number formatting (including thousands and decimal separator)
-   **Fixed**: No thousands separator and full precision. Period as decimal separator (e.g. `100000.1`)
-   **Exponential**: Always use exponential notation. (e.g. `1.000001e5`)
-   **Engineering**: Exponential notation with exponent a multiple of 3. (e.g. `100.0001e3`)
-   **Formatted**: Forces a specific type of formatted notation.
    -   Style 1: `100,000.1`
    -   Style 2: `100.000,1`
    -   Style 3: `100 000,1`
    -   Style 4: `1,00,000.1`

## Installation

[](https://github.com/gtg922r/obsidian-numerals#installation)

*Numerals* can be found in the Obsidian community plugin list.

### Using BRAT

[](https://github.com/gtg922r/obsidian-numerals#using-brat)

To try the latest features of *Numerals* before they are released, and provide helpful feedback and testing, try *Numerals* by using the [Obsidian BRAT plugin](https://github.com/TfTHacker/obsidian42-brat). **All new *Numerals* features will be pushed to beta testers first.**

1.  Ensure BRAT is installed
2.  Trigger the command `Obsidian42 - BRAT: Add a beta plugin for testing`
3.  Enter this repository, `gtg922r/obsidian-numerals`
4.  Activate *Numerals* plugin in community plugin list

## Features in progress and roadmap

[](https://github.com/gtg922r/obsidian-numerals#features-in-progress-and-roadmap)

-   Support for mapping currency symbols to different currencies ([#17](https://github.com/gtg922r/obsidian-numerals/issues/17)) both `$` and `¥` can be mapped to different currencies in settings
-   Style Settings support for all colors and other style options ([#13](https://github.com/gtg922r/obsidian-numerals/issues/13))
    -   Partial support added in 1.0.5
-   Result annotation, similar to Calca feature ([#4](https://github.com/gtg922r/obsidian-numerals/issues/4))
    -   Support added in 1.0.5
-   Autocompletion of functions and variable inside math code block ([#15](https://github.com/gtg922r/obsidian-numerals/issues/15))
    -   Support added in 1.0.8
-   Inline calculation for inline code blocks ([#5](https://github.com/gtg922r/obsidian-numerals/issues/5))

Feel free to suggest additional features by creating an [issue](https://github.com/gtg922r/obsidian-numerals/issues)!

## Related

[](https://github.com/gtg922r/obsidian-numerals#related)

There are a number of other plugins that address math and calculation use cases in Obsidian.

-   If you are primarily interested in evaluating math expressions and inserting the result into your notes, look into [meld-cp/obsidian-calc](https://github.com/meld-cp/obsidian-calc)
-   If you are looking for a full-featured Computer Algebra System including plots and with similar code block rendering, consider [Canna71/obsidian-mathpad: Computer Algebra System (CAS) for Obsidian.md](https://github.com/Canna71/obsidian-mathpad)

There are also a number of "calculator as notes" apps that acted as the inspiration for *Numerals*. If you are looking for a purpose-built app outside of Obsidian, consider:

-   [Numi. Beautiful calculator app for Mac.](https://numi.app/)
-   [Numbr](https://numbr.dev/)
-   [Soulver 3 - Notepad Calculator App for Mac](https://soulver.app/)