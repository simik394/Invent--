---
page-title: "sytone/obsidian-queryallthethings: Query all your data stored in Obsidian, this plugin allows SQL based queries against the data collections available in Obsidian and Dataview. Output can then be rendered by Handlebars"
url: https://github.com/sytone/obsidian-queryallthethings
date: "2024-01-18 08:30:05"
tags: A/sw/plugin
purpose:
extends: "[[Obsidian]]"
---

## Query All The Things

 [![](https://camo.githubusercontent.com/97580aead5d859df950188e88e550d6ea717a89d18b3886b7a78ccb62c06a2e8/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6d616e69666573742d6a736f6e2f762f7379746f6e652f6f6273696469616e2d7175657279616c6c7468657468696e67733f636f6c6f723d626c7565)](https://github.com/sytone/obsidian-queryallthethings/releases/latest)[![](https://camo.githubusercontent.com/def48390aeab5067ef3937c92af0ecc2b0bd49d82acf5ffe039ed76cd32d90d4/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f72656c656173652d646174652f7379746f6e652f6f6273696469616e2d7175657279616c6c7468657468696e6773)](https://camo.githubusercontent.com/def48390aeab5067ef3937c92af0ecc2b0bd49d82acf5ffe039ed76cd32d90d4/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f72656c656173652d646174652f7379746f6e652f6f6273696469616e2d7175657279616c6c7468657468696e6773) [![](https://camo.githubusercontent.com/1a381258fa0aa511d73174053e59c545fc57b94d81819d2e94994c1d65c4ca86/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6c6963656e73652f7379746f6e652f6f6273696469616e2d7175657279616c6c7468657468696e6773) ](https://github.com/sytone/obsidian-queryallthethings/blob/main/LICENSE)[![](https://camo.githubusercontent.com/6ec1128e72ef8e645e6bf551410766fb96e21d101937788e274a58c62750b453/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f646f776e6c6f6164732f7379746f6e652f6f6273696469616e2d7175657279616c6c7468657468696e67732f746f74616c)](https://camo.githubusercontent.com/6ec1128e72ef8e645e6bf551410766fb96e21d101937788e274a58c62750b453/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f646f776e6c6f6164732f7379746f6e652f6f6273696469616e2d7175657279616c6c7468657468696e67732f746f74616c) [![](https://camo.githubusercontent.com/b7a25c57f4646fd5e507d987a2dd5957f3fec920f6462daa78c3ed8324f4012f/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6973737565732f7379746f6e652f6f6273696469616e2d7175657279616c6c7468657468696e6773)](https://github.com/sytone/obsidian-queryallthethings/issues)

***Execute flexible SQL base queries against your data in [Obsidian](https://obsidian.md/) and render it how you want using Handlebars templates.***

---

## Features

-   Use SQL based queries that are extensible and handle JSON and objects.
-   Query any data collection found in the Obsidian API.
-   Query data stored in DataView as well as cached view of DataView Data like tasks.
-   Render using handlebar templates in HTML or Markdown
-   Use custom handle bar helpers and/or provide your own.

---

## Roadmap and Issues

Look at the [Qatt Project](https://github.com/users/sytone/projects/4) to see what is in progress or planned. Please make a issue if you have a problem or want to add/request a new feature. Open to PRs at any point.

---

## Getting started

Documentation on installing the plugin and using it can be found at [https://sytone.github.io/obsidian-queryallthethings/](https://sytone.github.io/obsidian-queryallthethings/)

## Getting Started - I don't need documentation

Well, in short after you have installed the plugin make a code block like the following example, this will list all your tasks that are not done and group them by the month when they are due.

If you want more details.... Read the documentation, or reverse engineer the code base. Your Choice!

Note: This plugin currently has a soft dependency on DataView, make sure it is installed if you want to use the dataview backed tables.

\`\`\`qatt
query: |
  SELECT TOP 5 \* FROM obsidian\_markdown\_notes ORDER BY stat->mtime DESC
template: |
  {{#each result}}
   - \[\[{{path}}\\|{{basename}}\]\]
  {{/each}}
\`\`\`

---