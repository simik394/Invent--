---
page-title: "nothingislost/obsidian-query-control: An experimental Obsidian plugin that adds controls to embedded queries"
url: https://github.com/nothingislost/obsidian-query-control
date: 2024-01-16 17:35:35
purpose:
  - view
extends:
  - "[[Obsidian]]"
tags:
  - A/sw/plugin
---

> This plugin adds additional functionality to Obsidian's [search/query](https://help.obsidian.md/Plugins/Search) feature. The current version will add a control bar to each embedded query with various actions such as: collapse all, show context, sort, hide title, hide results, render markdown, and copy results.
> 
> Controls are added to embedded queries in Live Preview and Reading modes.
> 
> Each of the controls have defaults which can be defined in the plugin settings tab. So, if you wanted all embedded queries to render collapsed by default, you would go into the settings and change that default.
> 
> If you want to configure the controls on a per embedded query basis, this plugin implements an extended query syntax which allows for this. The full syntax looks like this:
> 
> ````
> ```query
> path: foo tag:#obsidian
> title: custom query name
> collapsed: true | false
> context: true | false
> hideTitle: true | false
> hideResults: true | false
> renderMarkdown: true | false
> sort: alphabetical | alphabeticalReverse | byModifiedTime | byModifiedTimeReverse | byCreatedTime | byCreatedTimeReverse
> ```
> ````
> 
> Each of the extended keys are optional. If a key is not provided, the configured default will be used instead.
> 
> Install the BRAT plugin via the Obsidian Plugin Browser and then add the beta repository "nothingislost/obsidian-embedded-query-control"
