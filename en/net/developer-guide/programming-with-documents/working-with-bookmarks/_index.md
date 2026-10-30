---
title: Working with Bookmarks in C#
second_title: Aspose.Words for .NET
articleTitle: Working with Bookmarks
linktitle: Working with Bookmarks
description: "Understanding bookmark concepts and how bookmark can be used in your program using C#."
type: docs
weight: 180
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/working-with-bookmarks/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with bookmarks in Aspose.Words.

{{% /alert %}}

Bookmarks identify in a Microsoft Word document the locations or fragments that you name and identify for future reference. For example, you might use a bookmark to identify text that you want to revise later. Instead of scrolling through the document to locate the text, you can go to it by using the Bookmark dialog box.

The actions that can be performed with bookmarks using Aspose.Words are the same as the ones you can perform using Microsoft Word. You can insert a new bookmark, delete, move to a bookmark, get or set a bookmark name, get or set text enclosed in it.

## Insert a Bookmark

Use [StartBookmark](https://reference.aspose.com/words/net/aspose.words/documentbuilder/startbookmark/) and [EndBookmark](https://reference.aspose.com/words/net/aspose.words/documentbuilder/endbookmark/) to create a bookmark by marking its start and end, respectively. Do not forget to pass the same bookmark name to both methods. Bookmarks in a document can overlap and span any range. Badly formed bookmarks or bookmarks with duplicate names will be ignored when the document is saved.

{{% alert color="primary" %}}

All white spaces in the bookmarks were replaced with underscores. This restriction came from Microsoft Word formats, since bookmarks in Word formats like DOCX or DOC cannot have white spaces. However, PDF allows such bookmarks. So now, if you need to use bookmarks in PDF or XPS outlines, you can use them with white spaces.

{{% /alert %}}

The following code example shows how to create a new bookmark:

{{< gist "aspose-words-gists" "c4555b1a088856e21394104faeb86e51" "create-bookmark.cs" >}}

## Obtain Bookmarks

Sometimes it is necessary to obtain a bookmark collection to iterate through bookmarks or for other purposes. Use the [Node.Range](https://reference.aspose.com/words/net/aspose.words/node/range/) property exposed by any document node that returns a [Range](https://reference.aspose.com/words/net/aspose.words/range/) object representing the portion of the document contained in this node. Use this object to retrieve a [BookmarkCollection](https://reference.aspose.com/words/net/aspose.words/bookmarkcollection/) and then use the collection indexer to get a specific bookmark.

The following code example shows how to obtain bookmarks from a bookmark collection:

{{< gist "aspose-words-gists" "c4555b1a088856e21394104faeb86e51" "access-bookmarks.cs" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-.NET/blob/master/Examples/Data/Bookmarks.docx).

{{% /alert %}}

The following code example shows how to get or set a bookmark name and text:

{{< gist "aspose-words-gists" "c4555b1a088856e21394104faeb86e51" "update-bookmark-data.cs" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-.NET/blob/master/Examples/Data/Bookmarks.docx).

{{% /alert %}}

The following code example shows how to bookmark a table:

{{< gist "aspose-words-gists" "c4555b1a088856e21394104faeb86e51" "bookmark-table.cs" >}}

If you change the name of a bookmark to a name that already exists in the document, no error will be generated and only the first bookmark will be stored when you save the document.

Note that some bookmarks in the document are assigned to form fields. Moving to such a bookmark and inserting text there inserts the text into the form field code. Although this will not invalidate the form field, the inserted text will not be visible because it becomes part of the field code.

The following code example shows how to access columns of the bookmarked table:

{{< gist "aspose-words-gists" "c4555b1a088856e21394104faeb86e51" "bookmark-table-columns.cs" >}}

## Move to a Bookmark

If you need to insert rich content (not just plain text) into a bookmark, you should use [MoveToBookmark](https://reference.aspose.com/words/net/aspose.words/documentbuilder/movetobookmark/) to move the cursor to the bookmark and then use [DocumentBuilder's](https://reference.aspose.com/words/net/aspose.words/documentbuilder/) methods and properties to insert content.

## Show Hide Bookmark Content

The entire Bookmark (*including the bookmarked content*) can be encapsulated within the True part of the `IF` field using Aspose.Words. It can be in such a way that the `IF` field contains a nested Merge Field in the expression (*Left of Operator*) and depending upon the value of Merge Field, the `IF` field shows or hides the content of Bookmark in Word Document.

The following code example shows how to show/ hide bookmarks:

{{< gist "aspose-words-gists" "c4555b1a088856e21394104faeb86e51" "show-hide-bookmarks.cs" >}}

{{< gist "aspose-words-gists" "c4555b1a088856e21394104faeb86e51" "show-hide-bookmarked-content.cs" >}}

------

## FAQ

1. **Q:** How do I create a bookmark in a Word document using C#?  
   **A:** Use `DocumentBuilder.StartBookmark("MyBookmark")` to mark the start and `DocumentBuilder.EndBookmark("MyBookmark")` to mark the end. Both calls must use the identical bookmark name. Example:  

   ```csharp
   Document doc = new Document();
   DocumentBuilder builder = new DocumentBuilder(doc);
   builder.StartBookmark("MyBookmark");
   builder.Writeln("Text inside the bookmark.");
   builder.EndBookmark("MyBookmark");
   ```

2. **Q:** Can a bookmark name contain spaces?  
   **A:** In Word formats (DOC, DOCX) spaces are not allowed; Aspose.Words automatically replaces spaces with underscores. PDF and XPS outlines do allow spaces, so you can keep them when exporting to those formats.

3. **Q:** What happens if I add two bookmarks with the same name?  
   **A:** Aspose.Words does not throw an exception. When the document is saved, only the first bookmark with that name is retained. To avoid data loss, ensure each bookmark name is unique within the document.

4. **Q:** How can I move the cursor to an existing bookmark to insert additional content?  
   **A:** Call `DocumentBuilder.MoveToBookmark("MyBookmark")`. After the cursor is positioned, you can use any `DocumentBuilder` methods (e.g., `Write`, `InsertTable`, `InsertImage`) to add content at that location.  

   ```csharp
   DocumentBuilder builder = new DocumentBuilder(doc);
   builder.MoveToBookmark("MyBookmark");
   builder.Writeln("Additional text after the bookmark.");
   ```

5. **Q:** How do I read or modify the text that a bookmark encloses?  
   **A:** Retrieve the `Bookmark` object from the document's `BookmarkCollection` and use its `Text` property. Setting this property replaces the entire bookmarked content.  

   ```csharp
   Bookmark bookmark = doc.Range.Bookmarks["MyBookmark"];
   string currentText = bookmark.Text;          // read
   bookmark.Text = "New content for the bookmark"; // replace
   ```

These FAQs address the most common questions users have when working with bookmarks in Aspose.Words for .NET.