---
title: Working with Bookmarks in Java
second_title: Aspose.Words for Java
articleTitle: Working with Bookmarks
linktitle: Working with Bookmarks
description: "Understanding bookmark concepts and how bookmark can be used in your program using Java."
type: docs
weight: 180
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-bookmarks/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with bookmarks in Aspose.Words.

{{% /alert %}}

Bookmarks identify in a Microsoft Word document the locations or fragments that you name and identify for future reference. For example, you might use a bookmark to identify text that you want to revise later. Instead of scrolling through the document to locate the text, you can go to it by using the Bookmark dialog box.

The actions that can be performed with bookmarks using Aspose.Words are the same as the ones you can perform using Microsoft Word. You can insert a new bookmark, delete, move to a bookmark, get or set a bookmark name, get or set text enclosed in it.

## Insert a Bookmark

Use [startBookmark](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#startBookmark-java.lang.String) and [endBookmark](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#endBookmark-java.lang.String) to create a bookmark by marking its start and end, respectively. Do not forget to pass the same bookmark name to both methods. Bookmarks in a document can overlap and span any range. Badly formed bookmarks or bookmarks with duplicate names will be ignored when the document is saved.

{{% alert color="primary" %}}

All white spaces in the bookmarks were replaced with underscores. This restriction came from Microsoft Word formats, since bookmarks in Word formats like DOCX or DOC cannot have white spaces. However, PDF allows such bookmarks. So now, if you need to use bookmarks in PDF or XPS outlines, you can use them with white spaces.

{{% /alert %}}

The following code example shows how to create a new bookmark:

{{< gist "aspose-words-gists" "ac2265ee10ddb4f0649f31ab8d219a94" "create-bookmark.java" >}}

## Obtain Bookmarks

Sometimes it is necessary to obtain a bookmark collection to iterate through bookmarks or for other purposes. Use the [Node.getRange()](https://reference.aspose.com/words/java/com.aspose.words/node/#getRange) property exposed by any document node that returns a [Range](https://reference.aspose.com/words/java/com.aspose.words/range/) object representing the portion of the document contained in this node. Use this object to retrieve a [BookmarkCollection](https://reference.aspose.com/words/java/com.aspose.words/bookmarkcollection/) and then use the collection indexer to get a specific bookmark.

The following code example shows how to obtain bookmarks from a bookmark collection:

{{< gist "aspose-words-gists" "ac2265ee10ddb4f0649f31ab8d219a94" "access-bookmarks.java" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Bookmarks.docx).

{{% /alert %}}

The following code example shows how to get or set a bookmark name and text:

{{< gist "aspose-words-gists" "ac2265ee10ddb4f0649f31ab8d219a94" "update-bookmark-data.java" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Bookmarks.docx).

{{% /alert %}}

The following code example shows how to bookmark a table:

{{< gist "aspose-words-gists" "ac2265ee10ddb4f0649f31ab8d219a94" "bookmark-table.java" >}}

If you change the name of a bookmark to a name that already exists in the document, no error will be generated and only the first bookmark will be stored when you save the document.

Note that some bookmarks in the document are assigned to form fields. Moving to such a bookmark and inserting text there inserts the text into the form field code. Although this will not invalidate the form field, the inserted text will not be visible because it becomes part of the field code.

The following code example shows how to access columns of the bookmarked table:

{{< gist "aspose-words-gists" "ac2265ee10ddb4f0649f31ab8d219a94" "bookmark-table-columns.java" >}}

## Move to a Bookmark

If you need to insert rich content (not just plain text) into a bookmark, you should use [moveToBookmark](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveToBookmark-java.lang.String) to move the cursor to the bookmark and then use [DocumentBuilder's](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/) methods and properties to insert content.

## Show Hide Bookmark Content

The entire Bookmark (*including the bookmarked content*) can be encapsulated within the True part of the `IF` field using Aspose.Words. It can be in such a way that the `IF` field contains a nested Merge Field in the expression (*Left of Operator*) and depending upon the value of Merge Field, the `IF` field shows or hides the content of Bookmark in Word Document.

The following code example shows how to show/ hide bookmarks:

{{< gist "aspose-words-gists" "ac2265ee10ddb4f0649f31ab8d219a94" "show-hide-bookmarks.java" >}}

{{< gist "aspose-words-gists" "ac2265ee10ddb4f0649f31ab8d219a94" "show-hide-bookmarked-content.java" >}}

## FAQ

1. **Q:** How can I insert a new bookmark using Aspose.Words for Java?  
   **A:** Create a `DocumentBuilder` for your document, call `builder.startBookmark("MyBookmark")` at the start position, add the desired content, and then call `builder.endBookmark("MyBookmark")`. The same name must be used for both calls.

2. **Q:** How do I retrieve the text stored inside an existing bookmark?  
   **A:** Obtain the `Bookmark` object from the document's bookmark collection:  
   ```java
   Document doc = new Document("input.docx");
   Bookmark bookmark = doc.getRange().getBookmarks().get("MyBookmark");
   String text = bookmark.getText();
   ```  
   The `getText()` method returns the full text enclosed by the bookmark.

3. **Q:** Is it possible to rename a bookmark after it has been created?  
   **A:** Yes. After retrieving the `Bookmark` object, call `bookmark.setName("NewName")`. Ensure the new name is unique; if a duplicate exists, only the first bookmark with that name will be saved.

4. **Q:** How can I move the cursor to a bookmark to insert rich content?  
   **A:** Use `DocumentBuilder.moveToBookmark("MyBookmark")`. Once the builder's cursor is positioned, you can insert paragraphs, tables, images, etc., just as with any other `DocumentBuilder` operation.

5. **Q:** How can I conditionally show or hide the content of a bookmark?  
   **A:** Wrap the bookmark inside an `IF` field that evaluates a merge field or custom document variable. When the condition is true, the bookmark's content is displayed; otherwise, it is hidden. This technique is demonstrated in the “Show Hide Bookmark Content” example.