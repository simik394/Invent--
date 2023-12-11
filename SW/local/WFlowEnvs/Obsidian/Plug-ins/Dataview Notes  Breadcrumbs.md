---
created: 2023-12-11T22:56:06 (UTC +01:00)
tags: []
source: https://breadcrumbs-wiki.onrender.com/docs/Alternative%20Hierarchies/Dataview%20Notes
author: 
---

# Dataview Notes | Breadcrumbs

> ## Excerpt
> Dataview Notes

---
A _Dataview Note_ allows you to run any valid [Dataview `from` query](https://blacksmithgu.github.io/obsidian-dataview/query/sources/), and add Breadcrumbs to all notes that match the query.

The query must be wrapped in quotes, and folder names must be wrapped in **double** quotes. Therefore, to avoid confusing Yaml, you need to wrap the entire query in single quotes, so that folders can be wrapped in double quotes.

The query is passed directly into the Dataview API, so you can troubleshoot it by running `app.plugins.plugins.dataview.api.pages(query: string)` in the Obsidian console

For example, to automatically mark all notes link to note A as their parent, you can use:

```
<span data-darkreader-inline-color=""><span data-darkreader-inline-color="">---</span><span></span><br></span><span data-darkreader-inline-color=""><span></span><span data-darkreader-inline-color="">BC-dataview-note</span><span data-darkreader-inline-color="">:</span><span> </span><span data-darkreader-inline-color="">"[[A]]"</span><span></span><br></span><span data-darkreader-inline-color=""><span></span><span data-darkreader-inline-color="">BC-dataview-note-field</span><span data-darkreader-inline-color="">:</span><span> parent</span><br></span><span data-darkreader-inline-color=""><span></span><span data-darkreader-inline-color="">---</span><br></span>
```
