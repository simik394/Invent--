---
url: https://github.com/shabegom/buttons
qual.README: 80
---
# obsi.plugin.Buttons

GitHub: [shabegom/buttons: Buttons in Obsidian (github.com)](https://github.com/shabegom/buttons)
## 2024-01-16 03:02:52
**last updated:** Sept 28, 2022

---

## [](https://github.com/shabegom/buttons/blob/main/README.md#install)Install

You can find Buttons in the list of community plugins!

## [](https://github.com/shabegom/buttons/blob/main/README.md#usage)Usage

The quickest way to get started with Buttons is to use the Button Maker. You can open the Button Maker from the Command Palette. Here is an overview of the Button Maker options.

- **Name:** The name of your button.
- **Button Type:** Choose which type of button to create your options are:
    - **Command:** Click the Button to run a Command from the Command Palette.
    - **Link:** Click the Button to open a URL or URI.
    - **Calculate:** Click the Button to run a math calculation. Calculate Buttons can reference lines from the note.
    - **Template:** Click the Button to prepend, append, insert, or create a new note from a template note.
    - **Text:** Clock the Button to prepend, append, insert, or create a new note with specified text.
    - **Swap:** A Swap Button is a special type of Inline Button. With a Swap Button you can run a different type of Button on each click.
- **Action:** Depending on what **Button Type** you choose, you will choose an Action to perform:
    - **Command:** Choose the Command Palette Command to run.
    - **Link:** Write the URL or URI.
    - **Calculate:** Write the math equation.
    - **Template:** Choose Prepend, Append, New Note, or Line and the template you want to use:
        - **Prepend Template:** Click the Button to prepend a template into the current note.
        - **Append Template:** Click the Button to append a template into the current note.
        - **Add Template at Line:** Click the Button to add a template into the current note at the specified line.
        - **New Note From Template:** Choose the Template, write the name of the new note, choose whether the new note should open in a split pane.
    - **Text:** Choose Prepend, Append, New Note, or Line and the text you want to use:
        - **Prepend Template:** Click the Button to prepend text into the current note.
        - **Append Template:** Click the Button to append text into the current note.
        - **Add Template at Line:** Click the Button to add text into the current note at the specified line.
        - **New Note From Template:** Write the name of the new note, choose whether the new note should open in a split pane.
    - **Swap:** Write the button-block-ids of the Buttons the Swap Button will be on each click, e.g. `[id1, id2]` (for more information on Swap Buttons, see below).
- **Remove:** You can remove the Button after you click it. You can also remove other Buttons in the note by supplying an array of button-block-ids, e.g. `[id1, id2]`.
- **Replace:** You can remove lines from the existing note which can then be replaced using the **Append Template** or **Prepend Template** Button types. Write an array with the starting and ending line numbers, e.g. `[startingLine, endingLine]`.
- **Inherit:** By adding a button-block-id of another Button, the Button you are making can inherit arguments.
- **Templater:** If the templater arg is `true` you can include a Templater command inside your button. The command will be converted to its value when the button is clicked and converted back to the command after. This cannot be used with Inline Buttons.
- **Custom Class:** Supply a custom CSS class to style your Button.
- **Color:** Choose a Button color.

### [](https://github.com/shabegom/buttons/blob/main/README.md#button-block-id)Button Block ID

The button-block-id is a block-id placed direcly below a Button codeblock and starts with `button`, e.g. `^button-id`. Button-block-ids can be used to:

- Create inline buttons (see below for details on inline buttons) `button-button1`
- Choose which Buttons to use in an Inline Swap Button: `swap [button1, button2]`
- Inherit arguments from another Button: `id button1`
- Remove multiple Buttons with a `remove [button1, button2]` argument

### [](https://github.com/shabegom/buttons/blob/main/README.md#inline-buttons)Inline Buttons

Inline Buttons can be created inline with other text, or other Buttons. An Inline Button is essentially a copy of an existing Button codeblock placed inline. To create an inline button:

1. Create a regular Button using the Button Maker or hand-written Button codeblock.
2. Ensure your Button has a unique button-block-id.
3. Go to the note you want an inline Button and run the Insert Inline Button Command, or write the button-block-id between backticks, e.g. `button-id`.

Inline Buttons must start with `button`, whereas other usages of the button-block-id only require the id.

### [](https://github.com/shabegom/buttons/blob/main/README.md#swap-button)Swap Button

A Swap Button is a special type of Inline Button. When you click a Swap Button it cycles through multiple other Buttons. Use a Swap Button to run a succession of actions with one Button. To Create a Swap Button:

1. Create Buttons that perform the actions you want the Swap Button to do. Ensure each button has a unique button-block-id.
2. Create a Swap Button and supply the button-block-id of the other buttons, e.g. `swap [id1, id2, id3]`. Ensure the Swap Button has a unique button-block-id.
3. Insert the Swap Button as an Inline Button using the Insert Inline Button Command.

Swap Buttons can currently only be used as Inline Buttons.

### [](https://github.com/shabegom/buttons/blob/main/README.md#inherit-button-args)Inherit Button Args

If you are using the same (or similar) Buttons across many notes, you can create one parent Button and have other Buttons inherit from the parent.

1. Create a Parent Button with the arguments you'd like to be inherited. Ensure the Parent Button has a unique button-block-id.
2. Create Child Buttons and supply the Parent Button button-block-id `id parentButton`.

Child Buttons can also have their own arguments. Any argument supplied on the Child supersedes arguments from the Parent Button.

### [](https://github.com/shabegom/buttons/blob/main/README.md#templater-button)Templater Button

The Templater arg allows you to supply a Templater command inside the Button. The command is converted to its value when the Button is clicked and then converted back to the Templater Command for the next click. This is best used with the New Note Button type.

A button with this command…

````
```button
name Make an Hourly Note
type note(<% tp.date.now("HH:MM") %>) template
action Log Template Note
templater true
```
````

…will convert when clicked to:

````
```button
name Make an Hourly Note
type note(16:20) template
action Log Template Note
templater true
```
````

And then `09` will change back to `<% tp.date.now("HH:MM") %>`.

The Templater arg also works with the Text Button type:

````
```button
name Add Current Time
type line(1) text
action <% tp.date.now("HH:mm:ss") %>
replace [1,1]
templater true
```
````

This will insert the current time on line one of the note, replacing any existing text on that line and then convert back to the Templater command for future use.

### [](https://github.com/shabegom/buttons/blob/main/README.md#button-styling)Button Styling

#### [](https://github.com/shabegom/buttons/blob/main/README.md#style-settings)Style Settings

Install the Style Settings plugin for an easy way to change the default Button styling.

#### [](https://github.com/shabegom/buttons/blob/main/README.md#custom-class)Custom Class

If you want a truly custom style, or want Buttons with multiple different styles, you can add a `class` argument in a Button and use a css snippet to style it.

### [](https://github.com/shabegom/buttons/blob/main/README.md#remove-button-after-command-execution)Remove Button after command execution

If you have a Button that only needs to run once and then can be removed from a note (handy for inserting prompts into a Daily Note) you can add a `remove true` argument to your Button.

If you have multiple Buttons in a note and want to remove them all when a Button is clicked, you can supply an array of button-block-ids to the `remove` argument, e.g. `remove [id1, id2, id3]`.

### [](https://github.com/shabegom/buttons/blob/main/README.md#replace-content-in-section)Replace content in section

When using an Append or Prepend Template Button, you may want to remove lines from the existing note which will be replaced by the Template. To do this, write a `replace` argument and supply the first line and last line in an array; e.g. `replace [1, 5]` will remove lines 1 through 5.

## [](https://github.com/shabegom/buttons/blob/main/README.md#examples)Examples

### [](https://github.com/shabegom/buttons/blob/main/README.md#command-button)Command Button

Open the previous day's daily note using the Periodic Notes Plugin:

````
```button
name Open Previous Daily Note
type command
action Periodic Notes: Open previous daily note
```
^button-previous
````

Turn spellcheck on/off:

````
```button
name Toggle spellcheck
type comand
action Toggle spellcheck
color blue
```
^button-spellcheck
````

### [](https://github.com/shabegom/buttons/blob/main/README.md#link-button)Link Button

Open the Obsidian Forum:

````
```button
name To the Forum Batman!
type link
action https://forum.obsidian.md/
```
^button-forum
````

### [](https://github.com/shabegom/buttons/blob/main/README.md#template--line-button)Template & Line Button

#### [](https://github.com/shabegom/buttons/blob/main/README.md#append)Append

Append a Log Template Note:

````
```button
name Log
type append template
action Hourly Log Template Note
```
^button-log
````

Append the current time:

````
```button
name Log
type append text
action <% tp.date.now("HH:mm") %>
templater true
```
````

#### [](https://github.com/shabegom/buttons/blob/main/README.md#prepend-template)Prepend Template

Replace a Weather Template Note with the updated Weather:

````
```button
name Current Weather
type prepend template
action Weather Template Note
replace [1,5]
```
^button-weather
````

Prepend a weekly todo list and remove other buttons:

````
```button
name Monday List
type prepend template
action Monday Template Note
remove [mon,tues,wed]
```
^button-mon

```button
name Tuesday List
type prepend template
action Tuesday Template Note
remove [mon,tues,wed]
```
^button-tues

```button
name Wednesday List
type prepend template
action Wednesday Template Note
remove [mon,tues,wed]
```
^button-wed
````

Even better, set up those buttons and then add them all on one line as Inline Buttons:

```
`button-mon` `button-tues` `button-wed`
```

### [](https://github.com/shabegom/buttons/blob/main/README.md#add-template-at-line)Add Template at Line

Say you want the weather to appear at a specific place in your note that isn't directly beside the button:

````
```button
name Current Weather
type line(1) template
action Weather Template Note
replace [1,5]
```
^button-weatherLine
````

#### [](https://github.com/shabegom/buttons/blob/main/README.md#new-note-from-template)New Note From Template

Create a new note for an upcoming meeting based on a Meeting Note Template:

````
```button
name New Meeting
type note(Meeting, split) note
action Meeting Note Template
```
^button-meeting
````

Dynamically add the hour and minute to the note title:

````
```button
name New Meeting
type note(Meeting-<%tp.date.now("HH-MM") %>, split) note
action Meeting Note Template
templater true
```
^button-meeting2
````

### [](https://github.com/shabegom/buttons/blob/main/README.md#calculate-button)Calculate Button

Do some simple math:

````
```button
name Add Em Up
type calculate
action 2+2
```
^button-add
````

Reference numbers outside of the Button:

````
Bananas Have: 5  
Bananas Lost: 5

```button
name How Many Bananas Today?
type calculate
action $1-$2
color yellow
```
^button-bananas
````

Natural Language Math:

````
5 dogs plus 2 cats divided by 2 people

```button
name Who Get The Pets?
type calculate
action $1
class sad-button
```
^button-breakup
````

The calculate button uses [math-expression-evaluator](https://github.com/bugwheels94/math-expression-evaluator), so it should support any symbol supported by that library.

### [](https://github.com/shabegom/buttons/blob/main/README.md#swap-buttons)Swap Buttons

Let's create a Swap Button using the button-block-id of previous Buttons:

````
```button
name Crazy Swap Button
swap [add,meeting,forum]
```
^button-swap
````

Then insert that button inline:

```
`button-swap`
```

1. On the first click of Crazy Swap Button we will add 2+2.
2. On the second click of Crazy Swap Button we will create a new Meeting note.
3. On the third click of the Crazy Swap Button we will go to the Obsidian forum.

Note: swap count is reset if you close the note.

## [](https://github.com/shabegom/buttons/blob/main/README.md#releases)Releases

### [](https://github.com/shabegom/buttons/blob/main/README.md#next-version-not-released-yet)Next version (not released yet)

- Bugfix: buttons now render in Live Preview mode when Obsidian starts ([Lx](https://github.com/Lx))

### [](https://github.com/shabegom/buttons/blob/main/README.md#044)0.4.4

- Bugfix: blue and purple colors should now work
- Bugfix: reduced the height of the Button Maker for smaller displays

### [](https://github.com/shabegom/buttons/blob/main/README.md#043)0.4.3

- New Line Template Button: insert a template into the current note at a specified line

### [](https://github.com/shabegom/buttons/blob/main/README.md#042)0.4.2

- Scrollable Button Maker
- Add custom button-block-id inside the Button Maker

### [](https://github.com/shabegom/buttons/blob/main/README.md#040)0.4.0

- Inline Buttons! You can add buttons inline using the button block-id (^button-id) using this syntax `button-id`
- Insert Inline Button: Use **Insert Inline Button** from the command palette to quickly insert a new inline button
- Button Maker: Open the Button Maker from the command palette to quickly and easily create a new button
- New Button Arg - `swap`: use the `swap [id1, id2, id3]` arg along with an inline button to create a button that performs multiple actions on each click
- New Button Arg - `templater`: the templater arg allows you to put a templater command inside a button. When the button is clicked the templater command is converted to it's value and then is converted back to the templater command: `note(<% tp.date.now("MM-DD") %>) template`

### [](https://github.com/shabegom/buttons/blob/main/README.md#032)0.3.2

- Fix the uncaught Type Error if there are no button block-ids in the vault
- Fix the position error if not on insiders build

### [](https://github.com/shabegom/buttons/blob/main/README.md#030)0.3.0

- You can add a block-id below a button block. The button block-id can be used to inherit arguments from a button or to remove multiple buttons
- `remove` can now be an array of button block-ids to remove (it can still be true to remove the clicked button)
- `replace` now takes an array like [startLine,endLine] to define the start and end line to be replaced.
- `append`, `prepend`, `remove`, `replace` have been updated to use the button position. `name` is no longer required.

### [](https://github.com/shabegom/buttons/blob/main/README.md#0210)0.2.10

- Bugfix: new notes created by a template can now have `-` and `!` and other characters in their title.

### [](https://github.com/shabegom/buttons/blob/main/README.md#029)0.2.9

- You can open a note created via template type button in a split pane by using `note(Note Name, split) template`

### [](https://github.com/shabegom/buttons/blob/main/README.md#028)0.2.8

- You can now have the core Templates plugin disabled if you are using Templater. You still need to define a Templates folder

### [](https://github.com/shabegom/buttons/blob/main/README.md#026)0.2.6

- Bugfix for converting button values to lowercase
- add some padding around the button

### [](https://github.com/shabegom/buttons/blob/main/README.md#024)0.2.4

- Add a command palette command to add a button codeblock to a note
- Set default button styles with Style Settings plugin

### [](https://github.com/shabegom/buttons/blob/main/README.md#023-calculate-button-type)0.2.3: Calculate button type

- Added a `calculate` button type that can do maths and output results
- `calculate` can reference numbers outside the button by their line number
- Bug Fix: Removed extra whitespace when using the append action
- Bug Fix: Button names are now escaped in regex which prevents an error when adding content to a note

### [](https://github.com/shabegom/buttons/blob/main/README.md#022-remove-logging)0.2.2: Remove logging

- Remove mobile logging that was accidentally included in the previous release

### [](https://github.com/shabegom/buttons/blob/main/README.md#021-styling-update)0.2.1: Styling update

- Updated default button styling

### [](https://github.com/shabegom/buttons/blob/main/README.md#020-add-replace-argument-and-note-template-feature)0.2.0: Add replace argument and note() template feature

- Removed the shine hover effect because it looked crummy on movible
- Added a `replace` argument that replaces content between a specified header and the button
- Added a `note() template` feature that will create a new note based on a specified template

### [](https://github.com/shabegom/buttons/blob/main/README.md#011-released-to-community-plugins)0.1.1: Released to Community Plugins!

- Buttons is now available in the list of community plugins within Obsidian

### [](https://github.com/shabegom/buttons/blob/main/README.md#010-add-template-feature)0.1.0: Add template feature

- Added the `template` button type
- prepend or append a specified template into a note

### [](https://github.com/shabegom/buttons/blob/main/README.md#005-add-remove-feature)0.0.5: Add remove feature

- Added a `remove` argument. If `remove true` is the last argument in a button the button will be removed from the note after it is clicked.

### [](https://github.com/shabegom/buttons/blob/main/README.md#004-updated-styling)0.0.4: Updated Styling

**This release includes a breaking change from the previous release (0.0.3)**

- customClass argument is now class
- customId argument is now id
- Adding a class argument will remove default button styling. You can add that styling back by including the class names as values to the class argument:  
    `class button-default button-shine`

### [](https://github.com/shabegom/buttons/blob/main/README.md#003-add-customid-argument)0.0.3: Add `customId` argument

- Added `customId` to further customize button styles

### [](https://github.com/shabegom/buttons/blob/main/README.md#002-add-customclass-argument)0.0.2: Add `customClass` argument

- Added `customClass` to define your own class for button stylinh

### [](https://github.com/shabegom/buttons/blob/main/README.md#001-initial-release)0.0.1: Initial Release

- The first release of Buttons!

shabegom/buttons on May 28, 2023 Seeking Maintainer(s) #179 I no longer have time to maintain Buttons. There is a half finished update that needs… Press escape to close this hovercard

Outline

[

](https://app.maxai.me/)[

](https://app.maxai.me/pricing)[

](https://app.maxai.me/rewards)