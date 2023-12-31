**Create third-party resources from the @ menu**

> **Developer Preview:** This feature is available as part of the [Google Workspace Developer Preview Program](https://developers.google.com/workspace/preview), which grants early access to certain features.

This page explains how to build a Google Workspace Add-on that lets Google Docs users create resources, such as a support case or project task, in a third-party service from within Google Docs.

With a Google Workspace Add-on, you can add your service to the @ menu in Docs. The add-on adds menu items that let users create resources in your service through a form dialog in Docs.

## How users create resources

To create a resource in your service from within a Google Docs document, users type `@` in a document and select your service from the @ menu:

![User previews a card](https://developers.google.com/static/workspace/add-ons/images/create-resource.svg)

When users type `@` in a document and select your service, you present them with a card that includes the form inputs that users need in order to create a resource. After the user submits the resource creation form, your add-on should create the resource in your service and generate a URL that points to it.

**Note:** If users encounter whitespace when they first open the resource creation form for your add-on, they must scroll down within the form to access the authorization prompt. This is a known issue for the developer preview of resource creation.

The add-on inserts a chip into the document for the created resource. When users hold the pointer over this chip, it invokes the add-on's associated link preview trigger. Make sure your add-on inserts chips with link patterns that are supported by your link preview triggers.

## Prerequisites
- A Google Workspace Add-on that supports link previews for the link patterns of the resources that users create. To build an add-on with link previews, refer to [Preview links with smart chips](https://developers.google.com/workspace/add-ons/guides/preview-links-smart-chips).

## Set up resource creation for your add-on

This section explains how to set up resource creation for your add-on, which includes the following steps:

1. [Configure resource creation](https://developers.google.com/workspace/add-ons/guides/create-insert-resource-smart-chip#configure) in your add-on's deployment resource or manifest file.
2. [Build the form cards](https://developers.google.com/workspace/add-ons/guides/create-insert-resource-smart-chip#build-cards) that users need to create resources within your service.
3. [Handle form submissions](https://developers.google.com/workspace/add-ons/guides/create-insert-resource-smart-chip#handle-submission) so that the function that creates the resource runs when users submit the form.

### Configure resource creation

To configure resource creation, specify the following sections and fields in your add-on's deployment resource or manifest file:

1. Under the `addOns` section in the `docs` field, implement the `createActionTriggers` trigger that includes a `runFunction`. (You define this function in the following section, [Build the form cards](https://developers.google.com/workspace/add-ons/guides/create-insert-resource-smart-chip#build-cards).)
    
    To learn about what fields you can specify in the `createActionTriggers` trigger, see the reference documentation for [Apps Script manifest files](https://developers.google.com/apps-script/manifest/editor-addons#createActiontriggers) or [deployment resources for other runtimes](https://developers.google.com/workspace/add-ons/reference/rest/v1/projects.deployments#CreateActionExtensionPoint).
    
2. In the `oauthScopes` field, add the scope `https://www.googleapis.com/auth/workspace.linkcreate` so that users can authorize the add-on to create resources. Specifically, this scope allows the add-on to read the information that users submit to the resource creation form and insert a smart chip into the document based on that information.

As an example, see the `addons` section of a deployment resource that configures resource creation for the following support case service:

```
{  "oauthScopes": [    "https://www.googleapis.com/auth/workspace.linkpreview",    "https://www.googleapis.com/auth/workspace.linkcreate"  ],  "addOns": {    "docs": {      "linkPreviewTriggers": [        ...      ],      "createActionTriggers": [        {          "id": "createCase",          "labelText": "Create support case",          "localizedLabelText": {            "es": "Crear caso de soporte"          },          "runFunction": "createCaseInputCard",          "logoUrl": "https://www.example.com/images/case.png"        },        {          "id": "createHotlist",          "labelText": "Create a hotlist",          "localizedLabelText": {            "es": "Crear una hotlist"          },          "runFunction": "createHotlistInputCard",          "logoUrl": "https://www.example.com/images/hotlist.png"        }      ]    }  }}
```

In the example, the Google Workspace Add-on lets users create support cases and hotlists. Each `createActionTriggers` trigger must have the following fields:

- An unique ID
- A text label that appears in the Docs @ menu
- A logo URL pointing to an icon that appears next to the label text in the @ menu
- A callback function that references either an Apps Script function or an HTTP endpoint that returns a card

### Build the form cards

To create resources in your service from the Docs @ menu, you must implement any functions that you specified in the `createActionTriggers` object.

When a user interacts with one of your menu items, the corresponding `createActionTriggers` trigger fires and its callback function presents a card with form inputs for creating the resource.

To create the card interface, you use widgets to display information and inputs that users need in order to create the resource. Most Google Workspace Add-on widgets and actions are supported with the following exceptions:

- Card footers aren't supported.
- For navigations, only the [`updateCard`](https://developers.google.com/apps-script/reference/card-service/navigation#updatecardcard) navigation is supported.

Here's an example of an Apps Script callback function that displays a card when a user selects **Create support case** from the @ menu:
https://developers.google.com/workspace/add-ons/guides/create-insert-resource-smart-chip#build-cards
```
function createCaseInputCard() {  let cardSection1TextInput1 = CardService.newTextInput()      .setFieldName('caseTitle')      .setTitle('Case Title')      .setMultiline(false);  let cardSection1TextInput2 = CardService.newTextInput()      .setFieldName('description')      .setTitle('Description')      .setMultiline(true);  let cardSection1SelectionInput1 = CardService.newSelectionInput()      .setFieldName('priority')      .setTitle('Priority')      .setType(CardService.SelectionInputType.RADIO_BUTTON)      .addItem('P0', 'P0', false)      .addItem('P1', 'P1', false)      .addItem('P2', 'P2', false)      .addItem('P3', 'P3', false);  let cardSection1ButtonList1Button1Action1 = CardService.newAction()      .setFunctionName('submitCaseCreationForm')      .setParameters({});  let cardSection1ButtonList1Button1 = CardService.newTextButton()      .setText('Create case')      .setBackgroundColor('#66b73a')      .setTextButtonStyle(CardService.TextButtonStyle.FILLED)      .setOnClickAction(cardSection1ButtonList1Button1Action1);  let cardSection1ButtonList1 = CardService.newButtonSet()      .addButton(cardSection1ButtonList1Button1);  let cardSection1 = CardService.newCardSection()      .addWidget(cardSection1TextInput1)      .addWidget(cardSection1TextInput2)      .addWidget(cardSection1SelectionInput1)      .addWidget(cardSection1ButtonList1);  let card = CardService.newCardBuilder()      .addSection(cardSection1)      .build();  return card;}
```

The `createCaseInputCard` function renders the following card:

![Card with form inputs](https://developers.google.com/static/workspace/add-ons/images/create-case-form.png)

The card includes text inputs and a selection input. It also has a text button with an`onClick` action that refers to another run function to handle the submission of this creation form. After the user fills out the form and clicks **Create case**, the add-on sends the form fields to the`onClick` action function, at which point the add-on can use them to create the resource in the third-party service.

### Handle form submissions

After a user submits the creation form, the function associated with the `onClick` action runs. For an ideal user experience, your add-on should handle both successful and erroneous form submissions.

#### Handle successful resource creation

The `onClick` function of your add-on should create the resource in your third-party service and generate a URL that points to it.

In order to communicate the resource's URL back to Docs for chip creation, the `onClick` function should return a `SubmitFormResponse` with a one-element array in `renderActions.action.links` that points to a link. The link title should represent the title of the created resource and the URL should point to that resource. If additional elements are returned in the `renderActions.action.links` array, they are ignored.

Refer to the following example of a `SubmitFormResponse` for a created resource:
```
{  "renderActions": {    "action": {      "links": [        {          "url": "http://example.com/resource/123",          "title": "Created Resource Name"        }      ]    }  }}
```

After the `SubmitFormResponse` is returned, the modal dialog closes and the add-on inserts a chip into the document. When users hold the pointer over this chip, it invokes the associated link preview trigger. Make sure your add-on doesn't insert chips with link patterns not supported by your link preview triggers.

#### Handle errors

If a user tries to submit a form with invalid fields, instead of returning a `SubmitFormResponse` with a link, the add-on should return a render action that displays an error above or below the invalid input fields using an `updateCard` navigation. This lets the user see what they did wrong and try again. See [`updateCard(card)`](https://developers.google.com/apps-script/reference/card-service/navigation#updatecardcard) for Apps Script and [`updateCard`](https://developers.google.com/workspace/add-ons/reference/rpc/google.apps.card.v1#google.apps.card.v1.Navigation.FIELDS.google.apps.card.v1.Card.google.apps.card.v1.Navigation.updateCard) for other runtimes. Notifications and `pushCard` navigations aren't supported.

## Complete example: Support case add-on

The following example features a Google Workspace Add-on that previews links to a company's support cases and lets users create support cases from within Google Docs.

The example does the following:

- Previews links to support cases, such as `https://www.example.com/support/cases/1234`. The smart chip displays a support icon, and the preview card includes the case ID and a description.
- Creates support cases from the @ menu and inserts them into the Docs document as smart chips.

### Deployment resource

https://developers.google.com/workspace/add-ons/guides/create-insert-resource-smart-chip#deployment_resource
### Code

https://developers.google.com/workspace/add-ons/guides/create-insert-resource-smart-chip#code