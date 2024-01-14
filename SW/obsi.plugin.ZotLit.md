---
tags: 
---

[obsidian link](obsidian://show-plugin?id=zotlit)
# README
[obsidian-zotlit/README.md at master · PKM-er/obsidian-zotlit (github.com)](https://github.com/PKM-er/obsidian-zotlit/blob/master/README.md)

# Docs
[Introduction – ZotLit (aidenlx.top)](https://zotlit.aidenlx.top/)

# Template cheatsheet
## Grouping[](https://zotlit.aidenlx.top/how-to/template-cheatsheet#grouping)

For details, see [Object.groupBy(opens in a new tab)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/groupBy) and [Map.groupBy(opens in a new tab)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/groupBy).

### Group by annotation color[](https://zotlit.aidenlx.top/how-to/template-cheatsheet#group-by-annotation-color)

```

Note Annotations

<% const byColor = Object.groupBy(it, (annot) => annot.colorName); 
for (const color in byColor) { -%>

## <%= color %>
  <%_ for (const annot of byColor[color]) { %>

<%~ include("annotation", annot) %>
  <%_ } %>
<% } %>
```

### Group by annotation color, customized label[](https://zotlit.aidenlx.top/how-to/template-cheatsheet#group-by-annotation-color-customized-label)

Note Annotations

```
<% const byColor = Object.groupBy(it, (annot) => annot.colorName);
const label = {
  "red": "Important",
  "orange": "Question",
  "yellow": "Summary",
  "gray": "Comment",
  "green": "Answer",
  "cyan": "Task",
  "blue": "Fact",
  "navy": "Definition",
  "purple": "Quote",
  "brown": "Source",
  "magenta": "To Do",
};
// Merge colors with customized label with unexpected colors, if any
// Keep the order of the colors from the original color-label map
const colorSet = new Set([...Object.keys(label), ...Object.keys(byColor)]);
for (const color of colorSet) { 
if (!(color in byColor)) continue -%>

### <%= label[color] ?? color %>
  <%_ for (const annot of byColor[color]) { %>

<%~ include("annotation", annot) %>
  <%_ } %>
<% } %>
```