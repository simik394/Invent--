---
abstract: "This plugin for Obsidian creates a small File Info view that displays the active file's date created, date modified, file size, and links to open the file in its native application and to open the file's folder."
page-title: "CattailNu/obsidian-file-info-panel-plugin: This plugin for Obsidian creates a small File Info view that displays the active file's date created, date modified, file size, and links to open the file in its native application and to open the file's folder."
url: https://github.com/CattailNu/obsidian-file-info-panel-plugin
date: "2024-04-12 04:44:22"
tags: 
- A/sw/plugin/file-info
- F/homepage
- C/
- P/
about: 
- "[[Obsidian]]"
aliases: 
- 05ecb7e9-f792-4afb-8f25-fdf0901ed06f
- CattailNu/obsidian-file-info-panel-plugin: This plugin for Obsidian creates a small File Info view that displays the active file's date created, date modified, file size, and links to open the file in its native application and to open the file's folder.
by: 
length: 8292
dir: 
---

## obsidian-file-info-panel-plugin

[](https://github.com/CattailNu/obsidian-file-info-panel-plugin#obsidian-file-info-panel-plugin)

This plugin for [Obsidian](https://obsidian.md/) creates a File Information view that displays the active file's date created, date modified, file size, and links to open the file in its native application and to open the file's folder. It also has writing statistics (character, word, sentence, and paragraph counts) and a word frequency analysis.

## Usage

[](https://github.com/CattailNu/obsidian-file-info-panel-plugin#usage)

After enabling the plugin in the settings menu, you should see the info button appear in the left navigation panel. This will toggle the File Info Panel view.

The File Info Panel settings allows you to set which file information is displayed.

## Features

[](https://github.com/CattailNu/obsidian-file-info-panel-plugin#features)

-   Click on the file name to open the file in its native app.
-   Click on the folder name to open the file's location.
-   Unobtrusive text matches your currently installed theme.
-   File size is displayed in human-readable format (includes bytes, KB, MB, GB, etc.).
-   Image files show image width and height.
-   Dates include human-readable "from now" text. Example:

> Mon, Nov 22, 2021 7:59 PM
> 
> 21 days ago

-   Writing statistics:
    -   Character, word, sentence, and paragraph counts.
    -   Selected text's character, word, sentence, and paragraph counts.
    -   Estimated page count based on your provided words per page.
    -   Word frequency analysis. Optional split into two lists based on your provided regex.
    -   URLs and File names can be separate from Word counts.

## Compatibility

[](https://github.com/CattailNu/obsidian-file-info-panel-plugin#compatibility)

`obsidian-file-info-panel-plugin` has been tested on Mac and Windows 11, Obsidian v0.12.19. Mobile versions appear to be working.

## Settings

[](https://github.com/CattailNu/obsidian-file-info-panel-plugin#settings)

-   **Show Date Created**: Display the date and time the file was created.
    
-   **Show Date Modified**: Display the date and time the file was last modified.
    
-   **Show File Size**: Display the human readable file size.
    
-   **Show File**: Display the file name as a link to open the file in its default application.
    
-   **Show Folder**: Display the file's folder as a link to open that folder.
    
-   **Show Folder as Relative Path**: Display the file's vault-relative location rather than the full path.
    
-   **Show Character Count**: Display a character count for md and txt files.
    
-   **Show Word Count**: Display a word count for md and txt files.
    
-   **Show Sentence Count**: Display a sentence count for md and txt files.
    
-   **Show Paragraph Count**: Display a paragraph count for md and txt files. Does not include empty lines.
    
-   **Show Page Count Estimate**: Display a sentence count for md and txt files.
    
-   **Words Per Page**: Enter the estimated words per page to use in the page count calculation.
    
-   **Show a Word Frequency Report**: Display a sorted list of unique words and how often these were used.
    
-   **Filter Word Frequency Report**: Split the report into two lists using the provided regex.
    
-   **Filter Regex**: Customize which words are split out of the main report. [Regex Assistance](https://cattail.nu/obsidian/filePluginRegexHelper.html)
    
-   **Show Filtered Words**: Show the words filtered by the above regex.
    
-   **Show a URL and File Frequency Report**: Shows mentioned URLs and files.
    
-   **Exclude URLs and Files From Word Frequency Report and Word Counts**: Excludes URLs and Files from the word-count parsers. Does not apply to characters, sentences, paragraphs, or pages.
    
-   **Show Selected Character Count**: Display a character count for selected text.
    
-   **Show Selected Word Count**: Display a word count for for selected text.
    
-   **Show Selected Sentence Count**: Display a sentence count for selected text.
    
-   **Show Selected Paragraph Count**: Display a paragraph count for selected text. Does not include empty lines.
    

## Screenshots

[](https://github.com/CattailNu/obsidian-file-info-panel-plugin#screenshots)

[![File Info Panel Info view](https://camo.githubusercontent.com/a5d654babcb8fb1d8f56de785ac6fac7a56e37b0c0c2756e8ff7c3b7f32bcdeb/68747470733a2f2f6361747461696c2e6e752f6f6273696469616e2f73637265656e73686f745f3131302e706e67)](https://camo.githubusercontent.com/a5d654babcb8fb1d8f56de785ac6fac7a56e37b0c0c2756e8ff7c3b7f32bcdeb/68747470733a2f2f6361747461696c2e6e752f6f6273696469616e2f73637265656e73686f745f3131302e706e67)

\*Screenshot is not showing the URL/File exclusion report.

[Enlarge Above](https://cattail.nu/obsidian/screenshot_110.png)

[![File Info Panel Info button](https://camo.githubusercontent.com/c0bd2ce70eb07b3e817d91e9d14415ce8ad89a6a0370d197a46b20db5c584aeb/68747470733a2f2f6361747461696c2e6e752f6f6273696469616e2f736964656261725f69636f6e5f73637265656e73686f742e706e67)](https://camo.githubusercontent.com/c0bd2ce70eb07b3e817d91e9d14415ce8ad89a6a0370d197a46b20db5c584aeb/68747470733a2f2f6361747461696c2e6e752f6f6273696469616e2f736964656261725f69636f6e5f73637265656e73686f742e706e67)

[![File Info Panel Info setting 1 of 4](https://camo.githubusercontent.com/ad3beef351b63c64017a112cb236aef0b6a60e4eb98836a12719b412c3272f7c/68747470733a2f2f6361747461696c2e6e752f6f6273696469616e2f73657474696e6730315f3132302e706e67)](https://camo.githubusercontent.com/ad3beef351b63c64017a112cb236aef0b6a60e4eb98836a12719b412c3272f7c/68747470733a2f2f6361747461696c2e6e752f6f6273696469616e2f73657474696e6730315f3132302e706e67)

[![File Info Panel Info setting 2 of 4](https://camo.githubusercontent.com/7c8e8fa578382f7d0dcdfa8670e707184b4f309158c202fc05839986c09a1a21/68747470733a2f2f6361747461696c2e6e752f6f6273696469616e2f73657474696e6730325f3131302e706e67)](https://camo.githubusercontent.com/7c8e8fa578382f7d0dcdfa8670e707184b4f309158c202fc05839986c09a1a21/68747470733a2f2f6361747461696c2e6e752f6f6273696469616e2f73657474696e6730325f3131302e706e67)

[![File Info Panel Info setting 3 of 4](https://camo.githubusercontent.com/bbdf9ca8775d6b1f056f46bb2794465f02228236c13e9505f2522d8ab0f87a35/68747470733a2f2f6361747461696c2e6e752f6f6273696469616e2f73657474696e6730335f3132302e706e67)](https://camo.githubusercontent.com/bbdf9ca8775d6b1f056f46bb2794465f02228236c13e9505f2522d8ab0f87a35/68747470733a2f2f6361747461696c2e6e752f6f6273696469616e2f73657474696e6730335f3132302e706e67)

... options for URL / file name report and exclusion ...

[![File Info Panel Info setting 4 of 4](https://camo.githubusercontent.com/4e388eb1f78d8332323f2a275a28f944e0626d31f278fcac4e9d0c31d775aba6/68747470733a2f2f6361747461696c2e6e752f6f6273696469616e2f73657474696e6730345f3131302e706e67)](https://camo.githubusercontent.com/4e388eb1f78d8332323f2a275a28f944e0626d31f278fcac4e9d0c31d775aba6/68747470733a2f2f6361747461696c2e6e752f6f6273696469616e2f73657474696e6730345f3131302e706e67)

## Customization

[](https://github.com/CattailNu/obsidian-file-info-panel-plugin#customization)

The following CSS Variables can be overridden in your `obsidian.css` file. See the notes for wrapping dates/file/folders in the css comments.

/\* obsidian-file-info-panel-plugin \*/
/\* https://github.com/CattailNu/obsidian-file-info-panel-plugin
20230112 updated to fix button styles that broke
 \*/

/\* all other tables \*/
.tlfFileInfoTable {
	display: table;
	border: none;
	margin: 0em;
	padding: 0em;
}

/\* the word filter report lists, file open/folder open buttons \*/
.tlfFileInfoTable100 {
	display: table;
	border: none;
	margin: 0em;
	padding: 0em;
	width: 100%;
}


.tlfFileInfoRow {
	display: table-row;
	border: none;
	margin: 0em;
	margin-bottom: 0.3em;
	padding: 0em;
}


.tlfFileInfoCell {
	display: table-cell;
	border: none;
	margin: 0px;
	margin-left: 0.5em;
	padding: 0em;
	text-align: left;
	white-space: nowrap;
}

/\* applies to word/url footnote \*/
.tlfFileInfoParagraph {
	display: table-cell;
	border: none;
	margin: 0px;
	margin-left: 0.5em;
	margin-right: 0.5em;
	padding: 0em;
	text-align: left;
	white-space: normal;
	word-break: break-word;
}


.tlfFileInfoLabel {
	border: none;
	margin: 0px;
	margin-right: 0.3em;
	padding: 0.3em;
	font-size: 0.7em;
	color: var(\--text-muted);
}

/\*
	To wrap date text automatically,
	replace "white-space: nowrap;" below in tlfFileInfoValue with:
	white-space: normal;
	word-break: break-word;
\*/

.tlfFileInfoValue {
	border: none;
	margin: 0px;
	padding: 0em;
	padding-left: 2em;
	padding-top: 0.3em;
	padding-bottom: 0.3em;
	font-size: 0.7em;
	font-weight: bold;
	height: auto;
	white-space: nowrap;
}

.tlfFileInfoValueNumber {
	border: none;
	margin: 0px;
	padding: 0em;
	padding-left: 3em;
	font-weight: bold;
	font-size: 0.7em;
	text-align: right;
}

.tlfFileInfoCellButton {
	display: table-cell;
	border: none;
	margin: 0px;
	padding: 0.3em;
	text-align: left;
	margin-left: 0.5em;
	padding: 0em;
}

/\*
	To wrap text in file name / folder name automatically,
	replace "white-space: nowrap;" below in tlfFileInfoButton with:
	white-space: normal;
	word-break: break-all;
\*/

.tlfFileInfoButton {
	border: none;
	margin: 0px;
	margin-bottom:0.3em;
	margin-top:0.3em;
	padding: 0px;
	text-align: left;
	font-size: 0.7em;
	background:none;
	color: var(\--text-muted);
	height: 2em;
	width:100%;
	max-width:100%;
	height:auto;
	white-space: nowrap;
}

.tlfFileInfoButton:Hover {
	font-weight: bold;
}

.tlfFileInfoTextArea {
	margin: 0px;
	padding: 0.3em;
	font-size: 0.7em;
	color: var(\--text-muted);
	line-height: 1.2;
	width: 100%;
	height: 8em;
}

[![File Info Panel CSS Customization Variables](https://camo.githubusercontent.com/7600d810f04615b7e50b24b0587e511f923147f508ac85c82bbd810e05fd423d/68747470733a2f2f6361747461696c2e6e752f6f6273696469616e2f6373735f637573746f6d697a6174696f6e5f7661726961626c65732e706e67)](https://camo.githubusercontent.com/7600d810f04615b7e50b24b0587e511f923147f508ac85c82bbd810e05fd423d/68747470733a2f2f6361747461696c2e6e752f6f6273696469616e2f6373735f637573746f6d697a6174696f6e5f7661726961626c65732e706e67)

## Say Thanks 🙏

[](https://github.com/CattailNu/obsidian-file-info-panel-plugin#say-thanks-)

Consider reading and sharing one of my books (available through Amazon). There are fantasy, science fiction, novelty art books, non-fiction, and a thriller. Share links to them. Seriously, I really need your help as an author getting the word out. Trying to be an independently-published author is challenging.

[https://www.amazon.com/T.-L.-Ford/e/B0034Q6Q2S](https://www.amazon.com/T.-L.-Ford/e/B0034Q6Q2S)

You'll also find a bunch of free content and writing/art tools on my personal website.

[https://www.Cattail.Nu](https://www.cattail.nu/)

Featured: Make your own dreamcatcher graphics: [http://www.cattail.nu/journal\_tools/page\_dreamcatcher\_art.html](http://www.cattail.nu/journal_tools/page_dreamcatcher_art.html)

## Change Log

[](https://github.com/CattailNu/obsidian-file-info-panel-plugin#change-log)

Thank you to those who have taken the time to submit issues on github. Your feedback is helpful!

### 1.3

[](https://github.com/CattailNu/obsidian-file-info-panel-plugin#13)

-   Feature add: separate URLs from word counts and word frequency report. (Issue #9)
-   Feature add: open and close items for hotkeys. (Issue #10)
-   Feature add: show image width/height for images. (Issue #11)
-   Bug Fix: css updated for new version that broke the old css. (Issue #12)

### 1.2.5

[](https://github.com/CattailNu/obsidian-file-info-panel-plugin#125)

-   Bug fix (Issue #8).

### 1.2.4

[](https://github.com/CattailNu/obsidian-file-info-panel-plugin#124)

-   Mobile versions working.
-   Selected text counts functioning again (broke with new version of Obsidian).
-   Optimization.
-   Potential bug fixes.

### 1.2.1

[](https://github.com/CattailNu/obsidian-file-info-panel-plugin#121)

-   Removed reference to timer in the settings as it is no longer used.
-   Changed to say "No file." when there is no file.
-   Fixed a display bug when file is dragged out of the vault folder while it is open in Obsidian.
-   Changed all settings to be on by default.

### 1.2.0

[](https://github.com/CattailNu/obsidian-file-info-panel-plugin#120)

-   Added setting option to change date diplay format.
-   Updated view/css to allow better fine-tuning, specifically, the ability to wrap text for file/folder names and filter lists.
-   Added setting option to display the folder path as relative to vault.
-   Adjusted word frequency textbox display.
-   Added setting option to show/hide filtered words.
-   Changed the selected text algorithm from a timer to an event, improving responsiveness.
-   Changed the document path code to try and fix android issues.

### 1.1.0

[](https://github.com/CattailNu/obsidian-file-info-panel-plugin#110)

Addition of document statistics.

-   Character count
-   Word count
-   Sentence count
-   Paragraph count
-   Estimated pages
-   Word frequency report with regex filter
-   Selected characters count
-   Selected Words count
-   Selected Sentences count

### 1.0.1

[](https://github.com/CattailNu/obsidian-file-info-panel-plugin#101)

Initial release: File name link, date modified, date created, full folder path link.