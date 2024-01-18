---
page-title: "EasyChris/obsidian-to-notion: Share obsidian markdown file to notion and generate notion share link 同步obsdian文件到notion，并生成notion分享链接，可以方便的分享obsidian的文件。"
url: https://github.com/EasyChris/obsidian-to-notion
date: "2024-01-17 20:59:44"
tags: obsi/plugin
purpose: integration
---

## Obsidian to Notion

[![](https://github.com/Easychris/obsidian-to-notion/actions/workflows/CI.yml/badge.svg)](https://github.com/Easychris/obsidian-to-notion/actions/workflows/CI.yml) [![Release Obsidian plugin](https://github.com/Easychris/obsidian-to-notion/actions/workflows/release.yml/badge.svg)](https://github.com/Easychris/obsidian-to-notion/actions/workflows/release.yml) [![GitHub license](https://camo.githubusercontent.com/4bcd9f6e685da53d1384d1b5dd0e01a4d0286f569996e7481869724d297413da/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6c6963656e73652f4561737943687269732f6f6273696469616e2d746f2d6e6f74696f6e)](https://raw.githubusercontent.com/EasyChris/obsidian-to-notion/master/LICENSE) [![Github all releases](https://camo.githubusercontent.com/5783c1bc08159fad19602622f680d5b970494c8168c3a684c5d52634701db9a4/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f646f776e6c6f6164732f4561737963687269732f6f6273696469616e2d746f2d6e6f74696f6e2f746f74616c2e737667)](https://github.com/Easychris/obsidian-to-notion/releases/) [![GitLab latest release](https://camo.githubusercontent.com/eaaaccf565156a9cd851cd1ecb920c7a566ebd8963abf08dc0c7d3b745aa4598/68747470733a2f2f62616467656e2e6e65742f6769746875622f72656c656173652f4561737963687269732f6f6273696469616e2d746f2d6e6f74696f6e2f)](https://github.com/Easychris/obsidian-to-notion/releases)

Share of obsidian to Notion [中文文档](https://github.com/EasyChris/obsidian-to-notion/blob/master/README-zh.md)

Sharing files from Obsidian to Notion with a single click, and Obsidian will automatically add the Notion share link

You are welcome to offer it a star if it can benefit you.

[![](https://github.com/EasyChris/obsidian-to-notion/raw/master/doc/1.gif)](https://github.com/EasyChris/obsidian-to-notion/blob/master/doc/1.gif)

## TODO

### [TODO Board](https://github.com/users/EasyChris/projects/3/views/1)

-   support for custom page banner
-   update the exsit page
-   support for mult language
-   support for auto copy the share link to clipboard
-   support for mobile
-   support tags thank for [@jannikbuscha](https://github.com/jannikbuscha)
-   transfer the bi-link format like \[\[\]\] into the format that Notion supports.

## How to use

## Install the plugin

### Marketplace download

Open obsidian setting -> Add plugin -> Search -> notion

[![](https://camo.githubusercontent.com/89d9fca2178dc3f02c235cf039eff1049a84344e6f90f736e9081154781e999d/68747470733a2f2f61666f782d313235363136383938332e636f732e61702d7368616e676861692e6d7971636c6f75642e636f6d2f32303232303632383231343134352e706e67)](https://camo.githubusercontent.com/89d9fca2178dc3f02c235cf039eff1049a84344e6f90f736e9081154781e999d/68747470733a2f2f61666f782d313235363136383938332e636f732e61702d7368616e676861692e6d7971636c6f75642e636f6d2f32303232303632383231343134352e706e67)

### BRAT

Enter `BRAT` into the plugin market center to find it. Add `EasyChris/obsidian-to-notion` to the list of BRAT plugins that have been installed. Return to the plugin center and turn it on.

### Manual installation

```
cd YOUR_OBSIDIAN_FOLDER/.obsidian/plugins/
git clone https://github.com/EasyChris/obsidian-to-notion.git
```

## Apply Notion API

Official reference documentation: [https://developers.notion.com/docs](https://developers.notion.com/docs)

### Step 1: Create integration.

Go to [https://www.notion.com/my-integrations](https://www.notion.com/my-integrations) Once created, copy `secrets toekn` [![](https://camo.githubusercontent.com/4b51fe68aed224e0cc5f4cac29a4d1b3c17de62197da9163cfb07255a680dc25/68747470733a2f2f66696c65732e726561646d652e696f2f326563313337642d303933616434392d6372656174652d696e746567726174696f6e2e676966)](https://camo.githubusercontent.com/4b51fe68aed224e0cc5f4cac29a4d1b3c17de62197da9163cfb07255a680dc25/68747470733a2f2f66696c65732e726561646d652e696f2f326563313337642d303933616434392d6372656174652d696e746567726174696f6e2e676966)

#### Note:

database first custom name must be "Name", otherwise sync to notion will be failed

[![](https://camo.githubusercontent.com/2821ee136b014acfc937b57331abb2a418e947931582389ab370cbded5921719/68747470733a2f2f61666f782d313235363136383938332e636f732e61702d7368616e676861692e6d7971636c6f75642e636f6d2f32303232303631383130323032392e706e67)](https://camo.githubusercontent.com/2821ee136b014acfc937b57331abb2a418e947931582389ab370cbded5921719/68747470733a2f2f61666f782d313235363136383938332e636f732e61702d7368616e676861692e6d7971636c6f75642e636f6d2f32303232303631383130323032392e706e67)

### Step 2: Share a database with your integration

Create a new page (with public permissions) Create a new database in the page -> you need `full page database` [![](https://github.com/EasyChris/obsidian-to-notion/raw/master/doc/3.gif)](https://github.com/EasyChris/obsidian-to-notion/blob/master/doc/3.gif)

Add `integration` to your new database

[![](https://github.com/EasyChris/obsidian-to-notion/raw/master/doc/6.gif)](https://github.com/EasyChris/obsidian-to-notion/blob/master/doc/6.gif)

### Step 3: Copy the database ID

```
https://www.notion.so/myworkspace/a8aec43384f447ed84390e8e42c2e089?v=...
                                  | --------- Database ID --------|

```

## Open the plugin configuration

Fill the configuration with the `NOTION_API_KEY` and `DATABASE_ID` you got [![](https://github.com/EasyChris/obsidian-to-notion/raw/master/doc/2.png)](https://github.com/EasyChris/obsidian-to-notion/blob/master/doc/2.png)

## Upload file content to notion

Click the upload notion button [![](https://github.com/EasyChris/obsidian-to-notion/raw/master/doc/4.png)](https://github.com/EasyChris/obsidian-to-notion/blob/master/doc/4.png) A share link will be automatically generated after successful upload [![](https://github.com/EasyChris/obsidian-to-notion/raw/master/doc/5.png)](https://github.com/EasyChris/obsidian-to-notion/blob/master/doc/5.png)

## Banner URL \[option\]

Banner url must be a image url like: [https://i.imgur.com/xxx.jpg](https://i.imgur.com/xxx.jpg) If you don't want to use banner, leave it blank

## Convert Tags \[option\]

Transfer the Obsidian tags to the Notion table. It requires the column with the name 'Tags'. [![](https://github.com/EasyChris/obsidian-to-notion/raw/master/doc/7.png)](https://github.com/EasyChris/obsidian-to-notion/blob/master/doc/7.png)

Add tags to your notion page

[![](https://github.com/EasyChris/obsidian-to-notion/raw/master/doc/10.png)](https://github.com/EasyChris/obsidian-to-notion/blob/master/doc/10.png)

-   open plugin convert tags

[![](https://github.com/EasyChris/obsidian-to-notion/raw/master/doc/8.png)](https://github.com/EasyChris/obsidian-to-notion/blob/master/doc/8.png)

-   add tags in the head

\---
tags: \[tag1,tag2\]
\---

this is test tags

\---
tags:
  - tag4
\---

this is test tags

[![](https://github.com/EasyChris/obsidian-to-notion/raw/master/doc/9.png)](https://github.com/EasyChris/obsidian-to-notion/blob/master/doc/9.png)

Thanks for [@jannikbuscha](https://github.com/jannikbuscha) contribution

## Notion ID \[option\]

Notion ID is the your notion site ID that you want to share the file to. if you don't write it, notion will share to the default link like: [https://www.notion.so/myworkspace/a8aec43384f447ed84390](https://www.notion.so/myworkspace/a8aec43384f447ed84390) that visit this page need to redirect to your site url if you write the Notion ID, it will share to the page link like: [https://your\_user\_name.notion.site/myworkspace/a8aec43384f447ed84390](https://your_user_name.notion.site/myworkspace/a8aec43384f447ed84390). The visiter don't need to redirect url.

## Sync image to Notion

To sync images to your oss or cos bucket, use the [Obsidian Image Auto Upload Plugin](https://github.com/renmu123/obsidian-image-auto-upload-plugin).

## Development

```
git clone https://github.com/EasyChris/obsidian-to-notion.git
yarn install
yarn dev
```

## Release

```
node update-version.js
./release.sh
```

```




# Thanks
[Development Process | Obsidian Plugin Development Documentation](https://luhaifeng666.github.io/obsidian-plugin-docs-zh/zh/getting-started/development-workflow.html)

[GitHub - devbean/obsidian-wordpress: An obsidian plugin for publishing docs to WordPress.](https://github.com/devbean/obsidian-wordpress)

[GitHub - obsidianmd/obsidian-api](https://github.com/obsidianmd/obsidian-api)

[GitHub - Easychris/obsidian-to-notion: Obsidian Weread Plugin is an plugin to sync Weread(微信读书) hightlights and annotations into your Obsidian Vault.](https://github.dev/zhaohongxuan/obsidian-weread-plugin)

[GitHub - Quorafind/Obsidian-Memos: A quick capture plugin for Obsidian, all data from your notes.](https://github.com/Quorafind/Obsidian-Memos)

[https://github.com/jannikbuscha/obsidian-to-notion](https://github.com/jannikbuscha)

# License
GNU GPLv3
```