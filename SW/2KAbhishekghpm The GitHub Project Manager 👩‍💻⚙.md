---
page-title: "2KAbhishek/ghpm: The GitHub Project Manager 👩‍💻⚙"
url: https://github.com/2kabhishek/ghpm
date: "2024-06-24 00:02:36"
tags: [A/sw/command-line, F/, C/, P/pwf]
about: ["[[github]]"]
aliases: 
- 
by: 
length: 1611
dir: 
---

## [ghpm](https://2kabhishek.github.io/ghpm)

[](https://github.com/2kabhishek/ghpm#ghpm)

 [![License](https://camo.githubusercontent.com/e55dd2b1a313ffce2c60f249fe4ac1c0460da630f7274a8338a5a0647e24e603/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6c6963656e73652f326b616268697368656b2f6768706d3f7374796c653d666c617426636f6c6f723d656565266c6162656c3d)](https://github.com/2KAbhishek/ghpm/blob/main/LICENSE)[![People](https://camo.githubusercontent.com/dc4d0a852a50a295de916701c49cce95b7fc46269f2a1e4025f709a64b739bd8/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f636f6e7472696275746f72732f326b616268697368656b2f6768706d3f7374796c653d666c617426636f6c6f723d666661616632266c6162656c3d50656f706c65) ](https://github.com/2KAbhishek/ghpm/graphs/contributors)[![Stars](https://camo.githubusercontent.com/6773cb48331c3974fb3e5eeb1f7d5eea49a9a8bcd0c9a848fae052f13b40e582/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f73746172732f326b616268697368656b2f6768706d3f7374796c653d666c617426636f6c6f723d393863333739266c6162656c3d5374617273)](https://github.com/2KAbhishek/ghpm/stargazers) [![Forks](https://camo.githubusercontent.com/b0fcef216e4bf4ceb6a020b0d0e4ec9375f71d969b4f91c92b2ff60dadef1793/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f666f726b732f326b616268697368656b2f6768706d3f7374796c653d666c617426636f6c6f723d363661386530266c6162656c3d466f726b73) ](https://github.com/2KAbhishek/ghpm/network/members)[![Watches](https://camo.githubusercontent.com/d6c4263346c9521166db6686b16704b810d81ce1ccd0b5deee29bd7247703589/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f77617463686572732f326b616268697368656b2f6768706d3f7374796c653d666c617426636f6c6f723d663564303862266c6162656c3d57617463686573) ](https://github.com/2KAbhishek/ghpm/watchers)[![Last Updated](https://camo.githubusercontent.com/ce4170d9584770ea8b18c4fe13550d6b8871e0047b18b2a1ca6d8fe30a3ab1ee/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f6c6173742d636f6d6d69742f326b616268697368656b2f6768706d3f7374796c653d666c617426636f6c6f723d653036633735266c6162656c3d)](https://github.com/2KAbhishek/ghpm/pulse)

### The GitHub Project Manager 🧑‍💻⚙️

[](https://github.com/2kabhishek/ghpm#the-github-project-manager-%EF%B8%8F)

[![ghpm Demo](https://github.com/2KAbhishek/ghpm/raw/main/images/screenshot.png)](https://github.com/2KAbhishek/ghpm/blob/main/images/screenshot.png)  
ghpm screenshot

## What is this

[](https://github.com/2kabhishek/ghpm#what-is-this)

ghpm is a utility that allows you to manage all your GitHub projects by allowing batch operations.

You can clone all of your or any other user's repos at once.

You can use it to push, pull and do any other operation on all your projects at once.

## Inspiration

[](https://github.com/2kabhishek/ghpm#inspiration)

I have a lot of repos on my GitHub and maintaining them was becoming a pain, also this makes moving my work to a new machine really smooth.

## Prerequisites

[](https://github.com/2kabhishek/ghpm#prerequisites)

Before you begin, ensure you have met the following requirements:

-   You have installed the latest version of `bash`
-   Cloning self repos needs authentication and relies on `gh`, the GitHub cli

## Getting ghpm

[](https://github.com/2kabhishek/ghpm#getting-ghpm)

To install ghpm, follow these steps:

git clone https://github.com/2kabhishek/ghpm.git
cd ghpm
# Setup symlink make sure target directory is added to PATH
ln -sfnv $PWD/ghpm.sh ~/.local//bin/ghpm

## Using ghpm

[](https://github.com/2kabhishek/ghpm#using-ghpm)

After symlinking, you can run `ghpm` in your GitHub repos parent directory, or you can pass it in as an argument

ghpm
# or
ghpm ~/Projects/GitHub

This will open up the self guided menu with a list of operations you can perform.

> You can use option 3 to run any command in all your GitHub repos, very useful for push, pull and similar commands.

## How it was built

[](https://github.com/2kabhishek/ghpm#how-it-was-built)

ghpm was built using `bash`

## Challenges faced

[](https://github.com/2kabhishek/ghpm#challenges-faced)

Figuring out the GitHub api and authentication was a challenge, I used `gh` to do some heavy lifting.

## What I learned

[](https://github.com/2kabhishek/ghpm#what-i-learned)

-   Best practices for `bash` scripts
-   Bash functions and how it handles variables
-   Used `awk`, `find`, `xargs` and other useful tools.

Hit the ⭐ button if you found this useful.

## More Info

[](https://github.com/2kabhishek/ghpm#more-info)