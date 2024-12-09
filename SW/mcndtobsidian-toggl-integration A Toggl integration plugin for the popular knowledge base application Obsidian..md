---
page-title: "mcndt/obsidian-toggl-integration: A Toggl integration plugin for the popular knowledge base application Obsidian."
url: https://github.com/mcndt/obsidian-toggl-integration
date: "2024-06-24 03:17:18"
tags: [a/sw/plugin, f/prod/homepage, c/, p/pwf]
about: ["[[Obsidian]]"]
aliases: 
- 
by: 
length: 2016
dir: 
---

[![GitHub tag (Latest by date)](https://camo.githubusercontent.com/a17ea2606e69ec581e2363e7865d1c079e857ab0d38e91de9faf7e0fe4e7a382/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f762f7461672f6d636e64742f6f6273696469616e2d746f67676c2d696e746567726174696f6e)](https://github.com/mcndt/obsidian-toggl-integration/releases) [![GitHub all releases](https://camo.githubusercontent.com/b879300ecbf6b771be20e9b8c2d149a5205ed6923334895685987bd2e82be614/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f646f776e6c6f6164732f6d636e64742f6f6273696469616e2d746f67676c2d696e746567726174696f6e2f746f74616c)](https://camo.githubusercontent.com/b879300ecbf6b771be20e9b8c2d149a5205ed6923334895685987bd2e82be614/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f646f776e6c6f6164732f6d636e64742f6f6273696469616e2d746f67676c2d696e746567726174696f6e2f746f74616c)

## Toggl Track Integration for Obsidian

[](https://github.com/mcndt/obsidian-toggl-integration#toggl-track-integration-for-obsidian)

Add integration with the Toggl Track API to manage your timers inside Obsidian.

## Functionality

[](https://github.com/mcndt/obsidian-toggl-integration#functionality)

-   ✨ **NEW**: **Generate time tracking reports inside of your notes with code blocks**
-   See your current timer and how long it has been running in the status bar
-   Get a summary of your day in the side panel
-   Create, start, and stop a new timer using the command palette, or restart an recent one

[![](https://raw.githubusercontent.com/mcndt/obsidian-toggl-integration/master/demo2.gif)](https://raw.githubusercontent.com/mcndt/obsidian-toggl-integration/master/demo2.gif)

## Rendering time reports inside your notes

[](https://github.com/mcndt/obsidian-toggl-integration#rendering-time-reports-inside-your-notes)

Using simple code blocks it is possible to render time tracking reports inside your Obsidian notes. For example,

````
```toggl
SUMMARY
PAST 7 DAYS
```
````

Will result in something like:

[![example-summary-report](https://user-images.githubusercontent.com/23149353/148293946-4e70ede9-0a9f-401e-af4b-f954caaeed84.png)](https://user-images.githubusercontent.com/23149353/148293946-4e70ede9-0a9f-401e-af4b-f954caaeed84.png)

You can find a full tutorial and reference on rendering time reports in the [plugin wiki](https://github.com/mcndt/obsidian-toggl-integration/wiki/Toggl-Query-Language-\(TQL\)-Reference).

## Setup

[](https://github.com/mcndt/obsidian-toggl-integration#setup)

Configuring this plugin requires you to first request an API token from Toggl. More info on how to do this [can be found here](https://support.toggl.com/en/articles/3116844-where-is-my-api-token-located).

To set up this plugin, simply enter your API token in the settings tab, click connect and select the Toggl Workspace you wish to use.

[![settings](https://raw.githubusercontent.com/mcndt/obsidian-toggl-integration/master/settings.png)](https://raw.githubusercontent.com/mcndt/obsidian-toggl-integration/master/settings.png)

## Use with other plugins:

[](https://github.com/mcndt/obsidian-toggl-integration#use-with-other-plugins)

### QuickAdd

[](https://github.com/mcndt/obsidian-toggl-integration#quickadd)

The developer of the QuickAdd plugin has created a preset menu for timers using QuickAdd. Instructions are available [here](https://github.com/chhoumann/quickadd/blob/master/docs/docs/Examples/Macro_TogglManager.md) and you can find out how he did it on the Obsidian Discord server ([link to message](https://discord.com/channels/686053708261228577/707816848615407697/876069796553293835)).

## Roadmap

[](https://github.com/mcndt/obsidian-toggl-integration#roadmap)

You can see my more detailed roadmap for this plugin on this page: [Development Roadmap](https://github.com/mcndt/obsidian-toggl-integration/projects/1). I try to keep the cards in each column sorted by priority.

## Feature Requests

[](https://github.com/mcndt/obsidian-toggl-integration#feature-requests)

Please make feature requests in the GitHub discussions tab: [click here](https://github.com/mcndt/obsidian-toggl-integration/discussions/categories/feature-requests)

If you would to like to talk about the plugin with me more directly, you can find me in the Obsidian Discord server as `Maximio#6460`. Feel free to tag me!

## Dependencies

[](https://github.com/mcndt/obsidian-toggl-integration#dependencies)

Currently I rely on this repo for providing a JavaScript interface with the Toggl Track API: [https://github.com/saintedlama/toggl-client](https://github.com/saintedlama/toggl-client)

However in the future I might write fork this so I can refactor it to use mobile friendly APIs (e.g. using Obsidian’s own request API).

## Support

[](https://github.com/mcndt/obsidian-toggl-integration#support)

If you like this plugin and want to support me, you can do so via *Buy me a Coffee*:

[![](https://camo.githubusercontent.com/32b8ec6b5d70821195133ee361a3628c23f62c55fcadb5ee0c0e90a6e918bec4/68747470733a2f2f696d672e6275796d6561636f666665652e636f6d2f627574746f6e2d6170692f3f746578743d427579206d65206120636f6666656526656d6f6a693d26736c75673d6d636e647426627574746f6e5f636f6c6f75723d35463746464626666f6e745f636f6c6f75723d66666666666626666f6e745f66616d696c793d496e746572266f75746c696e655f636f6c6f75723d30303030303026636f666665655f636f6c6f75723d464644443030)](https://www.buymeacoffee.com/mcndt)