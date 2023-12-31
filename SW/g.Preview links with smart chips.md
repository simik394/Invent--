This page explains how to build a Google Workspace Add-on that lets Google Docs, Sheets, and Slides users preview links from a third-party service.

A Google Workspace Add-on can detect your service's links and prompt users to preview them. You can configure an add-on to preview multiple URL patterns, such as links to support cases, sales leads, and employee profiles.

## How users preview links

To preview links, users interact with _smart chips_ and _cards_.

![User previews a card](https://developers.google.com/static/apps-script/add-ons/images/preview-card.svg)

When users type or paste a URL into a document, Google Docs prompts them to replace the link with a smart chip. The smart chip displays an icon and short title or description of the link's content. When the user hovers over the chip, they see a card interface that previews more information about the file or link.

The following video shows how a user converts a link into a smart chip and previews a card:

### How users preview links in Sheets and Slides

Third-party smart chips aren't supported for the developer preview of link previews in Sheets and Slides. When users type or paste a URL into a spreadsheet or presentation, Sheets or Slides prompts them to replace the link with its title as linked text instead of a chip. When the user hovers over the link title, they see a card interface that previews information about the link.

The following image shows how a link preview renders in Sheets and Slides:

![Link preview example for Sheets and Slides](https://developers.google.com/static/apps-script/add-ons/images/link-preview-sheets-slides.gif)
## Prerequisites

[Apps Script](https://developers.google.com/workspace/add-ons/guides/preview-links-smart-chips#apps-script)

- A [Google Workspace](https://workspace.google.com/features/) account.
- A Google Workspace Add-on. To build an add-on, follow this [quickstart](https://developers.google.com/apps-script/add-ons/cats-quickstart).

## Optional: Set up authentication to a third-party service

If your add-on connects to a service that requires authorization, users must authenticate to the service to preview links. This means that when users paste a link from your service into a Docs, Sheets, or Slides file for the first time, your add-on must invoke the authorization flow.

To set up an OAuth service or custom authorization prompt, see one of the following guides:

- If you built your add-on using Apps Script, see [Connecting to non-Google Services from a Google Workspace Add-on](https://developers.google.com/apps-script/add-ons/how-tos/non-google-services).
    
- If you built your add-on using a different runtime, see [Connect your add-on to a third-party service](https://developers.google.com/workspace/add-ons/guides/connect-third-party-service).
    

## Set up link previews for your add-on

This section explains how to set up link previews for your add-on, which includes the following steps:

1. [Configure link previews](https://developers.google.com/workspace/add-ons/guides/preview-links-smart-chips#configure) in your add-on's deployment resource or manifest file.
2. [Build the smart chip and card interface](https://developers.google.com/workspace/add-ons/guides/preview-links-smart-chips#build-chip-card) for your links.

### Configure link previews

To configure link previews, specify the following sections and fields in your add-on's deployment resource or manifest file:

1. Under the `addOns` section, add the `docs` field to extend Docs, the `sheets` field to extend Sheets, and the `slides` field to extend Slides.
2. In each field, implement the `linkPreviewTriggers` trigger that includes a `runFunction` (You define this function in the following section, [Build the smart chip and card](https://developers.google.com/workspace/add-ons/guides/preview-links-smart-chips#build-chip-card)).
    
    To learn about what fields you can specify in the `linkPreviewTriggers` trigger, see the reference documentation for [Apps Script manifest files](https://developers.google.com/apps-script/manifest/editor-addons#linkpreviewtriggers) or [deployment resources for other runtimes](https://developers.google.com/workspace/add-ons/reference/rest/v1/projects.deployments#LinkPreviewExtensionPoint).
    
3. In the `oauthScopes` field, add the scope `https://www.googleapis.com/auth/workspace.linkpreview` so that users can authorize the add-on to preview links on their behalf.
    

As an example, see the `oauthScopes` and `addons` section of the following deployment resource that configures link previews for a support case service.

**Note:** For the Sheets and Slides developer preview, `labelText` and `localizedLabelText` don't render, but you must include `labelText` for when Sheets and Slides start supporting third-party smart chips. `localizedLabelText` is optional.

```
{  "oauthScopes": [    "https://www.googleapis.com/auth/workspace.linkpreview"  
],  
"addOns": {    
	"common": {      
		"name": "Preview support cases",      
		"logoUrl": "https://www.example.com/images/company-logo.png",      
		"layoutProperties": {        
			"primaryColor": "#dd4b39"      }    },    
"docs": {      "linkPreviewTriggers": [        {          "runFunction": "caseLinkPreview",          "patterns": [            {              "hostPattern": "example.com",              "pathPrefix": "support/cases"            },            {              "hostPattern": "*.example.com",              "pathPrefix": "cases"            },            {              "hostPattern": "cases.example.com"            }          ],          "labelText": "Support case",          "logoUrl": "https://www.example.com/images/support-icon.png",          "localizedLabelText": {            "es": "Caso de soporte"          }        }      ]    },    "sheets": {      "linkPreviewTriggers": [        {          "runFunction": "caseLinkPreview",          "patterns": [            {              "hostPattern": "example.com",              "pathPrefix": "support/cases"            },            {              "hostPattern": "*.example.com",              "pathPrefix": "cases"            },            {              "hostPattern": "cases.example.com"            }          ],          "labelText": "Support case",          "logoUrl": "https://www.example.com/images/support-icon.png",          "localizedLabelText": {            "es": "Caso de soporte"          }        }      ]    },    "slides": {      "linkPreviewTriggers": [        {          "runFunction": "caseLinkPreview",          "patterns": [            {              "hostPattern": "example.com",              "pathPrefix": "support/cases"            },            {              "hostPattern": "*.example.com",              "pathPrefix": "cases"            },            {              "hostPattern": "cases.example.com"            }          ],          "labelText": "Support case",          "logoUrl": "https://www.example.com/images/support-icon.png",          "localizedLabelText": {            "es": "Caso de soporte"          }        }      ]    }  }}
```

In the example, the Google Workspace Add-on previews links for a company's support case service. The add-on specifies three URL patterns to preview links. Whenever a link matches one of the URL patterns, the callback function `caseLinkPreview` builds and displays a card and a smart chip, or in Sheets and Slides, replaces the URL with the link title.

### Build the smart chip and card

To return a smart chip and card for a link, you must implement any functions that you specified in the `linkPreviewTriggers` object.

When a user interacts with a link that matches a specified URL pattern, the `linkPreviewTriggers` trigger fires and its callback function passes the event object `EDITOR_NAME.matchedUrl.url` as an argument. You use the payload of this event object to build the smart chip and card for your link preview.

For example, for an add-on that specifies the URL pattern `example.com/cases` for Docs, if a user previews the link `https://www.example.com/cases/123456`, the following event payload is returned:

```
{  "docs": {    "matchedUrl": {        "url": "https://www.example.com/support/cases/123456"    }  }  
}  
```


To create the card interface, you use widgets to display information about the link. You can also build actions that let users open the link or modify its contents. For a list of available widgets and actions, see [Supported components for preview cards](https://developers.google.com/workspace/add-ons/guides/preview-links-smart-chips#supported-components).

To build the smart chip and card for a link preview:

1. Implement the function that you specified in the `linkPreviewTriggers` section of your add-on's deployment resource or manifest file:
    1. The function must accept an event object containing `EDITOR_NAME.matchedUrl.url` as an argument and return a single `Card` object.
    2. If your service requires authorization, the function must also [invoke the authorization flow](https://developers.google.com/workspace/add-ons/guides/preview-links-smart-chips#set-up-authentication).
2. For each preview card, implement any callback functions that provide widget interactivity for the interface. For example, if you include a button that says "View link," you can create an action that specifies a callback function to open the link in a new window. To learn more about widget interactions, see [Add-on actions](https://developers.google.com/apps-script/add-ons/concepts/actions).

**Note:** For link previews, the card response is cached for each user for 5 minutes. During that time, if a user previews a link, they receive the cached response. The cache is cleared when the user refreshes the file, or after 5 minutes. If the title of the returned card has changed, the app then prompts the user to refresh the title.

The following code creates the callback function `caseLinkPreview` for Docs:

[add-ons-samples/apps-script/preview-links/preview-link.gs at main · googleworkspace/add-ons-samples (github.com)](https://github.com/googleworkspace/add-ons-samples/blob/main/apps-script/preview-links/preview-link.gs)
#### Supported components for preview cards

Google Workspace Add-ons support the following widgets and actions for link preview cards:

|Card (`google.apps.card.v1`) field|Type|
|---|---|
|[`TextParagraph`](https://developers.google.com/workspace/add-ons/reference/rpc/google.apps.card.v1#textparagraph)|Widget|
|[`DecoratedText`](https://developers.google.com/workspace/add-ons/reference/rpc/google.apps.card.v1#decoratedtext)|Widget|
|[`Image`](https://developers.google.com/workspace/add-ons/reference/rpc/google.apps.card.v1#image)|Widget|
|[`Icon`](https://developers.google.com/workspace/add-ons/reference/rpc/google.apps.card.v1#icon)|Widget|
|[`ButtonList`](https://developers.google.com/workspace/add-ons/reference/rpc/google.apps.card.v1#buttonlist)|Widget|
|[`Button`](https://developers.google.com/workspace/add-ons/reference/rpc/google.apps.card.v1#button)|Widget|
|[`Grid`](https://developers.google.com/workspace/add-ons/reference/rpc/google.apps.card.v1#grid)|Widget|
|[`Divider`](https://developers.google.com/workspace/add-ons/reference/rpc/google.apps.card.v1#divider)|Widget|
|[`OpenLink`](https://developers.google.com/workspace/add-ons/reference/rpc/google.apps.card.v1#openlink)|Action|
|[`Navigation`](https://developers.google.com/workspace/add-ons/reference/rpc/google.apps.card.v1#navigation)|Action  <br>Only the `updateCard` method is supported.|

## Complete example: Support case add-on

The following example features a Google Workspace Add-on that previews links to a company's support cases and employee profiles in Google Docs.

The example does the following:

- Previews links to support cases, such as `https://www.example.com/support/cases/1234`. The smart chip displays a support icon, and the preview card includes the case ID and a description.
- Previews links to support case agents, such as `https://www.example.com/people/rosario-cruz`. The smart chip displays a person icon, and the preview card includes the employee's name, email, job title, and profile photo.
- If the user's locale is set to Spanish, the smart chip localizes its `labelText` into Spanish.

## Deploy resource
[add-ons-samples/apps-script/preview-links/appsscript.json at main · googleworkspace/add-ons-samples (github.com)](https://github.com/googleworkspace/add-ons-samples/blob/main/apps-script/preview-links/appsscript.json)

## Code
[add-ons-samples/apps-script/preview-links/preview-link.gs at main · googleworkspace/add-ons-samples (github.com)](https://github.com/googleworkspace/add-ons-samples/blob/main/apps-script/preview-links/preview-link.gs)