---
page-title: "linanwx/aosr: Aosr is Another Obsidian plugin for Spaced Repetition."
url: https://github.com/linanwx/aosr
date: "2024-03-20 14:40:41"
tags: 
- A/sw/plugin
- F/homepage
- C/
- P/
about: "[[Obsidian]]"
aliases: 
- 56f3ee6b-a39f-4b4a-b8a9-b1df8d694cdc
- linanwx/aosr: Aosr is Another Obsidian plugin for Spaced Repetition.
by: 
length: 19190
dir: 
---

## Aosr

[](https://github.com/linanwx/aosr#aosr)

[![GitHub all releases](https://camo.githubusercontent.com/fc01a92c5fcf54975db1c8869a2dc0c89e1d28b6a2649c08e5aecea06309f529/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f646f776e6c6f6164732f6c696e616e77782f616f73722f746f74616c)](https://camo.githubusercontent.com/fc01a92c5fcf54975db1c8869a2dc0c89e1d28b6a2649c08e5aecea06309f529/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f646f776e6c6f6164732f6c696e616e77782f616f73722f746f74616c) [![release](https://camo.githubusercontent.com/8860e2e0f515a08cbcb4156e312b7e1abda6ac7e7b68d22db4b4a3257c0d59b4/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f762f72656c656173652f6c696e616e77782f616f7372)](https://camo.githubusercontent.com/8860e2e0f515a08cbcb4156e312b7e1abda6ac7e7b68d22db4b4a3257c0d59b4/68747470733a2f2f696d672e736869656c64732e696f2f6769746875622f762f72656c656173652f6c696e616e77782f616f7372)

Aosr is **A**nother **O**bsidian plugin for **S**paced **R**epetition.

It uses flashcards to help remember knowledge.

This plugin is similar to [spaced repetition](https://github.com/st3v3nmw/obsidian-spaced-repetition), but some changes have been made according to personal habits.

## What's New

[](https://github.com/linanwx/aosr#whats-new)

-   The new feature now writes review data separately inside the .obsidian/aosr.db file, so it no longer affects the notes. If you need to immediately migrate all the old data from the notes to the new DB file and clean up the old notes, there is a migration tool available in the settings interface.

## Features

[](https://github.com/linanwx/aosr#features)

-   **Rich Text Format Support**: The plugin supports rich text formats such as audio. This allows you to create multimedia flashcards for a more immersive learning experience.
-   **Dedicated Review Window**: The plugin features a separate review window, allowing you to review cards while simultaneously making changes to them in the editor. This is perfect for making quick adjustments on the fly.
-   **Minute-Level Review Intervals**: The plugin allows you to set review intervals down to the minute. This offers a high level of precision in scheduling your reviews.
-   **Three Basic Learning Types**: The plugin supports three basic learning types - single line, multi-line, and cloze deletion.
-   **Mobile Optimization for Review Interface:** The plugin now supports mobile devices, providing an optimized review interface specifically designed for mobile users. This ensures a seamless and user-friendly experience when reviewing cards on your mobile device.
-   **Multi-language support**: Supports virtually all languages within Obsidian. Translated by ChatGPT.
-   **Deck Functionality**: Aosr now includes a powerful Deck feature that allows you to manage your flashcards in a highly customizable manner. You can define your own rules to manage your decks, providing a tailored review experience.

## Demo

[](https://github.com/linanwx/aosr#demo)

The demo shown below is from an earlier version. You can refer to its operation process. Some of the content has been optimized.

[![屏幕录制2022-11-08 17 56 11](https://user-images.githubusercontent.com/16589958/200536163-9aa947ff-0898-40ec-ae6a-911fc9107098.gif)](https://user-images.githubusercontent.com/16589958/200536163-9aa947ff-0898-40ec-ae6a-911fc9107098.gif)

## Format

[](https://github.com/linanwx/aosr#format)

## Card

[](https://github.com/linanwx/aosr#card)

A CARD begins with `#Q` and ends with an empty line. Caution: #Q is case sensitive.

`#Q  This is a card. Here, please write your questions and answers in Pattern format. The format of Pattern is described below. Only content within the #Q and the empty line will be treated as review content. Pattern formats outside this range will not be processed. <- There should have an empty line if this is not the end of the document.`

In the card, the PATTERN is your question and answer.

A card can contain multiple patterns. For instance, if you're studying a vocabulary list, your card could include several lines of :: style patterns, each pairing a word with its definition. In essence, you can think of a card as a text block within Obsidian, while a pattern is a question and its corresponding answer. A single text block can contain multiple questions and their respective answers.

Using `***` to split the card into sub-cards. This would be helpful if you don't want to write `#Q` and create a new card.

The effect of the above writing is the same as that of the following.

### Range Cards (Scope Cards)

[](https://github.com/linanwx/aosr#range-cards-scope-cards)

Range Cards, also known as Scope Cards, are a special type of card in the Markdown format. They were introduced as a new feature to enhance the flexibility of creating flashcards.

A Range Card begins with `#Q` and ends with `#/Q`. The Range Card's unique feature is that it supports formats that include empty lines, making it versatile for various content types. Here is an example:

#Q
...
(blank line)
...
(blank line)
...
#/Q

Apart from this, Range Cards behave similarly to Block Cards in all other respects.

In the context of Range Cards, patterns still follow their usual rules. Notably, the multi-line pattern does not include complete blank lines. However, within Range Cards, you can create multiple multi-line patterns, each separated by blank lines. In the cloze deletion format, the question - that is, the remaining text - extends across the entire card.

This introduces some best practices for using Range Cards.

1.  **Creating Multiple Multi-line Question Groups**: You can leverage the format of Range Cards to create multiple multi-line patterns. These patterns can be individually grouped and separated by blank lines, providing you with a flexible way of organizing complex information.
    
2.  **Creating a Complex Question with a Cloze Deletion Answer**: If you're dealing with intricate topics, you can create a comprehensive question, and then use the cloze deletion format (`==`) to encapsulate the answer. If your answer spans multiple lines or you need to consider different sections as a whole answer, you may need to use the `#multicloze` tag to bundle multiple answers together.
    

Please be aware that if your answer is excessively complicated, involving many blank lines, you may need to reconsider your question structuring. Extremely complex answers may not be suitable for flashcard-based review.

## Pattern

[](https://github.com/linanwx/aosr#pattern)

A pattern represents a question and its corresponding answer.

### :: Pattern

[](https://github.com/linanwx/aosr#-pattern)

In the card, `::` symbol is used to split a line. The front part will become a question, and the back part will become an answer.

Each line will be processed as a separate Pattern.

```
word::definition
word::definition
word::definition
```

You can use the symbol `:::` to create cards that can be reviewed in both directions - from question to answer and from answer to question.

### ? Pattern

[](https://github.com/linanwx/aosr#-pattern-1)

In the card, a line with a `?` will divide the content into a question and an answer. The front part will become a question, and the back part will become an answer.

`Question. Maybe there are many lines. ? Answer. Maybe there are many lines.`

### \== Pattern

[](https://github.com/linanwx/aosr#-pattern-2)

In the card, a cloze with a pair of `==` will split this card. The remaining part will become a question, and the cloze part will become an answer. Note that each cloze will be treated as a separate Pattern.

```
Fruits include ==watermelons==, ==apples== and ==pears==.
```

Note that each cloze will be treated as a separate Pattern. Otherwise, you should write like this.

```
Fruits include ==watermelons, apples, and pears==.
```

In addition, you could add a [#multicloze](https://github.com/linanwx/aosr#multicloze-pattern) tag to the card to get the same effect.

##### Multicloze Pattern

[](https://github.com/linanwx/aosr#multicloze-pattern)

If a `#multicloze` tag has been found in the card, Aosr treats all cloze in the card as a group of cloze.

```
You should remember ==this== and ==that== at the same time. #multicloze 
```

## Example

[](https://github.com/linanwx/aosr#example)

Several examples are shown below. Their writing is valid in the document.

`#Q word1::ans1 word2::ans2 word3::ans3 word:::definition  #Q This is a question1. ? This is an answer. *** This is a question2. ? This is an answer.  #Q This is a very ==important== answer.  #Q word1::ans1 *** This is a question. ? This is an answer. *** This is a very ==important== answer. *** This is multi-cloze ==question== and ==answer==. #multicloze  #Q  Information  Complex card information  Complex card information  Complex card information  Answer: ==The answer.==  #/Q`

## Review

[](https://github.com/linanwx/aosr#review)

Once you've finished your document, click on the card icon in the sidebar to start reviewing.

[![屏幕快照 2022-11-15 的 12 59 37 下午](https://user-images.githubusercontent.com/16589958/201830351-1f2959d7-3610-4fc1-b0e5-1f031de25ee4.png)](https://user-images.githubusercontent.com/16589958/201830351-1f2959d7-3610-4fc1-b0e5-1f031de25ee4.png)

It consists of three parts. New, Review and Learning.

[![Screenshot 2023-06-13 at 11 52 37 AM](https://private-user-images.githubusercontent.com/16589958/245346565-572181c7-70e6-4f0a-9db0-2b0c31dd5819.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTA5NDIzMzIsIm5iZiI6MTcxMDk0MjAzMiwicGF0aCI6Ii8xNjU4OTk1OC8yNDUzNDY1NjUtNTcyMTgxYzctNzBlNi00ZjBhLTlkYjAtMmIwYzMxZGQ1ODE5LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAzMjAlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMzIwVDEzNDAzMlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTljN2U4ZWZlNWY5ZGM2NmI4MjU3MGM4MzNiMTFlMWEzN2I1NzEyMWU3NWQ4ZThjNzBiMjE4ZDk3NzU4OGZlZWMmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.y2dIez5qrXwk2ZLoYuPSxM9sqBR7kvVdxOhvzBSBdUI)](https://private-user-images.githubusercontent.com/16589958/245346565-572181c7-70e6-4f0a-9db0-2b0c31dd5819.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTA5NDIzMzIsIm5iZiI6MTcxMDk0MjAzMiwicGF0aCI6Ii8xNjU4OTk1OC8yNDUzNDY1NjUtNTcyMTgxYzctNzBlNi00ZjBhLTlkYjAtMmIwYzMxZGQ1ODE5LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAzMjAlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMzIwVDEzNDAzMlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTljN2U4ZWZlNWY5ZGM2NmI4MjU3MGM4MzNiMTFlMWEzN2I1NzEyMWU3NWQ4ZThjNzBiMjE4ZDk3NzU4OGZlZWMmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.y2dIez5qrXwk2ZLoYuPSxM9sqBR7kvVdxOhvzBSBdUI)

New content means something new that hasn't been reviewed.

Review means something needs to review.

Reinforcement learning means you need to consolidate some concepts.

Once you click one of the buttons, the review begins. Please follow the buttons and instructions on the screen to review.

[![Screenshot 2023-06-13 at 12 09 46 PM](https://private-user-images.githubusercontent.com/16589958/245348517-4ce6a725-51c4-46bc-8f13-cd3e7bc216ee.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTA5NDIzMzIsIm5iZiI6MTcxMDk0MjAzMiwicGF0aCI6Ii8xNjU4OTk1OC8yNDUzNDg1MTctNGNlNmE3MjUtNTFjNC00NmJjLThmMTMtY2QzZTdiYzIxNmVlLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAzMjAlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMzIwVDEzNDAzMlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTc3NWYxZTg5YTNjNzlhZjJhMjBhYThhZTRlZTZiMWMwODU2NGJiMjE5ZmFiYmI5NWM5ZjJlZGQ4N2MzNWZkZTImWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.qAV1bzakas7rMFTiy9mJkxNQRRzfAI4_LGef49WLpwQ)](https://private-user-images.githubusercontent.com/16589958/245348517-4ce6a725-51c4-46bc-8f13-cd3e7bc216ee.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTA5NDIzMzIsIm5iZiI6MTcxMDk0MjAzMiwicGF0aCI6Ii8xNjU4OTk1OC8yNDUzNDg1MTctNGNlNmE3MjUtNTFjNC00NmJjLThmMTMtY2QzZTdiYzIxNmVlLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAzMjAlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMzIwVDEzNDAzMlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTc3NWYxZTg5YTNjNzlhZjJhMjBhYThhZTRlZTZiMWMwODU2NGJiMjE5ZmFiYmI5NWM5ZjJlZGQ4N2MzNWZkZTImWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.qAV1bzakas7rMFTiy9mJkxNQRRzfAI4_LGef49WLpwQ)

## Parameter Adjustment

[](https://github.com/linanwx/aosr#parameter-adjustment)

The default parameters work quite well in most cases. If you think you need to adjust the parameters, the following information can help you.

-   **Initial Ease**: This parameter defaults to 250, meaning that the review interval will increase or decrease by 2.5 times. For example, if a card was last reviewed 2 days ago, then if you choose a positive option, the next review time will be 2.5 \* 2 = 5 days, so it will be reviewed again after 5 days. If you choose a negative option, the next review time will be 2.5 / 2 = 1.25 days, so it will be reviewed again after 1.25 days.
    
-   **Easy Option Bonus**: This parameter defaults to 1. When you choose the easy option (meaning you chose "I know" on the first screen and "Easy" on the second screen), in this case, the review time will be postponed by an extra day. In the above situation, it is equivalent to reviewing again one more day after 5 days, that is, after 6 days.
    
-   **Hard Option Bonus**: This parameter defaults to 1. When you choose the hard option (meaning you chose "I got it wrong" or "I forgot"), in this case, the review time will be advanced by one day. In the above situation, it will be reviewed one day earlier after 1.25 days, that is, 0.25 days later.
    

If you think you are reviewing too much content every day, it is recommended to start adjusting from the easy option bonus. You can adjust it to 2 or 3, so that you can postpone the review time for some too simple content.

If you want to review those forgotten contents more, you can adjust the hard option bonus to 2 or 3. In this case, you will review the content you got wrong earlier.

Generally, there is no need to adjust the initial ease, as the review ease of each card will automatically increase or decrease based on your options, with a baseline value of 250. If you want to change the review baseline of all cards, you can change this value. Generally, you can change it to a value between 200-300. It is not recommended to adjust the value beyond this range.

## Deck Functionality in Aosr

[](https://github.com/linanwx/aosr#deck-functionality-in-aosr)

Aosr offers a unique feature known as "Deck" that allows users to manage their flashcards in a highly customizable manner. This feature is designed to cater to the diverse needs of users, providing flexibility in how flashcards are organized and reviewed.

### Background

[](https://github.com/linanwx/aosr#background)

Users have different preferences when it comes to managing their flashcards. Some may prefer organizing their cards by directories, while others might find it more convenient to manage them by tags. Recognizing this, Aosr does not impose a preset deck system. Instead, it empowers users to define their own rules to manage their decks.

### How Deck Works

[](https://github.com/linanwx/aosr#how-deck-works)

The Deck feature in Aosr leverages a rule-based system powered by "json-rules-engine". This allows users to define the contents of their decks based on custom rules. These rules can be freely defined to customize the inclusion of flashcards in a deck.

### Rule Examples

[](https://github.com/linanwx/aosr#rule-examples)

Here are some examples of how you can define rules for your decks:

1.  **Including Cards from a Specific Path:** Replace the keyword in the following code with your desired keyword. The deck will then include cards from the specified path.

` ```aosr-deck-config { 	"rule": { 		"conditions": { 			"all": [{ 				"fact": "card", 				"operator": "regexMatch", 				"value": "KEYWORD",    <--  Replace with your own note path keyword 				"path": "$.path" 			}] 		}, 		"event": { 			"type": "match" 		} 	} } ``` `

2.  **Excluding Cards with a Specific Keyword in Their Path:** You can create a deck that excludes cards with a specific keyword in their path.

` ```aosr-deck-config { 	"rule":{ 		"conditions":{ 			"not": 				{ 					"fact":"card", 					"operator":"regexMatch",            					"value":"KEYWORD",    <-- Replace with the keyword you want to filter out 					"path":"$.path" 				} 		}, 		"event":{ 			"type":"match" 		} 	} } ``` `

3.  **Filtering Cards with a Specific Tag:** You can create a deck that includes all cards with a specific tag.

` ```aosr-deck-config { 	"rule": { 		"conditions": { 			"all": [{ 				"fact": "card", 				"operator": "contains", 				"value": "#KEYWORD",    <-- Replace with the tag you want to filter 				"path": "$.tags" 			}] 		}, 		"event": { 			"type": "match" 		} 	} } ``` `

4.  **Filtering Files with a Specific Tag in Frontmatter:**

` ```aosr-deck-config { 	"rule": { 		"conditions": { 			"all": [{ 				"fact": "file", 				"path": "$.tags", 				"operator": "regexMatch", 				"value": "mathematics" 			}] 		}, 		"event": { 			"type": "match" 		} 	} } `

These examples should suffice for most use cases. However, if you need more complex rules, such as including cards from a specific path that contain certain tags but not others, you may need to write more complex rules. For more information on writing rules, refer to the [json-rules-engine documentation](https://github.com/CacheControl/json-rules-engine). Also, you may need to refer to the fact of the pattern, which is defined as follows:

`interface FactPattern { 	card: { 		path: string 		tags: string[] 		text: string 		outline: string // outline heading string 	} 	file: { 		tags: string[] // from frontmatter 	} }`

### Using Deck in Your Notes

[](https://github.com/linanwx/aosr#using-deck-in-your-notes)

With Aosr's Deck functionality, you can write your own Deck rules directly in your notes. This allows you to review only the selected cards in your notes, providing a tailored review experience.

To use these examples, simply copy and paste the code into your Obsidian notes. If you have the Aosr plugin installed, it will automatically recognize the `aosr-deck-config` code block and transform it into a deck for review.

If the code block does not automatically transform into a review card, please ensure that your cursor is not within the code block. Additionally, if any errors are prompted, check that the rule is in the correct JSON format. Any formatting errors will prevent the transformation into the correct review interface. Once correctly transformed, you should see an interface similar to the one generated when clicking the button in the sidebar. This interface will also contain the review content you need.

The final note should look something like this:

[![截屏2023-07-23 15 02 45](https://private-user-images.githubusercontent.com/16589958/255379139-b05aecc8-51f6-40d0-98bc-f07a7ada6221.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTA5NDIzMzIsIm5iZiI6MTcxMDk0MjAzMiwicGF0aCI6Ii8xNjU4OTk1OC8yNTUzNzkxMzktYjA1YWVjYzgtNTFmNi00MGQwLTk4YmMtZjA3YTdhZGE2MjIxLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAzMjAlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMzIwVDEzNDAzMlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTFiNTc2MzI1ZmI0YzYxNzM0MTAzMjM0ZjE3YmIyM2RjZTZiMTI5Y2U1OTVmMWFiNDYyYWE2ZDYzZmZjYTBiZjYmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.ZsDdA2FuuXnDPsA7Jz1u9Bf8zSPBAkkNWqd50jyHFrw)](https://private-user-images.githubusercontent.com/16589958/255379139-b05aecc8-51f6-40d0-98bc-f07a7ada6221.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTA5NDIzMzIsIm5iZiI6MTcxMDk0MjAzMiwicGF0aCI6Ii8xNjU4OTk1OC8yNTUzNzkxMzktYjA1YWVjYzgtNTFmNi00MGQwLTk4YmMtZjA3YTdhZGE2MjIxLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAzMjAlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMzIwVDEzNDAzMlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTFiNTc2MzI1ZmI0YzYxNzM0MTAzMjM0ZjE3YmIyM2RjZTZiMTI5Y2U1OTVmMWFiNDYyYWE2ZDYzZmZjYTBiZjYmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.ZsDdA2FuuXnDPsA7Jz1u9Bf8zSPBAkkNWqd50jyHFrw)

### Troubleshooting

[](https://github.com/linanwx/aosr#troubleshooting)

If it's not working as expected, please follow these steps:

First, this code can be copied into any note; it doesn't have to be a specific one.

Second, make sure the code block starts with ` ```aosr-deck-config ` and ends with ` ``` `, without any extra spaces in between.

Please check that there are no extra backticks (\`) at the beginning or end of the code block. This can happen if you copy the code from the GitHub page using Ctrl+C.

Ensure you've removed any placeholders like “ <-- Replace with,” as these are not valid JSON and won't be recognized.

Assuming you have a card tagged with #math, like this:

#Q
a^2 + b^2 = ? :: c^2 #math

The code to filter corresponding cards would be:

{
	"rule":{
		"conditions":{
			"all":\[
				{
					"fact":"card",
					"operator":"contains",
					"value":"#math",
					"path":"$.tags"
				}
			\]
		},
		"event":{
			"type":"match"
		}
	}
}

Make sure to wrap this code with ` ```aosr-deck-config ` and ` ``` ` .

Suppose you have a folder called `math` containing many notes, each with multiple cards. You can use the following code to review all the notes within the `math` folder:

` ```aosr-deck-config { 	"rule": { 		"conditions": { 			"all": [{ 				"fact": "card", 				"operator": "regexMatch", 				"value": "math",  				"path": "$.path" 			}] 		}, 		"event": { 			"type": "match" 		} 	} } ``` `

After you finish editing, move the cursor out of this code block or switch Obsidian to preview mode. You should see this code block correctly transformed into a review interface.

## Annotation

[](https://github.com/linanwx/aosr#annotation)

In versions prior to 1.0.40, review data was written at the end of the notes. In subsequent versions, the data is stored in the aosr.db file located under the .obsidian folder. When reading, the data in the db is prioritized, followed by the data in the notes. There is a tool in the settings interface designed to migrate old data into the DB, while also cleaning the notes. It is strongly recommended that you perform this migration operation with a backup of your vault.

[![Screenshot 2023-06-13 at 12 11 48 PM](https://private-user-images.githubusercontent.com/16589958/245348792-624e627e-fa10-4234-8446-fc139b51d355.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTA5NDIzMzIsIm5iZiI6MTcxMDk0MjAzMiwicGF0aCI6Ii8xNjU4OTk1OC8yNDUzNDg3OTItNjI0ZTYyN2UtZmExMC00MjM0LTg0NDYtZmMxMzliNTFkMzU1LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAzMjAlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMzIwVDEzNDAzMlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWFlM2M1YmExNjVjNTRkMjI1MjRlYTkxYWYzMDc3ZDM0ZGIxMDdiZjU5NzQ2YjYwOWIyMDExMmNmMDBmYWVhNTMmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.vfRj1Cv2UH6QOOLpbH7bXNJOsQg_bKdT2Y-HXJCirh0)](https://private-user-images.githubusercontent.com/16589958/245348792-624e627e-fa10-4234-8446-fc139b51d355.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTA5NDIzMzIsIm5iZiI6MTcxMDk0MjAzMiwicGF0aCI6Ii8xNjU4OTk1OC8yNDUzNDg3OTItNjI0ZTYyN2UtZmExMC00MjM0LTg0NDYtZmMxMzliNTFkMzU1LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAzMjAlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMzIwVDEzNDAzMlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWFlM2M1YmExNjVjNTRkMjI1MjRlYTkxYWYzMDc3ZDM0ZGIxMDdiZjU5NzQ2YjYwOWIyMDExMmNmMDBmYWVhNTMmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.vfRj1Cv2UH6QOOLpbH7bXNJOsQg_bKdT2Y-HXJCirh0)

## Work with Dataview

[](https://github.com/linanwx/aosr#work-with-dataview)

By installing the Dataview plugin, you can view information about your review progress.

[![截屏2023-07-23 14 17 48](https://private-user-images.githubusercontent.com/16589958/255377421-fbc09bf0-aa37-43ed-a5e4-174d1920d6b2.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTA5NDIzMzIsIm5iZiI6MTcxMDk0MjAzMiwicGF0aCI6Ii8xNjU4OTk1OC8yNTUzNzc0MjEtZmJjMDliZjAtYWEzNy00M2VkLWE1ZTQtMTc0ZDE5MjBkNmIyLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAzMjAlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMzIwVDEzNDAzMlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTUzZGU2ZmJlYTI0ZDcyNzRjMzRmMTc2ZGFjYThkYzlmNDQ5NGJlM2QwOTg0YTg3OGEzMTQ0NGY1ZTA4MWQxNzImWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.KueQ3uqwiA5MqqvoyLrDvhf8ocOJ4hlKrTASB-0R2hI)](https://private-user-images.githubusercontent.com/16589958/255377421-fbc09bf0-aa37-43ed-a5e4-174d1920d6b2.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTA5NDIzMzIsIm5iZiI6MTcxMDk0MjAzMiwicGF0aCI6Ii8xNjU4OTk1OC8yNTUzNzc0MjEtZmJjMDliZjAtYWEzNy00M2VkLWE1ZTQtMTc0ZDE5MjBkNmIyLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAzMjAlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMzIwVDEzNDAzMlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTUzZGU2ZmJlYTI0ZDcyNzRjMzRmMTc2ZGFjYThkYzlmNDQ5NGJlM2QwOTg0YTg3OGEzMTQ0NGY1ZTA4MWQxNzImWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.KueQ3uqwiA5MqqvoyLrDvhf8ocOJ4hlKrTASB-0R2hI)

You can obtain the complete set of review data by using the code `let patterns = await app.plugins.plugins.aosr.api.getAllPattern();`. Then, you can write Dataview code to display the data. Below is an example provided for you to copy and run.

Please note that you need to enable the corresponding option in Dataview to use `dataviewjs`!

` ```dataviewjs let patterns = await app.plugins.plugins.aosr.api.getAllPattern();  let today = new Date(); today.setHours(0, 0, 0, 0);  let futureLimit = new Date(); futureLimit.setDate(today.getDate() + 15); // Set the future limit to 15 days from today.  let reviewCountsByDate = {};  patterns.forEach(pattern => {     let nextReviewDate = new Date(pattern.schedule.Next);      if (nextReviewDate < today) {         nextReviewDate = today;     }      if (nextReviewDate <= futureLimit) {         nextReviewDate.setHours(0, 0, 0, 0);         let dateStr = nextReviewDate.toISOString().split('T')[0];         if (!reviewCountsByDate[dateStr]) {             reviewCountsByDate[dateStr] = 0;         }         reviewCountsByDate[dateStr]++;     } });  let tableData = Object.entries(reviewCountsByDate)     .map(([date, count]) => [date, count])     .sort((a, b) => new Date(a[0]) - new Date(b[0])); // Sort by date  dv.header(3, "Total amount of Review"); dv.table(["Count"], [[patterns.length]])  dv.header(3, "The amount of daily Review required in the future"); dv.table(["Date", "Review Count"], tableData);   let difficultPatterns = patterns     .map(pattern => [pattern.TagID.substring(1), pattern.schedule.Ease])     .sort((a, b) => a[1] - b[1]) // Sort by Ease     .slice(0, 10); // Take only the first 10 dv.header(3, "The most difficult content in terms of review")  dv.table(["TagID", "Ease"], difficultPatterns); ``` `

> Conflict between the double colon (::) review format and the metadata format of Dataview. It may be necessary to introduce a new format to replace the double colon review format.

## What's the difference?

[](https://github.com/linanwx/aosr#whats-the-difference)

What's the difference between Aosr and obsidian-spaced-repetition?

-   The review time is calculated in minutes, not days. This helps to review the time calculation more accurately. And the calculation when reviewing across the zero point of the day will also be more accurate. For example, at 23:59 and 00:01 in the evening, the review time will not be rudely counted as the day before and the day after.
-   The review interface will now open a standard page instead of a pop-up window. Under the standard page, you can do many obsidian activities at the same time, for example, you can review and comment on the document at the same time. In pop-up mode, this mode hinders further operation.
-   The review process has been optimized. Now a learning process has been added to learn the last item that was marked as forgotten.
-   Redesigned the format. The new format contributes to some minor changes. For example, the cloze will no longer be disrupted by the addition of a new cloze. In addition, the new review format should also be easier to develop and expand.

However, some core functions, such as viewing review data statistics, are not available yet. I will improve the function according to my free time.

## Precautions:

[](https://github.com/linanwx/aosr#precautions)

-   Please do not create identical content with the same pattern in the same file, as the current implementation relies on unique string matching, and creating duplicate patterns will cause exceptions and prevent review.
-   Currently, development and testing are only carried out with "strict line breaks" mode turned off. It has not been tested with the mode turned on, so it is recommended to turn it off.

## License

[](https://github.com/linanwx/aosr#license)

-   MIT [https://opensource.org/licenses/MIT](https://opensource.org/licenses/MIT)

```
react (MIT)   https://github.com/facebook/react
YAML (ISC)    https://github.com/eemeli/yaml
MUI (MIT)     https://github.com/mui/material-ui
```