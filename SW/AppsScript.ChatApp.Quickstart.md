# Google Apps Script Chat app quickstart

bookmark

- On this page
- [Objectives](https://developers.google.com/apps-script/quickstart/chat-app#objectives)
- [Prerequisites](https://developers.google.com/apps-script/quickstart/chat-app#prerequisites)
- [Set up your environment](https://developers.google.com/apps-script/quickstart/chat-app#set_up_your_environment)
    - [Open your Cloud project in the Google Cloud console](https://developers.google.com/apps-script/quickstart/chat-app#open_your_in_the)
    - [Turn on the Chat API](https://developers.google.com/apps-script/quickstart/chat-app#turn_on_the)
    - [Configure the OAuth consent screen](https://developers.google.com/apps-script/quickstart/chat-app#configure_the_oauth_consent_screen)
- [Set up the script](https://developers.google.com/apps-script/quickstart/chat-app#set_up_the_script)
    - [Create the script from the template](https://developers.google.com/apps-script/quickstart/chat-app#create_the_script_from_the_template)

Create a Google Chat app that you can directly message and that responds by echoing your messages.

The following diagram shows the architecture and messaging pattern:

![Architecture of a Chat app implemented with Apps Script.](https://developers.google.com/static/chat/images/design-patterns/gsuite-via-appsscript.svg)

In the preceding diagram, a user interacting with an Apps Script Chat app has the following flow of information:

1. A user sends a message to a Chat app, either in a direct message or in a Chat space.
2. The Chat app logic that's implemented in Apps Script, which resides in Google Cloud, receives and processes the message.
3. Optionally, the Chat app logic can integrate with Google Workspace services, such as a Calendar or Sheets, or other Google Services, such as Google Maps or YouTube.
4. The Chat app logic sends a response back to the Chat app service in Chat.
5. The response is delivered to the user.

## Objectives

- Set up your environment.
- Set up the script.
- Publish the Chat app.
- Test the Chat app.

## Prerequisites

- A [Google Workspace](https://workspace.google.com/features/) account with access to [Chat](https://workspace.google.com/products/chat/).
- A [Google Cloud project](https://developers.google.com/workspace/guides/create-project).

## Set up your environment

### Open your Cloud project in the Google Cloud console

If it's not open already, open the Cloud project that you intend to use for this sample:

1. In the Google Cloud console, go to the **Select a project** page.
    
    [Select a Cloud project](https://console.cloud.google.com/projectselector2)
    
2. Select the Google Cloud project you want to use. Or, click **Create project** and follow the on-screen instructions. If you create a Google Cloud project, you might need to [turn on billing for the project](https://cloud.google.com/billing/docs/how-to/modify-project#enable_billing_for_a_project).

### Turn on the Chat API

Before using Google APIs, you need to turn them on in a Google Cloud project. You can turn on one or more APIs in a single Google Cloud project.

- In the Google Cloud console, enable the Google Chat API.
    
    [Enable the API](https://console.cloud.google.com/flows/enableapi?apiid=chat.googleapis.com)
    

### Configure the OAuth consent screen

All apps using OAuth 2.0 require a consent screen configuration. Configuring your app's OAuth consent screen defines what is displayed to users and app reviewers, and registers your app so you can publish it later.

1. In the Google Cloud console, go to Menu menu > **APIs & Services** > **OAuth consent screen**.
    
    [Go to OAuth consent screen](https://console.cloud.google.com/apis/credentials/consent)
    
2. Select the user type for your app, then click **Create**.
3. Complete the app registration form, then click **Save and Continue**.
4. For now, you can skip adding scopes and click **Save and Continue**. In the future, when you create an app for use outside of your Google Workspace organization, you must add and verify the authorization scopes that your app requires.
    
5. If you selected **External** for user type, add test users:
    1. Under **Test users**, click **Add users**.
    2. Enter your email address and any other authorized test users, then click **Save and Continue**.
6. Review your app registration summary. To make changes, click **Edit**. If the app registration looks OK, click **Back to Dashboard**.

## Set up the script

To set up the script, you use a template and then set your Cloud project in Apps Script.

### Create the script from the template

1. Go to the [Apps Script **Getting Started** page](https://script.google.com/home/start).
2. Click the **Chat App** template. You might have to scroll down to see this template.
3. Click **Untitled project**, type `Quickstart app`, and click **Rename**.

### Copy the Cloud project number

1. Go to your Cloud project in the [Google Cloud console](https://console.cloud.google.com/).
2. Click Settings and Utilities more_vert > **Project settings**.
3. Copy the **Project number**.

### Set the Apps Script project's Cloud project

1. In the Chat app Apps Script project, click **Project Settings** ![The icon for project settings](https://fonts.gstatic.com/s/i/short-term/release/googlesymbols/settings/default/24px.svg).
2. Under **Google Cloud Platform (GCP) Project**, click **Change project**.
3. In **GCP project number**, paste the Google Cloud project number.
4. Click **Set project**.

You now have working app code that you can try out (as described in the following steps) and then customize to meet your requirements.

Make sure that you're signed in to the correct Google Account when you open the Apps Script template. The current account can sometimes switch to your default account without you noticing.

### Create a test deployment

You need a deployment ID for this Apps Script project, so that you can use it in the next step.

To get the head deployment ID, do the following:

1. In the Chat app Apps Script project, click **Deploy** > **Test deployments**.
2. Copy the **Head deployment ID** for use in a later step and click **Done**.

## Publish the Chat app

Publish the Chat app from the Google Cloud console.

1. In the [Google Cloud console](https://console.cloud.google.com/), search for `Google Chat API`, and click **Google Chat API**.
2. Click **Manage**.
3. Click **Configuration** and set up the Chat app:
    
    1. In the **App name** field, enter `Quickstart app`.
    2. In the **Avatar URL** field, enter `https://developers.google.com/chat/images/quickstart-app-avatar.png`.
    3. In the **Description** field, enter `Quickstart app`.
    4. Under Functionality, select **Receive 1:1 messages** and **Join spaces and group conversations**.
    5. Under Connection settings, select **Apps Script project** and paste the Deployment ID into the field.
    6. Under Visibility, select **Specific people and groups in your domain**, and enter your email.
4. Click **Save** and refresh the page.
    
5. On the configuration page, under **App status**, set the status to **Live - available to users**.
    
6. Click **Save**.
    

The Chat app is ready to respond to messages.

## Test the Chat app

1. Open [Chat](https://chat.google.com/).
2. Send a new direct message to the app by clicking **Start a chat add > Find apps**.
3. On the Find apps page, search for `Quickstart App`.
4. Next to **Quickstart App**, click **Chat**.
5. In the new direct message with the app, type `Hello` and press `enter`.

The app thanks you for adding it and echoes your message.

## Next steps

- [Create interactive cards](https://developers.google.com/chat/api/guides/v1/messages/create#create)–Card messages support a defined layout, interactive UI elements like buttons, and rich media like images. Use card messages to present detailed information, gather information from users, and guide users to take a next step.
- [Support slash commands](https://developers.google.com/chat/how-tos/slash-commands)–Slash commands let you register and advertise specific commands that users can give your app by typing a command that begins with a forward slash (`/`), like `/help`.
- [Launch dialogs](https://developers.google.com/chat/how-tos/dialogs)–Dialogs are windowed, card-based interfaces that your app can open to interact with a user. Multiple cards can be strung together sequentially, which helps users complete multi-step processes, like filling in form data.