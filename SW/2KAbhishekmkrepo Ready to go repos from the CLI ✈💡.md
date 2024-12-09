---
page-title: "2KAbhishek/mkrepo: Ready to go repos from the CLI ✈💡"
url: https://github.com/2kabhishek/mkrepo
date: "2024-06-24 00:03:49"
tags: [a/sw/command-line, F/, C/, P/pwf]
about: ["[[github]]",]
aliases: 
- 
by: 
length: 1758
dir: 
---

## [mkrepo](https://2kabhishek.github.io/mkrepo)

[](https://github.com/2kabhishek/mkrepo#mkrepo)

 [![License](https://camo.githubusercontent.com/e4961168abce8d700b34956b1d2097bc69ac7eeb41a9257b59bbb2261bd0a1b0/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6c6963656e73652f326b616268697368656b2f6d6b7265706f3f7374796c653d666c617426636f6c6f723d656565266c6162656c3d)](https://github.com/2KAbhishek/mkrepo/blob/main/LICENSE)[![People](https://camo.githubusercontent.com/c1d2452392fad616e01055ebcbbb38f49afbc2c00dad8c831e3cd4e14fcd601d/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f636f6e7472696275746f72732f326b616268697368656b2f6d6b7265706f3f7374796c653d666c617426636f6c6f723d666661616632266c6162656c3d50656f706c65) ](https://github.com/2KAbhishek/mkrepo/graphs/contributors)[![Stars](https://camo.githubusercontent.com/3228510f1e383c32b6a58262d7acf02e887afdfa9cc737ca51642086cf633ce4/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f73746172732f326b616268697368656b2f6d6b7265706f3f7374796c653d666c617426636f6c6f723d393863333739266c6162656c3d5374617273)](https://github.com/2KAbhishek/mkrepo/stargazers) [![Forks](https://camo.githubusercontent.com/eea0d8d6dcc4e8df8b3c48f3f7c3a3e2078cc85c7e04b83840438e388112092e/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f666f726b732f326b616268697368656b2f6d6b7265706f3f7374796c653d666c617426636f6c6f723d363661386530266c6162656c3d466f726b73) ](https://github.com/2KAbhishek/mkrepo/network/members)[![Watches](https://camo.githubusercontent.com/f0da29f0ccd24fd3b584489cd9b5863d482a63552e307f5e4468bef3f1d50f25/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f77617463686572732f326b616268697368656b2f6d6b7265706f3f7374796c653d666c617426636f6c6f723d663564303862266c6162656c3d57617463686573) ](https://github.com/2KAbhishek/mkrepo/watchers)[![Last Updated](https://camo.githubusercontent.com/74fecde34b3dc0f893aa2ce7b76ca50428987255aebc70329068fc5c582c667a/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6c6173742d636f6d6d69742f326b616268697368656b2f6d6b7265706f3f7374796c653d666c617426636f6c6f723d653036633735266c6162656c3d)](https://github.com/2KAbhishek/mkrepo/pulse)

### Ready to go repos from the CLI ✈💡

[](https://github.com/2kabhishek/mkrepo#ready-to-go-repos-from-the-cli-)

## What is this

[](https://github.com/2kabhishek/mkrepo#what-is-this)

mkrepo is a little wrapper around `github-cli` that allows you to make new repos even more quickly and sets up remotes so that you can jump straight into typing out code.

## Inspiration

[](https://github.com/2kabhishek/mkrepo#inspiration)

I make a lot of projects (as you might have seen on my GitHub profile), and I needed a tool to fasttrack the first commit.

## Prerequisites

[](https://github.com/2kabhishek/mkrepo#prerequisites)

Before you begin, ensure you have met the following requirements:

-   You have installed the latest version of `github-cli`
    
-   A template repo like [mkrepo](https://github.com/2kabhishek/mkrepo)
    

## Installing mkrepo

[](https://github.com/2kabhishek/mkrepo#installing-mkrepo)

To install mkrepo, follow these steps:

git clone https://github.com/2kabhishek/mkrepo
cd mkrepo
# Link mkrepo to a directory that's in PATH (~/.local/bin here)
ln -sfnv "$PWD/mkrepo.sh" ~/.local/bin/mkrepo

## Using mkrepo

[](https://github.com/2kabhishek/mkrepo#using-mkrepo)

If you have an existing project, you can use `mkrepo project_dirname` to create a new repo with the same name, and it will automatically set things up for you.

For new repos you can use `mkrepo` to create a new repo that uses the template you pass (mkrepo if empty) for setting things up.

mkrepo: Ready to go repos from the CLI 🚀💡

Usage: mkrepo <repoName\> \[templateName\] \[description\]

Arguments:
  repo name:        The name of the new repository.
  template name:    The name of the template repo to use (default: bare-minimum).
  description:      The description for the repository (default: Short Sweet Headline 🎇🎉).

## Templates

[](https://github.com/2kabhishek/mkrepo#templates)

These are some templates I have set up and use:

-   [bare-minimum](https://github.com/2kabhishek/bare-minimum): General purpose template (default)
-   [tiny-web](https://github.com/2kabhishek/tiny-web): Template for calssic web pages
-   [shelly](https://github.com/2kabhishek/shelly): Template for CLI tools

## How it was built

[](https://github.com/2kabhishek/mkrepo#how-it-was-built)

mkrepo was built using `bash` and `gh`

## What's next

[](https://github.com/2kabhishek/mkrepo#whats-next)

Needs changes to support customization for other users.

Hit the ⭐ button if you found this useful.

## More Info

[](https://github.com/2kabhishek/mkrepo#more-info)