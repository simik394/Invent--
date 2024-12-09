---
page-title: "GitHub - pyrochlore/obsidian-tracker: A plugin tracks occurrences and numbers in your notes"
url: https://github.com/pyrochlore/obsidian-tracker
date: 2024-03-03 17:11:05
tags:
  - A/sw/plugin
  - F/homepage
  - C/
  - P/pwf/visObsiData
  - M/⭐/pwf
about:
  - "[[Obsidian]]"
related_to:
  - "[[Prods/pwf/_goals/visualize answers to queries from obsidian data|visualize answers to queries from obsidian data]]"
uuid: 78d2a707-8cb8-43d1-92bb-1b4a42fcdffe
---

## Obsidian Tracker Plugin

[](https://github.com/pyrochlore/obsidian-tracker#obsidian-tracker-plugin)

[![GitHub release](https://camo.githubusercontent.com/286cdffdf926ef43d965bad2f594fe1a6c3d56217378cc9037bddf273e88665f/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f762f72656c656173652f7079726f63686c6f72652f6f6273696469616e2d747261636b6572)](https://camo.githubusercontent.com/286cdffdf926ef43d965bad2f594fe1a6c3d56217378cc9037bddf273e88665f/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f762f72656c656173652f7079726f63686c6f72652f6f6273696469616e2d747261636b6572)

[![](https://raw.githubusercontent.com/pyrochlore/obsidian-tracker/master/docs/images/screenshot_v1.9.png)](https://raw.githubusercontent.com/pyrochlore/obsidian-tracker/master/docs/images/screenshot_v1.9.png)

This is an [Obsidian](https://obsidian.md/) plugin that helps you collect data from notes and represent it comprehensively.

[Here](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Examples.md) is a table containing simplified examples showing what you can track.

## What's New

[](https://github.com/pyrochlore/obsidian-tracker#whats-new)

Version 1.13.2

-   Update dependencies
-   Fix typo in README.md
-   Change streak counts to terminate on falsey values rather than null

Version 1.13.1

-   Fix packaging script

Version 1.13.0

-   Add support for inline dataview fields (including emoji support for values)
-   Update dependencies

Version 1.12.0

-   Add aspect ratio parameter for graphs
-   Reorganize release notes in readme to be in descending order (latest release first)

Version 1.11.0

-   Add support for checkboxes in new properties added in Obsidian 1.4
-   Fix typos in documentation and examples

Version 1.10.9

-   Replace tab characters by spaces
-   Accept more unicode characters in dvField
-   Allow emojis in the folder path
-   Fixed bugs

Version 1.10.8

-   Fixed startDate/endDate misread as a relative date

Version 1.10.7

-   Allow using html image tags as emoji inputs

Version 1.10.6

-   Fixed the coloring for missing data in the month view

Version 1.10.5

-   Allow using a relative date value in `initMonth` in the month view

Version 1.10.4

-   Allow using a regular expression as a key of the parameter `textValueMap`
-   Add a parameter `shiftOnlyValueLargerThan` to determine when to do `valueShift`
-   Fixed bugs reported by users
-   Fixed typo in plugin settings

Version 1.10.3

-   Allow using the parameter `fitPanelWidth` with the output type `month` and `pie`
-   Fixed the resizing and positioning of the chart tooltip

Version 1.10.2

-   Fixed plugin not rendering on some macOS machines

Version 1.10.1

-   Fixed 'failed to load plugin' on iOS

Version 1.10.0

-   Add annotation mode for month view ([examples](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestCalendar.md))
-   Add parameters `xAxisTickInterval`, `yAxisTickInterval`, `xAxisTickLabelFormat` and `yAxisTickLabelFormat` for the line and bar chart ([examples](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestAxisIntervalAndFormat.md))
-   Allow using regular expression in parameter `dateFormatPrefix` and `dateFormatSuffix` ([examples](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestDateFormats.md))
-   Add parameters `file`, `specifiedFilesOnly`, `fileContainsLinkedFiles`, and `fileMultiplierAfterLink` to retrieve data from specified files ([examples](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestSpecifiedFiles.md))
-   Add a parameter `textValueMap` to convert texts or emojis to specified values ([examples](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestTextValueMap.md))
-   Fixed bugs
-   Enhanced error messages

## !!! Breaking Changes !!!

[](https://github.com/pyrochlore/obsidian-tracker#-breaking-changes-)

From version 1.9.0, template variables, e.g. '{{sum}}', are deprecated. Instead, Tracker provide operators (+, -, \*, /, %) and functions (dataset(), sum(), maxStreak(), ......etc) to help us do data processing. For users having code blocks from previous version, please replace '{{sum}}' by '{{sum()}}' or '{{sum(1)}}' by '{{sum(dataset(1))}}'. More information about the new expressions could be found [here](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Expressions.md).

## Usage

[](https://github.com/pyrochlore/obsidian-tracker#usage)

1.  Have some targets you want to track in daily notes.
2.  Add a new note for displaying the tracker.
3.  Add tracker code blocks manually ([examples](https://github.com/pyrochlore/obsidian-tracker/tree/master/examples)) or using [commands](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Commands.md).
4.  Switch the document view mode to 'Preview', then the code block will get rendered.

For more use cases, please download and open the [examples](https://github.com/pyrochlore/obsidian-tracker/tree/master/examples) folder in obsidian with this plugin installed and enabled.

## More Details You May Want to Know

[](https://github.com/pyrochlore/obsidian-tracker#more-details-you-may-want-to-know)

-   [Installation](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Installation.md): Install the plugin from Obsidian or install it manually
-   [Concepts](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Concepts.md): Explain how this plugin works and what to setup
    -   [Target Evaluation](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/TargetEvaluation.md)
    -   [Input Parameters](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/InputParameters.md)
    -   [Expressions](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Expressions.md)
-   [Examples](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Examples.md)
-   [Plugin Settings](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Settings.md)
-   [Release Notes](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/ReleaseNotes.md)
-   [Road Map](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/RoadMap.md)
-   [Frequently Asked Questions](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Questions.md)

## Support

[](https://github.com/pyrochlore/obsidian-tracker#support)

-   If you like this plugin or want to support further development, you can [Buy Me a Coffee](https://www.buymeacoffee.com/pyrochlore).
-   Please report bugs and request features in [GitHub Issues](https://github.com/pyrochlore/obsidian-tracker/issues)


# Docs
## 2024-06-23 22:48:53

## Target Evaluation

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/TargetEvaluation.md#target-evaluation)

From the [input parameters](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/InputParameters.md) you provided, the search targets dispersed in the notes will be counted or evaluated as a value. Tracker plugin supports eight kinds of `searchType`: `tag`, `frontmatter`, `wiki`, `text`, `table`, `dvField`, `task`, and `fileMeta`, dealing with different types of searching condition.

## Multiple Targets

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/TargetEvaluation.md#multiple-targets)

You can provide multiple search targets in code block by entering an array of targets separated by a comma under parameter `searchType` and `searchTarget`. Each of the targets will be identified in order and then the values in notes will be evaluated and form a dataset indexed by that order in the array (zero-based indexing).

```
searchTarget: target0, target1, target2, ...... 
searchType: type0, type1, type2, .....
datasetName: dataset0, dataset1, dataset2, ......
line:
    lineColor: red, blue, yellow
```

Above is an example of multiple targets searching. In the code block, multiple targets are provided and separated by a comma. If they have a different searchType, provide the same number of types in the same order. In this case, the second search target 'target1' with index 1 has type 'type1' and name 'dataset1'.

Many other parameters that accept multiple values (e.g. lineColor) can also be provided and the value given will be applied to the corresponding dataset.

## Multiple Values

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/TargetEvaluation.md#multiple-values)

Multiple values under a target (value tuple) separated by a slash, e.g. `#bloodpressure`:180/120mmHg, are supported after version 1.3.0. To identify a specific value as a target, use an accessor with bracket notation where the value in the bracket is the index by the order of values. In this case, they are bloodpressure\[0\] and bloodpressure\[1\]. You can find the example of this [here](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/BloodPressureTracker.md). You can also use a custom separator by using the parameter `separator`.

## Search Target in Detail

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/TargetEvaluation.md#search-target-in-detail)

### searchType: tag

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/TargetEvaluation.md#searchtype-tag)

Simple tags in the format of '*#tagName*' in the file content are evaluated as a constant value (default value 1.0). You can override the value by assigning the key `constValue` in the code block. Use the tag name (the name after #) as the value of key `searchTarget` or use quoted tag (`#tagName`) to make it work.

For tags in frontmatter (e.g. tags: meditation), it works like simple tags and will be evaluated as a constant value. For example,

\---  
tags: tagName1, tagName2  
......  
\---  

Set `searchTarget` to tagName1 or tagName2 will make the plugin do its work.

In your content, a value can be attached to the tag in the format of '*#tagName:value*'. Note the value should be appended right after your tag and an extra colon **without spaces**. If a value is attached this way, the obsidian-tracker will automatically use the provided value instead of the constant one.

Nested tags with values attached could be useful for tracking children's data separately and also still see the overall merged data using parent tags.

If you don't want value-attached tags in your content, you can also put data in front matter and use `frontmatter` as your searchType.

### searchType: frontmatter

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/TargetEvaluation.md#searchtype-frontmatter)

This search type is used to query the key-value pairs in the front matter. If you don't want these values been seen in your article, the front matter would be the best place to record. For example,

\---  
mood: 10  
......  
\---  

### searchType: wiki

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/TargetEvaluation.md#searchtype-wiki)

This search type helps you count wiki links in articles. For example, \[\[A\]\] \[\[B|Link to B\]\]

### searchType: text

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/TargetEvaluation.md#searchtype-text)

searchType `text` is the most powerful one among all. If you simply provide text like 'love', the number of occurrences of tags will be counted. You can provide a regular expression to search for a very complicated target by wrapping it in single quotes. If you want to retrieve a value from it, use the group name in the expression. To see more detail, see [this case](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestRegex.md).

Multiple values in text search can be achieved by separate regex by comma and wrap them all in single quotes as follows:

```
searchTarget: 'regex1, regex2'
......
```

### searchType: dvField

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/TargetEvaluation.md#searchtype-dvfield)

Tracker supports retrieving inline fields used with the dataview plugin. To get "targetName:: value" in your article, try the following tracker settings.

```
searchType: dvField
searchTarget: targetName
......
```

If you have multiple values in field, like "targetName:: 123 @ 456", use the following tracker settings.  

```
searchType: dvField
searchTarget: targetName[0], targetName[1]
separator: '@'
......
```

More dvField example can be found [here](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestMultipleTargesMultipleValues.md#multiple-values-in-dvfield-dataview-inline-field).

### searchType: table

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/TargetEvaluation.md#searchtype-table)

This search type is very much different from others because it does not search over files in the specified folder. Instead, it looks into a given file, finds the specified table, and retrieves data from specified columns. Here is an example,

```
searchType: table
searchTarget: data/Tables[0][0], data/Tables[0][1], data/Tables[0][2]
xDataset:
line:
    yAxisLocation: none, left, right
    lineColor: none, yellow, red
    showLegend: true
```

In this case, "data/Tables" is the path of the file of interest. The number in the first brackets after the path (\[0\]) is the index of the table of interest in the file, starts from 0. And the number in the second brackets is the index of the column containing target data. If there are multiple values in table cells, you can provide a third index to identify them.

More table examples can be found [here](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestTable.md).

### searchType: fileMeta

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/TargetEvaluation.md#searchtype-filemeta)

With this search type, you can retrieve infomation of files. Currently, three kinds of data you can get.

-   cDate: creation date of a file
-   mDate: last modification date of a file
-   size: file size in bytes
-   numWords: number of words in a file
-   numChars: number of characters in a file (including spaces)
-   numSentences: number of setences in a file

`cData` and `mDate` can be used as X dataset and `size` can be used as Y dataset.

### searchType: task

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/TargetEvaluation.md#searchtype-task)

You can retrieve infomation from tasks by using `searchType` `task`. The provided `searchTarget` will limit the result with task's contents match the input.

Using type `task` or `task.all` will get you all tasks no matter it is done or not. To get task done, use `task.done`. By contrast, use `task.notdone`.

# examples

## obsidian-tracker/examples at master · pyrochlore/obsidian-tracker
[online](https://github.com/pyrochlore/obsidian-tracker/tree/master/examples)
date: "2024-08-17 03:01:25"

## Finance Tracker

``` tracker
searchType: tag
searchTarget: finance
folder: diary
accum: true
line:
    title: Finance
    yAxisLabel: USD
    lineWidth: 4
```


``` tracker
searchType: tag
searchTarget: finance/bank1
folder: diary
accum: true
line:
    title: Bank1
    yAxisLabel: USD
```


``` tracker
searchType: tag
searchTarget: finance/bank2
folder: diary
accum: true
line:
    title: Bank2
    yAxisLabel: USD
    fillGap: true
```

Please also check those search targets in markdown files under folder 'diary'.
