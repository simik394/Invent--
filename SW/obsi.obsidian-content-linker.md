---
page-title: "Medill-East/obsidian-content-linker: Trying to create a new obsidian plugin to enable user to create bi-directional links easily based on the content of their vault."
url: https://github.com/Medill-East/obsidian-content-linker
date: "2024-01-16 08:38:32"
---

> More than 95% of the code in this plugin was developed by codeGPT. This plugin has only undergone self-testing as a precaution. Please make a backup of your vault contents in advance :) Unless unexpected situations arise, there may be no further updates :)
> 
> The purpose of this plugin is to help users quickly establish bi-directional links based on existing content in the vault.
> 
> If you see "bi-link" in this plugin, it means "bi-directional link". i.e., content with the format of \[\[\]\] :)
> 
> Use the "Remove bi-directional links for selected option(s)" button to convert selected items from bi-directional-link format to non-bi-directional-link format. The Count here includes the total count of both bi-link and non-bi-link forms. E.g., "Content" and "\[\[Content\]\]" are counted.
> 
> The general approach involves interacting with codeGPT and using the following prompt (in chinese, below is a translated version) to implement the code:
> 
> You are an excellent Obsidian plugin developer. You want to develop a new plugin called "Content Linker" for Obsidian, allowing users to add bidirectional links to existing content in their vault.
> 
> ```
> Please analyze each piece of code to determine if it can achieve the following functionalities. If not, provide an analysis of the issues and present the corrected and complete code:
> 
> 1. The plugin should be able to search through all existing vault content by either calling a function in the edit window or clicking the "Search Possible Bi-Directional Link in Vault" button in the settings panel;
> 2. The plugin should have a dedicated settings page;
> 3. Based on 1, store all content that appears more than once in the vault and that is not in bi-link format. Treat this content as potential bi-link keywords. Display a pop-up with the message "Search Finished!" once completed;
> 4. Present the top n results from the stored results of 2, in descending order of frequency, as a list in the plugin's settings page. Include an input field called "Option Count" and a button called "Update" in the settings page. The number entered by the user in the input field will determine how many options (i.e., n) are displayed in the list;
> 5. Based on the previous response, present the results from 4 in a four-column list format on the plugin's settings page. Each potential bi-link keyword will be an option in the list. The first column shows the index, the second column shows the frequency of the keyword's occurrence in the vault, the third column displays the keyword, and the fourth column indicates the current selection status of the option;
> 6. When the user clicks the "Update Bi-Link For Selected Options" button on the settings page, iterate through all the selected options from 5 and replace their corresponding content in the original locations with bi-link format;
> 7. The settings page of the plugin should include a dedicated list called "Ignored Content List." This list has four columns: index, frequency of the potential bi-link keyword's occurrence in the vault, the keyword itself, and the current selection status of the option;
> 8. When the user clicks the "Ignore Selected Option(s)" button on the settings page, iterate through all the selected options from 5. Exclude these options from the potential bi-link keyword list, add them to the Ignored Content List, and display them within it. The contents of the Ignored Content List should be sorted in descending order based on the Count in the second column;
> 9. When the user clicks the "Remove From Ignored Content List" button on the settings page, iterate through all the selected options from 7 and re-add them to the potential bi-link keyword list.
> ```
