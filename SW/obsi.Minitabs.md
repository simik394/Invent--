---
page-title: "ssjy1919/Obsidian-minitabs: Obsidian tabs"
url: https://github.com/ssjy1919/Obsidian-minitabs
date: "2024-01-18 08:11:24"
tags: sw/plugin
purpose:
extends: "[[Obsidian]]"
---

-   Watch 1
    
    ### Notifications
    
-   [Fork 0](https://github.com/ssjy1919/Obsidian-minitabs/fork) Fork your own copy of ssjy1919/Obsidian-minitabs
    
-   #### Lists
    
    #### Lists
    

[Open in github.dev](https://github.dev/) [Open in a new github.dev tab](https://github.dev/) [Open in codespace](https://github.com/codespaces/new/ssjy1919/Obsidian-minitabs?resume=1)

## ssjy1919/Obsidian-minitabs

## Add file

## Add file

## 这是一个Obsidian笔记软件的插件

可以通过代码块嵌入多个标签页

## 例1，tab按钮在上

效果:

[![Image 例一](https://github.com/ssjy1919/Obsidian-minitabs/raw/master/Screenshots/%E4%BE%8B%E4%B8%80.png)](https://github.com/ssjy1919/Obsidian-minitabs/blob/master/Screenshots/%E4%BE%8B%E4%B8%80.png) 代码块语法：

\`\`\`minitabs
tabs
\`按钮1\` \`按钮2\` \`可以一直写下去……\` 
\===
第一个按钮对应的页面
\===
按钮二对应的页面
\===
按钮三对应的页面
\`\`\`

## 例2，tab按钮在下

效果:

[![Image 例二](https://github.com/ssjy1919/Obsidian-minitabs/raw/master/Screenshots/%E4%BE%8B%E4%BA%8C.png)](https://github.com/ssjy1919/Obsidian-minitabs/blob/master/Screenshots/%E4%BE%8B%E4%BA%8C.png) 代码块语法：

\`\`\`minitabs
tabsBottom
\`按钮1\` \`按钮2\` \`可以一直写下去……\` 
\===
第一个按钮对应的页面
\===
按钮二对应的页面
\===
按钮三对应的页面
\`\`\`

## 上下tab按钮相互套娃

效果:

[![Image 例三](https://github.com/ssjy1919/Obsidian-minitabs/raw/master/Screenshots/%E4%BE%8B%E4%B8%89.png)](https://github.com/ssjy1919/Obsidian-minitabs/blob/master/Screenshots/%E4%BE%8B%E4%B8%89.png)

代码块语法：

\`\`\`\`\`minitabs
tabs
\`按钮1\` \`按钮2\` \`按钮3\` 
\---
\>\[!Note\]+ 1
\># 1
\`\`\`\`minitabs
tabsBottom
\`按钮1\` \`按钮2\` \`按钮3\` 
\===
\>\[!Note\]+ 1
\># 1.1
\===
\>\[!Note\]+ 1
\># 1.2
\===
\>\[!Note\]+ 1
\># 1.3
\`\`\`\`
\---
\>\[!Note\]+ 1
\># 2
\`\`\`\`minitabs
tabsBottom
\`按钮1\` \`按钮2\` \`按钮3\` 
\===
\>\[!Note\]+ 1
\># 2.1
\===
\>\[!Note\]+ 1
\># 2.2
\===
\>\[!Note\]+ 1
\># 2.3
\`\`\`\`
\---
\>\[!Note\]+ 1
\># 3
\`\`\`\`minitabs
tabsBottom
\`按钮3.1\` \`按钮3.2\` \`按钮3.3\` 
\===
\>\[!Note\]+ 1
\># 3.1
\===
\>\[!Note\]+ 1
\># 3.2
\===
\>\[!Note\]+ 1
\># 3.3
\`\`\`\`
\`\`\`\`\`

## 四象限视图

效果:

[![四象限视图](https://github.com/ssjy1919/Obsidian-minitabs/raw/master/Screenshots/%E5%9B%9B%E8%B1%A1%E9%99%90%E8%A7%86%E5%9B%BE.png)](https://github.com/ssjy1919/Obsidian-minitabs/blob/master/Screenshots/%E5%9B%9B%E8%B1%A1%E9%99%90%E8%A7%86%E5%9B%BE.png)

代码块语法：

\`\`\`\`minitabs
fourQuadrant
\---
\### 不紧急但重要⭐⭐⭐
\- \[ \] 呆呆
\---
\### 紧急且重要⭐⭐⭐⭐
\- \[ \] 呆呆
\---
\### 不紧急不重要⭐
\- \[ \] 呆呆
\---
\### 紧急不重要⭐⭐
\- \[ \] 呆呆
\`\`\`\`