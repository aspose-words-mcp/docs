---
title: Navigation with Cursor in Java
second_title: Aspose.Words for Java
articleTitle: Navigation with Cursor
linktitle: Navigation with Cursor
description: "Navigate between different nodes within a document, such as a paragraph, bookmark, or a specific character using Java."
type: docs
weight: 5
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/navigation-with-cursor/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to navigate a document using the document cursor and associated API operations.

{{% /alert %}}

While working with a document, even if it is a short or long one, you will need to navigate through your document. Navigation with a virtual cursor represents the ability to navigate between different nodes in a document.

Within a short document, moving around in a document is simple as you can move the insertion point even by using the keyboard's arrow keys or by clicking the mouse to locate the insertion point wherever you want. But once you have a large document that has many pages, these basic techniques will be insufficient.

This article explains how to move around in a document and navigate with a virtual cursor to different parts of it.

## Detecting Current Cursor Position

Before starting the process of navigating through your document, you will need to get the node that is currently selected. You can get the exact position of the cursor at a selected node by using the [getCurrentNode()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#getCurrentNode) property. In addition, instead of getting the current node, you can get the currently selected paragraph or the currently selected section by using the [getCurrentParagraph()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#getCurrentParagraph) and [getCurrentSection()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#getCurrentSection) properties.

Any insert operations you perform using the [DocumentBuilder](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/) will be inserted before the [getCurrentNode()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#getCurrentNode). When the current paragraph is empty or the cursor is positioned just before the end of the paragraph, the **getCurrentNode()** returns null.

## Navigating Methods in a Document

When you are editing text, it is important to know how to navigate your document and where exactly to move in it. Aspose.Words allows you to move around in a document and navigate to its different sections and parts – this is similar to the functionality of the Navigation Pane in Microsoft Word to go to a page or heading in a Word document without scrolling.

The main method is to be able to move the cursor position to a specific node in your document, you can achieve this by using the [moveTo()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveTo-com.aspose.words.Node) method.

The following code example shows how to move the **DocumentBuilder** to different nodes in a document:

{{< gist "aspose-words-gists" "402a4aea5f494d032783f0e9365d5990" "move-to-node.java" >}}

But besides the basic **moveTo()** method, there are more specific ones.

### Navigate to Beginning or End of a Document

You can go to the beginning or the end of your document using the [moveToDocumentStart()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveToDocumentStart) and [moveToDocumentEnd()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveToDocumentEnd) methods.

The following code example shows how to move the cursor position to the beginning or the end of a document:

{{< gist "aspose-words-gists" "402a4aea5f494d032783f0e9365d5990" "move-to-document-start-end.java" >}}

### Navigate With Bookmarks

You can mark a place that you want to find and move to it again easily. You can insert as many bookmarks into your document as you want, and then navigate through them by identifying the bookmarks with unique names. You can move to a bookmark by using the [moveToBookmark()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveToBookmark-java.lang.String-boolean-boolean) method.

The following code examples shows how to move a cursor position to a bookmark:

{{< gist "aspose-words-gists" "402a4aea5f494d032783f0e9365d5990" "move-to-bookmark.java" >}}

### Navigate to Table Cells

You can move to a table cell by using the [moveToCell()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveToCell-int-int-int-int) method. This method will enable you to navigate your cursor into any cell in a specific table. In addition, you can specify an index to move the cursor to any position or specified character in a cell within the **moveToCell()** method.

The following code example shows how to move a cursor position to a specified table cell:

{{< gist "aspose-words-gists" "402a4aea5f494d032783f0e9365d5990" "move-to-table-cell.java" >}}

### Navigate to a Field

You can move to a specific field in your document by using the [moveToField()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveToField-com.aspose.words.Field-boolean) method. In addition, you can move to a specific merge field by using the [moveToMergeField()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveToMergeField-java.lang.String) method.

The following code example shows how to move the document builder cursor to a specific field:

{{< gist "aspose-words-gists" "402a4aea5f494d032783f0e9365d5990" "move-to-merge-field.java" >}}

### Navigate to a Header or Footer

You can move to the beginning of a header or footer by using the [moveToHeaderFooter()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveToHeaderFooter-int) method. 

The following code example shows how to move document builder cursor to a document header or footer:

{{< gist "aspose-words-gists" "402a4aea5f494d032783f0e9365d5990" "move-to-headers-footers.java" >}}

### Navigate to a Section or Paragraph

You can move to a specific section or paragraph by using the [moveToParagraph()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveToParagraph-int-int) or [moveToSection()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveToSection-int) methods. In addition, you can specify an index to move the cursor to any position or a specified character in a paragraph within the **moveToParagraph()** method.

The following code example shows how to move to a specific section and a specific paragraph in a document:

{{< gist "aspose-words-gists" "402a4aea5f494d032783f0e9365d5990" "move-to-section.java" >}}

## Related APIs

- [DocumentBuilder.getCurrentNode()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#getCurrentNode)
- [DocumentBuilder.getCurrentParagraph()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#getCurrentParagraph)
- [DocumentBuilder.getCurrentSection()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#getCurrentSection)
- [DocumentBuilder.moveTo](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveTo-com.aspose.words.Node)
- [DocumentBuilder.moveToBookmark](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveToBookmark-java.lang.String)
- [DocumentBuilder.moveToCell](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveToCell-int-int-int-int)
- [DocumentBuilder.moveToField](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveToField-com.aspose.words.Field-boolean)
- [DocumentBuilder.moveToMergeField](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveToMergeField-java.lang.String)
- [DocumentBuilder.moveToHeaderFooter](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveToHeaderFooter-int)
- [DocumentBuilder.moveToParagraph](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveToParagraph-int-int)
- [DocumentBuilder.moveToSection](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveToSection-int)
- [DocumentBuilder.moveToDocumentStart](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveToDocumentStart)
- [DocumentBuilder.moveToDocumentEnd](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveToDocumentEnd)
