

# 1. Intro
[src](https://developers.google.com/codelabs/apps-script-fundamentals-3#0)
_subject_Last updated Apr 4, 2022
_account_circle_Written by Google Workspace Developer Relations

Welcome to the third part of the Fundamentals of Apps Script with Google Sheets codelab playlist.

By completing this codelab, you can learn how to use data manipulation, [custom menus](https://developers.google.com/apps-script/guides/menus), and public API data retrieval in Apps Script to improve your Sheets' experience. You'll continue working with the [**`SpreadsheetApp`**](https://developers.google.com/apps-script/reference/spreadsheet/spreadsheet-app), [**`Spreadsheet`**](https://developers.google.com/apps-script/reference/spreadsheet/spreadsheet), [**`Sheet`**](https://developers.google.com/apps-script/reference/spreadsheet/sheet), and [**`Range`**](https://developers.google.com/apps-script/reference/spreadsheet/range) classes the previous codelabs in this playlist introduced.

## What you'll learn

- How to import data from a personal or shared spreadsheet in Drive.
- How to create a custom menu with the [`onOpen()`](https://developers.google.com/apps-script/guides/triggers/#onopene) function.
- How to parse and manipulate string data values in Google Sheet cells.
- How to pull and manipulate [JSON](https://www.json.org/) object data from a public API source.

## Before you begin

This is the third codelab in the Fundamentals of Apps Script with Google Sheets playlist. Before starting this codelab, be sure to complete the previous codelabs:

1. [Macros and Custom Functions](https://codelabs.developers.google.com/codelabs/apps-script-fundamentals-1)
2. [Spreadsheets, Sheets, and Ranges](https://codelabs.developers.google.com/codelabs/apps-script-fundamentals-2)

## What you'll need

- An understanding of the basic Apps Script topics explored in the previous codelabs of this playlist.
- Basic familiarity with the Apps Script editor
- Basic familiarity with [Google Sheets](https://www.google.com/sheets/about/)
- Ability to read Sheets [A1 Notation](https://developers.google.com/sheets/api/guides/concepts#a1_notation)
- Basic familiarity with JavaScript and its [**`String`** class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)

# 2. Set up
The exercises in this codelab require a spreadsheet to work in. Follow these steps to create a spreadsheet to use in these exercises:

1. Create a spreadsheet in your Google Drive. You can do this from the [Drive interface](https://drive.google.com/drive/my-drive) by selecting **New > Google Sheets**. This creates and opens your new spreadsheet. The file is saved to your Drive folder.
2. Click the spreadsheet title and change it from "Untitled spreadsheet" to "Data Manipulation and Custom Menus". Your sheet should look like this:

![545c02912de7d112.png](https://developers.google.com/static/codelabs/apps-script-fundamentals-3/img/545c02912de7d112.png)

3. To open the script editor, click **Extensions**> **Apps Script**
4. Click the Apps Script project title and change it from "Untitled Project" to "Data Manipulation and Custom Menus." Click **Rename** to save the title change.

With a blank spreadsheet and project, you're ready to start the lab. Move to the next section to start learning about custom menus.

**Note:** If you're using a [gmail.com](http://gmail.com/) account, you might get a "This app isn't verified" dialog when you first use your script. Google uses this to warn users who may be using code from unknown or untrusted authors. If you see this dialog, it's OK to proceed since you're the script author. Follow the on-screen prompts to continue authorizing the script:

1. In the unverified app dialog, click **Advanced**.
2. Click **Go to Data Manipulation and Custom Menus (unsafe)**.
3. Click **Allow**.

Throughout this codelab, you might get several permission prompts. You can read more about this process in [Authorization for Google Services](https://developers.google.com/apps-script/guides/services/authorization).
# 3. Overview: Import data with a custom menu item
[src](https://developers.google.com/codelabs/apps-script-fundamentals-3#2)

Apps Script gives you the ability to define [custom menus](https://developers.google.com/apps-script/guides/menus) that can appear in Google Sheets. You can also use custom menus in Google Docs, Google Slides, and Google Forms. When you define a custom menu item, you create a text label and connect it to an Apps Script function in your script project. You can then add the menu to the UI so it appears in Google Sheets:

![d6b694da6b8c6783.png](https://developers.google.com/static/codelabs/apps-script-fundamentals-3/img/d6b694da6b8c6783.png)

When a user clicks a custom menu item, the Apps Script function you associated with it executes. This is a quick way of running Apps Script functions without having to open the script editor. It also allows other users of the spreadsheet to execute your code without having to know anything about how it or how Apps Script works. For them, it's just another menu item.

Custom menu items are defined in the [**`onOpen()`**](https://developers.google.com/apps-script/guides/triggers/#onopene) _simple trigger_ function, which you'll learn about in the next section.

# 4
[Fundamentals of Apps Script with Google Sheets #3: Working with Data  |  Google for Developers](https://developers.google.com/codelabs/apps-script-fundamentals-3#4)

# 5


# 6


# 7


# 8


# 9


# 10


# 11


# 12


# 13
