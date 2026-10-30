---
title: Navigation with Cursor in Python
second_title: Aspose.Words for Python via .NET
articleTitle: Navigation with Cursor
linktitle: Navigation with Cursor
description: "Navigate between different nodes within a document such as a paragraph, bookmark, or a specific character using Python."
type: docs
weight: 10
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/navigation-with-cursor/
aliases: [/python/navigation-with-cursor/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page shows how to use Aspose.Words for Python via .NET DocumentBuilder to detect the current cursor position and navigate to various document nodes, including the start/end of the document, bookmarks, table cells, fields, headers/footers, sections, and paragraphs.
{{% /alert %}}

While working with a document, even if it is a short or long one, you will need to navigate through your document. Navigation with a virtual cursor represents the ability to navigate between different nodes in a document.

Within a short document, moving around in a document is simple as you can move the insertion point even by using the keyboard's arrow keys or by clicking the mouse to locate the insertion point wherever you want. But once you have a large document that has many pages, these basic techniques will be insufficient.

This article explains how to move around in a document and navigate with a virtual cursor to different parts of it.

## Detecting Current Cursor Position

Before starting the process of navigating through your document, you will need to get the node that is currently selected. You can get the exact position of the cursor at a selected node by using the [current_node](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/current_node/) property. In addition, instead of getting the current node, you can get the currently selected paragraph or the currently selected section by using the [current_paragraph](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/current_paragraph/) and [current_section](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/current_section/) properties.

Any insert operations you perform using the [DocumentBuilder](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/) will be inserted before the [current_node](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/current_node/). When the current paragraph is empty or the cursor is positioned just before the end of the paragraph, the **current_node** returns None.

## Navigating Methods in a Document

When you are editing text, it is important to know how to navigate your document and where exactly to move in it. Aspose.Words allows you to move around in a document and navigate to its different sections and parts – this is similar to the functionality of the Navigation Pane in Microsoft Word to go to a page or heading in a Word document without scrolling.

The main method is to be able to move the cursor position to a specific node in your document, you can achieve this by using the [move_to](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/move_to/) method.

The following code example shows how to move the **DocumentBuilder** to different nodes in a document:

{{< gist "aspose-words-gists" "28dae30609edfc01f5106ff23c7a81f1" "move-to-node.py" >}}

But besides the basic **move_to** method, there are more specific ones.

### Navigate to Beginning or End of a Document

You can go to the beginning or the end of your document using the [move_to_document_start](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/move_to_document_start/) and [move_to_document_end](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/move_to_document_end/) methods.

The following code example shows how to move the cursor position to the beginning or the end of a document:

{{< gist "aspose-words-gists" "28dae30609edfc01f5106ff23c7a81f1" "move-to-document-start-end.py" >}}

### Navigate With Bookmarks

You can mark a place that you want to find and move to it again easily. You can insert as many bookmarks into your document as you want, and then navigate through them by identifying the bookmarks with unique names. You can move to a bookmark by using the [move_to_bookmark](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/move_to_bookmark/) method.

The following code examples shows how to move a cursor position to a bookmark:

{{< gist "aspose-words-gists" "28dae30609edfc01f5106ff23c7a81f1" "move-to-bookmark.py" >}}

### Navigate to Table Cells

You can move to a table cell by using the [move_to_cell](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/move_to_cell/) method. This method will enable you to navigate your cursor into any cell in a specific table. In addition, you can specify an index to move the cursor to any position or specified character in a cell within the **move_to_cell** method.

The following code example shows how to move a cursor position to a specified table cell:

{{< gist "aspose-words-gists" "28dae30609edfc01f5106ff23c7a81f1" "move-to-table-cell.py" >}}

### Navigate to a Field

You can move to a specific field in your document by using the [move_to_field](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/move_to_field/) method. In addition, you can move to a specific merge field by using the [move_to_merge_field](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/move_to_merge_field/) method.

The following code example shows how to move the document builder cursor to a specific field:

{{< gist "aspose-words-gists" "28dae30609edfc01f5106ff23c7a81f1" "move-to-merge-field.py" >}}

### Navigate to a Header or Footer

You can move to the beginning of a header or footer by using the [move_to_header_footer](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/move_to_header_footer/) method.

The following code example shows how to move document builder cursor to a document header or footer:

{{< gist "aspose-words-gists" "28dae30609edfc01f5106ff23c7a81f1" "move-to-headers-footers.py" >}}

### Navigate to a Section or Paragraph

You can move to a specific section or paragraph by using the [move_to_paragraph](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/move_to_paragraph/) or [move_to_section](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/move_to_section/) methods. In addition, you can specify an index to move the cursor to any position or a specified character in a paragraph within the **move_to_paragraph** method.

The following code example shows how to move to a specific section and a specific paragraph in a document:

{{< gist "aspose-words-gists" "28dae30609edfc01f5106ff23c7a81f1" "move-to-section.py" >}}

## Related APIs

- [DocumentBuilder.current_node](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/current_node/)
- [DocumentBuilder.current_paragraph](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/current_paragraph/)
- [DocumentBuilder.current_section](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/current_section/)
- [DocumentBuilder.move_to](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/move_to/)
- [DocumentBuilder.move_to_bookmark](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/move_to_bookmark/)
- [DocumentBuilder.move_to_cell](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/move_to_cell/)
- [DocumentBuilder.move_to_field](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/move_to_field/)
- [DocumentBuilder.move_to_merge_field](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/move_to_merge_field/)
- [DocumentBuilder.move_to_header_footer](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/move_to_header_footer/)
- [DocumentBuilder.move_to_paragraph](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/move_to_paragraph/)
- [DocumentBuilder.move_to_section](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/move_to_section/)
- [DocumentBuilder.move_to_document_start](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/move_to_document_start/)
- [DocumentBuilder.move_to_document_end](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/move_to_document_end/) 

## FAQ

1. **Q:** How can I obtain the node that the cursor is currently positioned on?  
   **A:** Use the `DocumentBuilder.current_node` property. It returns the `Node` object where the cursor resides, or `None` if the cursor is at the end of an empty paragraph. You can also retrieve the current paragraph with `DocumentBuilder.current_paragraph` or the current section with `DocumentBuilder.current_section`.

2. **Q:** How do I move the cursor to a specific bookmark?  
   **A:** Call `DocumentBuilder.move_to_bookmark("BookmarkName")`. Replace `"BookmarkName"` with the name you assigned to the bookmark when creating it. The cursor will be placed at the start of that bookmark.

3. **Q:** What is the correct way to navigate to a particular cell in a table?  
   **A:** Use `DocumentBuilder.move_to_cell(table_index, row_index, column_index, character_index)`. Pass the zero‑based indices of the table, row and column, and the character offset inside the cell (`0` for the start of the cell).

4. **Q:** How can I move the cursor to the header or footer of a document?  
   **A:** Invoke `DocumentBuilder.move_to_header_footer(HeaderFooterType.HEADER_PRIMARY)` or `DocumentBuilder.move_to_header_footer(HeaderFooterType.FOOTER_PRIMARY)`. Use `HEADER_FIRST`/`HEADER_EVEN` (or `FOOTER_FIRST`/`FOOTER_EVEN`) to target the first-page or even-page header/footer.

5. **Q:** How do I quickly move the cursor to the very start or end of the document?  
   **A:** Use `DocumentBuilder.move_to_document_start()` to place the cursor at the beginning, and `DocumentBuilder.move_to_document_end()` to place it at the end of the document. These methods are useful for inserting content at the document boundaries.