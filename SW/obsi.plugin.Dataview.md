---
purpose:
  - view
  - search
---

# Community sources
## .troubleshooting
[Troubleshooting a Dataview field - Help - Obsidian Forum](https://forum.obsidian.md/t/troubleshooting-a-dataview-field/41162/3)

## .cheatsheets
[obsidian-dataview-cheatsheet/README.md at main · seburbandev/obsidian-dataview-cheatsheet (github.com)](https://github.com/seburbandev/obsidian-dataview-cheatsheet/blob/main/README.md)

## .queries
### ..list specific callouts
[Trying to retrieve Callout with DataView - Help - Obsidian Forum](https://forum.obsidian.md/t/trying-to-retrieve-callout-with-dataview/40312/15)

[Extract the contents of callout boxes from daily notes](https://share.note.sx/1f2nsian)

# Tests
```dataview
list tested
from [[obsi.plugin.Dataview]]
where tested
```

# Samples
## List text list itemů s parametrem key
```dataviewjs
dv.list(dv.pages('"myDM/Experiments"')
	.file.lists
	.where(t => t.text.includes("key::"))
	.text)
```
# Documentation
[[obsi.plugin.dataview.doc.official]]


