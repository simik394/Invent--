---
page-title: "ivan-lednev/better-search-views: Outliner-like breadcrumb trees for search, backlinks and embedded queries"
url: https://github.com/ivan-lednev/better-search-views
date: "2024-04-08 20:10:31"
tags: 
- A/sw/plugin
- F/homepage
- C/
- P/
about: "[[Obsidian]]"
aliases: 
- bf414d69-7b02-4b2b-a66e-9e4604a03071
- ivan-lednev/better-search-views: Outliner-like breadcrumb trees for search, backlinks and embedded queries
by: 
length: 1983
dir: 
---

## Better Search Views

[](https://github.com/ivan-lednev/better-search-views#better-search-views)

> **Warning**
> 
> -   You need to reload Obsidian after you **install/update/enable/disable** the plugin
> -   The plugin reaches into Obsidian's internals, so it may break after an update. If you noticed that, [please create an issue](https://github.com/ivan-lednev/better-search-views/issues)

## How to use it

[](https://github.com/ivan-lednev/better-search-views#how-to-use-it)

Just install it and reload Obsidian. Now Obsidian's built-in global search, backlinks and queries should be decorated with breadcrumbs.

## What it does

[](https://github.com/ivan-lednev/better-search-views#what-it-does)

### Before 'Better Search Views', search results look like this:

[](https://github.com/ivan-lednev/better-search-views#before-better-search-views-search-results-look-like-this)

[![image](https://private-user-images.githubusercontent.com/41428836/292629983-4069c2ef-6ec9-4a87-9881-2d300cddd10e.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTI2MDAxMzUsIm5iZiI6MTcxMjU5OTgzNSwicGF0aCI6Ii80MTQyODgzNi8yOTI2Mjk5ODMtNDA2OWMyZWYtNmVjOS00YTg3LTk4ODEtMmQzMDBjZGRkMTBlLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA0MDglMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNDA4VDE4MTAzNVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTkwZDU2NDdiMDVmODgxNWYxYmZlYzU2YzVmNTI5Y2M2OTQwYTkyMDZkMzk0MDkyZGMyMTcxOGQ3NDQ5NWJiYmImWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.TfRMMEgQaPo6QaFdPHhU3kq57iQqP0vpTG5hDvh_pu4)](https://private-user-images.githubusercontent.com/41428836/292629983-4069c2ef-6ec9-4a87-9881-2d300cddd10e.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTI2MDAxMzUsIm5iZiI6MTcxMjU5OTgzNSwicGF0aCI6Ii80MTQyODgzNi8yOTI2Mjk5ODMtNDA2OWMyZWYtNmVjOS00YTg3LTk4ODEtMmQzMDBjZGRkMTBlLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA0MDglMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNDA4VDE4MTAzNVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTkwZDU2NDdiMDVmODgxNWYxYmZlYzU2YzVmNTI5Y2M2OTQwYTkyMDZkMzk0MDkyZGMyMTcxOGQ3NDQ5NWJiYmImWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.TfRMMEgQaPo6QaFdPHhU3kq57iQqP0vpTG5hDvh_pu4)

### After 'Better Search Views' they look like this:

[](https://github.com/ivan-lednev/better-search-views#after-better-search-views-they-look-like-this)

[![image](https://private-user-images.githubusercontent.com/41428836/292630010-b191f14a-b75c-46d9-a19c-a8f91cafcd9f.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTI2MDAxMzUsIm5iZiI6MTcxMjU5OTgzNSwicGF0aCI6Ii80MTQyODgzNi8yOTI2MzAwMTAtYjE5MWYxNGEtYjc1Yy00NmQ5LWExOWMtYThmOTFjYWZjZDlmLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA0MDglMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNDA4VDE4MTAzNVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTU1ZmJjNjg0NmM0YWY1NzIzZDMyNWEzMTE2M2IyMDQ4NTQwMDhlZDRiNTI3YzllOTJhMWU4OTU3M2QyNGFkMmEmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.SaymwAt4_g1aAGITL1HTcgWPGkEF8IC2-tzp-ptpdnA)](https://private-user-images.githubusercontent.com/41428836/292630010-b191f14a-b75c-46d9-a19c-a8f91cafcd9f.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTI2MDAxMzUsIm5iZiI6MTcxMjU5OTgzNSwicGF0aCI6Ii80MTQyODgzNi8yOTI2MzAwMTAtYjE5MWYxNGEtYjc1Yy00NmQ5LWExOWMtYThmOTFjYWZjZDlmLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA0MDglMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNDA4VDE4MTAzNVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTU1ZmJjNjg0NmM0YWY1NzIzZDMyNWEzMTE2M2IyMDQ4NTQwMDhlZDRiNTI3YzllOTJhMWU4OTU3M2QyNGFkMmEmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.SaymwAt4_g1aAGITL1HTcgWPGkEF8IC2-tzp-ptpdnA)

### A closer look

[](https://github.com/ivan-lednev/better-search-views#a-closer-look)

Let's open one of the files with matches, and see how the hierarchy in the search result matches the file: [![image](https://private-user-images.githubusercontent.com/41428836/292630304-953b2de2-cc9a-496c-ad85-27f0c361424a.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTI2MDAxMzUsIm5iZiI6MTcxMjU5OTgzNSwicGF0aCI6Ii80MTQyODgzNi8yOTI2MzAzMDQtOTUzYjJkZTItY2M5YS00OTZjLWFkODUtMjdmMGMzNjE0MjRhLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA0MDglMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNDA4VDE4MTAzNVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWU4M2UxZDE3MjA5OTQ5MWZlYTM5MThiYTcxYmY1ODRjNTlhOTIyODA1ZGJmMTkxNDI4ODEyM2JiZTdiMTNhMjQmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.NokceG0QtrcrQOunwH9BDAoqiDZXI-Ta-SZO0wtIFEc)](https://private-user-images.githubusercontent.com/41428836/292630304-953b2de2-cc9a-496c-ad85-27f0c361424a.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTI2MDAxMzUsIm5iZiI6MTcxMjU5OTgzNSwicGF0aCI6Ii80MTQyODgzNi8yOTI2MzAzMDQtOTUzYjJkZTItY2M5YS00OTZjLWFkODUtMjdmMGMzNjE0MjRhLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA0MDglMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNDA4VDE4MTAzNVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWU4M2UxZDE3MjA5OTQ5MWZlYTM5MThiYTcxYmY1ODRjNTlhOTIyODA1ZGJmMTkxNDI4ODEyM2JiZTdiMTNhMjQmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.NokceG0QtrcrQOunwH9BDAoqiDZXI-Ta-SZO0wtIFEc)

### But what does it do exactly?

[](https://github.com/ivan-lednev/better-search-views#but-what-does-it-do-exactly)

The plugin brings more outliner goodness into Obsidian: it improves search views to create an outliner-like context around every match.

-   **It patches native search, backlinks view, embedded backlinks and embedded queries**
-   It renders markdown in the match to HTML
-   It builds structural breadcrumbs to the match by chaining all the ancestor headings and list items above
-   If the match is in a list item, it displays all the sub-list items below it
-   If the match is in a heading, it displays the first section below the heading (you know, for context)

### Backlinks in document look like this

[](https://github.com/ivan-lednev/better-search-views#backlinks-in-document-look-like-this)

[![image](https://private-user-images.githubusercontent.com/41428836/255157901-2f5229bc-8d3d-4027-b01c-fa36d5872716.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTI2MDAxMzUsIm5iZiI6MTcxMjU5OTgzNSwicGF0aCI6Ii80MTQyODgzNi8yNTUxNTc5MDEtMmY1MjI5YmMtOGQzZC00MDI3LWIwMWMtZmEzNmQ1ODcyNzE2LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA0MDglMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNDA4VDE4MTAzNVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWY3YzBjYmY0ZDY4ZjBkYjZhMTE3ZWUwZWEyNDMzNzAxZDNlMjdlMjI1NzM3MzJhNTZjYzAyMmI0ZjU5NTlkZmImWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.DYxUv-x3uLi74OxM4E1qjgljdeYR9gARdmoCPXsE0YY)](https://private-user-images.githubusercontent.com/41428836/255157901-2f5229bc-8d3d-4027-b01c-fa36d5872716.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTI2MDAxMzUsIm5iZiI6MTcxMjU5OTgzNSwicGF0aCI6Ii80MTQyODgzNi8yNTUxNTc5MDEtMmY1MjI5YmMtOGQzZC00MDI3LWIwMWMtZmEzNmQ1ODcyNzE2LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA0MDglMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNDA4VDE4MTAzNVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWY3YzBjYmY0ZDY4ZjBkYjZhMTE3ZWUwZWEyNDMzNzAxZDNlMjdlMjI1NzM3MzJhNTZjYzAyMmI0ZjU5NTlkZmImWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.DYxUv-x3uLi74OxM4E1qjgljdeYR9gARdmoCPXsE0YY)

### Embedded queries look like this

[](https://github.com/ivan-lednev/better-search-views#embedded-queries-look-like-this)

[![image](https://private-user-images.githubusercontent.com/41428836/255175809-bdf7fb5d-dcc2-4067-9abb-9c2064c09a27.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTI2MDAxMzUsIm5iZiI6MTcxMjU5OTgzNSwicGF0aCI6Ii80MTQyODgzNi8yNTUxNzU4MDktYmRmN2ZiNWQtZGNjMi00MDY3LTlhYmItOWMyMDY0YzA5YTI3LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA0MDglMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNDA4VDE4MTAzNVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTJlM2JjMjI2MTdjZTc3NThiN2NmY2I2N2Q2NGM0ZTUxYjE0NzFkMzBiMzAxZTFkZmNjYTZjYTU4ZmEyY2FmNjMmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.CTB3nEMBVbuIR-f8_qO9CPqCv5_H1iUhXs95v-LFnR0)](https://private-user-images.githubusercontent.com/41428836/255175809-bdf7fb5d-dcc2-4067-9abb-9c2064c09a27.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTI2MDAxMzUsIm5iZiI6MTcxMjU5OTgzNSwicGF0aCI6Ii80MTQyODgzNi8yNTUxNzU4MDktYmRmN2ZiNWQtZGNjMi00MDY3LTlhYmItOWMyMDY0YzA5YTI3LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA0MDglMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNDA4VDE4MTAzNVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTJlM2JjMjI2MTdjZTc3NThiN2NmY2I2N2Q2NGM0ZTUxYjE0NzFkMzBiMzAxZTFkZmNjYTZjYTU4ZmEyY2FmNjMmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.CTB3nEMBVbuIR-f8_qO9CPqCv5_H1iUhXs95v-LFnR0)

### Clicking on breadcrumbs works just as you might expect

[](https://github.com/ivan-lednev/better-search-views#clicking-on-breadcrumbs-works-just-as-you-might-expect)

[![image](https://github.com/ivan-lednev/better-search-views/raw/master/click-demo.gif)](https://github.com/ivan-lednev/better-search-views/blob/master/click-demo.gif)

### Hovering over any element with the control key pressed triggers a pop-up

[](https://github.com/ivan-lednev/better-search-views#hovering-over-any-element-with-the-control-key-pressed-triggers-a-pop-up)

[![image](https://github.com/ivan-lednev/better-search-views/raw/master/hover-demo.gif)](https://github.com/ivan-lednev/better-search-views/blob/master/hover-demo.gif)

## Contribution

[](https://github.com/ivan-lednev/better-search-views#contribution)

If you noticed a bug or have an improvement idea, [please create an issue](https://github.com/ivan-lednev/better-search-views/issues).

Pull-requests are welcome! If you want to contribute but don't know where to start, you can create an issue or write me an email: [bishop1860@gmail.com](mailto:bishop1860@gmail.com).

You can also support the development directly:

[![Buy Me A Coffee](https://camo.githubusercontent.com/cace41b0afc90c68d0207e2bd809ee121f9ff4f72ac032e8ced972aee7adbb23/68747470733a2f2f63646e2e6275796d6561636f666665652e636f6d2f627574746f6e732f76322f64656661756c742d79656c6c6f772e706e67)](https://www.buymeacoffee.com/machineelf)

## Acknowledgements

[](https://github.com/ivan-lednev/better-search-views#acknowledgements)

-   Thanks to [TFTHacker](https://tfthacker.com/) for [his plugin](https://github.com/TfTHacker/obsidian42-strange-new-worlds), which helped me figure out how to implement a bunch of small improvements
-   Thanks to [NothingIsLost](https://github.com/nothingislost) for his awesome plugins, that helped me figure out how to patch Obsidian internals
-   Thanks to [PJEby](https://github.com/pjeby) for his [patching library](https://github.com/pjeby/monkey-around)