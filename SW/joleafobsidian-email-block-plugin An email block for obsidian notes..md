---
page-title: "joleaf/obsidian-email-block-plugin: An email block for obsidian notes."
url: https://github.com/joleaf/obsidian-email-block-plugin
date: "2024-07-16 19:55:21"
tags: [a/sw/plugin, f/prod/homepage, c/, p/pwf]
about: ["[[Obsidian]]"]
aliases: 
- 
by: 
length: 2526
dir: 
---

This plugin lets you plan small emails inside your [Obsidian](https://www.obsidian.md/) notes.

## Install ..

[](https://github.com/joleaf/obsidian-email-block-plugin#install-)

### .. automatically in Obsidian

[](https://github.com/joleaf/obsidian-email-block-plugin#-automatically-in-obsidian)

1.  Go to **Community Plugins** in your Obsidian Settings and **disable** Safe Mode
2.  Click on **Browse** and search for "Email Block"
3.  Click install
4.  Toggle the plugin on in the **Community Plugins** tab

### .. manually from this repo

[](https://github.com/joleaf/obsidian-email-block-plugin#-manually-from-this-repo)

1.  Download the latest [release](https://github.com/joleaf/obsidian-email-block-plugin/releases) `*.zip` file.
2.  Unpack the zip in the `.obsidan/plugins` folder of your obsidian vault

## How to use

[](https://github.com/joleaf/obsidian-email-block-plugin#how-to-use)

Add the "email" code block into your note:

... with plain text as body content:

````
```email
to: info@randommail.com
subject: My Subject
body: "Hey info,

  here is some content"
```
````

... with a referenced note as body content:

````
```email
to: info@randommail.com
subject: My Subject
body: [[MyMail4711]]
variables:
  myvar: TestVar
```
````

You can use the `variables` parameter to replace placeholders in your body text with the variable values. To include a variable in the body text just add a placeholder `{{myvar}}`. Variables from fontmatter data can be used as well.

... with a body text after the yaml:

````
```email
to: info@randommail.com
subject: Hello World
---
Hi there,
this is my new body
Best!
JB
```
````

... you can use properties, like variables, on the subject or within the body:

````
```email
to: info@randommail.com
subject: reminder for {{name}}
---
Dear {{name}},
this is not a personal email.
Regards,
FI
```
````

### Parameter

[](https://github.com/joleaf/obsidian-email-block-plugin#parameter)

You can customize the view with the following parameters:

Parameter

Description

Values

Required

to

The main receiver of the mail. Multiple receiver seperated by ",".

String / List of Strings

cc

The cc receiver of the mail. Multiple receiver seperated by ",".

String / List of Strings

bcc

The bcc receiver of the mail. Multiple receiver seperated by ",".

String value / List of Strings

subject

The subject of the email. Plain text or combined text with variables

String value

x

body (1)

The body of the email. Plain text or a link to a \[\[NoteFile\]\] (2).

String value

x

showmailto

Show the "mailto" link after the mail body.

true/false (Default: true)

variables

A map of placeholder variables.

YAML Object

from

A from field (only for documentation).

String value

1.  The body can be appended after the yaml with a "---" separation
2.  No formatting is supported (only new lines) ([reason](https://stackoverflow.com/questions/5620324/mailto-link-with-html-body)).

### Example

[](https://github.com/joleaf/obsidian-email-block-plugin#example)

[![Example](https://github.com/joleaf/obsidian-email-block-plugin/raw/main/example/email-block-plugin.gif)](https://github.com/joleaf/obsidian-email-block-plugin/blob/main/example/email-block-plugin.gif)

## How to dev

[](https://github.com/joleaf/obsidian-email-block-plugin#how-to-dev)

1.  Clone this repo into the plugin folder of a (non-productive) vault (`.obsidian/plugins/`)
2.  `npm i`
3.  `npm run dev`
4.  Toggle the plugin on in the **Community Plugins** tab

## Contributors

[](https://github.com/joleaf/obsidian-email-block-plugin#contributors)

Thank you for your contributions!

-   [Vrum89](https://github.com/Vrum89)
-   [xxie-xd](https://github.com/)

## Donate

[](https://github.com/joleaf/obsidian-email-block-plugin#donate)

[![Buy Me a Coffee at ko-fi.com](https://camo.githubusercontent.com/7d739f9fe7f01b08cc051bec4997dc58d7552e1d6a2e7a211de2f4ee68657495/68747470733a2f2f617a3734333730322e766f2e6d7365636e642e6e65742f63646e2f6b6f6669332e706e673f763d30)](https://ko-fi.com/joleaf)