---
tags:
  - installed
---
GitHub: [https://github.com/Taitava/obsidian-shellcommands](https://github.com/Taitava/obsidian-shellcommands)
Docs: [Index - Shell commands documentation - Obsidian Publish](https://publish.obsidian.md/shellcommands/Index)

# README
This plugin lets you define shell/terminal commands in settings and run them quickly via Obsidian's command palette, or via hotkeys. Use note related variables as part of the commands, and insert output back to your notes, if you wish. This is a Swiss army knife when it comes to accessing external applications from Obsidian, and you are the one who defines its tools.

You can customise your commands with built-in variables that can provide the current file title/name/path, current file's parent folder name/path, and date/time stamp with a custom format.

[A changelog is available in a separate file.](https://github.com/Taitava/obsidian-shellcommands/blob/main/CHANGELOG.md)

**WARNING:** Be careful with system commands! Only use commands that you know and trust. If you are copying and pasting commands from the internet or from files written by other people, you need to understand precisely what those commands do! Otherwise, you might lose your files, or screw up your system!

Linux: **[If you have installed Obsidian using Flatpak, shell commands are executed in an isolated environment, which may cause unexpected behaviour or error messages.](https://github.com/Taitava/obsidian-shellcommands/discussions/225)** Please consider other installation options.

**The plugin is still in its early development stage.** Use at your own risk, and note that when you upgrade the plugin, things may break.

**This plugin doesn't come with any kind of warranty in case it does something bad to your files!** If you know programming, [check the source code in GitHub](https://github.com/Taitava/obsidian-shellcommands) so you know how it executes commands.

## Main issues

- **Windows & PowerShell: Non-English characters can be corrupted in output**. Input _might_ work ok. Read more: #157. Linux and Mac users should not have this issue.
- Special characters in `{{variable}}` values are escaped (except if CMD.EXE is used as a shell), but it's **still experimental**. Potential escaping problems can be dangerous. [Documentation about how special characters are escaped in variable values](https://publish.obsidian.md/shellcommands/Variables/Escaping+special+characters+in+variable+values). Edit 2022-03-11: Now that the escaping system has been in use for a few months, it seems that it works quite nicely. However, more experience is still welcome. Edit 2022-06-10: Changed the link to point to documentation that contains newer information than [issue #11](https://github.com/Taitava/obsidian-shellcommands/issues/11).
- **No mobile support**, because the plugin uses NodeJS's `child_process`, so I've flagged this plugin as desktop only. I do not have any plans at the moment to research an ability to make this work on mobile. If you have some clues, please start a discussion in GitHub.

For future ideas, see the [Discussions section](https://github.com/Taitava/obsidian-shellcommands/discussions).

## Installation & usage

1. Search for this plugin in Obsidian's community plugins settings panel.
2. Click Install, and after that **remember to click Enable**!
3. Head to _Shell commands_ settings tab.
4. All commands will be run in a certain directory. By default, it's your vault's base directory. If you want to run the commands in some other directory, you can type it in the _Working directory_ field.
5. Define one or more commands by clicking the _New command_ button and entering a command. Read variable usage instructions in the settings panel if you need them.
6. For advanced settings, such as a command alias name that appears in the command palette instead of the actual shell command, or an ability to direct command output to a currently active note, click a small gear icon next to the shell command.
7. All commands that you have defined, will be added to Obsidian's command palette. You can execute them from there (by hitting `Ctrl/Cmd + P` and searching for your command) or you can define a hotkey for each individual command in Obsidian's Hotkeys settings tab.

## Extensive documentation

... is available right here: [https://publish.obsidian.md/shellcommands](https://publish.obsidian.md/shellcommands)

## Usage examples

Example shell commands have been moved to: [https://publish.obsidian.md/shellcommands/Example+shell+commands/Example+shell+commands](https://publish.obsidian.md/shellcommands/Example+shell+commands/Example+shell+commands)

## Escaping special characters in variable values

(Todo: check that the Documentation has all this content, and then remove this section from README.md.)

Note that special characters (= anything else than letters, numbers and underscores `_`) are automatically escaped in variable values. Escaping depends on the shell that you use, but generally speaking, each special character is prefixed with an escape character, which might be `\`, ` or `%` depending on shell.

**Without escaping**, if you would have a command and a quoted string parameter like `mycommand {{clipboard}}`, it might break if your clipboard content contains `>` characters, because those would be inserted into the command as-is. Your command might end up looking like this: `mycommand Text pasted from clipboard that contains a > character.` The `>` character would redirect output to a file and might overwrite an important file. That's why escaping is in place, making the aforementioned command look like this: `mycommand\ Text\ pasted\ from\ clipboard\ that\ contains\ a\ \>\ character\.` (when the shell is Bash). Your shell then parses the escaped special characters and uses them as literal letters, not as special characters.

If you want to avoid escaping special characters in variable values, you can use `{{!variable}}` syntax, meaning that you can add an exclamation mark `!` in the front of a variable's name. Note that this can be dangerous, and you need to understand very well what you are doing if you use this kind of raw, unescaped variable values! In most situations, you should be able to use escaped variables really well.

## Benefits from other plugins

Not a single plugin can be great just by itself. And not a single plugin suits every situation. Here I'm collecting a list of plugins that can be good companions or good alternatives to _Shell commands_.

- **[Advanced URI](https://github.com/Vinzent03/obsidian-advanced-uri)**: You can use this to open other vaults, switch workspaces without using a graphical user interface, and append content to notes, etc. Example command to insert clipboard content into a note with a shell command: `start "" obsidian://advanced-uri?vault=Vault_name&filepath=Filename.md&data={{clipboard}}&mode=append` (on Windows). Another way, without _Advanced URI_, is to use something like `echo {{clipboard}} >> Filename.md` (on Windows).
- **[cMenu](https://github.com/chetachiezikeuzor/cMenu-Plugin)**: When you select text, this plugin opens a small modal of buttons for text formatting and other actions. You can add shell commands to the mix!
- **[Customizable Sidebar](https://github.com/phibr0/obsidian-customizable-sidebar)**: Allows you to add new left side menu icons that fire what ever Obsidian command you want - including shell commands!
- **[QuickAdd](https://github.com/chhoumann/quickadd)**: You can create macros that launch multiple commands at once. Sure, in _Shell commands_, you can have multiple terminal commands executed one after another (with `&&` operator for Linux and Mac, and `&` operator for Windows), but _QuickAdd_ allows you to have macros that combine shell commands to other Obsidian commands.
- **[Text Expander](https://github.com/konodyuk/obsidian-text-expander)**: If you want to write codeblocks in your markdown note files and execute them, then _Text Expander_ is the solution for you. _Shell commands_ focuses on bringing short, rarely changed terminal commands at your fingertips via hotkeys. You can run longer scripts with _Shell commands_ too by writing them into a bash/batch file and executing that file as a command, but if you need to view the script before executing it, or make changes regularly, then _Shell commands_ is not so optimal for your situation, and you might benefit more from _Text Expander_. But of course, you can also have both if you like.