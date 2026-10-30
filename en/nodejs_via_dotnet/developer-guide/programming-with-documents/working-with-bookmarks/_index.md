---
title: Working with Bookmarks in Node.js
second_title: Aspose.Words for Node.js via .NET
articleTitle: Working with Bookmarks
linktitle: Working with Bookmarks
description: "How to insert, obtain, move, show or hide bookmarks using Node.js."
type: docs
weight: 180
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/working-with-bookmarks/
timestamp: 2025-07-09-10-05-05
---

Bookmarks identify in a Microsoft Word document the locations or fragments that you name and identify for future reference. For example, you might use a bookmark to identify text that you want to revise later. Instead of scrolling through the document to locate the text, you can go to it by using the Bookmark dialog box.

The actions that can be performed with bookmarks using Aspose.Words are the same as the ones you can perform using Microsoft Word. You can insert a new bookmark, delete, move to a bookmark, get or set a bookmark name, get or set text enclosed in it. With Aspose.Words, you can also use bookmarks in reports or documents to insert some data into the bookmark or apply special formatting to its content. You can also use bookmarks to retrieve text from a certain location in your document.

## Insert a Bookmark

Use [startBookmark](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/startbookmark/) and [endBookmark](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/endbookmark/) to create a bookmark by marking its start and end, respectively. Do not forget to pass the same bookmark name to both methods. Bookmarks in a document can overlap and span any range. Badly formed bookmarks or bookmarks with duplicate names will be ignored when the document is saved.

{{% alert color="primary" %}}

All white spaces in the bookmarks were replaced with underscores. This restriction came from Microsoft Word formats, since bookmarks in MS Word formats, like DOCX or DOC, cannot have white spaces. However, PDF allows such bookmarks. So now, if you need to use bookmarks in PDF or XPS outlines, you can use them with white spaces.

{{% /alert %}}

The following code example shows how to create a new bookmark:

{{< gist "aspose-words-gists" "6b8a885f5544cddd9bc77edb3ad18692" "create-bookmark.js" >}}

## Obtain Bookmarks

Sometimes it is necessary to obtain a bookmark collection to iterate through bookmarks or for other purposes. Use the [Node.range](https://reference.aspose.com/words/nodejs-net/aspose.words/node/range/) property exposed by any document node that returns a [Range](https://reference.aspose.com/words/nodejs-net/aspose.words/range/) object representing the portion of the document contained in this node. Use this object to retrieve a [BookmarkCollection](https://reference.aspose.com/words/nodejs-net/aspose.words/bookmarkcollection/) and then use the collection indexer to get a specific bookmark.

{{% alert color="primary" %}}

You can download the sample file of these examples from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Node.js-via-.NET/blob/main/Data/Bookmarks.docx).

{{% /alert %}}

The following code example shows how to obtain bookmarks from a bookmark collection:

{{< gist "aspose-words-gists" "6b8a885f5544cddd9bc77edb3ad18692" "access-bookmarks.js" >}}

The following code example shows how to get or set a bookmark name and text:

{{< gist "aspose-words-gists" "6b8a885f5544cddd9bc77edb3ad18692" "update-bookmark-data.js" >}}

The following code example shows how to bookmark a table:

{{< gist "aspose-words-gists" "6b8a885f5544cddd9bc77edb3ad18692" "bookmark-table.js" >}}

If you change the name of a bookmark to a name that already exists in the document, no error will be generated and only the first bookmark will be stored when you save the document.

Note that some bookmarks in the document are assigned to form fields. Moving to such a bookmark and inserting text there inserts the text into the form field code. Although this will not invalidate the form field, the inserted text will not be visible because it becomes part of the field code.

The following code example shows how to access columns of the bookmarked table:

{{< gist "aspose-words-gists" "6b8a885f5544cddd9bc77edb3ad18692" "bookmark-table-columns.js" >}}

## Move to a Bookmark

If you need to insert rich content (not just plain text) into a bookmark, you should use [moveToBookmark](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/moveToBookmark/) to move the cursor to the bookmark and then use [DocumentBuilder's](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/) methods and properties to insert content.

## Show Hide Bookmark Content

The entire Bookmark (*including the bookmarked content*) can be encapsulated within the True part of the `IF` field using Aspose.Words. It can be in such a way that the `IF` field contains a nested Merge Field in the expression (*Left of Operator*) and depending upon the value of Merge Field, the `IF` field shows or hides the content of Bookmark in Word Document.

The following code example shows how to show/ hide bookmarks:

{{< gist "aspose-words-gists" "6b8a885f5544cddd9bc77edb3ad18692" "show-hide-bookmarks.js" >}}

{{< gist "aspose-words-gists" "6b8a885f5544cddd9bc77edb3ad18692" "show-hide-bookmarked-content.js" >}}

------ 

## FAQ

1. **Q:** How can I verify that a bookmark exists before calling `moveToBookmark`?  
   **A:** Retrieve the document's `BookmarkCollection` via `doc.range.bookmarks` and check `doc.range.bookmarks.at(bookmarkName) != null`. Only call `moveToBookmark` when the bookmark is present to avoid an exception.

2. **Q:** Why does a bookmark disappear after I save the document?  
   **A:** Aspose.Words does not rename bookmarks when saving: a name such as `"My Bookmark"` is kept in DOC and DOCX. A bookmark disappears when its `BookmarkStart` or `BookmarkEnd` node is removed, for example, together with the content that contains it. Check that your code does not remove these nodes.

3. **Q:** Can bookmark names contain special characters such as spaces or punctuation?  
   **A:** In its user interface, Microsoft Word accepts only letters, digits, and underscores in bookmark names, starting with a letter. Aspose.Words does not check or change names: a name with spaces or punctuation is saved as it is. Use Word-style names if the document will be edited in Microsoft Word.

4. **Q:** How do I rename an existing bookmark without losing its content?  
   **A:** Set the `name` property of the `Bookmark` object, for example, `doc.range.bookmarks.at("OldName").name = "NewName";`. The bookmarked content stays in place.

5. **Q:** How can I conditionally hide or show the content of a bookmark?  
   **A:** Format the content as hidden text: go from `bookmark.bookmarkStart` to `bookmark.bookmarkEnd` through `nextSibling` and set `font.hidden = true` for each `Run` (cast the nodes with `node.asRun()`). Setting it back to `false` shows the content again.