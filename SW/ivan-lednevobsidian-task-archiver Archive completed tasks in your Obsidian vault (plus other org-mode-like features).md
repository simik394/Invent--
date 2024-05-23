---
page-title: "ivan-lednev/obsidian-task-archiver: Archive completed tasks in your Obsidian vault (plus other org-mode-like features)"
url: https://github.com/ivan-lednev/obsidian-task-archiver
date: "2024-04-08 20:10:12"
tags: 
- A/sw/plugin
- F/homepage
- C/
- P/
about: "[[Obsidian]]"
aliases: 
- 8d1c6001-805b-4260-9672-3b329dbac900
- ivan-lednev/obsidian-task-archiver: Archive completed tasks in your Obsidian vault (plus other org-mode-like features)
by: 
length: 5437
dir: 
---

This plugin is a toolbox for working with completed tasks in your markdown files. It brings some of [org-mode's](https://orgmode.org/) features to Obsidian.

-   [Contribution](https://github.com/ivan-lednev/obsidian-task-archiver#contribution)
-   [Commands](https://github.com/ivan-lednev/obsidian-task-archiver#commands-)
-   [Settings](https://github.com/ivan-lednev/obsidian-task-archiver#settings)
    -   [Placeholders](https://github.com/ivan-lednev/obsidian-task-archiver#placeholders)
    -   [Archive file path](https://github.com/ivan-lednev/obsidian-task-archiver#archive-file-path)
    -   [Replacing text before archiving](https://github.com/ivan-lednev/obsidian-task-archiver#replacing-text-before-archiving)
    -   [Append stuff before archiving](https://github.com/ivan-lednev/obsidian-task-archiver#append-stuff-before-archiving)
    -   [Additional patterns to detect completed tasks](https://github.com/ivan-lednev/obsidian-task-archiver#additional-patterns-to-detect-completed-tasks)
    -   [Heading & list hierarchies](https://github.com/ivan-lednev/obsidian-task-archiver#heading--list-hierarchies)
    -   [Rules](https://github.com/ivan-lednev/obsidian-task-archiver#rules)
-   [Usage](https://github.com/ivan-lednev/obsidian-task-archiver#usage)
-   [Acknowledgements](https://github.com/ivan-lednev/obsidian-task-archiver#acknowledgements)
    -   [Contributors](https://github.com/ivan-lednev/obsidian-task-archiver#contributors)
-   [Development](https://github.com/ivan-lednev/obsidian-task-archiver#development)

## Contribution

[](https://github.com/ivan-lednev/obsidian-task-archiver#contribution)

If you noticed a bug or thought of some way to improve the plugin, feel free to create an issue: [https://github.com/ivan-lednev/obsidian-task-archiver/issues](https://github.com/ivan-lednev/obsidian-task-archiver/issues).

Pull-requests are also welcome! If you want to contribute but don't know where to start, you can create an issue or write me an email: [bishop1860@gmail.com](mailto:bishop1860@gmail.com).

You can also support me by buying me a coffee:

[![Buy Me A Coffee](https://camo.githubusercontent.com/cace41b0afc90c68d0207e2bd809ee121f9ff4f72ac032e8ced972aee7adbb23/68747470733a2f2f63646e2e6275796d6561636f666665652e636f6d2f627574746f6e732f76322f64656661756c742d79656c6c6f772e706e67)](https://www.buymeacoffee.com/machineelf)

## Commands

[](https://github.com/ivan-lednev/obsidian-task-archiver#commands-)

Archive tasks in this file

Here is what it looks like:

\-   \[ \] This one I haven't done yet
\-   \[x\] Water the dog
    \-   Some task details
\-   \[x\] Feed the plants

Turns into:

\-   \[ \] This one I haven't done yet

\# Archived

\-   \[x\] Water the dog
    \-   Some task details
\-   \[x\] Feed the plants

Or, with date tree enabled:

\-   \[ \] This one I haven't done yet

\# Archived

\-   \[\[2021-09-W-38\]\]
    \-   \[\[2021-09-16\]\]
        \-   \[x\] Water the dog
            \-   Some task details
        \-   \[x\] Feed the plants

Archive tasks including nested tasks in this file

Same as simple archiving, except that now completed nested tasks also get archived, with their sub-items.

This:

\-   \[ \] Incomplete task
    \-   \[x\] Completed subtask
        \-   Task details
    \-   \[ \] Incomplete subtask

Turns into:

\-   \[ \] Incomplete task
    \-   \[ \] Incomplete subtask

\# Archived

\-   \[x\] Completed subtask
    \-   Task details

Delete tasks in this file

This one is the same as 'Archive tasks in this file', except that the tasks get discarded.

Archive heading under cursor

Grab the whole section under the heading under cursor, including all the child sections and move it to the archive.

This:

Some top-level text

\# H1 heading

Some text

\## H2 heading

More text

Turns into:

Some top-level text

\# Archived

\## H1 heading

Some text

\### H2 heading

More text

Sort tasks in list under cursor

Grab the whole list under cursor and **recursively** reorder all the items based on completeness:

1.  Plain list items first
2.  Then, incomplete tasks
3.  And finally, completed tasks

This list:

\-   \[x\] Task
\-   Item
\-   \[ \] Incomplete
    \-   \[x\] Task
    \-   Item More notes
    \-   \[ \] Incomplete
\-   Item 2
\-   \[ \] Incomplete 2
    \-   \[x\] Task
    \-   Item
    \-   \[x\] Task 2

Turns into:

\-   Item
\-   Item 2
\-   \[ \] Incomplete
    \-   Item More notes
    \-   \[ \] Incomplete
    \-   \[x\] Task
\-   \[ \] Incomplete 2
    \-   Item
    \-   \[x\] Task
    \-   \[x\] Task 2
\-   \[x\] Task

Toggle task under cursor done and archive it

When the cursor is on a task, this command completes the task and archives it at once.

## Settings

[](https://github.com/ivan-lednev/obsidian-task-archiver#settings)

There are a lot of settings to help you build a suitable workflow.

### Placeholders

[](https://github.com/ivan-lednev/obsidian-task-archiver#placeholders)

You can use several placeholders throughout the settings to build cool workflows. Those get resolved to different values when you run the archiver:

-   `{{date}}`
    -   Points to today
-   `{{obsidianTasksCompletedDate}}`
    -   Points to the completed date on the task (✅ 2023-03-29). This way you can archive tasks created with the `obsidian-tasks` plugin where they belong
-   `{{sourceFileName}}`
    -   Resolves to the base name of the file you're in
-   `{{sourceFilePath}}`
    -   Resolves to the path from the root of the vault to the file you're in
-   `{{heading}}`
    -   Points to the heading above the task
-   `{{headingChain}}`)
    -   Creates a chain from headings above the task. E.g. `Project 1 > Team 2`

### Archive file path

[](https://github.com/ivan-lednev/obsidian-task-archiver#archive-file-path)

You can send tasks to the same file or to a separate file, say, to a daily note, or to some path based on the name of the file you're in.

### Replacing text before archiving

[](https://github.com/ivan-lednev/obsidian-task-archiver#replacing-text-before-archiving)

A regular expression for replacing the contents of the task during archiving; this is useful if you want to strip tags from archived tasks.

### Append stuff before archiving

[](https://github.com/ivan-lednev/obsidian-task-archiver#append-stuff-before-archiving)

This might be useful if you want to see what you accomplished in a day: [![](https://github.com/ivan-lednev/obsidian-task-archiver/raw/master/metadata-demo.png)](https://github.com/ivan-lednev/obsidian-task-archiver/blob/master/metadata-demo.png)

### Additional patterns to detect completed tasks

[](https://github.com/ivan-lednev/obsidian-task-archiver#additional-patterns-to-detect-completed-tasks)

This way you can archive only those tasks that match a pattern and leave the rest of them alone. Say, you only want to archive tasks with a global filter used by the `obsidian-tasks` plugin (like the tag `#task`).

### Heading & list hierarchies

[](https://github.com/ivan-lednev/obsidian-task-archiver#heading--list-hierarchies)

You can create arbitrary hierarchies with placeholders both with headings and with list items. New archived tasks are going to be merged into existing trees.

You can use this feature to create a date tree in your archive: [![](https://github.com/ivan-lednev/obsidian-task-archiver/raw/master/tree-demo.png)](https://github.com/ivan-lednev/obsidian-task-archiver/blob/master/tree-demo.png)

Or you can create a single archive file with links to sources in headings: [![](https://github.com/ivan-lednev/obsidian-task-archiver/raw/master/tree-demo-big-archive.png)](https://github.com/ivan-lednev/obsidian-task-archiver/blob/master/tree-demo-big-archive.png)

### Rules

[](https://github.com/ivan-lednev/obsidian-task-archiver#rules)

Rules allow you to customize how you treat tasks that match certain conditions: [![](https://github.com/ivan-lednev/obsidian-task-archiver/raw/master/rule-demo.png)](https://github.com/ivan-lednev/obsidian-task-archiver/blob/master/rule-demo.png)

Potentially rules can specify any custom workflow for any set of tasks that match certain conditions. If you'd like to see some additional features here, feel free to create a feature request!

## Usage

[](https://github.com/ivan-lednev/obsidian-task-archiver#usage)

Open the command palette and run one of the archiver [commands](https://github.com/ivan-lednev/obsidian-task-archiver#commands).

## Acknowledgements

[](https://github.com/ivan-lednev/obsidian-task-archiver#acknowledgements)

This plugin is an implementation of some features of [org-mode](https://orgmode.org/) for Emacs.

Also, I relied on the code from these excellent plugins:

-   [obsidian-kanban](https://github.com/mgmeyers/obsidian-kanban)
-   [obsidian-outliner](https://github.com/vslinko/obsidian-outliner). This plugin is a beauty in terms of architecture and code quality
-   [obsidian-commander](https://github.com/phibr0/obsidian-commander). Helped me figure out how to use a reactive framework to build a settings page

### Contributors

[](https://github.com/ivan-lednev/obsidian-task-archiver#contributors)

-   Richard Cook ([wealthychef@gmail.com](mailto:wealthychef@gmail.com))

## Development

[](https://github.com/ivan-lednev/obsidian-task-archiver#development)

-   [Solid.js](https://www.solidjs.com/) is used for the settings page.