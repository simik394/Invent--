
# README
![[myDM/captured/Docs/zot.addon.Actions_and_Tags.README]]

# community Actions
[windingwind/zotero-actions-tags Action Scripts · Discussions · GitHub](https://github.com/windingwind/zotero-actions-tags/discussions/categories/action-scripts)

#### [Share] Auto-run Better Notes template when opening an item, only when no other notes present #109
date: "2024-01-16 16:11:10"

##### CODE
> // Auto-run Better Notes template when opening an item for the first time, only if other notes aren't present.
> // @author windingwind
> // @author wklimowicz
> // @link https://github.com/windingwind/zotero-tag/discussions/109
> // @usage Event=Open File
> 
> const Zotero \= require("Zotero");
> const window \= require("window");
> 
> if (!Zotero.BetterNotes?.api.note?.insert) {
> 	return "\[Action:Auto-Template\] Better Notes for Zotero > 1.1.4-21 is not installed or disabled.";
> }
> if (!item) {
> 	return "\[Action:Auto-Template\] Target item is empty";
> }
> 
> // Check if any note exists for the item
> const autoTemplateTag \= "auto-template";
> const notes \= Zotero.Items.get(item.getNotes());
> if (notes.length \> 0) {
>     return "A note exists for this item";
> }
> 
> const prefsKey \= "extensions.actionsTags.customAction.autoRunBNTemplate";
> 
> // Get template name
> let templateName \= Zotero.Prefs.get(prefsKey, true);
> let templateContent \= Zotero.BetterNotes.api.template.getTemplateText(templateName);
> if (!templateContent) {
> 	// Template name is not defined or invalid. Get from input
> 	const templateNames \= Zotero.BetterNotes.api.template.getTemplateKeys();
> 
> 	function selectItems(itemList) {
> 		var io \= { dataIn: itemList, dataOut: null };
> 		window.openDialog("chrome://zotero/content/ingester/selectitems.xhtml",
> 			"\_blank", "chrome,modal,centerscreen,resizable=yes", io);
> 		return io.dataOut;
> 	}
> 
> 	templateName \= Object.values(selectItems(templateNames))\[0\];
> 	templateContent \= Zotero.BetterNotes.api.template.getTemplateText(templateName);
> 	if (!templateContent) {
> 		return "\[Action:Auto-Template\] Template is invalid";
> 	}
> 	Zotero.Prefs.set(prefsKey, templateName, true);
> }
> 
> const parentItem \= Zotero.Items.getTopLevel(\[item\])\[0\];
> 
> const noteItem \= new Zotero.Item("note");
> noteItem.libraryID \= parentItem.libraryID;
> noteItem.parentID \= parentItem.id;
> noteItem.addTag(autoTemplateTag, 0);
> await noteItem.saveTx();
> 
> let html \= "";
> if (templateName.toLowerCase().startsWith("\[item\]")) {
> 	html \= await Zotero.BetterNotes.api.template.runItemTemplate(templateName, {
> 		itemIds: \[parentItem.id\],
> 		targetNoteId: noteItem.id,
> 	});
> } else {
> 	html \= await Zotero.BetterNotes.api.template.runTextTemplate(templateName, {
> 		targetNoteId: noteItem.id,
> 	});
> }
> await Zotero.BetterNotes.api.note.insert(
> 	noteItem,
> 	html,
> 	\-1,
> );
> 
> return \`\[Action:Auto-Template\] Note ${noteItem.getNoteTitle()} is created on item ${item.getField("title")} from tem

---



#### [Share] Auto-tag when keyword detected in title · windingwind/zotero-actions-tags · Discussion #119
date: "2024-01-16 16:14:48"

##### Description

Auto-tag when keyword detected in title. See [#77](https://github.com/windingwind/zotero-actions-tags/issues/77) [#85](https://github.com/windingwind/zotero-actions-tags/issues/85).

##### Action Settings

Event: Create Item  
Type: Script  
Data:
##### code
// Auto-tag when keyword detected in title
// @author windingwind
// @link https://github.com/windingwind/zotero-actions-tags/discussions/119
// @usage Replace the \`KEYWORD\` and \`TAG\_NAME\`.
// @see https://github.com/windingwind/zotero-actions-tags/issues/77
// @see https://github.com/windingwind/zotero-actions-tags/issues/85

if (!item) {
	return "\[Conditional Tag\] item is empty";
}

const KEYWORD \= "REPLACE WITH YOUR KEYWORD";
const TAG\_NAME \= "REPLACE WITH YOUR TAG"

if (item.getField("title").includes(KEYWORD)) {
	item.addTag(TAG\_NAME, 1);
	return \`\[Conditional Tag\] item ${item.getField("title")} with keyword ${KEYWORD} is  tagged ${TAG\_NAME}\`;
}

return \`\[Conditional Tag\] item ${item.getField("title")} does not contain keyword ${KEYWORD}\`

Thanks, this feature is very useful. How can I use multiple keywords and tags in only one script? More specifically, if the title contains keywords A or B, add tags named C and D.  
I have tried separating multiple keywords with commas like `A, B`, and the expected result is not to check each keyword individually, but to check together and determine that the title does not contain `A, B`.

[![@windingwind](https://avatars.githubusercontent.com/u/33902321?s=60&v=4)](https://github.com/windingwind)

[![@yuzixieshouhuajiaqi](https://avatars.githubusercontent.com/u/76084234?s=60&v=4)](https://github.com/yuzixieshouhuajiaqi)

大佬,是最新版1.0.0-15呀，还是有错误提示，不过结果都正常，也成功添加了

[![@windingwind](https://avatars.githubusercontent.com/u/33902321?s=60&v=4)](https://github.com/windingwind)

[![@yuzixieshouhuajiaqi](https://avatars.githubusercontent.com/u/76084234?s=60&v=4)](https://github.com/yuzixieshouhuajiaqi)

// Auto-tag when keywords detected in title  
// [@author](https://github.com/author) windingwind  
// [@link](https://github.com/link) [#119](https://github.com/windingwind/zotero-actions-tags/discussions/119)  
// [@Usage](https://github.com/Usage) Replace the `KEYWORDS` and `TAG_NAMES`.  
// [@see](https://github.com/see) [#77](https://github.com/windingwind/zotero-actions-tags/issues/77)  
// [@see](https://github.com/see) [#85](https://github.com/windingwind/zotero-actions-tags/issues/85)

if (!item) {  
return "\[Conditional Tag\] item is empty";  
}

const KEYWORDS1 = \["meta", "Meta"\];  
const TAG\_NAMES1 = \["♏"\];  
const KEYWORDS2 = \["review", "Review", "现状", "进展"\];  
const TAG\_NAMES2 = \["®"\];  
const KEYWORDS3 = \["case", "Case"\];  
const TAG\_NAMES3 = \["©"\];

if (KEYWORDS1.some(kwd => item.getField("title").includes(kwd))) {  
TAG\_NAMES1.forEach(tag => item.addTag(tag, 1));  
return `[Conditional Tag] item ${item.getField("title")} with keyword ${KEYWORDS1} is tagged ${TAG_NAMES1}`;  
} else if (KEYWORDS2.some(kwd => item.getField("title").includes(kwd))) {  
TAG\_NAMES2.forEach(tag => item.addTag(tag, 1));  
return `[Conditional Tag] item ${item.getField("title")} with keyword ${KEYWORDS2} is tagged ${TAG_NAMES2}`;  
} else if (KEYWORDS3.some(kwd => item.getField("title").includes(kwd))) {  
TAG\_NAMES3.forEach(tag => item.addTag(tag, 1));  
return `[Conditional Tag] item ${item.getField("title")} with keyword ${KEYWORDS3} is tagged ${TAG_NAMES3}`;  
} else {  
return `[Conditional Tag] item ${item.getField("title")} does not contain any of the specified keywords`;  
}

[![@yuzixieshouhuajiaqi](https://avatars.githubusercontent.com/u/76084234?s=60&v=4)](https://github.com/yuzixieshouhuajiaqi)

大佬，是我用了多种条件的原因嘛，这是gpt帮我改的，还是有那个错误提示

###### 

This comment was marked as off-topic.

I keep getting SyntaxError: return not in function?

[![@windingwind](https://avatars.githubusercontent.com/u/33902321?s=60&v=4)](https://github.com/windingwind)

###### 

This comment was marked as off-topic.

update the plugin, or please provide steps to reproduce.

[![@huachuman](https://avatars.githubusercontent.com/u/125603964?s=60&v=4)](https://github.com/huachuman)

###### 

This comment was marked as off-topic.

Here are the steps to reproduce:

Click the copy button in the code you provided

Paste copied text in "Run Javascript" window in Zotero.

Click Run.

[![@windingwind](https://avatars.githubusercontent.com/u/33902321?s=60&v=4)](https://github.com/windingwind)

No. This is not for `run js`. See readme.

以下代码可以同时检测标题或摘要中是否含有某个字段，并返回相应标签：

// Auto-tag based on specific keywords in the title and abstract
// @author windingwind
// @link https://github.com/windingwind/zotero-actions-tags/discussions/119
// @usage Replace the \`KEYWORDS\_AND\_TAGS\` array with your own keywords and corresponding tags.
// @see https://github.com/windingwind/zotero-actions-tags/issues/77
// @see https://github.com/windingwind/zotero-actions-tags/issues/85

if (!item) {
    return "\[Conditional Tag\] item is empty";
}

const KEYWORDS\_AND\_TAGS \= \[
    { keyword: "FIELD\_A", tag: "TAG\_B" },
    { keyword: "FIELD\_C", tag: "TAG\_D" },
    // You can add more keyword-tag pairs as needed
\];

const title \= item.getField("title");
const abstract \= item.getField("abstract");
let tagged \= false;

for (const pair of KEYWORDS\_AND\_TAGS) {
    const { keyword, tag } \= pair;
    if (title.includes(keyword) || (abstract && abstract.includes(keyword))) {
        item.addTag(tag, 1);
        tagged \= true;
    }
}

if (tagged) {
    return \`\[Conditional Tag\] item "${title}" has been tagged based on keywords in title or abstract.\`;
} else {
    return \`\[Conditional Tag\] item "${title}" does not match any keywords in the list in title or abstract.\`;
}

[![@windingwind](https://avatars.githubusercontent.com/u/33902321?s=60&v=4)](https://github.com/windingwind)

脚本内容需用markdown格式  
\`\`\`js  
// code  
\`\`\`

包裹。

[![@BoBo-YunYun](https://avatars.githubusercontent.com/u/121593119?s=60&v=4)](https://github.com/BoBo-YunYun)

感谢大佬回答，不过运行后没有成功添加标签  
// Auto-tag based on specific keywords in the title and abstract  
// [@author](https://github.com/author) windingwind  
// [@link](https://github.com/link) [#119](https://github.com/windingwind/zotero-actions-tags/discussions/119)  
// [@Usage](https://github.com/Usage) Replace the KEYWORDS\_AND\_TAGS array with your own keywords and corresponding tags.  
// [@see](https://github.com/see) [#77](https://github.com/windingwind/zotero-actions-tags/issues/77)  
// [@see](https://github.com/see) [#85](https://github.com/windingwind/zotero-actions-tags/issues/85)

if (!item) {  
return "\[Conditional Tag\] item is empty";  
}

const KEYWORDS\_AND\_TAGS = \[  
{ keyword: "meta", "Meta", tag: "♏" },  
{ keyword: "review", "Review", "现状", "进展", "综述", tag: "®" },  
{ keyword: "case", "Case", tag: "©" },  
// You can add more keyword-tag pairs as needed  
\];

const title = item.getField("title");  
const abstract = item.getField("abstract");  
let tagged = false;

for (const pair of KEYWORDS\_AND\_TAGS) {  
const { keyword, tag } = pair;  
if (title.includes(keyword) || (abstract && abstract.includes(keyword))) {  
item.addTag(tag, 1);  
tagged = true;  
}  
}

if (tagged) {  
return \[Conditional Tag\] item "${title}" has been tagged based on keywords in title or abstract.;  
} else {  
return \[Conditional Tag\] item "${title}" does not match any keywords in the list in title or abstract.;  
}

Was this translation helpful? [Give feedback.](https://github.com/windingwind/zotero-actions-tags/discussions/119#)

[![@windingwind](https://avatars.githubusercontent.com/u/33902321?s=60&v=4)](https://github.com/windingwind)

建议先用gpt做基础错误排除，或者了解一下js语法。

> No. This is not for `run js`. See readme.

oh I see so this is also only for Z7

###### Add a comment

Comment

##### Select a reply

We don’t support that file type.

Try again with GIF, JPEG, JPG, MOV, MP4, PNG, SVG, WEBM, CPUPROFILE, CSV, DMP, DOCX, FODG, FODP, FODS, FODT, GZ, JSON, JSONC, LOG, MD, ODF, ODG, ODP, ODS, ODT, PATCH, PDF, PPTX, TGZ, TXT, XLS, XLSX or ZIP.

Attaching documents requires write permission to this repository.

Try again with GIF, JPEG, JPG, MOV, MP4, PNG, SVG, WEBM, CPUPROFILE, CSV, DMP, DOCX, FODG, FODP, FODS, FODT, GZ, JSON, JSONC, LOG, MD, ODF, ODG, ODP, ODS, ODT, PATCH, PDF, PPTX, TGZ, TXT, XLS, XLSX or ZIP.

This file is empty.

Try again with a file that’s not empty.

This file is hidden.

Try again with another file.

Something went really wrong, and we can’t process that file.

Try again.
#### [Share] Save/Restore Reader Tabs · windingwind/zotero-actions-tags · Discussion #129
date: "2024-01-16 16:36:49"

##### Description
> 
> Save/restore reader tabs
> 
> See [https://forums.zotero.org/discussion/97425/feature-idea-pdf-tab-groups](https://forums.zotero.org/discussion/97425/feature-idea-pdf-tab-groups)  
> Inspired by [https://gist.github.com/ifree/a91b68dbe1a6927bd9fd8ba4b67aad6a](https://gist.github.com/ifree/a91b68dbe1a6927bd9fd8ba4b67aad6a)

##### code
> // Save/restore reader tabs
> // @author windingwind
> // @link https://github.com/windingwind/zotero-actions-tags/discussions/129
> // @usage Trigger with shortcuts
> // @see https://forums.zotero.org/discussion/97425/feature-idea-pdf-tab-groups
> // @see https://gist.github.com/ifree/a91b68dbe1a6927bd9fd8ba4b67aad6a
> 
> const Zotero\_Tabs \= require("Zotero\_Tabs");
> 
> const window \= require("window");
> 
> const prefsKey \= "extensions.actionsTags.customAction.tabGroup";
> 
> return window.confirm("Press OK to save tabs, Cancel to restore tabs")
> 	? saveTabs()
> 	: restoreTabs();
> 
> function saveTabs() {
> 	let tabs \= Zotero\_Tabs.\_tabs.filter(
> 		(t) \=> !!t.data && \["reader", "reader-reloaded"\].includes(t.type)
> 	);
> 
> 	let tabData \= JSON.stringify(tabs);
> 	Zotero.Prefs.set(prefsKey, tabData, true);
> 	return "\[Tab Group\] Saved " + tabs.length + " tabs";
> }
> 
> function restoreTabs() {
> 	let tabData \= Zotero.Prefs.get(prefsKey, true);
> 	if (!tabData) {
> 		return "\[Tab Group\] No tabs to restore";
> 	}
> 	let tabs \= JSON.parse(tabData);
> 	for (let tab of tabs) {
> 		// open tab if not already opened
> 		if (Zotero\_Tabs.\_tabs.some((t) \=> t.data?.itemID \=== tab.data?.itemID)) {
> 			continue;
> 		}
> 		if (tab.type \== "reader") tab.type \= "reader-unloaded"; // force reload
> 
> 		Zotero\_Tabs.add(tab);
> 	}
> 	return "\[Tab Group\] Restored " + tabs.length + " tabs";
> }

---



#### [Share] Relate selected items · windingwind/zotero-actions-tags · Discussion #164
date: "2024-01-16 16:41:40"


> replace the "Relate selected items" function from Zutilo, available from a right-click on several items:
> 
> Relate items: Set all selected items to be related to each other.

##### code
> /\*\*
>  \* Relate selected items
>  \* @author windingwind
>  \* @usage Set all selected items to be related to each other from a right-click on several items
>  \* @link https://github.com/windingwind/zotero-actions-tags/discussions/164
>  \* @see https://github.com/windingwind/zotero-actions-tags/discussions/164
>  \*/
> if (items?.length \=== 0 || item) {
> 	return;
> }
> 
> // https://github.com/wshanks/Zutilo/blob/8d53047cf35c11490e0d82156d4ee12136c7fb31/addon/chrome/content/zutilo/zoteroOverlay.js#L710
> const zitems \= items.filter(\_item \=> \_item.isRegularItem() || \_item.isNote() || \_item.isAttachment());
> if (zitems.length < 2) {
> 	return "Must select 2 or more items";
> }
> 
> for (let zitem of zitems) {
> 	for (let addItem of zitems) {
> 		if (zitem != addItem) {
> 			zitem.addRelatedItem(addItem)
> 		}
> 	}
> 	zitem.saveTx();
> }
> 
> return \`Successfully relate ${zitems.length} items.\`;

---

#### [Share] Copy and paste tags of selected item(s) 复制粘贴所选条目的标签 · windingwind/zotero-actions-tags · Discussion #194
date: "2024-01-16 16:42:57"


##### Description

Copy tags from item and paste them to another item.

复制、粘贴所选条目的标签  
大部分代码来源于Zutilo。  
感谢[@windingwind](https://github.com/windingwind)指导。

##### Event

None

##### Operation

Script

##### Data

Action Data for **COPY** tags from item:

// Copy tags. 
// Codes from Zutilo.
// 获取条目tags，并存入剪贴板
var tagsArray \= \[\];
var items \= Zotero.getActiveZoteroPane().getSelectedItems();
for (let item of items) {

    if (item.isRegularItem() && !item.isCollection()) {

        var tempTags \= item.getTags();
        var arrayStr \= '';
        for (var j \= 0; j < tempTags.length; j++) {
            arrayStr \= '\\n' + tagsArray.join('\\n') + '\\n';

            let tag
            tag \= tempTags\[j\].tag

            if (arrayStr.indexOf('\\n' + tag + '\\n') \== \-1) {
                tagsArray.push(tag);
            }
        }
    }

}
var clipboardText \= tagsArray.join('\\r\\n');
copyToClipboard(clipboardText)
return "Tags copied."

// 复制到剪贴板函数
function copyToClipboard(clipboardText) {
    var document \= require('window').document;  // Zotero Actions & Tags需要
    if (clipboardText) {
        const gClipboardHelper \=
            Components.classes\['@mozilla.org/widget/clipboardhelper;1'\]
                .getService(Components.interfaces.nsIClipboardHelper);
        gClipboardHelper.copyString(clipboardText, document);
    } else {
        var prompts \= Components.
            classes\['@mozilla.org/embedcomp/prompt-service;1'\].
            getService(Components.interfaces.nsIPromptService);
        var title \= 'Invalid copy selection';
        var text \= 'No valid items selected for copying. The clipboard has not been modified.';
        prompts.alert(null, title, text)
    }
}

Action Data for **PASTE** tags to item:

// Paste tags
// Codes from Zutilo.
// 从剪贴板获取tags
var clipboardText \= getFromClipboard().trim()
if (!clipboardText) {
    return false;
}
// 拆分
var tagArray \= clipboardText.split(/\\r\\n?|\\n/)
tagArray \= tagArray.map(function (val) { return val.trim() });
tagArray \= tagArray.filter(Boolean)
// 添加tags
var items \= Zotero.getActiveZoteroPane().getSelectedItems();
for (let item of items) {
    if (item.isRegularItem() && !item.isCollection()) {
        for (let tag of tagArray) {
            item.addTag(tag)
        }
        item.saveTx()
    }

}
return "Tags pasted."

// 从剪贴板获取数据函数
function getFromClipboard(silent) {
    var trans \= Components.classes\['@mozilla.org/widget/transferable;1'\].
        createInstance(Components.interfaces.nsITransferable);
    // if ('init' in trans) {
    //     trans.init(window.QueryInterface(Ci.nsIInterfaceRequestor).
    //         getInterface(Ci.nsIWebNavigation));
    // }
    trans.addDataFlavor('text/unicode');

    Services.clipboard.getData(trans, Services.clipboard.kGlobalClipboard);

    var str \= {}
    var strLength \= {}

    try {
        trans.getTransferData('text/unicode', str, strLength);
    } catch (err) {
        if (!silent) {
            var prompts \= Cc\['@mozilla.org/embedcomp/prompt-service;1'\].
                getService(Components.interfaces.nsIPromptService);
            prompts.alert(
                null,
                'clipboard error',
                'attempted to copy text from the clipboard, but no valid text was found.'
            )
        }
        return '';
    }

    var pasteText
    if (str) {
        pasteText \= str.value.
            QueryInterface(Components.interfaces.nsISupportsString).data;
    } else {
        pasteText \= '';
    }

    return pasteText;
};

##### Anything else

Note that you'll need to create **TWO** actions, one for copy and one for paste.

有些代码可能不需要，可以自行删除。  
需要分别建立两个动作。

---


#### Paper Rating System by a set of Scripts[Share] · windingwind/zotero-actions-tags · Discussion #232
date: "2024-01-16 16:44:57"
##### descript
Rate your paper by pressing `0`, `1`, `2`, `3`, `4` and `5`. Simply unzip the attachment and import the `yml` file, then enjoy it !
##### code
/\*\*
 \* A description of this script.
 \* @author jsbyysheng
 \* @usage 
 \* @link https://github.com/windingwind/zotero-actions-tags/discussions/
 \* @see https://github.com/windingwind/zotero-actions-tags/discussions/
 \*/

if (!item) {
	return "\[Rating Item\] item is empty";
}

var i;
const tagsToRemove\=\["#⭐️", "#⭐️⭐️", "#⭐️⭐️⭐️", "#⭐️⭐️⭐️⭐️", "#⭐️⭐️⭐️⭐️⭐️"\];

for (i \= 0; i < tagsToRemove.length; i++) {
	if (item.getTags().some(obj \=> obj.tag \=== tagsToRemove\[i\])) {
		item.removeTag(tagsToRemove\[i\]);
	}
}

item.addTag('#⭐️⭐️⭐️⭐️⭐️');

return "\[Rating Item\] Done";

---


#### [Share] Replace Tag · windingwind/zotero-actions-tags · Discussion #113
date: "2024-01-16 16:48:48"


> Replace tag.
> 
> // Replace tags
> // @author windingwind
> // @link https://github.com/windingwind/zotero-tag/discussions/113
> // @usage Shortcut
> 
> if (!item) {
> 	return "\[Replace Tags\] item is empty";
> }
> 
> // Modify this line 👇
> const tagToReplace \= "TAG\_TO\_REPLACE";
> 
> // Modify this line 👇
> const tagToAdd \= "TAG\_TO\_ADD";
> 
> if (item.getTags().some(obj \=> obj.tag \=== tagToReplace)) {
> 	item.addTag(tagToAdd);
> 	item.removeTag(tagToReplace);
> 	return \`\[Replace Tags\] replace tag ${tagToReplace} to ${tagToAdd} on ${item.getField("title")}\`;
> }
> 
> return \`\[Replace Tags\] tag ${tagToReplace} does not exist on ${item.getField("title")}\`;

---


#### [Share] add tag shortcut · windingwind/zotero-actions-tags · Discussion #139
date: "2024-01-16 16:49:37"


> A script for quickly adding tags. By configuring the settings, you can use shortcut keys to add tags.  
> The script is based on the code of [Zutilo](https://github.com/wshanks/Zutilo).
> 
> //add tag shortcut
> // @author nilleo
> // @link https://github.com/windingwind/zotero-actions-tags/discussions/139
> // @usage Select an item in the library and press the assigned shortcut keys
> 
> const ZoteroPane \= require("ZoteroPane")
> // Select tag tab of item pane
> var tabIndex \= 2;
> var tabbox \= ZoteroPane.document.getElementById('zotero-view-tabbox');
> tabbox.tabs.selectedIndex \= tabIndex;
> 
> // Focus new tag entry textbox
> let header \= ZoteroPane.document.querySelector(".tags-box-header");
> if (header \=== null) {
>   // Zotero version < 5.0.78
>   let tagPane \= ZoteroPane.document.getElementById('zotero-editpane-tags');
>   if (tagPane.\_tagColors \=== undefined) {
>     window.setTimeout(function() { tagPane.new(); }, 200);
>   } else {
>     tagPane.newTag();
>   }
> } else {
>   let addButton \= header.querySelector("button");
>   addButton.click();
> }

---


#### [Share]用其他程序打开PDF（Open PDF with specific application） · windingwind/zotero-actions-tags · Discussion #132
date: "2024-01-16 16:50:22"


> 楼主好  
> 我想使用[QL-Win/QuickLook](https://github.com/QL-Win/QuickLook)打开PDF，进行预览，然后探索出来下面两种方案
> 
> 方案1：  
> 使用你上述代码，指定一下QuickLook.exe的路径就可以，但是只能“选中PDF条目-执行”才有效，**不能**“选中父条目-执行”打开父条目下的PDF
> 
> 方案2：  
> 使用如下代码，无论父条目还是子条目都可以，感谢 [@windingwind](https://github.com/windingwind)
> 
> if(item) return;
> 
> const window \= require("window");
> const ZoteroPane \= require("ZoteroPane");
> 
> async function getPDFAttachmentPath(item) {
>     // 如果是PDF，直接获取路径
>     if (item.isAttachment() && item.attachmentContentType \=== 'application/pdf') {
>         return await item.getFilePathAsync();
>     }
>     // 如果是父条目，查找其PDF附件
>     else if (item.isRegularItem() && !item.isAttachment()) {
>         let attachments \= await item.getAttachments();
>         for (let attachmentID of attachments) {
>             let attachment \= await Zotero.Items.getAsync(attachmentID);
>             if (attachment.attachmentContentType \=== 'application/pdf') {
>                 return await attachment.getFilePathAsync();
>             }
> 			//break;
>         }
>     }
>     return null;
> }
> 
> async function openPDF(item) {
>     let path \= await getPDFAttachmentPath(item);
>     if (!path) {
>         Zotero.alert(window, "打开失败", "未找到PDF附件");
>         return "未找到PDF附件";
>     }
>   
>     let exePath \= Zotero.Prefs.get("extensions.actionsTags.mypdfapp2", true);
>     if (!exePath) {
>         exePath \= window.prompt("输入打开PDF的exe程序路径");
>         Zotero.Prefs.set("extensions.actionsTags.mypdfapp2", exePath, true);
>     }
>   
>     // Example: exe path string in windows, C:\\\\QuickLook\\\\QuickLook.exe
>     Zotero.launchFileWithApplication(path, exePath);
> 	// 减少提示干扰
>     // return "打开成功";
> }
> 
> // 你需要获取当前选中的条目
> return await openPDF(items\[0\]);

---

#### [Share] Copy Open Tabs to Clipboard as Markdown or HTML list · windingwind/zotero-actions-tags · Discussion #206
date: "2024-01-16 16:50:59"


##### Description
> 
> [![image](https://private-user-images.githubusercontent.com/17838489/286749128-82bf73e8-c66f-452e-9d8a-9c4c122eb3a0.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDU0MjA1NDIsIm5iZiI6MTcwNTQyMDI0MiwicGF0aCI6Ii8xNzgzODQ4OS8yODY3NDkxMjgtODJiZjczZTgtYzY2Zi00NTJlLTlkOGEtOWM0YzEyMmViM2EwLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAxMTYlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMTE2VDE1NTA0MlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWViZTgwNjZhMzE5YzUyYmU0NTFjOGIwNTFjN2RhMmQ5NDFmYTY5MTg0MTYwMDI5YzM5MmIwOGU0NjZjNDBlOGEmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.rVGAEy3Dae2UA5t6LzmkKD4-zwxmcRfp2GwMx5rVXNw)](https://private-user-images.githubusercontent.com/17838489/286749128-82bf73e8-c66f-452e-9d8a-9c4c122eb3a0.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDU0MjA1NDIsIm5iZiI6MTcwNTQyMDI0MiwicGF0aCI6Ii8xNzgzODQ4OS8yODY3NDkxMjgtODJiZjczZTgtYzY2Zi00NTJlLTlkOGEtOWM0YzEyMmViM2EwLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAxMTYlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMTE2VDE1NTA0MlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWViZTgwNjZhMzE5YzUyYmU0NTFjOGIwNTFjN2RhMmQ5NDFmYTY5MTg0MTYwMDI5YzM5MmIwOGU0NjZjNDBlOGEmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.rVGAEy3Dae2UA5t6LzmkKD4-zwxmcRfp2GwMx5rVXNw)
> 
> You can then paste the result to Zotero notes, obsidian, or any Markdown editor:
> 
> [![image](https://private-user-images.githubusercontent.com/17838489/286750003-54702cf0-ca61-4349-aff5-0a4b7980dbeb.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDU0MjA1NDIsIm5iZiI6MTcwNTQyMDI0MiwicGF0aCI6Ii8xNzgzODQ4OS8yODY3NTAwMDMtNTQ3MDJjZjAtY2E2MS00MzQ5LWFmZjUtMGE0Yjc5ODBkYmViLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAxMTYlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMTE2VDE1NTA0MlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTNiOTMzZGMxYjVjMDJjNzUxODc5ZDQ0YTZkZjBlYWE3NWQ0ZjBhNWJlOTc1MmExMTZiYjlhZjFmOTJmMmUwOTYmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.tr8da7SzWOwcV-4IXav7R-G6Gs7QyTF-6ACtzYG7FsM)](https://private-user-images.githubusercontent.com/17838489/286750003-54702cf0-ca61-4349-aff5-0a4b7980dbeb.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDU0MjA1NDIsIm5iZiI6MTcwNTQyMDI0MiwicGF0aCI6Ii8xNzgzODQ4OS8yODY3NTAwMDMtNTQ3MDJjZjAtY2E2MS00MzQ5LWFmZjUtMGE0Yjc5ODBkYmViLnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDAxMTYlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwMTE2VDE1NTA0MlomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTNiOTMzZGMxYjVjMDJjNzUxODc5ZDQ0YTZkZjBlYWE3NWQ0ZjBhNWJlOTc1MmExMTZiYjlhZjFmOTJmMmUwOTYmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.tr8da7SzWOwcV-4IXav7R-G6Gs7QyTF-6ACtzYG7FsM)
> 
> ### Event
> 
> None
> 
> ### Operation
> 
> Script
> 
> ### Data
> 
> /\*\*
>  \* Copy the open tabs to Clipboard as a Markdown or HTML list; ready to paste in Zotero notes or Obisidian.
>  \* @author Samir Ouchene, Thanks to FeralFlora for their hints.
>  \* @usage plug and play 
>  \* @link https://github.com/windingwind/zotero-actions-tags/discussions/206
>  \* @see https://github.com/windingwind/zotero-actions-tags/discussions/206
>  \*/
> 
> const Zotero\_Tabs \= require("Zotero\_Tabs");
> //const window = require("window");
> const clipboard \= new Zotero.ActionsTags.api.utils.ClipboardHelper();
> 
> /\*\* @type {'md' | 'html'} Change the type of the URL. \*/
> URLType \= 'html';
> 
> // For efficiency, only execute once for all selected items
> if (item) return;
> // Filter the tabs to include only the one with type 'reader' or 'reader-unloaded'
> let tabs \= Zotero\_Tabs.\_tabs.filter(tab \=> 
> \['reader', 'reader-unloaded'\].includes(tab.type)
> );
> let tabData\_ \= JSON.stringify(tabs);
> tabData \= JSON.parse(tabData\_);
> itemIDs \= tabData.map(obj \=> obj.data.itemID);
> itemTitles \= tabData.map(obj \=> obj.title);
> 	
> // get the item keys using the itemIDs
> itemKeys \= itemIDs.map(itemID \=> Zotero.Items\['\_objectCache'\]\[itemID\]\['key'\]);
> URIs \= itemKeys.map(itemKey \=> \`zotero://open-pdf/library/items/${itemKey}\`);
> 
> if (URLType.toLowerCase() \=== 'md') {
>     mimeStr \= "text/unicode";
>     listOfURIs \= itemTitles.map((title,index) \=> \`\* \[${title}\](${URIs\[index\]})\`).join('\\n');
> } else if (URLType.toLowerCase() \=== 'html') {
>     mimeStr \= "text/html";
>     listOfURIs\_ \= itemTitles.map((title,index) \=> \`<li><a href="${URIs\[index\]}"> ${title}</a></li>\`).join('');
>     listOfURIs \= \`<ul>${listOfURIs\_}</ul>\`;
> }
> 
> clipboard.addText(listOfURIs, mimeStr);
> clipboard.copy();
> //window.alert("Successfully copied " + itemIDs.length + " tabs to clipboard");
> return \`\[Copy Open Tabs\] copied ${itemIDs.length} items to clipboard\`;

---



#### [Share] Copy Zotero link · windingwind/zotero-actions-tags · Discussion #115
date: "2024-01-16 16:57:24"
##### Description
> 
> Copy Zotero link of the selected item/PDF/note/annotation/collection.
> 
> -   Support `zotero://select`, `zotero://open-pdf`, and Better Notes link `zotero://note`
> -   Support `markdown`/`html`/`plain-text`
> -   Support customization of link text

##### code
// Copy zotero link
// @author windingwind, garth74
// @link https://github.com/windingwind/zotero-actions-tags/discussions/115
// @usage Select an item in the library and press the assigned shortcut keys
// @update Wed, 29 Nov 2023 07:12:46 GMT (by new Date().toGMTString())

// EDIT THESE SETTINGS

/\*\* @type {string} Name of the field to use as the link text. To use the citation key, set this to "citationKey". \*/
let linkTextField \= "title";

/\*\* @type {'html' | 'md' | 'plain'} What type of link to create. \*/
let linkType \= "html";

/\*\* @type {boolean} If true, make the link specific to the currently selected collection. \*/
let useColl \= false;

/\*\* @type {boolean} If true, use Better Notes zotero://note link when the selected item is a note. \*/
let useNoteLink \= false;

/\*\* @type {'select' | 'open-pdf' | 'auto'} Action of link\*/
let linkAction \= "auto"; // auto = open-pdf for PDFs and annotations, select for everything else

// END OF EDITABLE SETTINGS

// For efficiency, only execute once for all selected items
if (item) return;
item \= items\[0\];
if (!item && !collection) return "\[Copy Zotero Link\] item is empty";

if (collection) {
  linkAction \= "select";
  useColl \= true;
}

if (linkAction \=== "auto") {
  if (item.isPDFAttachment() || item.isAnnotation()) {
    linkAction \= "open-pdf";
  } else {
    linkAction \= "select";
  }
}

const uriParts \= \[\];
let uriParams \= "";

let targetItem \= item;
if (linkAction \=== "open-pdf") {
  uriParts.push("zotero://open-pdf");
  if (item.isRegularItem()) {
    targetItem \= (await item.getBestAttachments()).find((att) \=>
      att.isPDFAttachment()
    );
  } else if (item.isAnnotation()) {
    targetItem \= item.parentItem;
    // If the item is an annotation, we want to open the PDF at the page of the annotation
    let pageIndex \= 1;
    try {
      pageIndex \= JSON.parse(item.annotationPosition).pageIndex + 1;
    } catch (e) {
      Zotero.warn(e);
    }
    uriParams \= \`?page=${pageIndex}&annotation=${item.key}\`;
  }
} else {
  uriParts.push("zotero://select");
  if (item?.isAnnotation()) {
    targetItem \= item.parentItem;
  }
}

if (!targetItem && !collection) return "\[Copy Zotero Link\] item is invalid";

// Get the link text using the \`link\_text\_field\` argument
let linkText;
if (!item && collection) {
  // Use collection name if this is a collection link
  linkText \= collection.name;
} else if (item.isAttachment()) {
  // Try to use top-level item for link text
  linkText \= Zotero.Items.getTopLevel(\[item\])\[0\].getField(linkTextField);
} else if (item.isAnnotation()) {
  // Add the annotation text to the link text
  linkText \= \`${targetItem.getField(linkTextField)}(${
    item.annotationComment || item.annotationText || "annotation"
  })\`;
} else {
  // Use the item's field
  linkText \= item.getField(linkTextField);
}

// Add the library or group URI part
let libraryType \= (item || collection).library.libraryType;
if (libraryType \=== "user") {
  uriParts.push("library");
} else {
  uriParts.push(
    \`groups/${Zotero.Libraries.get((item || collection).libraryID).groupID}\`
  );
}

// If useColl, make the link collection specific
if (useColl) {
  // see https://forums.zotero.org/discussion/73893/zotero-select-for-collections
  let coll \= collection || Zotero.getActiveZoteroPane().getSelectedCollection();

  // It's possible that a collection isn't selected. When that's the case,
  // this will fall back to the typical library behavior.

  // If a collection is selected, add the collections URI part
  if (!!coll) uriParts.push(\`collections/${coll.key}\`);
}

if (targetItem) {
  // Add the item URI part
  uriParts.push(\`items/${targetItem.key}\`);
}

// Join the parts together
let uri \= uriParts.join("/");

// Add the URI parameters
if (uriParams) {
  uri += uriParams;
}

if (useNoteLink && item?.isNote() && Zotero.BetterNotes) {
  uri \= Zotero.BetterNotes.api.convert.note2link(item);
}

// Format the link and copy it to the clipboard
const clipboard \= new Zotero.ActionsTags.api.utils.ClipboardHelper();
if (linkType \== "html") {
  clipboard.addText(\`<a href="${uri}">${linkText}</a>\`, "text/unicode");
} else if (linkType \== "md") {
  clipboard.addText(\`\[${linkText}\](${uri})\`, "text/unicode");
} else {
  clipboard.addText(uri, "text/unicode");
}

clipboard.addText(\`<a href="${uri}">${linkText}</a>\`, "text/html");

clipboard.copy();

return \`\[Copy Zotero Link\] link ${uri} copied.\`;

---


##### 1N - full  thread screenshot
