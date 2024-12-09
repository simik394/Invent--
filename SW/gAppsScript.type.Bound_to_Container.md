A script is bound to a Google Sheets, Docs, Slides, or Forms file if it was created from that document rather than as a [standalone script](https://developers.google.com/apps-script/guides/standalone?authuser=0). The file that a bound script is attached to is called a "container.
Bound scripts generally behave like standalone scripts except that they do not appear in Google Drive, they cannot be detached from the file they are bound to, and they gain a few special privileges over the parent file.

> [!NOTE]
> Bound scripts are effectively unpublished [add-ons](https://developers.google.com/workspace/add-ons/concepts/types?authuser=0#editor_add-ons) that function only for the file they are bound to.
## Create a bound script

### Google Docs, Sheets, or Slides

To create a bound script in Google Docs, Sheets, or Slides, open a document in Docs, a spreadsheet in Sheets, or a presentation in Slides and click **Extensions** > **Apps Script**. To reopen the script in the future, do the same thing or open the script from the [Apps Script dashboard](https://script.google.com/home?authuser=0).
### Google Forms

To create a bound script in Google Forms, open a form and click More more_vert > **Script editor**. To reopen the script in the future, do the same thing or open the script from the [Apps Script dashboard](https://script.google.com/home?authuser=0).

> [!NOTE]
> The [`clasp`](https://developers.google.com/apps-script/guides/clasp?authuser=0) tool can't create bound scripts, but it can clone and edit them.

## Special methods

Bound scripts can call a few methods that standalone scripts cannot:

- [`getActiveSpreadsheet()`](https://developers.google.com/apps-script/reference/spreadsheet/spreadsheet-app?authuser=0#getActiveSpreadsheet()), [`getActiveDocument()`](https://developers.google.com/apps-script/reference/document/document-app?authuser=0#getActiveDocument()), [`getActivePresentation()`](https://developers.google.com/apps-script/reference/slides/slides-app?authuser=0#getactivepresentation), and [`getActiveForm()`](https://developers.google.com/apps-script/reference/forms/form-app?authuser=0#getActiveForm()) allow bound scripts to refer to their parent file without referring to the file's ID.
- [`getUi`](https://developers.google.com/apps-script/reference/spreadsheet/spreadsheet-app?authuser=0#getUi()) lets bound scripts access the user interface for their parent file to add [custom menus, dialogs, and sidebars](https://developers.google.com/apps-script/guides/bound?authuser=0#custom_menus_dialogs_and_sidebars).
- In Google Sheets, [`getActiveSheet()`](https://developers.google.com/apps-script/reference/spreadsheet/spreadsheet-app?authuser=0#getActiveSheet()), [`getActiveRange()`](https://developers.google.com/apps-script/reference/spreadsheet/spreadsheet-app?authuser=0#getActiveRange()), and [`getActiveCell()`](https://developers.google.com/apps-script/reference/spreadsheet/sheet?authuser=0#getActiveCell()) let the script determine the user's current sheet, selected range of cells, or selected individual cell. [`setActiveSheet(sheet)`](https://developers.google.com/apps-script/reference/spreadsheet/spreadsheet-app?authuser=0#setActiveSheet(Sheet)) and [`setActiveRange(range)`](https://developers.google.com/apps-script/reference/spreadsheet/spreadsheet-app?authuser=0#setActiveRange(Range)) let the script change those selections.
- In Google Docs, [`getCursor()`](https://developers.google.com/apps-script/reference/document/document?authuser=0#getCursor()) and [`getSelection()`](https://developers.google.com/apps-script/reference/document/document?authuser=0#getSelection()) let the script determine the position of the user's cursor or selected text. [`setCursor(position)`](https://developers.google.com/apps-script/reference/document/document?authuser=0#setCursor(Position)) and [`setSelection(range)`](https://developers.google.com/apps-script/reference/document/document?authuser=0#setSelection(Range)) let the script change those locations.

> [!NOTE]
> These methods are only available to bound scripts run from the script editor, menu items, dialogs, sidebars, or triggers. When a bound script is run as a web app or via the [Apps Script API](https://developers.google.com/apps-script/api/how-tos/execute?authuser=0), these methods are not available.
> For more information, see the [guide to extending Google Sheets](https://developers.google.com/apps-script/guides/sheets?authuser=0) or the [guide to extending Google Docs](https://developers.google.com/apps-script/guides/docs?authuser=0).
