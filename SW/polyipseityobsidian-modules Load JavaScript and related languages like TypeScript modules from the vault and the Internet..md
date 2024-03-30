---
page-title: "polyipseity/obsidian-modules: Load JavaScript and related languages like TypeScript modules from the vault and the Internet."
url: https://github.com/polyipseity/obsidian-modules
date: "2024-03-20 14:42:21"
tags: 
- A/sw/plugin
- F/homepage
- C/
- P/
about: "[[Obsidian]]"
aliases: 
- 377de7ea-17e8-4584-a9ad-20eb6c6e43ef
- polyipseity/obsidian-modules: Load JavaScript and related languages like TypeScript modules from the vault and the Internet.
by: 
length: 8644
dir: 
---

Load JavaScript and related languages like TypeScript modules from the vault and the Internet.

[![Buy Me a Coffee/embed](https://camo.githubusercontent.com/965824d071718f69c905bca28be1d126ae0e42438cf8af10e049a55809302c6c/68747470733a2f2f696d672e6275796d6561636f666665652e636f6d2f627574746f6e2d6170692f3f746578743d4275792532306d6525323061253230636f6666656526656d6f6a693d26736c75673d706f6c796970736569747926627574746f6e5f636f6c6f75723d34304443413526666f6e745f636f6c6f75723d66666666666626666f6e745f66616d696c793d4c61746f266f75746c696e655f636f6c6f75723d30303030303026636f666665655f636f6c6f75723d464644443030)](https://buymeacoffee.com/polyipseity)

**[Repository](https://github.com/polyipseity/obsidian-modules) · [Changelog](https://github.com/polyipseity/obsidian-modules/blob/main/CHANGELOG.md) · [Community plugin](https://obsidian.md/plugins?id=modules) · [Other things](https://github.com/polyipseity/obsidian-monorepo) · [Features](https://github.com/polyipseity/obsidian-modules#features) · [Installation](https://github.com/polyipseity/obsidian-modules#installation) · [Usage](https://github.com/polyipseity/obsidian-modules#usage) · [Contributing](https://github.com/polyipseity/obsidian-modules#contributing) · [Security](https://github.com/polyipseity/obsidian-modules#security)**

[![Trailer](https://raw.githubusercontent.com/polyipseity/obsidian-modules/main/assets/trailer.png)](https://raw.githubusercontent.com/polyipseity/obsidian-modules/main/assets/trailer.png)

For first time users, read the [installation](https://github.com/polyipseity/obsidian-modules#installation) section first!

This file is automatically opened on first install. You can reopen it in settings or command palette.

## Features

[](https://github.com/polyipseity/obsidian-modules#features)

-   Load JavaScript and TypeScript modules from the vault and the Internet on all platforms.
-   Load modules at startup.
-   No configuration needed.
-   Resolves relative paths, vault paths, Markdown links, wikilinks, and external links.
-   Loads Markdown files as code.
-   Supports using other modules inside modules.
-   Loads CommonJS (`module.exports`) and ES modules (`export`).
-   Supports circular dependencies for CommonJS modules.
-   Configurable require name.
-   Adds source maps for debugging.
-   Supports popular plugins like Dataview and Templater.

## Installation

[](https://github.com/polyipseity/obsidian-modules#installation)

1.  Install plugin.
    -   Community plugins
        1.  Install the [plugin](https://obsidian.md/plugins?id=modules) from community plugins directly.
    -   Manual
        1.  Create directory `modules` under `.obsidian/plugins` of your vault.
        2.  Place `manifest.json`, `main.js`, and `styles.css` from the [latest release](https://github.com/polyipseity/obsidian-modules/releases/latest) into the directory.
    -   Building (latest)
        1.  Clone this repository, including its submodules.
        2.  Install [npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm).
        3.  Run `npm install` in the root directory.
        4.  Run `npm run obsidian:install <vault directory>` in the root directory.
    -   [Obsidian42 - BRAT](https://obsidian.md/plugins?id=obsidian42-brat) (latest)
        -   See [their readme](https://github.com/TfTHacker/obsidian42-brat#readme).
2.  Enable plugin.
3.  (optional) Configure plugin settings.

## Usage

[](https://github.com/polyipseity/obsidian-modules#usage)

-   Enable the plugin.
-   To import a module:

// Using \`require.import\` is recommended.
await self.require.import("obsidian") // builtin modules such as the Obsidian API
await self.require.import("vault/path/to/a module.md") // vault path
// The following three require context and may not be able to infer the current directory. Please file an issue if so. Context inference is only available for top-level code, i.e. not inside functions or classes.
await self.require.import("../relative/path/to/a module.js") // relative path
await self.require.import("\[omitted or whatever\](markdown/link/to/a%20module.js.md)") // Markdown link
await self.require.import("\[\[wikilink/to/a module|ommited or whatever\]\]") // wikilink
// The following one requires enabling external links in settings.
await self.require.import("https://esm.sh/scratchblocks") // external link
// You can workaround the inability to infer the current directory.
await self.require.import("../relative/path/to/a module.js", { cwd: context.currentDirectory })

// If \`await\` is not supported, use \`require\` instead. It has less support for loading modules, however.
self.require("obsidian")
self.require("vault/path/to/a module.md")
// The following three require context and may not be able to infer the current directory. Please file an issue if so. Context inference is only available for top-level code, i.e. not inside functions or classes.
self.require("../relative/path/to/a module.js")
// The following three may not work in startup scripts.
self.require("\[ommited or whatever\](markdown/link/to/a%20module.js.md)")
self.require("\[\[wikilink/to/a module|omitted or whatever\]\]")
// The following one requires enabling external links and adding the link to preloaded external links in settings.
self.require("https://esm.sh/scratchblocks") // external link
// You can workaround the inability to infer the current directory.
self.require("../relative/path/to/a module.js", { cwd: context.currentDirectory })

-   To use entities in a module:

const { eat, pi } \= await self.require.import("\[\[module\]\]")
eat(2 \* pi)
// OR
const mod \= await self.require.import("\[\[module\]\]")
mod.eat(2 \* mod.pi)

-   To create a module, create a JavaScript or related language file or a Markdown file with JavaScript or related language code blocks.
    -   For `require` (but not `require.import`), the module file needs to be preloaded, which can be configured in settings. By default, preloaded files have the following extensions: `.js`, `.js.md`, `.mjs`, `.mjs.md`, `.ts.md`, `.mts.md`, `.ts`, `.ts.md`
    -   Modules should not have global or side effects because they are cached and thus not reloaded on every requiring.
    -   For Markdown files, code block languages that are loaded can be configured in settings.
    -   For non-JavaScript languages, ensure the module file has the correct file extension (also applies to `.xxx.md`) or prepend the following metadata:

// { "language": "TypeScript" }

export const variable: string \= "string"

\---
module:
  language: TypeScript
\---

\`\`\`TypeScript
export const variable: string \= "string"
\`\`\`

-   Module exports can be CommonJS-style or ES module-style:

// ES module-style, supported by \`require.import\`.
export function fun() {}
export const variable \= "string"
export default 42 // The default export has the name \`default\`.

// CommonJS-style, supported by both \`require\` and \`require.import\`.
module.exports.fun \= function() {}
module.exports.variable \= "string"
module.exports.default \= 42
exports.abbreviatedForm \= {}

-   To create a startup module, export a function (supports async) to run at startup using `export default` or assigning to `module.exports` and add the module to plugin settings:

// ES module-style
export default function() {
    console.log("Hello world!")
}

// CommonJS-style
module.exports \= function() {
    console.log("Hello world!")
}

-   The full API is available from [`sources/@types/obsidian-modules.ts`](https://github.com/polyipseity/obsidian-modules/blob/main/sources/%40types/obsidian-modules.ts).

## Contributing

[](https://github.com/polyipseity/obsidian-modules#contributing)

Contributions are welcome!

This project uses [`changesets`](https://github.com/changesets/changesets) to manage the changelog. When creating a pull request, please [add a changeset](https://github.com/changesets/changesets/blob/main/docs/intro-to-using-changesets.md#adding-changesets) describing the changes. Add multiple changesets if your pull request changes several things. End each changeset with `([PR number](PR link) by [author username](author link))`. For example, the newly created file under the directory `.changeset` should look like:

\---
"example": patch
\---

This is an example change. (\[GH#1\](https://github.com/ghost/example/pull/1) by \[@ghost\](https://github.com/ghost))

### Todos

[](https://github.com/polyipseity/obsidian-modules#todos)

The todos here, ordered alphabetically, are things planned for the plugin. There are no guarantees that they will be completed. However, we are likely to accept contributions for them.

-   User-defined module aliases.
-   Add bare module transformation support for more CDNs such as [https://cdn.jsdelivr.net](https://cdn.jsdelivr.net/).
-   Faster import analysis and transformation.
-   Autocomplete with JSDoc.

### Translating

[](https://github.com/polyipseity/obsidian-modules#translating)

Translation files are under [`assets/locales/`](https://github.com/polyipseity/obsidian-modules/blob/main/assets/locales). Each locale has its own directory named with its corresponding **[IETF language tag](https://wikipedia.org/wiki/IETF_language_tag)**. Some translation keys are missing here and instead located at [`obsidian-plugin-library`](https://github.com/polyipseity/obsidian-plugin-library).

To contribute translation for an existing locale, modify the files in the corresponding directory.

For a new locale, create a new directory named with its language tag and copy [`assets/locales/en/translation.json`](https://github.com/polyipseity/obsidian-modules/blob/main/assets/locales/en/translation.json) into it. Then, add an entry to [`assets/locales/en/language.json`](https://github.com/polyipseity/obsidian-modules/blob/main/assets/locales/en/language.json) in this format:

{
    // ...
    "en": "English",
    "(your-language-tag)": "(Native name of your language)",
    "uwu": "Uwuish",
    // ...
}

Sort the list of languages by the alphabetical order of their language tags. Then modify the files in the new directory. There will be errors in [`assets/locales.ts`](https://github.com/polyipseity/obsidian-modules/blob/main/assets/locales.ts), which you can ignore and we will fix them for you. You are welcome to fix them yourself if you know TypeScript.

When translating, keep in mind the following things:

-   Do not translate anything between `{{` and `}}` (`{{example}}`). They are **interpolations** and will be replaced by localized strings at runtime.
-   Do not translate anything between `$t(` and `)` (`$t(example)`). They refer to other localized strings. To find the localized string being referred to, follow the path of the key, which is separated by dots (`.`). For example, the key [`youtu.be./dQw4w9WgXcQ`](https://youtu.be./dQw4w9WgXcQ) refers to:

{
    // ...
    "youtu": {
        // ...
        "be": {
            // ...
            "/dQw4w9WgXcQ": "I am 'youtu.be./dQw4w9WgXcQ'!",
            // ...
        },
        // ...
    },
    // ...
}

-   The keys under `generic` are vocabularies. They can be referred in translation strings by `$t(generic.key)`. Refer to them as much as possible to standardize translations for vocabularies that appear in different places.
-   It is okay to move interpolations and references to other localized strings around to make the translation natural. It is also okay to not use some references used in the original translation. However, it is NOT okay to not use all interpolations.

## Security

[](https://github.com/polyipseity/obsidian-modules#security)

We hope that there will never be any security vulnerabilities, but unfortunately it does happen. Please [report](https://github.com/polyipseity/obsidian-modules#reporting-a-vulnerability) them!

### Supported versions

[](https://github.com/polyipseity/obsidian-modules#supported-versions)

Version

Supported

latest

✅

outdated

❌

### Reporting a vulnerability

[](https://github.com/polyipseity/obsidian-modules#reporting-a-vulnerability)

Please report a vulerability by opening an new issue. We will get back to you as soon as possible.