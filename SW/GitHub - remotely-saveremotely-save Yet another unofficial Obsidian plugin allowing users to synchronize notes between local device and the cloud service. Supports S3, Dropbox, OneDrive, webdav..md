---
page-title: "GitHub - remotely-save/remotely-save: Yet another unofficial Obsidian plugin allowing users to synchronize notes between local device and the cloud service. Supports S3, Dropbox, OneDrive, webdav."
url: https://github.com/remotely-save/remotely-save
date: "2024-03-03 17:10:07"
tags: 
- A/sw/plugin
- F/homepage
- C/
- P/
about: "[[Obsidian]]"
uuid: 8546006d-a492-4386-9c13-d430002b1d0d
---

## Remotely Save

[](https://github.com/remotely-save/remotely-save#remotely-save)

This is yet another unofficial sync plugin for Obsidian. If you like it or find it useful, please consider give it a [star ![GitHub Repo stars](https://camo.githubusercontent.com/45b49150a49b5f7ef28a82c0e8c133803171a16ffca6392d852212d2dd7f9085/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f73746172732f6679656172732f72656d6f74656c792d736176653f7374796c653d736f6369616c)](https://github.com/fyears/remotely-save) on Github.

[![BuildCI](https://github.com/fyears/remotely-save/actions/workflows/auto-build.yml/badge.svg)](https://github.com/fyears/remotely-save/actions/workflows/auto-build.yml)

[![downloads of latest version](https://camo.githubusercontent.com/399c14be73ff2e5332aa7f0c9153efaf7333f06284936c2c0e92a5550d6c01e3/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f646f776e6c6f6164732d7072652f72656d6f74656c792d736176652f72656d6f74656c792d736176652f6c61746573742f6d61696e2e6a733f736f72743d73656d766572)](https://github.com/fyears/remotely-save/releases)

## Disclaimer

[](https://github.com/remotely-save/remotely-save#disclaimer)

-   **This is NOT the [official sync service](https://obsidian.md/sync) provided by Obsidian.**

## !!!Caution!!!

[](https://github.com/remotely-save/remotely-save#caution)

**ALWAYS, ALWAYS, backup your vault before using this plugin.**

## Features

[](https://github.com/remotely-save/remotely-save#features)

-   Supports:
    -   Amazon S3 or S3-compatible (Cloudflare R2 / BackBlaze B2 / MinIO / ...)
    -   Dropbox
    -   OneDrive for personal
    -   Webdav
    -   [Here](https://github.com/remotely-save/remotely-save/blob/master/docs/services_connectable_or_not.md) shows more connectable (or not-connectable) services in details.
-   **Obsidian Mobile supported.** Vaults can be synced across mobile and desktop devices with the cloud service as the "broker".
-   **[End-to-end encryption](https://github.com/remotely-save/remotely-save/blob/master/docs/encryption.md) supported.** Files would be encrypted using openssl format before being sent to the cloud **if** user specify a password.
-   **Scheduled auto sync supported.** You can also manually trigger the sync using sidebar ribbon, or using the command from the command palette (or even bind the hot key combination to the command then press the hot key combination).
-   **[Minimal Intrusive](https://github.com/remotely-save/remotely-save/blob/master/docs/minimal_intrusive_design.md).**
-   **Skip Large files** and **skip paths** by custom regex conditions!
-   **Fully open source under [Apache-2.0 License](https://github.com/remotely-save/remotely-save/blob/master/LICENSE).**
-   **[Sync Algorithm open](https://github.com/remotely-save/remotely-save/blob/master/docs/sync_algorithm_v2.md) for discussion.**

## Limitations

[](https://github.com/remotely-save/remotely-save#limitations)

-   **To support deletions sync, extra metadata will also be uploaded.** See [Minimal Intrusive](https://github.com/remotely-save/remotely-save/blob/master/docs/minimal_intrusive_design.md).
-   **No Conflict resolution. No content-diff-and-patch algorithm.** All files and folders are compared using their local and remote "last modified time" and those with later "last modified time" wins.
-   **Cloud services cost you money.** Always be aware of the costs and pricing. Specifically, all the operations, including but not limited to downloading, uploading, listing all files, calling any api, storage sizes, may or may not cost you money.
-   **Some limitations from the browser environment.** More technical details are [in the doc](https://github.com/remotely-save/remotely-save/blob/master/docs/browser_env.md).
-   **You should protect your `data.json` file.** The file contains sensitive information.
    -   It's strongly advised **NOT** to share your `data.json` file to anyone.
    -   It's usually **NOT** a good idea to check the file into version control. By default, the plugin tries to create a `.gitignore` file inside the plugin directory if it doesn't exist, for ignoring `data.json` in the `git` version control. If you know exactly what it means and want to remove the setting, please modify the `.gitignore` file or set it to be empty.

## Questions, Suggestions, Or Bugs

[](https://github.com/remotely-save/remotely-save#questions-suggestions-or-bugs)

You are greatly welcome to ask questions, post any suggestions, or report any bugs! The project is mainly maintained on GitHub:

-   Questions: [GitHub repo Discussions](https://github.com/fyears/remotely-save/discussions)
-   Suggestions: also in [GitHub repo Discussions](https://github.com/fyears/remotely-save/discussions)
-   Bugs: [GitHub repo Issues](https://github.com/fyears/remotely-save/issues) (NOT Discussion)

Additionally, the plugin author may occasionally visit Obsidian official forum and official Discord server, and pay attention to this-plugin-related information there.

## Download and Install

[](https://github.com/remotely-save/remotely-save#download-and-install)

## Usage

[](https://github.com/remotely-save/remotely-save#usage)

### S3

[](https://github.com/remotely-save/remotely-save#s3)

-   Tutorials / Examples:
    -   [Cloudflare R2](https://github.com/remotely-save/remotely-save/blob/master/docs/remote_services/s3_cloudflare_r2/README.md)
    -   [BackBlaze B2](https://github.com/remotely-save/remotely-save/blob/master/docs/remote_services/s3_backblaze_b2/README.md)
    -   [Storj](https://github.com/remotely-save/remotely-save/blob/master/docs/remote_services/s3_storj_io/README.md)
    -   [腾讯云 COS](https://github.com/remotely-save/remotely-save/blob/master/docs/remote_services/s3_tencent_cloud_cos/README.zh-cn.md) | [Tencent Cloud COS](https://github.com/remotely-save/remotely-save/blob/master/docs/remote_services/s3_tencent_cloud_cos/README.md)
    -   [MinIO](https://github.com/remotely-save/remotely-save/blob/master/docs/remote_services/s3_minio/README.md)
-   Prepare your S3 (-compatible) service information: [endpoint, region](https://docs.aws.amazon.com/general/latest/gr/s3.html), [access key id, secret access key](https://docs.aws.amazon.com/sdk-for-javascript/v3/developer-guide/getting-your-credentials.html), bucket name. The bucket should be empty and solely for syncing a vault.
-   If you are using AWS S3, create [policy and user](https://github.com/remotely-save/remotely-save/blob/master/docs/remote_services/s3_general/s3_user_policy.md).
-   Very old version of Obsidian needs [configuring CORS](https://github.com/remotely-save/remotely-save/blob/master/docs/remote_services/s3_general/s3_cors_configure.md).
-   Download and enable this plugin.
-   Enter your information to the settings of this plugin.
-   If you want to enable end-to-end encryption, also set a password in settings. If you do not specify a password, the files and folders are synced in plain, original content to the cloud.
-   Click the new "circle arrow" icon on the ribbon (the left sidebar), **every time** you want to sync your vault between local and remote. (Or, you could configure auto sync in the settings panel (See next chapter).) While syncing, the icon becomes "two half-circle arrows". Besides clicking the icon on the sidebar ribbon, you can also activate the corresponding command in the command palette.
-   **Be patient while syncing.** Especially in the first-time sync.
-   If you want to sync the files across multiple devices, **your vault name should be the same** while using default settings.

### Dropbox

[](https://github.com/remotely-save/remotely-save#dropbox)

-   **This plugin is NOT an official Dropbox product.** The plugin just uses Dropbox's public API.
-   After the authorization, the plugin can read your name and email (which cannot be unselected on Dropbox api), and read and write files in your Dropbox's `/Apps/remotely-save` folder.
-   If you decide to authorize this plugin to connect to Dropbox, please go to plugin's settings, and choose Dropbox then follow the instructions. [More with screenshot is here](https://github.com/remotely-save/remotely-save/blob/master/docs/dropbox_review_material/README.md).
-   Password-based end-to-end encryption is also supported. But please be aware that **the vault name itself is not encrypted**.
-   If you want to sync the files across multiple devices, **your vault name should be the same** while using default settings.

### OneDrive for personal

[](https://github.com/remotely-save/remotely-save#onedrive-for-personal)

-   **This plugin is NOT an official Microsoft / OneDrive product.** The plugin just uses Microsoft's [OneDrive's public API](https://docs.microsoft.com/en-us/onedrive/developer/rest-api).
-   This plugin only works for "OneDrive for personal", and not works for "OneDrive for Business" (yet). See [#11](https://github.com/fyears/remotely-save/issues/11) to further details.
-   After the authorization, the plugin can read your name and email, and read and write files in your OneDrive's `/Apps/remotely-save` folder.
-   If you decide to authorize this plugin to connect to OneDrive, please go to plugin's settings, and choose OneDrive then follow the instructions.
-   Password-based end-to-end encryption is also supported. But please be aware that **the vault name itself is not encrypted**.
-   If you want to sync the files across multiple devices, **your vault name should be the same** while using default settings.

### webdav

[](https://github.com/remotely-save/remotely-save#webdav)

-   Tutorials / Examples:
    -   [ownCloud](https://github.com/remotely-save/remotely-save/blob/master/docs/remote_services/webdav_owncloud/README.md)
    -   [InfiniCloud](https://github.com/remotely-save/remotely-save/blob/master/docs/remote_services/webdav_infinicloud_teracloud/README.md)
    -   [Synology webdav server](https://github.com/remotely-save/remotely-save/blob/master/docs/remote_services/webdav_synology_webdav_server/README.md) | [群晖 webdav server](https://github.com/remotely-save/remotely-save/blob/master/docs/remote_services/webdav_synology_webdav_server/README.zh-cn.md)
    -   [AList（中文）](https://github.com/remotely-save/remotely-save/blob/master/docs/remote_services/webdav_alist/README.zh-cn.md) | [AList (English)](https://github.com/remotely-save/remotely-save/blob/master/docs/remote_services/webdav_alist/README.md)
    -   [坚果云](https://github.com/remotely-save/remotely-save/blob/master/docs/remote_services/webdav_jianguoyun/README.zh-cn.md) | [JianGuoYun/NutStore](https://github.com/remotely-save/remotely-save/blob/master/docs/remote_services/webdav_jianguoyun/README.md)
-   Very old version of Obsidian needs [configuring CORS](https://github.com/remotely-save/remotely-save/blob/master/docs/remote_services/webdav_general/webav_cors.md).
-   Your data would be synced to a `${vaultName}` sub folder on your webdav server.
-   Password-based end-to-end encryption is also supported. But please be aware that **the vault name itself is not encrypted**.
-   If you want to sync the files across multiple devices, **your vault name should be the same** while using default settings.

## Scheduled Auto Sync

[](https://github.com/remotely-save/remotely-save#scheduled-auto-sync)

-   You can configure auto syncing every N minutes in settings.
-   In auto sync mode, if any error occurs, the plugin would **fail silently**.
-   Auto sync only works when Obsidian is being opened. It's **technically impossible** to auto sync while Obsidian is in background, because the plugin just works in the browser environment provided by Obsidian.

## How To Deal With Hidden Files Or Folders

[](https://github.com/remotely-save/remotely-save#how-to-deal-with-hidden-files-or-folders)

**By default, all files or folder starting with `.` (dot) or `_` (underscore) are treated as hidden files, and would NOT be synced.** It's useful if you have some files just staying locally. But this strategy also means that themes / other plugins / settings of this plugin would neither be synced.

In the latest version, you can change the settings to allow syncing `_` files or folders, as well as `.obsidian` special config folder (but not any other `.` files or folders).

## How To Debug

[](https://github.com/remotely-save/remotely-save#how-to-debug)

See [here](https://github.com/remotely-save/remotely-save/blob/master/docs/how_to_debug/README.md) for more details.

## Bonus: Import And Export Not-Oauth2 Plugin Settings By QR Code

[](https://github.com/remotely-save/remotely-save#bonus-import-and-export-not-oauth2-plugin-settings-by-qr-code)

See [here](https://github.com/remotely-save/remotely-save/blob/master/docs/import_export_some_settings.md) for more details.