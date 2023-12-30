
This quickstart creates a Google Docs Editor Add-on that translates selected text in a document.

## Objectives

- Set up the script.
- Run the script.

## Prerequisites

To use this sample, you need the following prerequisites:

- A Google Account (Google Workspace accounts might require administrator approval).
- A web browser with access to the internet.

## Set up the script

1. Create a Google Docs document at [docs.new](https://docs.google.com/document/create).
2. Click **Extensions** > **Apps Script**.
3. Click **Untitled project**.
4. Rename the Apps Script project **Translate Docs** and click **Rename**.
5. Next to the `Code.gs` file, click More more_vert > **Rename**. Name the file `translate`.
6. Click Add a file add > **HTML**. Name the file `sidebar`.
7. Replace the contents of each file with the following corresponding code, then click Save ![Save icon](https://fonts.gstatic.com/s/i/short-term/release/googlesymbols/save/default/24px.svg).
    
    [translate.gs](https://github.com/googleworkspace/apps-script-samples/blob/main/docs/translate/translate.gs)[sidebar.html](https://github.com/googleworkspace/apps-script-samples/blob/main/docs/translate/sidebar.html)

## Run the script

1. In your Docs document, reload the page.
2. Click **Extensions** > **Translate Docs** > **Start**.
3. When prompted, authorize the add-on.
4. Again, click **Extensions** > **Translate Docs** > **Start**.
5. Type some text into your document and select it.
6. In the add-on, click **Translate**. To replace the text in the document, click **Insert**.

## Next steps

- [Extending Google Docs with Apps Script](https://developers.google.com/apps-script/guides/docs)
- [Document service reference](https://developers.google.com/apps-script/reference/document)