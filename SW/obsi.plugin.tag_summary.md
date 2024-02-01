
# 1N
[obsi.plugin.tag_summary.test.settings](onenote:https://d.docs.live.net/a3e7ec4e2a2bbe83/Documents/OneNote%20Notebooks/Projects/BP/latest.one#obsi.plugin.tag_summary.test.settings&section-id={CA37B6A0-3ECD-407A-AB93-01DEFA2ADAEA}&page-id={F5FF5779-937F-4DD1-87AB-57BA0571414F}&end)  ([Web view](https://onedrive.live.com/view.aspx?resid=A3E7EC4E2A2BBE83%2150469&id=documents&wd=target%28BP%2Flatest.one%7CCA37B6A0-3ECD-407A-AB93-01DEFA2ADAEA%2Fobsi.plugin.tag_summary.test.settings%7CF5FF5779-937F-4DD1-87AB-57BA0571414F%2F%29))

# README
# Tag Summary

This is a plugin for [Obsidian](https://obsidian.md/).

Tag Summary creates summaries with paragraphs or blocks of text that share the same tag(s). This plugin scans your files looking for blocks of text (text separated by empty lines) and creates a summary with all the blocks that contain the specified tag(s). For example, if you have the following paragraphs in your notes:

```
Monsters are real, and ghosts are real too. They live inside us, and sometimes, they win.
#chapter1
```

```
People think that I must be a very strange person. This is not correct. I have the heart of a small boy. It is in a glass jar on my desk.
#crazy
```

```
Great minds discuss ideas; average minds discuss events; small minds discuss people.
#chapter1 #crazy
```

```
You can create summaries with the paragraphs that include the [#chapter1](app://obsidian.md/index.html#chapter1) and [#crazy](app://obsidian.md/index.html#crazy) tags. For instance, if you create a summary with the [#chapter1](app://obsidian.md/index.html#chapter1) tag, the first and third paragraphs will be included, but if you create a summary with the [#crazy](app://obsidian.md/index.html#crazy) tag, the second and third paragraphs will be included instead.
```

## Add a Summary to a Note

Summaries are added to a note with a code block and the **add-summary** identifier. The tags are specified inside the code block with the **tags:** label, as shown next.

````markdown
```add-summary
tags: #chapter1
```
````

If you need to include blocks of texts with different tags, add the tags separated by a space, as shown next.

````markdown
```add-summary
tags: #chapter1 #crazy
```
````

A summary includes every block of text that contains any of the tags specified by the **tags:** label. In the last example, the summary will include the three paragraphs listed above, because each paragrah contains at least one of the tags specified by the label (#chapter1 OR [`#crazy`](app://obsidian.md/index.html#crazy)). If you want to include only the blocks of text that contain all the tags on the list, you can declare the **include:** label instead, as in the following example.

````markdown
```add-summary
include: #chapter1 #crazy
```
````

In this case, only the blocks of text that include both tags will be added to the summary. If you process the paragraphs listed above, only the third paragraph will be added to the summary because it is the only one that includes the `[#chapter1](app://obsidian.md/index.html#chapter1)` AND `[#crazy](app://obsidian.md/index.html#crazy)` tags. If what you want instead is to exclude the blocks of text that contain a specific tag(s), you can add the **exclude:** label, as shown next.

````markdown
```add-summary
tags: #chapter1
exclude: #crazy
```
````
```

This will add to the summary every block of text that includes the [#chapter1](app://obsidian.md/index.html#chapter1) tag but does NOT include the [#crazy](app://obsidian.md/index.html#crazy) tag. If you process the paragraphs listed above, only the first paragraph will be added to the summary. The **exclude:** label can be combined with the **tags:** and **include:** labels to specify complex conditions. The following example creates a summary with the blocks of text that include the [#chapter1](app://obsidian.md/index.html#chapter1) OR [#chapter2](app://obsidian.md/index.html#chapter2) tags and also contain both the [#chapter3](app://obsidian.md/index.html#chapter3) AND [#chapter4](app://obsidian.md/index.html#chapter4) tags, but do NOT contain the [#crazy](app://obsidian.md/index.html#crazy) tag.
```

````markdown
```add-summary
tags: #chapter1 #chapter2
include: #chapter3 #chapter4
exclude: #crazy
```
````

## Command to Add a Summary

The plugin includes the Add Summary command to add a summary to a note.

- Open the note where you want to include the summary.
- Move the cursor to the position where you want to add the summary.
- Press Command+P (Mac) or Control+P (Windows) to open the Command palette. (or drag down the note on a mobile device)
- Search for the **Tag Summary: Add Summary** command and click on it.
- On the popup window, select the tags you want to include and exclude to create the summary and press the Add Summary button.

After this, your note should include a code block like the examples above. The Add Summary command allows you to select only one tag to include and another to exclude, but you can manually add all the tags you want separated by a space, as in` **tags: [#chapter1](app://obsidian.md/index.html#chapter1) [#chapter2](app://obsidian.md/index.html#chapter2)**`.

## Summary Configuration

The plugin includes the following three options to configure the style of the summary.

- Show Callouts: Shows each block of text inside a callout box (default). If disabled, the blocks are displayed as plain text.
- Show Link: Includes a link at the top to open the note where the paragraph was taken from.
- Remove Tags: Removes the original tags from the text.

There are also two more options to determine how the plugin will process lists. If the options are enabled, the plugin will process each item of a list independently and include in the summary only the items that match the tags. If you want the plugin to process the entire list as a block of text, you can disable this options.

- List Items: Include only the items of a list that contain the tag(s), not the entire list.
- Include Child Items: Include the child items of a list.

## Usage

This plugin does not affect the way Obsidian, links, and tags work. You can still organize your notes the way you always do, but now you can assign tags to paragraphs, blocks of text, or items on a list, and then create summaries with those that include a specific list of tags.

When structuring your notes, please consider the following:

- The plugin considers a block of text to be all the text between empty lines. If you add an empty line in the middle of a paragraph or a block of text, the plugin will consider that as two different blocks.
- Tags can be specified in any position of the paragraph or block of text, even in a new line at the end, as long as there are no empty lines in between.

## Safety

This plugin does not modify the original notes, it doesn't download or upload any information to the web, and doesn't store or retrieve any private information.

## Disclaimer

This plugin comes with no guarantee of any kind, and neither the author nor Obsidian are responsible for any loss of data or inconvenience.  
Use this plugin at your own risk.

## From the Author

I created this plugin for personal use. I will try to post updates from time to time. If you find a bug, you can contact me through my website:  
[www.jdgauchat.com](https://www.jdgauchat.com/)