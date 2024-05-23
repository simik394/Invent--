---
page-title: "joshuakto/fit: File gIT (FIT) to sync your files across mobile and desktop devices using GitHub."
url: https://github.com/joshuakto/fit
date: "2024-04-10 13:02:13"
tags: 
- A/sw/plugin/sync
- F/homepage
- C/
- P/
- M/:star:
about: "[[Obsidian]]"
aliases: 
- e14e6732-399a-4110-8b49-a98a803e0eda
- joshuakto/fit: File gIT (FIT) to sync your files across mobile and desktop devices using GitHub.
by: 
length: 1886
dir: 
---

## FIT

[](https://github.com/joshuakto/fit#fit)

[![Obsidian Downloads](https://camo.githubusercontent.com/97690658e06e19e2de892ab5bd6401be14aaa36ee924a516dcddda081e136750/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f64796e616d69632f6a736f6e3f6c6f676f3d6f6273696469616e26636f6c6f723d253233343833363939266c6162656c3d646f776e6c6f6164732671756572793d2532342535422532326669742532322535442e646f776e6c6f6164732675726c3d68747470732533412532462532467261772e67697468756275736572636f6e74656e742e636f6d2532466f6273696469616e6d642532466f6273696469616e2d72656c65617365732532466d6173746572253246636f6d6d756e6974792d706c7567696e2d73746174732e6a736f6e)](https://camo.githubusercontent.com/97690658e06e19e2de892ab5bd6401be14aaa36ee924a516dcddda081e136750/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f64796e616d69632f6a736f6e3f6c6f676f3d6f6273696469616e26636f6c6f723d253233343833363939266c6162656c3d646f776e6c6f6164732671756572793d2532342535422532326669742532322535442e646f776e6c6f6164732675726c3d68747470732533412532462532467261772e67697468756275736572636f6e74656e742e636f6d2532466f6273696469616e6d642532466f6273696469616e2d72656c65617365732532466d6173746572253246636f6d6d756e6974792d706c7567696e2d73746174732e6a736f6e)

Sync your files across mobile and desktop devices with one click.

## Features

[](https://github.com/joshuakto/fit#features)

-   **Universally supported**: sync your vault across multiple devices, support both mobile and desktop
-   Auto sync is now available 🎉
-   One-click to sync your vault.
-   Conflict resolution: Stores conflicting changes from remote in the local \_fit folder so you can resolve conflicts after sync
-   Guided setup: **Intuitive** settings, easy to configure even if you are new to GitHub
-   Works with existing vaults or repos

**Note:** This plugin is still in alpha, please backup your vault before using this plugin.

## Quick demo

[](https://github.com/joshuakto/fit#quick-demo)

[![Kapture 2024-03-15 at 17 37 07](https://private-user-images.githubusercontent.com/34743132/313145778-27ea39b7-f54d-4c95-bf40-41972a29c26d.gif?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTI3NDYxODUsIm5iZiI6MTcxMjc0NTg4NSwicGF0aCI6Ii8zNDc0MzEzMi8zMTMxNDU3NzgtMjdlYTM5YjctZjU0ZC00Yzk1LWJmNDAtNDE5NzJhMjljMjZkLmdpZj9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA0MTAlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNDEwVDEwNDQ0NVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTJiZmEwZTk0YWY4NjMxNmNhNjg4NThhYTYwYjk5ZTc1NzlhNGI1Mjc1NDg5MThlZjQ2OGZmZjdiOTZiYzc0MjkmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.1h6rj3O7p8azAULdGHvmVtnNtyespi5TZkl0uIDQXXc)](https://private-user-images.githubusercontent.com/34743132/313145778-27ea39b7-f54d-4c95-bf40-41972a29c26d.gif?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTI3NDYxODUsIm5iZiI6MTcxMjc0NTg4NSwicGF0aCI6Ii8zNDc0MzEzMi8zMTMxNDU3NzgtMjdlYTM5YjctZjU0ZC00Yzk1LWJmNDAtNDE5NzJhMjljMjZkLmdpZj9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA0MTAlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNDEwVDEwNDQ0NVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTJiZmEwZTk0YWY4NjMxNmNhNjg4NThhYTYwYjk5ZTc1NzlhNGI1Mjc1NDg5MThlZjQ2OGZmZjdiOTZiYzc0MjkmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.1h6rj3O7p8azAULdGHvmVtnNtyespi5TZkl0uIDQXXc)

## Setup

[](https://github.com/joshuakto/fit#setup)

1.  Create a personal access token (refers to [Github: creating a personal access token](https://docs.github.com/en/enterprise-server@3.9/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-personal-access-token))
2.  Once the personal access token is filled in, you can authenticate the user. The GitHub username, list of repositories, and branches will auto-populate.
3.  Select a repo and branch and you are ready to sync.

[![Screenshot 2024-03-13 at 9 49 33 AM](https://private-user-images.githubusercontent.com/34743132/312282881-3ab3665a-5a78-468c-a936-fcf5fd2a8774.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTI3NDYxODUsIm5iZiI6MTcxMjc0NTg4NSwicGF0aCI6Ii8zNDc0MzEzMi8zMTIyODI4ODEtM2FiMzY2NWEtNWE3OC00NjhjLWE5MzYtZmNmNWZkMmE4Nzc0LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA0MTAlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNDEwVDEwNDQ0NVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTY0MGZlMjNmNzljMWFhNDRjZDg4NGExNzM5ZjZjY2FkZDJlYzI1ODQ3MDJjMjZiZThlYjc4NTdjZmYxNTlmMTEmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.q_FtQ36DHSQbnShHHhPQbKvGwKbxcXZvJwQCKYQMjss)](https://private-user-images.githubusercontent.com/34743132/312282881-3ab3665a-5a78-468c-a936-fcf5fd2a8774.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTI3NDYxODUsIm5iZiI6MTcxMjc0NTg4NSwicGF0aCI6Ii8zNDc0MzEzMi8zMTIyODI4ODEtM2FiMzY2NWEtNWE3OC00NjhjLWE5MzYtZmNmNWZkMmE4Nzc0LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA0MTAlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNDEwVDEwNDQ0NVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTY0MGZlMjNmNzljMWFhNDRjZDg4NGExNzM5ZjZjY2FkZDJlYzI1ODQ3MDJjMjZiZThlYjc4NTdjZmYxNTlmMTEmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.q_FtQ36DHSQbnShHHhPQbKvGwKbxcXZvJwQCKYQMjss)

## Notes about the first sync

[](https://github.com/joshuakto/fit#notes-about-the-first-sync)

-   Repo cannot be empty (Select 'Add a README file' if you are creating a new repo)
-   It is advised to use a new repo for syncing an existing vault, to minimize the chance of file name conflict on the first sync
-   If your existing vault or repo is large, the initial sync would take longer and require a good internet connection

## Roadmap

[](https://github.com/joshuakto/fit#roadmap)

1.  Improve user notification
    -   allow user to opt in to get list of file changes in Notice
2.  Enable integration of other git tools (e.g. gitlab, gitea)

## Relevant plugins

[](https://github.com/joshuakto/fit#relevant-plugins)

There are other community plugins with more advanced git features, if you need features such as branching of your repo, [Git](https://github.com/denolehov/obsidian-git) is a nice plugin to check out.

There are also other plugins for synchronizing changes such as [Git integration](https://github.com/noradroid/obsidian-git-integration), [GitHub sync](https://github.com/kevinmkchin/Obsidian-GitHub-Sync), and [YAOS](https://github.com/mahyarmirrashed/yaos). However, they do not support mobile yet as of writing this plugin.

[!["Buy Me A Coffee"](https://camo.githubusercontent.com/52867c19b7dfad6776f2d60ae248692873ae6bdcb9a3df2bfca2f1f2ffdfd15d/68747470733a2f2f63646e2e6275796d6561636f666665652e636f6d2f627574746f6e732f76322f64656661756c742d626c75652e706e67)](https://www.buymeacoffee.com/joshuakto)

## Acknowledgements

[](https://github.com/joshuakto/fit#acknowledgements)

-   This plugin used [Obsidian Sample Plugin](https://github.com/obsidianmd/obsidian-sample-plugin) as a template.
-   This plugin uses [Octokit](https://github.com/octokit/core.js/) to interface with GitHub rest api across devices.