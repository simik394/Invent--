# 1 online docs:
[Home - Various Complements (tadashi-aikawa.github.io)](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/)

## 1.1 📚 Custom dictionaries

### 1.1.1 Word definitions

#### 1.1.1.1 Inserted text
is used for inserting text after selecting a suggestion 
**but <mark class="hltr-orange">NOT USED for <b>MATCHING</b></mark>.

#### 1.1.1.2 Displayed text
is used for 
	displaying suggestions 
	and <mark class="hltr-orange"><b>MATCHING</b></mark> them.

![Pasted image 20220508152230.png](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/resources/Pasted%20image%2020220508152230.png)

Inserted text and Displayed text are the same 
<mark class="hltr-red"><b>EXCEPT</b> FOR </mark>the following cases:
- Use [⚙️ Delimiter to divide suggestions for display from ones for insertion](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/4.%20Options/4.6.%20Custom%20dictionary%20complement/%E2%9A%99%EF%B8%8F%20Delimiter%20to%20divide%20suggestions%20for%20display%20from%20ones%20for%20insertion/) in [📚 Custom dictionary formats#CSV like](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionary%20formats/#csv-like) format
- Use [⚙️ Delimiter to hide a suggestion](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/4.%20Options/4.6.%20Custom%20dictionary%20complement/%E2%9A%99%EF%B8%8F%20Delimiter%20to%20hide%20a%20suggestion/) in [📚 Custom dictionary formats#CSV like](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionary%20formats/#csv-like) format
- Specify a `displayed` property in [📚 Custom dictionary formats#JSON](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionary%20formats/#json) format

#### 1.1.1.3 Description
is used for showing a detail about a suggestion **but not used for matching**.

![Pasted image 20220508153756.png](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/resources/Pasted%20image%2020220508153756.png)

#### 1.1.1.4 Aliases
 are used for matching suggestions **but never displayed**.

![Pasted image 20220508154049.png](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/resources/Pasted%20image%2020220508154049.png)


### 1.1.2 Custom dictionary formats

#### 1.1.2.1 CSV like

##### 1.1.2.1.1 Definitions

###### 1.1.2.1.1.1 Row delimiter[¶](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionary%20formats/#row-delimiter "Permanent link")

Line breaks

###### 1.1.2.1.1.2 Column delimiter[¶](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionary%20formats/#column-delimiter "Permanent link")

Value set in [⚙️ Column delimiter](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/4.%20Options/4.6.%20Custom%20dictionary%20complement/%E2%9A%99%EF%B8%8F%20Column%20delimiter/)

###### 1.1.2.1.1.3 Column definitions[¶](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionary%20formats/#column-definitions "Permanent link")

|Col1|Col2|Col3 and later|
|---|---|---|
|[Inserted text](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionaries/#inserted-text)/[Displayed text](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionaries/#displayed-text)|[Description](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionaries/#description)|[Aliases](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionaries/#aliases)|

###### 1.1.2.1.1.4 Comment syntax[¶](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionary%20formats/#comment-syntax "Permanent link")

If a line starts with `%%`, It regards the line as a comment line.

###### 1.1.2.1.1.5 Escape syntax[¶](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionary%20formats/#escape-syntax "Permanent link")

|syntax|actual text|
|---|---|
|`\n`|Line break|
|`\t`|Tab|

###### 1.1.2.1.1.6 Other[¶](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionary%20formats/#other "Permanent link")

- [⚙️ Delimiter to divide suggestions for display from ones for insertion](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/4.%20Options/4.6.%20Custom%20dictionary%20complement/%E2%9A%99%EF%B8%8F%20Delimiter%20to%20divide%20suggestions%20for%20display%20from%20ones%20for%20insertion/)
- [⚙️ Delimiter to hide a suggestion](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/4.%20Options/4.6.%20Custom%20dictionary%20complement/%E2%9A%99%EF%B8%8F%20Delimiter%20to%20hide%20a%20suggestion/)

##### 1.1.2.1.2 Example

- [⚙️ Column delimiter](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/4.%20Options/4.6.%20Custom%20dictionary%20complement/%E2%9A%99%EF%B8%8F%20Column%20delimiter/): `Comma`
- [⚙️ Delimiter to divide suggestions for display from ones for insertion](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/4.%20Options/4.6.%20Custom%20dictionary%20complement/%E2%9A%99%EF%B8%8F%20Delimiter%20to%20divide%20suggestions%20for%20display%20from%20ones%20for%20insertion/): `>>>`

```csv
value1

%% with description %%
value2,description

%% with aliase %%
value3,,v3,val3

%% with \n %%
- one\n- two\n- three,,onetwo

%% Displayed text is different from Inserted text %%
Displayed >>> Inserted
```

It will load it as...

|[Inserted text](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionaries/#inserted-text)|[Displayed text](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionaries/#displayed-text)|[Description](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionaries/#description)|[Aliases](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionaries/#aliases)[0]|[Aliases](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionaries/#aliases)[1]|
|---|---|---|---|---|
|value1|value1||||
|value2|value2|description|||
|value3|value3||v3|val3|
|- one  <br>- two  <br>- three|- one  <br>- two  <br>- three||onetwo||
|Inserted|Displayed||||

#### 1.1.2.2 JSON

##### 1.1.2.2.1 Definitions

|key|type|required|description|
|---|---|---|---|
|caretSymbol|string||If set, take precedence over [⚙️ Caret location symbol after complement](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/4.%20Options/4.6.%20Custom%20dictionary%20complement/%E2%9A%99%EF%B8%8F%20Caret%20location%20symbol%20after%20complement/)|
|ignoreSpaceAfterCompletion|boolean||If set, ignore [⚙️ Insert space after completion](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/4.%20Options/4.1.%20Main/%E2%9A%99%EF%B8%8F%20Insert%20space%20after%20completion/)|
|words|Word |yes||

###### 1.1.2.2.1.1 Word

|key|type|required|description|
|---|---|---|---|
|value|string|yes|[Inserted text](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionaries/#inserted-text)|
|description|string||[Description](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionaries/#description)|
|aliases|string[]||[Aliases](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionaries/#aliases)|
|displayed|string||If set, use as [Displayed text](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionaries/#displayed-text)|

##### 1.1.2.2.2 Example

```json
{
  "caretSymbol": "~CUR~",
  "ignoreSpaceAfterCompletion": true,
  "words": [
    { "value": "value1" },
    { "value": "value2", "description": "hogehoge" },
    { "value": "value3", "aliases": ["w3", "word3"] },
    { "value": "begin\n[[CARET]]\nend", "displayed": "code-json" }
  ]
}
```

It will load it as...

|[Inserted text](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionaries/#inserted-text)|[Displayed text](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionaries/#displayed-text)|[Description](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionaries/#description)|[Aliases](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionaries/#aliases)[0]|[Aliases](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionaries/#aliases)[1]|
|---|---|---|---|---|
|value1|value1||||
|value2|value2|hogehoge|||
|value3|value3||w3|word3|
|begin  <br>~CUR~  <br>end|code-json||||

`~CUR~` is the caret location after completion.

##### 1.1.2.2.3 Related issues

- [FR: Use JSONs for Custom Dictionaries · Issue #108](https://github.com/tadashi-aikawa/obsidian-various-complements-plugin/issues/108)
## 1.2 Custom dictionary complement

It suggests and completes the text with words in [📚 Custom dictionaries](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/5.%20Terms/%F0%9F%93%9A%20Custom%20dictionaries/).

### 1.2.1 Images[](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/1.%20Features/Custom%20dictionary%20complement/#images "Permanent link")

![custom-dictionary-complement-demo.gif](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/resources/custom-dictionary-complement-demo.gif)

Settings of the above demo are as follows.

⚙️ Enable Custom dictionary complement: ON (required)
⚙️ Custom dictionary paths: _Privates/dictionary-test.md
⚙️ Column delimiter: Tab
⚙️Word regex pattern:
⚙️ Delimiter to hide a suggestion:
⚙️ Delimiter to divide suggestions for display from ones for insertion:
⚙️ Caret location symbol after complement: \<CARET>

## 1.3 ⚙️ Match strategy

### 1.3.1 Definitions[¶](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/4.%20Options/4.1.%20Main/%E2%9A%99%EF%B8%8F%20Match%20strategy/#definitions "Permanent link")

- `prefix` (default)
- `partial`

### 1.3.2 Examples[¶](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/4.%20Options/4.1.%20Main/%E2%9A%99%EF%B8%8F%20Match%20strategy/#examples "Permanent link")

#### 1.3.2.1 prefix[¶](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/4.%20Options/4.1.%20Main/%E2%9A%99%EF%B8%8F%20Match%20strategy/#prefix "Permanent link")

Input `orange` doesn't suggest `appleOrangeGrape` because it doesn't start with `orange` or `Orange`.

![match-storategy-prefix.gif](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/resources/match-storategy-prefix.gif)

#### 1.3.2.2 partial[¶](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/4.%20Options/4.1.%20Main/%E2%9A%99%EF%B8%8F%20Match%20strategy/#partial "Permanent link")

Input `orange` suggest `appleOrangeGrape` because it includes `Orange`.

![match-storategy-partial.gif](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/resources/match-storategy-partial.gif)

### 1.3.3 Notes[¶](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/4.%20Options/4.1.%20Main/%E2%9A%99%EF%B8%8F%20Match%20strategy/#notes "Permanent link")

There are two crucial points you should know.

- `partial` suggests many suggestions, it might be noisy for you depending on the situation
- `partial` is more than **10 times slower** than `prefix`

### 1.3.4 Related issues[¶](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/4.%20Options/4.1.%20Main/%E2%9A%99%EF%B8%8F%20Match%20strategy/#related-issues "Permanent link")

- [Version 3.0 and above, the candidate words obtained are incomplete · Issue #41](https://github.com/tadashi-aikawa/obsidian-various-complements-plugin/issues/41)


