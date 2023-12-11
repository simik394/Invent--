# Template Cheatsheet – ZotLit
Clipped from: [https://zotlit.aidenlx.top/how-to/template-cheatsheet](https://zotlit.aidenlx.top/how-to/template-cheatsheet)  
How-To Guide  
Template Cheatsheet  
Leave your common usage in the comment section below and we will add them to the list.  
## Authors  
### Get author shorthand  
Note Properties  
authors: \<%= it.authorsShort %&gt;  
It will be rendered like Gerasimavicius et al..  
### Get author shorthand in annotation template  
Info about parent literature are stored in it.docItem.  
Note Annotation  
from \<%= it.docItem.authorsShort %&gt;  
### Get List of Authors in Full Names  
Note Properties  
authors: \[\<%= it.authors %&gt;]  
### Get List of Authors in first name or last name  
Note Properties  
authors: \[\<%= it.authors.map(v =&gt; v.firstName) %&gt;]  
# or  
authors: \[\<%= it.authors.map(v =&gt; v.lastName) %&gt;]  
💡  
Do note that first name and last name are not always available.  
## Abstract  
### Get abstract in a single paragraph  
Note Content  
\## Abstract  
  
\<%= it.abstractNote.first().replace(/\[\r\n]+/g, " ") %&gt;  
## Tags  
### Include only manually created tags  
To include only manually created tags, not the ones retrieved from literature, use the following code:  
Note Properties  
tags: \[\<%= it.tags.filter(t =&gt; t.type === 0) %&gt;]  
This is the default behavior before the change in v1.1.0.  
💡  
In Zotero, manually created tags have value 0, while the ones retrieved from literature have value 1.  
## Date  
### Get when the literature was imported to Zotero  
Note Properties  
import-date: \<%= it.dateAccessed %&gt;  
### Get publish date  
Note Properties  
publish-date: \<%= it.date %&gt;  
## Collections  
### Get collections  
Note Properties  
collections: \[\<%= it.collections %&gt;]  
### Get collection with full path  
Note Properties  
collections: \[\<%= it.collections.map(c =&gt; c.path) %&gt;]  
By default, the collection path is separated by &gt;, output like Collection 1 &gt; Collection 2 &gt; Collection 3. You can customize the separator by using join function.  
The following code will output A/B/C, similar to multi-level tags in Obsidian:  
Note Properties  
collections: \[\<%= it.collections.map(c =&gt; c.path.join("/")) %&gt;]  
### Get top-level collections  
Note Properties  
top-collections: \[\<%= \[...new Set(it.collections.map(c =&gt; c.path\[0]))] %&gt;]  
## Grouping  
For details, see [Object.groupBy (opens in a new tab)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/groupBy) and <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/groupBy">Map.groupBy (opens in a new tab)</a>.  
### Group by annotation color  
Note Annotations  
\<% const byColor = Object.groupBy(it, (annot) =&gt; annot.colorName);   
for (const color in byColor) { -%&gt;  
  
## \<%= color %&gt;  
  \<%_ for (const annot of byColor\[color]) { %&gt;  
  
\<%~ include("annotation", annot) %&gt;  
  \<%_ } %&gt;  
\<% } %&gt;  
### Group by annotation color, customized label  
Note Annotations  
\<% const byColor = Object.groupBy(it, (annot) =&gt; annot.colorName);  
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
const colorSet = new Set(\[...Object.keys(label), ...Object.keys(byColor)]);  
for (const color of colorSet) {   
if (!(color in byColor)) continue -%&gt;  
  
### \<%= label\[color] ?? color %&gt;  
  \<%_ for (const annot of byColor\[color]) { %&gt;  
  
\<%~ include("annotation", annot) %&gt;  
  \<%_ } %&gt;  
\<% } %&gt;  
Last updated on September 11, 2023  
[Inserting Citations](https://zotlit.aidenlx.top/getting-started/basic-usage/citation-insertion)<a href="https://zotlit.aidenlx.top/faq/slurp">Extra Lines in the Template Output</a>  

