---
page-title: "cloud-atlas-ai/obsidian-client: Cloud Atlas Obsidian Client"
url: https://github.com/cloud-atlas-ai/obsidian-client
date: "2024-04-12 00:51:46"
tags: 
- A/sw/plugin/integrationForService
- F/homepage
- C/
- P/
about: "[[Obsidian]]"
aliases: 
- 2a068f3f-78cf-406d-a76d-7c1b1c513828
- cloud-atlas-ai/obsidian-client: Cloud Atlas Obsidian Client
by: 
length: 6821
dir: 
---

*This work is licensed under [CC BY-NC-ND 4.0![](https://camo.githubusercontent.com/458ceef6cb2ac6b254b4b0dfd4e48377408aec5fac260cd05cd8b2d8ae7662ba/68747470733a2f2f6d6972726f72732e6372656174697665636f6d6d6f6e732e6f72672f70726573736b69742f69636f6e732f63632e7376673f7265663d63686f6f7365722d7631)![](https://camo.githubusercontent.com/0facd73730f0913c3efc1c96c1b102dbca6ede745526e26314994d9811121f72/68747470733a2f2f6d6972726f72732e6372656174697665636f6d6d6f6e732e6f72672f70726573736b69742f69636f6e732f62792e7376673f7265663d63686f6f7365722d7631)![](https://camo.githubusercontent.com/a68cb809bc229256e15bdfe2ec830decaca1ec797d908ebfb33940800b264d72/68747470733a2f2f6d6972726f72732e6372656174697665636f6d6d6f6e732e6f72672f70726573736b69742f69636f6e732f6e632e7376673f7265663d63686f6f7365722d7631)![](https://camo.githubusercontent.com/9c2bab8f8fefdcc68b1b4127618b14739a7077c59eefa5c3855249c2e9bd8c14/68747470733a2f2f6d6972726f72732e6372656174697665636f6d6d6f6e732e6f72672f70726573736b69742f69636f6e732f6e642e7376673f7265663d63686f6f7365722d7631)](http://creativecommons.org/licenses/by-nc-nd/4.0/?ref=chooser-v1)*

## Obsidian Cloud Atlas Plugin

[](https://github.com/cloud-atlas-ai/obsidian-client#obsidian-cloud-atlas-plugin)

This plugin integrates Obsidian with Cloud Atlas, enriching your note-taking experience by automatically processing notes, providing contextual responses, and streamlining information gathering with the power of various computational models and external systems.

## Cloud Atlas Features

[](https://github.com/cloud-atlas-ai/obsidian-client#cloud-atlas-features)

-   **Canvas Flows**: Use the interactive canvas to set up and run flows with components like input, context, and user prompts.
    
    -   Name these as `<flow name>.flow.canvas`
    -   Execute them using the command palette or the Cloud Atlas view.
-   **Markdown Notes Mode**: Run flows directly on Markdown files with support for context selection or using the current file as context.
    
    -   Define flows in `CloudAtlas/<flow name>.flow.md`
    -   Optionally, include additional data with `CloudAtlas/<flow name>.flowdata.md`

### LLM options

[](https://github.com/cloud-atlas-ai/obsidian-client#llm-options)

You can use the plugin with Cloud Atlas as the Language Model (LLM) provider or bring your own OpenAI key.

-   No need for a separate ChatGPT account; choose between OpenAI ChatGPT-4 or AzureAI ChatGPT-4.
-   Cloud Atlas supports vision tasks and entity recognition to enhance notes with wikilinks automatically.
-   Server-side embeddings generation for adding relevant context to your requests.

## Cloud Atlas Subscription

[](https://github.com/cloud-atlas-ai/obsidian-client#cloud-atlas-subscription)

Due to high demand, we are limiting signups for Cloud Atlas as an LLM provider. If you wish to sign up, please email us at `signmeup@cloud-atlas.ai` with a brief description of your intended use and a confirmation of your willingness to pay for the service if it proves valuable.

## Using Your Own OpenAI Key

[](https://github.com/cloud-atlas-ai/obsidian-client#using-your-own-openai-key)

You can choose to use your own OpenAI key with the plugin. However, be aware that this mode comes with the following limitations:

-   Entity recognition and automatic will not be available.
-   Vision tasks are unsupported.
-   Server-side embeddings to improve context relevance are not included.

## What is a Flow?

[](https://github.com/cloud-atlas-ai/obsidian-client#what-is-a-flow)

A flow in Cloud Atlas is a powerful tool that simplifies and elevates your note-taking experience. It leverages content already in your vault you to:

1.  **Automatically Process Notes**: Transform the content of your current note into enriched information or actionable insights without manual intervention.
2.  **Get Contextual Responses**: Receive responses tailored to your specific queries or topics mentioned in your notes, making your notes more informative and useful.
3.  **Streamline Information Gathering**: Easily compile and summarize key points from your notes, providing quick access to important information and helping you stay organized.
4.  **Customize Your Note Processing**: Personalize how your notes are processed and what kind of output you receive, making your note-taking process more aligned with your individual needs and workflows.

Each flow is like having a personal assistant within Obsidian, helping you manage, analyze, and enhance your notes efficiently. We achieve this through a combination of an Obsidian plugin and a server component that makes use of systems that have knowledge (Weather services, Maps, Wolfram Knowledge base, Wikipedia, IMDB, etc...) and computational models (Wolfram Alpha, OpenAI ChatGPT, etc...).

## Understanding the Plugin's Functionality

[](https://github.com/cloud-atlas-ai/obsidian-client#understanding-the-plugins-functionality)

-   **Instructions and Prompt**: `<flow name>.flow.md` files from the `vault>/CloudAtlas` subdirectory. The value of the `system_instruction` property acts as the instructions or context for the API, and the content of the file provides a specific prompt or question.
-   **API Interaction**: The content of the active note, along with the system instructions, user prompt, and additional context, is sent to an external API. The API enriches and otherwise processes this and returns a response.
-   **Appending API Response**: The response from the API is then automatically appended to the end of the active note, providing insights, answers, or content based on the provided instructions and the serverside processing.

---

## Cloud Atlas Plugin Usage Guide

[](https://github.com/cloud-atlas-ai/obsidian-client#cloud-atlas-plugin-usage-guide)

This will walk you through creating, running, and customizing your personal flows. Let's get started.

### Step 1: Creating a New Flow

[](https://github.com/cloud-atlas-ai/obsidian-client#step-1-creating-a-new-flow)

1.  **Create a New Flow**: Use the command palette (`Ctrl/Cmd + P`) and type `Create New Flow`. This will create a new `.flow.md` file in the `CloudAtlas` directory.
    
2.  **Name Your Flow**: Follow the naming convention `CloudAtlas/<flow name>.flow.md` for markdown notes mode.
    
3.  **Setup Your Flow**: Populate your new flow file with the desired content, context, and instructions as needed.
    
    \---
    system\_instructions: You are a helpful assistant.
    resolveBacklinks: true
    resolveForwardLinks: true
    exclusionPattern: \["^Private/", ".\*-confidential.\*"\]
    \---
    
    Say hello to the user.
    
    In the front matter (the section between `---`), you can set various options:
    
    -   `system_instructions`: Instructions for Cloud Atlas on how to assist.
    -   `resolveBacklinks` and `resolveForwardLinks`: Whether to include content from linked notes.
    -   `exclusionPattern`: Patterns for notes to exclude, useful for omitting sensitive data.
4.  **Running Flows**:
    

### Step 2: Running Your Flow

[](https://github.com/cloud-atlas-ai/obsidian-client#step-2-running-your-flow)

1.  **Open Any Note**: With your flow created, open any note in your vault where you want to run the flow.
2.  **Execute the Flow**:
    1.  **From the Command Palette:** After creating or updating a flow, you can register it as a command. Go to the Settings and register it as a command. This will allow you to run the flow from the command palette.
    2.  **From the Cloud Atlas view:** You can also run flows from the Cloud Atlas view by clicking on the Play button next to the flow name.
3.  **View the Results**: Cloud Atlas processes the note and appends or replaces the content based on your flow settings. The response from Cloud Atlas will appear in your note.

### Step 3: Customizing Your Flow

[](https://github.com/cloud-atlas-ai/obsidian-client#step-3-customizing-your-flow)

1.  **Create a Customization File**: In the `CloudAtlas` directory, create a `demo.flowdata` file to customize the `demo` flow.
    
2.  **Add Custom Content and Settings**: Here's an example customization:
    
    \---
    resolveBacklinks: false
    resolveForwardLinks: false
    \---
    
    My name is Muness. I am the user.
    
    This file allows you to:
    
    -   Provide additional content that Cloud Atlas will consider when processing your flow.
    -   Override settings defined in `demo.flow`.
3.  **Re-run Your Flow**: After customizing, go back to any note and run the `demo` flow again. You'll see how the customizations impact the flow's output.
    

That's it! You've now learned how to create, run, and customize your own flows in Obsidian using the Cloud Atlas plugin. Go wild!

## Manually installing the plugin

[](https://github.com/cloud-atlas-ai/obsidian-client#manually-installing-the-plugin)

### With [Obsidian BRAT](https://github.com/TfTHacker/obsidian42-brat)

[](https://github.com/cloud-atlas-ai/obsidian-client#with-obsidian-brat)

1.  Install the BRAT plugin
    1.  Open `Settings` -> `Community Plugins`
    2.  Disable safe mode, if enabled
    3.  *Browse*, and search for "BRAT"
    4.  Install the latest version of **Obsidian42 - BRAT**
2.  Open BRAT settings (`Settings` -> `BRAT`)
    1.  Scroll to the `Beta Plugin List` section
    2.  `Add Beta Plugin`
    3.  Specify this repository: `cloud-atlas-ai/obsidian-client`
3.  Enable the `Cloud Atlas` plugin (`Settings` -> `Community Plugins`)
4.  Set the API key in the plugin settings. You can get an API key by signing up at the [Cloud Atlas website](https://www.cloud-atlas.ai/).