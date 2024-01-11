Google Docs, Sheets, and Slides provide a cloud-based productivity solution with real-time collaboration. However, modifying and surfacing relevant information in the Editors is often a time-consuming task.

You can save your users time and effort by extending Google Docs, Sheets, and Slides with Google Workspace Add-ons. Google Workspace Add-ons for Google Forms isn’t available yet.

When you build a Google Workspace Add-on, you can define custom interfaces that are inserted directly into the Editors. These interfaces help automate tasks, present additional information to the user, or let the user interact with a third-party system without having to switch to a new browser tab.

With Google Workspace Add-ons, you can create the following 
## Editor interfaces:

1. Homepage interfaces
2. REST API interfaces
3. Link preview interfaces

> [!Warning]
> You can't use Google Workspace Add-ons for Editors on mobile clients.

## See what you can make

Google Workspace Add-ons are built using the [Card service](https://developers.google.com/apps-script/reference/card-service/card-service?authuser=0). See [Building Google Workspace Add-ons](https://developers.google.com/apps-script/add-ons/how-tos/building-workspace-addons?authuser=0) for an overview.

Google Workspace Add-on behavior is configured using a [manifest](https://developers.google.com/workspace/add-ons/concepts/gsuite-manifests?authuser=0). To enable Google Workspace Add-on for Editors, include Editor-specific sections.

When configuring your Google Workspace Add-on for Editors, you must decide what interfaces to create for your add-on and what actions it can take. See the following guides for more information:

- [Building Google Editor interfaces](https://developers.google.com/apps-script/add-ons/editors/gsao/building-editor-interfaces?authuser=0)
- [Editor actions](https://developers.google.com/apps-script/add-ons/editors/gsao/editor-actions?authuser=0)
- [Manifest structure for Google Workspace Add-ons](https://developers.google.com/workspace/add-ons/concepts/gsuite-manifests?authuser=0#manifest_structure_for_g_suite_add-ons)