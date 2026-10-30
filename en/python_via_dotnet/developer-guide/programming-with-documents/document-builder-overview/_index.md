---
title: Document Builder Overview in Python
second_title: Aspose.Words for Python via .NET
articleTitle: Document Builder Overview
linktitle: Document Builder Overview
type: docs
description: "DocumentBuilder allows you to build dynamic documents from scratch or add new elements to existing ones using Python. DocumentBuilder provides methods to insert text, checkboxes, tables, images, and other content elements in Python."
weight: 30
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/document-builder-overview/
aliases: [/python/document-builder-overview/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}

*Purpose Summary. What is this page about?*

This page introduces the Aspose.Words DocumentBuilder class for Python via .NET, describing how it enables creation and modification of documents, navigation using a virtual cursor, and insertion of various elements such as text, tables, images, and fields with formatting. It also includes code examples that demonstrate building documents, applying formatting, and moving the cursor to specific locations.

{{% /alert %}}

[DocumentBuilder](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/) is a powerful class that associates with [Document](https://reference.aspose.com/words/python-net/aspose.words/document/) and enables you to build dynamic documents from scratch or add new elements to an existing one.

**DocumentBuilder** provides methods to insert text, checkboxes, ole objects, paragraphs, lists, tables, images, and other content elements. It allows you to specify fonts, paragraph or section formatting, and perform other operations.

## Document Builder or Aspose.Words DOM

**DocumentBuilder** complements classes and methods available in the Aspose.Words Document Object Model (DOM) to simplify the most common document building tasks. That is, you can create and modify the content of documents both through the Aspose.Words DOM, which requires a good understanding of the tree structure, and using the DocumentBuilder. The `DocumentBuilder` is a "facade" for the complex **Document** structure that allows you to quickly and easily insert content and formatting.

Operations that are possible with **DocumentBuilder** are also possible when using the classes of the Aspose.Words DOM directly. However, using Aspose.Words DOM classes directly usually requires more lines of code than using **DocumentBuilder**.

## Document Navigation

Document navigation is based on the concept of a virtual cursor, with which you can move to another location in the document using various **DocumentBuilder.move_to_XXX** methods such as [move_to_document_start](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/move_to_document_start/) and [move_to_field](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/move_to_field/). This virtual cursor indicates where the text will be inserted when calling the methods [write](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/write/), [writeln](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/writeln/), [insert_break](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_break/), and others. See the following article "Navigation with Cursor" to learn more about the virtual cursor.

The following code example shows how to navigate to a bookmark:

{{< gist "aspose-words-gists" "e934a01a96022d1546d17c47a5ab3904" "move-to-bookmark-end.py" >}}

## Document Building and Modifying

Aspose.Words API provides several classes that are responsible for formatting various elements of a document. Each of the classes encapsulates formatting properties related to a specific document element, such as text, paragraph, section, and others. For example, the [Font](https://reference.aspose.com/words/python-net/aspose.words/font/) class represents character formatting properties, the [ParagraphFormat](https://reference.aspose.com/words/python-net/aspose.words/paragraphformat/) class represents paragraph formatting properties, and so on. Objects of these classes are returned by the corresponding **DocumentBuilder** properties, which have the same names as the classes. Therefore, you can access them and set the desired formatting during the document build.

You can also insert text, checkbox, ole object, images, bookmarks, form fields, and other document elements at the cursor position using the `Write` method or any of the **DocumentBuilder.insert_XXX** methods, such as [insert_field](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_field/), [insert_html](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_html/), and similar methods.

Let's see how to create a simple document using the **DocumentBuilder**.

### Create a Document using DocumentBuilder

To start, you need to create a **DocumentBuilder** and associate it with a **Document** object. You create a new instance of **DocumentBuilder** by calling its constructor and pass it to a **Document** object for attachment to the builder.

To insert a text, pass the string of text you need to insert into the document to the **Write** method.

The following code example shows how to create a simple document using a document builder.

{{< gist "aspose-words-gists" "59e45f5041ff6b356c5165164c019a76" "create-new-document.py" >}}

### Specify Document Formatting

The [font](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/font/) property defines text formatting. This object contains different font attributes (font name, font size, color, and so on). Some important font attributes are also represented by **DocumentBuilder** properties to allow you to access them directly. These are the [Font.bold](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/bold/), [Font.italic](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/italic/), and [Font.underline](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/underline/) boolean properties.

The following code example shows how to insert a formatted text using **DocumentBuilder**:

{{< gist "aspose-words-gists" "e934a01a96022d1546d17c47a5ab3904" "insert-paragraph.py" >}}

{{% alert color="primary" %}}

- [font](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/font/) specifies the character formatting that will be applied to all text inserted from the current position in the document onwards.
- [paragraph_format](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/paragraph_format/) specifies the paragraph formatting for the current and all paragraphs to be inserted.
- [page_setup](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/page_setup/) specifies the page and section properties for the current section and the entire section that will be inserted.
- [cell_format](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/cell_format/) and [row_format](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/row_format/) specify formatting properties that will be applied to table cells and rows from the current position in the document onwards.

In this situation, "current" means the position, paragraph, section, cell, or row in which the cursor is.

{{% /alert %}}

{{% alert color="primary" %}}

Note that the **Font**, **ParagraphFormat**, and **PageSetup** properties are updated whenever you navigate to a different location in the document to reflect the formatting properties of this location.

{{% /alert %}}

## Related APIs

- [Document](https://reference.aspose.com/words/python-net/aspose.words/document/)
- [Font](https://reference.aspose.com/words/python-net/aspose.words/font/)
- [ParagraphFormat](https://reference.aspose.com/words/python-net/aspose.words/paragraphformat/)
- [PageSetup](https://reference.aspose.com/words/python-net/aspose.words/pagesetup/)
- [cell_format](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/cell_format/)
- [row_format](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/row_format/)
- [DocumentBuilder.move_to_bookmark](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/move_to_bookmark/)
- [DocumentBuilder.write](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/write/)
- [DocumentBuilder.writeln](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/writeln/)
- [DocumentBuilder.insert_field](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_field/)
- [DocumentBuilder.insert_html](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_html/) 

## FAQ

1. **Q:** How can I change the font size of text that I insert after calling `insert_document`?  
   **A:** After inserting another document, set the `Font.size` property on the `DocumentBuilder` before writing new text. The change affects all subsequent insertions.

2. **Q:** Does `DocumentBuilder.insert_document` preserve the source document's formatting by default?  
   **A:** The import mode is a required second argument. Pass `ImportFormatMode.KEEP_SOURCE_FORMATTING` to keep the source formatting, or `ImportFormatMode.USE_DESTINATION_STYLES` to apply the destination document's styles.  

   ```python
   builder.insert_document(source_doc, aw.ImportFormatMode.KEEP_SOURCE_FORMATTING)
   ```

3. **Q:** How do I move the cursor to a bookmark before inserting content?  
   **A:** Use `DocumentBuilder.move_to_bookmark("BookmarkName")`. The builder's cursor will be positioned at the start of the specified bookmark, and any subsequent insertions will occur there.  

   ```python
   builder.move_to_bookmark("MyBookmark")
   builder.writeln("Text inserted at the bookmark.")
   ```

4. **Q:** Can I insert a table of contents using `DocumentBuilder`?  
   **A:** Yes. Call `insert_table_of_contents` with the appropriate field code. The method inserts a TOC field that can be updated later.  

   ```python
   builder.insert_table_of_contents("\\o \"1-3\" \\h \\z \\u")
   ```

5. **Q:** Does `Document.get_child_nodes(NodeType.PARAGRAPH, True)` include paragraphs that are inside headers and footers?  
   **A:** Yes. With `is_deep=True` the method returns paragraphs from the whole document, including headers and footers. To get only body paragraphs, use `section.body.paragraphs` for each section.