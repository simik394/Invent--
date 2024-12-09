---
page-title: "dromse/obsidian-gamified-tasks: Gamify your task management with rewards system, craft your tasks by tags."
url: https://github.com/dromse/obsidian-gamified-tasks
date: 2024-06-20 22:14:54
tags:
  - A/sw/plugin
  - F/homepage
  - C/
  - P/
about:
  - "[[Obsidian]]"
aliases:
  - 59782907-ea2b-40fc-aee7-46ec81c99dcc
  - dromseobsidian-gamified-tasks Gamify your task management with rewards system, craft your tasks by tags.
by: 
length: 1148
dir: 
guide: https://github.com/dromse/obsidian-gamified-tasks/wiki/Getting-Started
---

> ## Gamified Tasks
> 
> [](https://github.com/dromse/obsidian-gamified-tasks#gamified-tasks)
> 
> [![Latest release](https://camo.githubusercontent.com/48e49f599bd688f7754e8626f6dfced6e6d454e165e4e06347f54d675e035c27/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f762f72656c656173652f64726f6d73652f6f6273696469616e2d6772696e642d6d616e616765723f7374796c653d666f722d7468652d6261646765266c6f676f3d7374617273686970266c6f676f436f6c6f723d443945304545266c6162656c436f6c6f723d3330324434312626636f6c6f723d64396233666626696e636c7564655f70726572656c6561736526736f72743d73656d766572)](https://github.com/dromse/obsidian-grind-manager/releases/latest) [![Last commit](https://camo.githubusercontent.com/98463336c4cd134c8bc95ff94d5ebb572329e20e4d3139b14854242c4eed66bf/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6c6173742d636f6d6d69742f64726f6d73652f6f6273696469616e2d6772696e642d6d616e616765723f7374796c653d666f722d7468652d6261646765266c6f676f3d676974687562266c6f676f436f6c6f723d443945304545266c6162656c436f6c6f723d33303244343126636f6c6f723d396664663966)](https://github.com/dromse/obsidian-grind-manager/pulse) [![](https://camo.githubusercontent.com/06ed59887d0f85f9f2a65daa6674c7a8d5e61721d1c6bd9ccd587cfcf4dac713/68747470733a2f2f646362616467652e76657263656c2e6170702f6170692f7365727665722f7a425855333778426b66)](https://discord.gg/zBXU37xBkf)
> 
> -   Unleash the magic of Gamified Tasks, merging task management with rewards system to your Obsidian workspace!
> -   Earn coins by completing tasks and acquire epic rewards!
> -   It's your ticket to excitement and adventure in your digital domain!
> 
> [![](https://private-user-images.githubusercontent.com/57846319/335782864-26b6914a-8a34-4553-957c-d0de34201ffe.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTg5MTQ3MDksIm5iZiI6MTcxODkxNDQwOSwicGF0aCI6Ii81Nzg0NjMxOS8zMzU3ODI4NjQtMjZiNjkxNGEtOGEzNC00NTUzLTk1N2MtZDBkZTM0MjAxZmZlLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA2MjAlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNjIwVDIwMTMyOVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTU1ZjAyODEyMmZkOTY4YjJjN2NkY2E3NWU4ODFlYmU2ZjE0MTJmNGM2MjkyNzg1ZDNiYTM1OGQyM2QxYzlmOGQmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.bIPuGoklg4bnfZpsIeezNdiShtpYiXiov_9dA5QhtQg)](https://private-user-images.githubusercontent.com/57846319/335782864-26b6914a-8a34-4553-957c-d0de34201ffe.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTg5MTQ3MDksIm5iZiI6MTcxODkxNDQwOSwicGF0aCI6Ii81Nzg0NjMxOS8zMzU3ODI4NjQtMjZiNjkxNGEtOGEzNC00NTUzLTk1N2MtZDBkZTM0MjAxZmZlLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA2MjAlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNjIwVDIwMTMyOVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTU1ZjAyODEyMmZkOTY4YjJjN2NkY2E3NWU4ODFlYmU2ZjE0MTJmNGM2MjkyNzg1ZDNiYTM1OGQyM2QxYzlmOGQmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.bIPuGoklg4bnfZpsIeezNdiShtpYiXiov_9dA5QhtQg) [![](https://private-user-images.githubusercontent.com/57846319/335782924-ca4f5a8d-6904-46b2-af8f-8ec9eb1060fb.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTg5MTQ3MDksIm5iZiI6MTcxODkxNDQwOSwicGF0aCI6Ii81Nzg0NjMxOS8zMzU3ODI5MjQtY2E0ZjVhOGQtNjkwNC00NmIyLWFmOGYtOGVjOWViMTA2MGZiLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA2MjAlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNjIwVDIwMTMyOVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWE4OTlkOGM5N2Q5MDZmMjUyZjBmNmM0MGYxZGFlYWUwMWEzYzYxODJiYTdmMmY1YWUwMjNmYjVjOGNiMDBjMWMmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.l3Ue20lYyI8KckvZ7Z9_Pz8YYZCqAz_UogO5CQsocMk)](https://private-user-images.githubusercontent.com/57846319/335782924-ca4f5a8d-6904-46b2-af8f-8ec9eb1060fb.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTg5MTQ3MDksIm5iZiI6MTcxODkxNDQwOSwicGF0aCI6Ii81Nzg0NjMxOS8zMzU3ODI5MjQtY2E0ZjVhOGQtNjkwNC00NmIyLWFmOGYtOGVjOWViMTA2MGZiLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA2MjAlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNjIwVDIwMTMyOVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWE4OTlkOGM5N2Q5MDZmMjUyZjBmNmM0MGYxZGFlYWUwMWEzYzYxODJiYTdmMmY1YWUwMjNmYjVjOGNiMDBjMWMmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.l3Ue20lYyI8KckvZ7Z9_Pz8YYZCqAz_UogO5CQsocMk)
> 
> ## Features
> 
> [](https://github.com/dromse/obsidian-gamified-tasks#features)
> 
> -   **Tasks**: View all tasks in your vault.
> -   **Filters**: Filter tasks by completion status, recurring or search by within content.
> -   **Rewards**: Purchase rewards with earned coins.
> -   **History**: View history of earnings and spending.
> -   **Recurrence**: Instead of repeating the same tasks, recurring tasks are saved to history and reappear in the task list when their time arrives.
> -   **Counters**: Utilize counters to break down a task into smaller segments for easier completion.
> -   **Difficulty**: Set difficulty level to earn coins based on it.
> 
> ## Usage
> 
> [](https://github.com/dromse/obsidian-gamified-tasks#usage)
> 
> Explore how to get started with Gamified Tasks by checking out our [Getting Started guide](https://github.com/dromse/obsidian-gamified-tasks/wiki/Getting-Started).
> 
> ## Inspiration
> 
> [](https://github.com/dromse/obsidian-gamified-tasks#inspiration)
> 
> -   [obsidian-tasks](https://github.com/obsidian-tasks-group/obsidian-tasks)
> -   [obsidian-pomodoro-timer](https://github.com/eatgrass/obsidian-pomodoro-timer)
> -   [Habitica](https://habitica.com/)
> 
> ## Can I contribute?
> 
> [](https://github.com/dromse/obsidian-gamified-tasks#can-i-contribute)
> 
> Yes, of course!

[Skip to content](https://github.com/dromse/obsidian-gamified-tasks#start-of-content)

## Navigation Menu

## Global navigation

[](https://github.com/)

## Navigate back to

## Provide feedback

## Saved searches

## Use saved searches to filter your results more quickly

[](https://github.com/notifications)

## Account menu

![](https://avatars.githubusercontent.com/u/65924524?v=4)