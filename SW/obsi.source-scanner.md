---
page-title: "gerrie-myburgh/source-scanner: obsidian plugin"
url: https://github.com/gerrie-myburgh/source-scanner
date: "2024-01-16 08:35:12"
---
# Source code scanner

Extracts comments from source code into notes. The plugin will only work for the Obsidian desktop application.

## [](https://github.com/gerrie-myburgh/source-scanner#problem-that-the-plugin-tries-to-address)Problem that the plugin tries to address

Developers that uses the agile methodology have a documentation problem. Agile does not mean no documentation, but only the necessary documentation. To enable the developer to minimise the work required to be able to show how business requirements are met and solved, tools are required.

The simplest solution from a developer point of view is to document the business requirement solution in the code itself. The ideal place to do this is in the block and line comments of the source code. What you then need are tools to extract these comments into notes and correlate the notes with the user requirements. The user requirement will be in the form of user stories also in notes.

## [](https://github.com/gerrie-myburgh/source-scanner#git-dependency)Git dependency

The plugin depends on git to check that the current branch is the one to be scanned. To do this you need to add the following git hook shell script for : post-checkout. If you want to fool the code scanner into thinking that the code getting scanned is using version control then create a current-branch.txt file in the root of the project and place the name of the branch in the file. This branch name value must be the same as defined in the plugin settings.

An example of a git hook script on Linux.

```
#!/bin/bash
git branch --show-current > current-branch.txt
```

## [](https://github.com/gerrie-myburgh/source-scanner#the-use-case-for-this-plugin-is-the-following-)The use case for this plugin is the following :

0. This plugin is restricted to source languages like java, scala, c, c++, typescript, javascript that have block and line comments.
1. Scan source code files for comments that is written out to notes in current specified document vault. These comment can include markdown text.
2. Correlate the comments with agile user stories.
3. Create a table of markers along with the notes where the markers appear in.

## [](https://github.com/gerrie-myburgh/source-scanner#comments-types-scanned-for-in-source-code)Comments types scanned for in source code

The following type of comments are picked from source files by the plugin and written out markdown notes `/** ... */` and `//bus ...`. The idea is to pick up only comments that relate to the solving of business rules. The other types of comments, `/* ... */` and `// ....` are ignored as they are deemed to be comments that explain some of other technical point in the implementation.

An example of a block comment that is picked is the following

```
  /**
   * ## onload()
   * Load the plugin and setup the commands
   * 1. Add a command to trigger the creation of solution files. Make sure all configs have been done before running the command
   * 2. Add ribbon command to toggle scanning _ON_ or _OFF_. Make sure the scanner have been configured before starting it.
   */
```

This will be rendered as follows in the relevant note in the specified document vault.

# [](https://github.com/gerrie-myburgh/source-scanner#onload)onload()

Load the plugin and setup the commands

1. Add a command to trigger the creation of solution files. Make sure all configs have been done before running the command
2. Add ribbon command to toggle scanning _ON_ or _OFF_. Make sure the scanner have been configured before starting it.

### [](https://github.com/gerrie-myburgh/source-scanner#comment-file-naming-convention)Comment file naming convention

The scanner must be configured to tell it where the source code is in the file system. Once this is done and the scanner is switched on then the note's name will be the fully qualified name of the class being scanned appended by ".md". This is an example of the note name :

**crosscut.CrossCuttingConcerns.md**

The file scanned is in this case could be:

**crosscut/CrossCuttingConcerns.scala**

## [](https://github.com/gerrie-myburgh/source-scanner#correlation-of-notes-with-the-user-stories)Correlation of notes with the user stories

It is now possible to correlate the generated document notes with the user stories by selecting the menu option :

**Create solution file**

This will create mapping notes that links the user story notes to the document notes.

### [](https://github.com/gerrie-myburgh/source-scanner#user-stories)User stories.

User stories are given to the developer and he/she can create sub stories from these initial stories. By using markers in the source comments you are able to create cross cutting concerns w.r.t the solution for the story.

The markers for the comments are of the form :

```
( |\t)\^([a-zA-Z0-9]+\-)*[a-zA-Z0-9]+\-[0-9]+
```

An example would be: ^story1-00. Once these markers have been placed in the source comments the system can create mappings between the notes and the stories. The solution files will the look as follows:

![[stories/update-payment-limits/summary of requirement#^summary]]

![[utils.Lexer.md#^story1-00]]

![[Main.md#^story1-02]]

## [](https://github.com/gerrie-myburgh/source-scanner#create-a-table-of-markers)Create a table of markers

Once the markers have been placed in the source files then they are essentially lost to the person that wants to generate the solution notes to the stories notes. To make it easier to see what marker is in what note and in what sequence, functionality is provided to generate a list of all markers along with the note file name they are in.

This should make is easier to update markers in the source code as required. An example of a such a mapping table is

|marker|document|
|---|---|
|story1-00|[[utils.Lexer.md#^story1-00]]|
|story1-02|[[Main.md#^story1-02]]|
|story2-00|[[Main.md#^story2-00]]|

## [](https://github.com/gerrie-myburgh/source-scanner#user-variables-that-can-be-set-in-the-plugin-settings)User variables that can be set in the plugin settings

- Application path : The file path to the application files to be scanned.
- Git branch to scan : The git branch to scan for. It this is not the current branch booked out then the scanner will not scan these booked out files for comments.
- Document path : The path where the notes are to be placed in.
- Application extension : The type of extension the source files have, e.g. for java, .java and so on.
- SleepLength : The duration between scanning the source files in milliseconds.
- Group by size : When the source files are scanned then this is done in batches. Group by size is the batch size.