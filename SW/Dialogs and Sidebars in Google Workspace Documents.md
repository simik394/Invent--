---
src: https://developers.google.com/apps-script/guides/dialogs
tags: []
-> Project: "[[BP.Podklady]]"
---
Scripts that are [bound](https://developers.google.com/apps-script/scripts_containers) to Google Docs, Sheets, or Forms can display several types of user-interface elements — pre-built alerts and prompts, plus dialogs and sidebars that contain custom [HTML service](https://developers.google.com/apps-script/guides/html) pages. Typically, these elements are opened from [menu items](https://developers.google.com/apps-script/guides/menus). (Note that in Google Forms, user-interface elements are visible only to an editor who opens the form to modify it, not to a user who opens the form to respond.)

## Alert dialogs

![](https://developers.google.com/static/apps-script/images/alert.png)

An alert is a pre-built dialog box that opens inside a Google Docs, Sheets, Slides, or Forms editor. It displays a message and an "OK" button; a title and alternative buttons are optional. It is similar to calling [`window.alert()`](https://developer.mozilla.org/en-US/docs/Web/API/window.alert) in client-side JavaScript within a web browser.

Alerts suspend the server-side script while the dialog is open. The script resumes after the user closes the dialog, but [JDBC](https://developers.google.com/apps-script/guides/jdbc) connections do not persist across the suspension.

As shown in the example below, Google Docs, Forms, Slides, and Sheets all use the method [`Ui.alert()`](https://developers.google.com/apps-script/reference/base/ui#alert(String)), which is available in three variants. To override the default "OK" button, pass a value from the [`Ui.ButtonSet`](https://developers.google.com/apps-script/reference/base/button-set) enum as the `buttons` argument. To evaluate which button the user clicked, compare the return value for `alert()` to the [`Ui.Button`](https://developers.google.com/apps-script/reference/base/button) enum.

```
function onOpen() {  SpreadsheetApp.getUi() // Or DocumentApp or SlidesApp or FormApp.      .createMenu('Custom Menu')      .addItem('Show alert', 'showAlert')      .addToUi();}function showAlert() {  var ui = SpreadsheetApp.getUi(); // Same variations.  var result = ui.alert(     'Please confirm',     'Are you sure you want to continue?',      ui.ButtonSet.YES_NO);  // Process the user's response.  if (result == ui.Button.YES) {    // User clicked "Yes".    ui.alert('Confirmation received.');  } else {    // User clicked "No" or X in the title bar.    ui.alert('Permission denied.');  }}
```

## Prompt dialogs

![](https://developers.google.com/static/apps-script/images/prompt.png)

A prompt is a pre-built dialog box that opens inside a Google Docs, Sheets, Slides, or Forms editor. It displays a message, a text-input field, and an "OK" button; a title and alternative buttons are optional. It is similar to calling [`window.prompt()`](https://developer.mozilla.org/en-US/docs/Web/API/window.prompt) in client-side JavaScript within a web browser.

Prompts suspend the server-side script while the dialog is open. The script resumes after the user closes the dialog, but [JDBC](https://developers.google.com/apps-script/guides/jdbc) connections do not persist across the suspension.

As shown in the example below, Google Docs¸ Forms, Slides, and Sheets all use the method [`Ui.prompt()`](https://developers.google.com/apps-script/reference/base/ui#prompt(String)), which is available in three variants. To override the default "OK" button, pass a value from the [`Ui.ButtonSet`](https://developers.google.com/apps-script/reference/base/button-set) enum as the `buttons` argument. To evaluate the user's response, capture the return value for `prompt()`, then call [`PromptResponse.getResponseText()`](https://developers.google.com/apps-script/reference/base/prompt-response#getResponseText()) to retrieve the user's input, and compare the return value for [`PromptResponse.getSelectedButton()`](https://developers.google.com/apps-script/reference/base/prompt-response#getSelectedButton()) to the [`Ui.Button`](https://developers.google.com/apps-script/reference/base/button) enum.

```
function onOpen() {  SpreadsheetApp.getUi() // Or DocumentApp or SlidesApp or FormApp.      .createMenu('Custom Menu')      .addItem('Show prompt', 'showPrompt')      .addToUi();}function showPrompt() {  var ui = SpreadsheetApp.getUi(); // Same variations.  var result = ui.prompt(      'Let\'s get to know each other!',      'Please enter your name:',      ui.ButtonSet.OK_CANCEL);  // Process the user's response.  var button = result.getSelectedButton();  var text = result.getResponseText();  if (button == ui.Button.OK) {    // User clicked "OK".    ui.alert('Your name is ' + text + '.');  } else if (button == ui.Button.CANCEL) {    // User clicked "Cancel".    ui.alert('I didn\'t get your name.');  } else if (button == ui.Button.CLOSE) {    // User clicked X in the title bar.    ui.alert('You closed the dialog.');  }}
```

## Custom dialogs

![](https://developers.google.com/static/apps-script/images/dialog.png)

A custom dialog can display an [HTML service](https://developers.google.com/apps-script/guides/html) user interface inside a Google Docs, Sheets, Slides, or Forms editor.

Custom dialogs do _not_ suspend the server-side script while the dialog is open. The client-side component can make asynchronous calls to the server-side script using the [`google.script`](https://developers.google.com/apps-script/guides/html/communication) API for HTML-service interfaces.

The dialog can close itself by calling [`google.script.host.close()`](https://developers.google.com/apps-script/guides/html/communication#closing_dialogs_and_sidebars_in_google_apps) in the client side of an HTML-service interface. The dialog cannot be closed by other interfaces, only by the user or itself.

As shown in the example below, Google Docs, Forms, Slides, and Sheets all use the method [`Ui.showModalDialog()`](https://developers.google.com/apps-script/reference/base/ui#showModalDialog(Object,String)) to open the dialog.

## Custom sidebars

![](https://developers.google.com/static/apps-script/images/sidebar.png)

A sidebar can display an [HTML service](https://developers.google.com/apps-script/guides/html) user interface inside a Google Docs, Forms, Slides, and Sheets editor.

Sidebars do _not_ suspend the server-side script while the dialog is open. The client-side component can make asynchronous calls to the server-side script using the [`google.script`](https://developers.google.com/apps-script/guides/html/communication) API for HTML-service interfaces.

The sidebar can close itself by calling [`google.script.host.close()`](https://developers.google.com/apps-script/guides/html/communication#closing_dialogs_and_sidebars_in_google_apps) in the client side of an HTML-service interface. The sidebar cannot be closed by other interfaces, only by the user or itself.

As shown in the example below, Google Docs, Forms, Slides, and Sheets all use the method [`Ui.showSidebar()`](https://developers.google.com/apps-script/reference/base/ui#showSidebar(Object)) to open the sidebar.

[Code.gs](https://developers.google.com/apps-script/guides/dialogs#code.gs)[Page.html](https://developers.google.com/apps-script/guides/dialogs#page.html)

function onOpen() {  SpreadsheetApp.getUi() // Or DocumentApp or SlidesApp or FormApp.      .createMenu('Custom Menu')      .addItem('Show sidebar', 'showSidebar')      .addToUi();  
}  
  
function showSidebar() {  var html = HtmlService.createHtmlOutputFromFile('Page')      .setTitle('My custom sidebar');  SpreadsheetApp.getUi() // Or DocumentApp or SlidesApp or FormApp.      .showSidebar(html);  
}

## File-open dialogs

[Google Picker](https://developers.google.com/picker) is a "file-open" dialog for information stored in Google servers, including Google Drive, Google Image Search, Google Video Search, and more.

As shown in the example below, Picker's client-side JavaScript API can be used in [HTML service](https://developers.google.com/apps-script/guides/html) to create a custom dialog that lets users select existing files or upload new ones, then pass that selection back to your script for further use.

**Note:** To use Google Picker, your script project must be using a [standard Google Cloud project](https://developers.google.com/apps-script/guides/cloud-platform-projects#standard_cloud_platform_projects).

To enable Picker and get an API key, follow these instructions:

1. Verify that your script project is using a [standard GCP project](https://developers.google.com/apps-script/guides/cloud-platform-projects#standard_cloud_platform_projects).
2. [Enable the "Google Picker API" in your Google Cloud project](https://developers.google.com/apps-script/guides/cloud-platform-projects#enabling_an_api_in_a_standard_gcp_project).
3. While your Google Cloud project is still open, select **APIs & Services**, then click **Credentials**.
4. Click **Create credentials > API key**. This action creates the key, but you should edit the key to add both application restrictions and an API restriction to the key.
5. In the API key dialog, click **Close**.
6. Next to the API key you created, click More ![More icon](https://fonts.gstatic.com/s/i/short-term/release/googlesymbols/more_vert/default/24px.svg)> **Edit API key**.
7. Under **Application restrictions**, complete the following steps:
    
    1. Select **HTTP referrers (web sites)**.
    2. Under **Website restrictions**, click **Add an item**.
    3. Click **Referrer** and enter `*.google.com`.
    4. Add another item and enter `*.googleusercontent.com` as the referrer.
    5. Click **Done**.
8. Under **API restrictions**, complete the following steps:
    
    1. Select **Restrict key**.
    2. In the **Select APIs** section, select **Google Picker API** and click **OK**.
        
        **Note:** The Google Picker API does not appear unless you have enabled it because the list only shows APIs that have been enabled for the Cloud project.
        
9. Under **API key**, click Copy to clipboard ![Copy to clipboard icon](https://fonts.gstatic.com/s/i/short-term/release/googlesymbols/content_copy/default/24px.svg).
    
10. At the bottom, click **Save**.
    

The following example calls [`ScriptApp.getOAuthToken()`](https://developers.google.com/apps-%20%20script/reference/script/script-app#getOAuthToken()) so that it can pass the user's OAuth 2.0 access token to Picker. This technique keeps Picker from needing to show its own authorization dialog, but is only possible if the [OAuth scope that Picker needs](https://developers.google.com/picker/docs#otherviews) is available in Apps Script. Otherwise, your Picker code will need to declare its own OAuth scopes, as shown in [this "hello world" example](https://developers.google.com/picker/docs#hiworld).  
  
You must call `setOrigin(google.script.host.origin)` when constructing the `PickerBuilder`.

[code.gs](https://developers.google.com/apps-script/guides/dialogs#code.gs)

[dialog.html](https://developers.google.com/apps-script/guides/dialogs#dialog.html)