---
up: "[[Apps Script]]"
---

## Login
[src](https://codelabs.developers.google.com/codelabs/clasp/#2)
Let's try out _clasp_! The only command you should remember is `clasp`.

```
clasp
```

We've installed `clasp` **globally** on our computer, so the command should work everywhere in your filesystem.

Before we start using the command line tool, we must log in. Run this command:

```
clasp login
```

or if using SSH:

```
clasp login --no-localhost
```

At this point, you are prompted to log in to Google. Any projects you create with the CLI are associated with this Google account.
In `Code.gs`, replace the existing code with the following:

```
function hello() { 
	Logger.log("Hello, " + world);
}
```

At the top, click Save ![save](https://fonts.gstatic.com/s/i/googlematerialicons/save/v6/24px.svg).

To run the function, at the top of the editor, select `hello` from the function dropdown list and click **Run**.

The greeting appears at the bottom in the execution log.
## Create a standalone project
[4. Create a New Project](https://codelabs.developers.google.com/codelabs/clasp/#3)
Start out by creating a standalone Google Apps Script project with the following command:

```
mkdir clasp_codelab;cd clasp_codelab;clasp create --title "Clasp Codelab";
```

You just created an Apps Script Project in the folder "clasp_codelab"!

Note: The `clasp create` command created a standalone script. This means the project is _not_ connected to a Google Sheet, Doc, Form, or Presentation. However, we'll cover how to create a bound script in the next section.

### (Optional alternative) Clone an existing project

Let's try creating a **container-bound** script for a Google Slides Add-on.

To do this, go to [slides.google.com](http://slides.google.com/) and create a new presentation. Change the presentation name to "**clasp Codelab Test**". In the header, under **Tools**, press **Script Editor...**.

This will open your Apps Script project at **script.google.com**. To clone a project, we need the `Script ID`. You can find this ID in the Apps Script project URL after `/projects/`. Copy the value and paste it in the following command:

```
clasp clone <scriptID>
```

The output should look like this...

![4e3b128f4dcf6467.gif](https://codelabs.developers.google.com/static/codelabs/clasp/img/4e3b128f4dcf6467.gif)

Now you have downloaded the project in your **current directory**. Use your favorite editor to view the contents of `Code.gs` (an empty function).

## Pulling & Pushing Files
[src](https://codelabs.developers.google.com/codelabs/clasp/#4)
### Edit code on script.google.com

Now that you're able to clone a project, let's learn how to pull and push files. We'll walk you through the steps to edit on the cloud via `script.google.com` and pull to locally to your computer. Let's open the script in the cloud:

```
clasp open
```

Now that we're on the online editor, we'll edit some code online that we'll later fetch using `clasp`.

To create a new Apps Script file, at the left of the editor next to **Files**, click Add a file ![add a file](https://fonts.gstatic.com/s/i/googlematerialicons/add/v7/gm_grey-24dp/1x/gm_add_gm_grey_24dp.png) **> Script**. Enter the name `utils/strings`. In the newly created file, `utils/strings.gs`, replace the code with the following:

```
var world = "世界";
```

In `Code.gs`, replace the existing code with the following:

```
function hello() {  Logger.log("Hello, " + world);}
```

At the top, click Save ![save](https://fonts.gstatic.com/s/i/googlematerialicons/save/v6/24px.svg).

To run the function, at the top of the editor, select `hello` from the function dropdown list and click **Run**.

The greeting appears at the bottom in the execution log.

### Edit code locally

Let's go back to the command line where we last cloned the project. You may notice that our code is now out of sync with the online editor. To fix that, let's pull the code from our online project.

```
clasp pull
```

Now go back to the code. You should notice there's a **folder** for our utils. The `clasp` CLI automatically converts the slash character **`/`** to folders on the local filesystem.

In your favorite text editor, navigate to `util/strings.gs` and replace the variable name `world` to `mondo`. Also, update the Code.gs by replacing `world` to `mondo`. To update the updated code on `script.google.com`, push your edited code.

```
clasp push
```

And that's it! Your code is now updated on `script.google.com`.

`clasp push` replaces code that is on script.google.com and `clasp pull` replaces all files locally. For this reason, follow these guidelines:

- Do not concurrently edit code locally and on _script.google.com_.
- Use a version control system, like [git](https://git-scm.com/).
## Versioning and Deploying
[src](https://codelabs.developers.google.com/codelabs/clasp/#5)

`clasp` allows you to manage versions and deployments. First, some vocabulary:

- **Version**: A "snapshot" of a script project. A version can be considered a read-only branch used for deployments.
- **Deployment**: A published release of a script project (often as an add-on or web app). Requires a version number.

Let's create a version of our script:

```
clasp version "First version"
```

Using the logged version string we created in place of `[version]`, we can deploy the script:

```
clasp deploy 1 "First deployment"
```

The `clasp deploy` command looks at your [manifest](https://developers.google.com/apps-script/concepts/manifests) and creates a new versioned deployment. Your code is now deployed as an executable. Learn more about this in the [deployments guide](https://developers.google.com/apps-script/concepts/deployments).

