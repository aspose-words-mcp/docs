---
title: Navigation with Cursor in C#
second_title: Aspose.Words for .NET
articleTitle: Navigation with Cursor
linktitle: Navigation with Cursor
description: "Navigate between different nodes within a document, such as a paragraph, bookmark, or a specific character using C#."
type: docs
weight: 10
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/navigation-with-cursor/
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

Before starting the process of navigating through your document, you will need to get the node that is currently selected. You can get the exact position of the cursor at a selected node by using the [CurrentNode](https://reference.aspose.com/words/net/aspose.words/documentbuilder/currentnode/) property. In addition, instead of getting the current node, you can get the currently selected paragraph or the currently selected section by using the [CurrentParagraph](https://reference.aspose.com/words/net/aspose.words/documentbuilder/currentparagraph/) and [CurrentSection](https://reference.aspose.com/words/net/aspose.words/documentbuilder/currentsection/) properties.

Any insert operations you perform using the [DocumentBuilder](https://reference.aspose.com/words/net/aspose.words/documentbuilder/) will be inserted before the [CurrentNode](https://reference.aspose.com/words/net/aspose.words/documentbuilder/currentnode/). When the current paragraph is empty or the cursor is positioned just before the end of the paragraph, the **CurrentNode** returns null.

## Navigating Methods in a Document

When you are editing text, it is important to know how to navigate your document and where exactly to move in it. Aspose.Words allows you to move around in a document and navigate to its different sections and parts – this is similar to the functionality of the Navigation Pane in Microsoft Word to go to a page or heading in a Word document without scrolling.

The main method is to be able to move the cursor position to a specific node in your document, you can achieve this by using the [MoveTo](https://reference.aspose.com/words/net/aspose.words/documentbuilder/moveto/) method.

The following code example shows how to move the **DocumentBuilder** to different nodes in a document:

{{< gist "aspose-words-gists" "1a2c340d1a9dde6fe70c2733084d9aab" "move-to-node.cs" >}}

But besides the basic **MoveTo** method, there are more specific ones.

### Navigate to Beginning or End of a Document

You can go to the beginning or  the end of your document using the [MoveToDocumentStart](https://reference.aspose.com/words/net/aspose.words/documentbuilder/movetodocumentstart/) and [MoveToDocumentEnd](https://reference.aspose.com/words/net/aspose.words/documentbuilder/movetodocumentend/) methods.

The following code example shows how to move the cursor position to the beginning or the end of a document:

{{< gist "aspose-words-gists" "1a2c340d1a9dde6fe70c2733084d9aab" "move-to-document-start-end.cs" >}}

### Navigate With Bookmarks

You can mark a place that you want to find and move to it again easily. You can insert as many bookmarks into your document as you want, and then navigate through them by identifying the bookmarks with unique names. You can move to a bookmark by using the [MoveToBookmark](https://reference.aspose.com/words/net/aspose.words/documentbuilder/movetobookmark/#movetobookmark/) method.

The following code examples shows how to move a cursor position to a bookmark:

{{< gist "aspose-words-gists" "1a2c340d1a9dde6fe70c2733084d9aab" "move-to-bookmark.cs" >}}

### Navigate to Table Cells

You can move to a table cell by using the [MoveToCell](https://reference.aspose.com/words/net/aspose.words/documentbuilder/movetocell/) method. This method will enable you to navigate your cursor into any cell in a specific table. In addition, you can specify an index to move the cursor to any position or specified character in a cell within the **MoveToCell** method.

The following code example shows how to move a cursor position to a specified table cell:

{{< gist "aspose-words-gists" "1a2c340d1a9dde6fe70c2733084d9aab" "move-to-table-cell.cs" >}}

### Navigate to a Field

You can move to a specific field in your document by using the [MoveToField](https://reference.aspose.com/words/net/aspose.words/documentbuilder/movetofield/) method. In addition, you can move to a specific merge field by using the [MoveToMergeField](https://reference.aspose.com/words/net/aspose.words/documentbuilder/movetomergefield/#movetomergefield/) method.

The following code example shows how to move the document builder cursor to a specific field:

{{< gist "aspose-words-gists" "1a2c340d1a9dde6fe70c2733084d9aab" "move-to-merge-field.cs" >}}

### Navigate to a Header or Footer

You can move to the beginning of a header or footer by using the [MoveToHeaderFooter](https://reference.aspose.com/words/net/aspose.words/documentbuilder/movetoheaderfooter/) method. 

The following code example shows how to move document builder cursor to a document header or footer:

{{< gist "aspose-words-gists" "1a2c340d1a9dde6fe70c2733084d9aab" "move-to-headers-footers.cs" >}}

### Navigate to a Section or Paragraph

You can move to a specific section or paragraph by using the [MoveToParagraph](https://reference.aspose.com/words/net/aspose.words/documentbuilder/movetoparagraph/) or [MoveToSection](https://reference.aspose.com/words/net/aspose.words/documentbuilder/movetosection/) methods. In addition, you can specify an index to move the cursor to any position or a specified character in a paragraph within the **MoveToParagraph** method.

The following code example shows how to move to a specific section and a specific paragraph in a document:

{{< gist "aspose-words-gists" "1a2c340d1a9dde6fe70c2733084d9aab" "move-to-section.cs" >}}

## Related APIs

- [DocumentBuilder.CurrentNode](https://reference.aspose.com/words/net/aspose.words/documentbuilder/currentnode/)
- [DocumentBuilder.CurrentParagraph](https://reference.aspose.com/words/net/aspose.words/documentbuilder/currentparagraph/)
- [DocumentBuilder.CurrentSection](https://reference.aspose.com/words/net/aspose.words/documentbuilder/currentsection/)
- [DocumentBuilder.MoveTo](https://reference.aspose.com/words/net/aspose.words/documentbuilder/moveto/)
- [DocumentBuilder.MoveToBookmark](https://reference.aspose.com/words/net/aspose.words/documentbuilder/movetobookmark/)
- [DocumentBuilder.MoveToCell](https://reference.aspose.com/words/net/aspose.words/documentbuilder/movetocell/)
- [DocumentBuilder.MoveToField](https://reference.aspose.com/words/net/aspose.words/documentbuilder/movetofield/)
- [DocumentBuilder.MoveToMergeField](https://reference.aspose.com/words/net/aspose.words/documentbuilder/movetomergefield/)
- [DocumentBuilder.MoveToHeaderFooter](https://reference.aspose.com/words/net/aspose.words/documentbuilder/movetoheaderfooter/)
- [DocumentBuilder.MoveToParagraph](https://reference.aspose.com/words/net/aspose.words/documentbuilder/movetoparagraph/)
- [DocumentBuilder.MoveToSection](https://reference.aspose.com/words/net/aspose.words/documentbuilder/movetosection/)
- [DocumentBuilder.MoveToDocumentStart](https://reference.aspose.com/words/net/aspose.words/documentbuilder/movetodocumentstart/)
- [DocumentBuilder.MoveToDocumentEnd](https://reference.aspose.com/words/net/aspose.words/documentbuilder/movetodocumentend/)

------

## FAQ
1. **Q:** How can I obtain the node where the cursor is currently positioned?  
   **A:** Use the `DocumentBuilder.CurrentNode` property. It returns the node that the builder is positioned before. If the cursor is at the start of an empty paragraph, the property returns `null`. You can also retrieve the current paragraph or section via `CurrentParagraph` and `CurrentSection`.

2. **Q:** How do I move the cursor to a specific bookmark?  
   **A:** Call `DocumentBuilder.MoveToBookmark("BookmarkName")`. Ensure the bookmark exists; you can create one with `DocumentBuilder.StartBookmark("BookmarkName")` and `DocumentBuilder.EndBookmark("BookmarkName")`.

3. **Q:** How can I navigate to the header or footer of a particular section?  
   **A:** Use `DocumentBuilder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary)` or `HeaderFooterType.FooterPrimary`. To target a specific section, call `DocumentBuilder.MoveToSection(sectionIndex)` first; `MoveToHeaderFooter` then moves to the header or footer of that section.

4. **Q:** How do I move the cursor to a cell inside a table?  
   **A:** Use `DocumentBuilder.MoveToCell(tableIndex, rowIndex, columnIndex, characterIndex)`. All four arguments are indexes: the table in the current story, the row, the cell, and the character position in the cell (`0` for the start, `-1` for the end).

5. **Q:** How can I move the cursor to the beginning or the end of the document?  
   **A:** Call `DocumentBuilder.MoveToDocumentStart()` to place the cursor at the very start, or `DocumentBuilder.MoveToDocumentEnd()` to place it at the end of the document.