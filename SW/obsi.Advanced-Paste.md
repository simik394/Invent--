---
page-title: "kxxt/obsidian-advanced-paste: Advanced pasting functionality for obsidian"
url: https://github.com/kxxt/obsidian-advanced-paste
date: "2024-01-18 08:20:58"
tags: A/sw/plugin
purpose:
extends: "[[Obsidian]]"
---

## Advanced Paste for Obsidian

[![Sponsor](https://camo.githubusercontent.com/eaf3d0a70f9f01bdeb7cd725171cc31c6158aa4ec957fbda0cd52a6d00ff5f3a/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f73706f6e736f722d76696125323070617970616c2d626c7565)](https://www.paypal.com/paypalme/tokxxt) [![License](https://camo.githubusercontent.com/a9e628e055272bcd0a0e07564124407f1d008e51ef7364c494e7d85cc756eda5/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6c6963656e73652f6b7878742f6f6273696469616e2d616476616e6365642d7061737465)](https://camo.githubusercontent.com/a9e628e055272bcd0a0e07564124407f1d008e51ef7364c494e7d85cc756eda5/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6c6963656e73652f6b7878742f6f6273696469616e2d616476616e6365642d7061737465) [![GitHub manifest version](https://camo.githubusercontent.com/812259cb3c94ac3fb23acb48a2d8310edfaf41cf16472bbf8823e718818188e0/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6d616e69666573742d6a736f6e2f762f6b7878742f6f6273696469616e2d616476616e6365642d7061737465)](https://camo.githubusercontent.com/812259cb3c94ac3fb23acb48a2d8310edfaf41cf16472bbf8823e718818188e0/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6d616e69666573742d6a736f6e2f762f6b7878742f6f6273696469616e2d616476616e6365642d7061737465)

This plugin provides advanced paste commands and enables you to create custom transforms for pasting.

Usage: Assign a hotkey to the command that you want to use and then press the hotkey to paste the content.

Personally, I prefer to assign Alt+V to [`Smart Join`](https://github.com/kxxt/obsidian-advanced-paste#smart-join) and Alt+Shift+V to [`Remove Blank Lines`](https://github.com/kxxt/obsidian-advanced-paste#remove-blank-lines).

> **Warning** Never add untrusted scripts to the script directory BECAUSE IT MIGHT DESTROY YOUR VAULT OR WORSE!

**You need to disable and re-enable this plugin in order to apply the changes to the script directory.**

## Features

## Default

This plugin provides a default transform that is better than Obsidian built-in. You can disable it in the plugin settings (You need to restart obsidian to apply the changes).

It is compatible with the [auto link title plugin](https://github.com/zolrath/obsidian-auto-link-title) but might not be compatible with some other plugins that mess with the clipboard.

**If you have bind Ctrl+V to this command previously, you should unbind it because the underlying mechanism has changed.**

The default transform will convert html to markdown using [turndown](https://github.com/mixmark-io/turndown) and [turndown-plugin-gfm](https://github.com/mixmark-io/turndown-plugin-gfm). And it will remove empty headings and links.

[![Showcase](https://github.com/kxxt/obsidian-advanced-paste/raw/master/images/remove-empty-links.gif)](https://github.com/kxxt/obsidian-advanced-paste/blob/master/images/remove-empty-links.gif)

### TODO

-   try to eliminate the extra blank lines in the converted markdown.

## Smart Join

This command trims all the lines and join them by a space before pasting. It will automatically join the words that are broken by hyphens.

This command is especially useful when pasting from a PDF file.

## Join Lines

This command joins all the lines without trimming them before pasting.

## Remove Blank Lines

This command removes all the blank lines before pasting.

This command is useful when you copy something from a web page and you find that there are too many blank lines when directly pasting into obsidian.

## Raw HTML

This command pastes the raw HTML of the copied content.

## Custom Transforms

You can define your own custom transform by writing JavaScript.

1.  Set your script directory in the settings of this plugin (Or stick to the default settings).
2.  Create a JavaScript source file(`*.js` or `*.mjs`) in the script directory. (You can't do it in obsidian. You need an editor like VSCode)
3.  Edit the JavaScript file to add your custom transform(s).
4.  Disable this plugin and re-enable it to apply your changes.
5.  Now you can find your custom transform in command platte and assign a hotkey to it.

## Creating Custom Transforms

The JavaScript source file will be imported as an ES Module.

To create a transform, you need to create an exported function:

export function myTransform(input) {
    return input;
}

The function name (in start case) will become the name of your custom transform.

You can write multiple transforms in a single JavaScript source file.

By default, the input to your transform is the text in the clipboard. To support other MIME types, you can set the `type` field of your transform to `"blob"`:

export async function myBlobTransform(input) {
    if (!input.types.includes("text/html")) {
        return { kind: "err", value: "No html found in clipboard!" };
    }
    const html \= await input.getType("text/html");
    return html.text();
}
myBlobTransform.type \= "blob";

This way, the input to your transform is a [`ClipboardItem`](https://developer.mozilla.org/en-US/docs/Web/API/ClipboardItem) instead of a `string`.

Your transform function should return either a `string` or a `TransformResult` (Of course, you can also return a `Promise` that resolves to one of them).

A `TransformResult` is a discriminated union. Its kind can only be `ok` or `err`. When you return an `ok` variant from your transform function, the `value` field should be the string of your final transformation result. When you return an `err` variant, a notice, in which the `value` field will be displayed as an error to the end user, will show up.

{ kind: "ok", value: "string" }
{ kind: "err", value: "An error occurred!" }

## Advanced: Utilities

The transform function can take an optional second parameter `utils` which is an object containing some useful helpers.

Currently, the [turndown service](https://github.com/mixmark-io/turndown) is provided as a utility. You can call `turndown.turndown` to convert html to markdown.

You can call `saveAttachment` to save a blob to the vault. The function signature is:

saveAttachment: (name: string, ext: string, data: ArrayBuffer) \=>
    Promise<TFile\>;

If you need more information about or control over the editor state, the [Obsidian `editor` object](https://docs.obsidian.md/Plugins/Editor/Editor) is provided as a utility.

`lodash`, `moment.js` and `mime` are also provided as utilities. Check out the following example:

export async function myTransform(
    input,
    { turndown, editor, \_, moment, mime, saveAttachment }
) {
    if (input.types.includes("text/html")) {
        const html \= await input.getType("text/html");
        return turndown.turndown(await html.text());
    }
    const text \= await input.getType("text/plain");
    return text.text();
}
myTransform.type \= "blob";

`remark` and `remark` plugins are also provided as utilities, which enables you to transform a Markdown AST. Check out the following example that removes all the images before pasting:

export async function noImage(
    input,
    {
        turndown,
        remark: {
            remark,
            remarkGfm,
            remarkMath,
            unistUtilVisit: { visit, SKIP },
        },
    }
) {
    if (input.types.includes("text/html")) {
        const html \= await input.getType("text/html");
        const md \= turndown.turndown(await html.text());
        return remark()
            .use(remarkGfm)
            .use(remarkMath)
            .use(() \=> (tree, file) \=> {
                visit(tree, "image", (node, index, parent) \=> {
                    parent.children.splice(index, 1);
                    return \[SKIP, index\];
                });
            })
            .processSync(md)
            .toString();
    }
    return { kind: "err", value: "No html found in clipboard!" };
}
noImage.type \= "blob";

For now, the following remark related utilities are provided:

remark: {
    unified: typeof import("unified").unified;
    remark: typeof import("remark").remark;
    remarkGfm: typeof import("remark-gfm").default;
    remarkMath: typeof import("remark-math").default;
    remarkParse: typeof import("remark-parse").default;
    remarkStringify: typeof import("remark-stringify").default;
    unistUtilVisit: typeof import("unist-util-visit");
    unistUtilIs: typeof import("unist-util-is");
}

If you need more utilities, feel free to open an issue or submit a PR.