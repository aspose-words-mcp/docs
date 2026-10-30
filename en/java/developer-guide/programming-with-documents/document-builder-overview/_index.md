---
title: Document Builder Overview in Java
second_title: Aspose.Words for Java
articleTitle: Document Builder Overview
linktitle: Document Builder Overview
type: docs
description: "DocumentBuilder allows you to build dynamic documents from scratch or add new elements to existing ones using Java. DocumentBuilder provides methods to insert text, checkboxes, tables, images, and other content elements in Java."
weight: 30
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/document-builder-overview/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains the basics of the DocumentBuilder API and shows how to construct document elements programmatically.

{{% /alert %}}

[DocumentBuilder](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/) is a powerful class that associates with [Document](https://reference.aspose.com/words/java/com.aspose.words/document/) and enables you to build dynamic documents from scratch or add new elements to an existing one.

**DocumentBuilder** provides methods to insert text, checkboxes, ole objects, paragraphs, lists, tables, images, and other content elements. It allows you to specify fonts, paragraph or section formatting, and perform other operations.

## Document Builder or Aspose.Words DOM

**DocumentBuilder** complements classes and methods available in the Aspose.Words Document Object Model (DOM) to simplify the most common document building tasks. That is, you can create and modify the content of documents both through the Aspose.Words DOM, which requires a good understanding of the tree structure, and using the DocumentBuilder. The `DocumentBuilder` is a "facade" for the complex **Document** structure that allows you to quickly and easily insert content and formatting.

Operations that are possible with **DocumentBuilder** are also possible when using the classes of the Aspose.Words DOM directly. However, using Aspose.Words DOM classes directly usually requires more lines of code than using **DocumentBuilder**.

## Document Navigation

Document navigation is based on the concept of a virtual cursor, with which you can move to another location in the document using various **DocumentBuilder.MoveToXXX** methods such as [moveToDocumentStart()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveToDocumentStart) and [moveToField()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveToField-com.aspose.words.Field-boolean). This virtual cursor indicates where the text will be inserted when calling the methods [write()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#write-java.lang.String), [writeln()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#writeln), [insertBreak()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertBreak-int), and others. See the following article "Navigation with Cursor" to learn more about the virtual cursor.

The following code example shows how to navigate to a bookmark:

{{< gist "aspose-words-gists" "f241f6361cb8566b906f0daa559ea33d" "move-to-bookmark-end.java" >}}

## Document Building and Modifying

Aspose.Words API provides several classes that are responsible for formatting various elements of a document. Each of the classes encapsulates formatting properties related to a specific document element, such as text, paragraph, section, and others. For example, the [Font](https://reference.aspose.com/words/java/com.aspose.words/font/) class represents character formatting properties, the [ParagraphFormat](https://reference.aspose.com/words/java/com.aspose.words/paragraphformat/) class represents paragraph formatting properties, and so on. Objects of these classes are returned by the corresponding **DocumentBuilder** properties, which have the same names as the classes. Therefore, you can access them and set the desired formatting during the document build.

You can also insert text, checkbox, ole object, images, bookmarks, form fields, and other document elements at the cursor position using the `Write` method or any of the **DocumentBuilder.InsertXXX** methods, such as [insertField()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertField-int-boolean), [insertHtml()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertHtml-java.lang.String), and similar methods.

Let's see how to create a simple document using the **DocumentBuilder**.

### Create a Document using DocumentBuilder

To start, you need to create a **DocumentBuilder** and associate it with a **Document** object. You create a new instance of **DocumentBuilder** by calling its constructor and pass it to a **Document** object for attachment to the builder.

To insert a text, pass the string of text you need to insert into the document to the **Write** method.

The following code example shows how to create a simple document using a document builder.

{{< gist "aspose-words-gists" "ae20848f6cefd3f85ab9bcbbdda340c7" "create-new-document.java" >}}

### Specify Document Formatting

The [getFont()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#getFont) property defines text formatting. This object contains different font attributes (font name, font size, color, and so on). Some important font attributes are also represented by **DocumentBuilder** properties to allow you to access them directly. These are the [Font.getBold()](https://reference.aspose.com/words/java/com.aspose.words/font/#getBold), [Font.getItalic()](https://reference.aspose.com/words/java/com.aspose.words/font/#getItalic), and [Font.getUnderline()](https://reference.aspose.com/words/java/com.aspose.words/font/#getUnderline) boolean properties.

The following code example shows how to insert a formatted text using **DocumentBuilder**:

{{< gist "aspose-words-gists" "f241f6361cb8566b906f0daa559ea33d" "insert-paragraph.java" >}}

{{% alert color="primary" %}}

- [getFont()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#getFont) specifies the character formatting that will be applied to all text inserted from the current position in the document onwards.
- [ParagraphFormat](https://reference.aspose.com/words/java/com.aspose.words/paragraphformat/) specifies the paragraph formatting for the current and all paragraphs to be inserted.
- [PageSetup](https://reference.aspose.com/words/java/com.aspose.words/pagesetup/) specifies the page and section properties for the current section and the entire section that will be inserted.
- [getCellFormat()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#getCellFormat) and [getRowFormat()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#getRowFormat) specify formatting properties that will be applied to table cells and rows from the current position in the document onwards.

In this situation, "current" means the position, paragraph, section, cell, or row in which the cursor is.

{{% /alert %}}

{{% alert color="primary" %}}

Note that the **Font**, **ParagraphFormat**, and **PageSetup** properties are updated whenever you navigate to a different location in the document to reflect the formatting properties of this location.

{{% /alert %}}

## Related APIs

- [Document](https://reference.aspose.com/words/java/com.aspose.words/document/)
- [Font](https://reference.aspose.com/words/java/com.aspose.words/font/)
- [ParagraphFormat](https://reference.aspose.com/words/java/com.aspose.words/paragraphformat/)
- [PageSetup](https://reference.aspose.com/words/java/com.aspose.words/pagesetup/)
- [getCellFormat()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#getCellFormat)
- [getRowFormat()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#getRowFormat)
- [DocumentBuilder.moveToBookmark](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#moveToBookmark-java.lang.String)
- [DocumentBuilder.write](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#write-java.lang.String)
- [DocumentBuilder.writeln](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#writeln-java.lang.String)
- [DocumentBuilder.insertField](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertField-int-boolean)
- [DocumentBuilder.insertHtml](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertHtml-java.lang.String)