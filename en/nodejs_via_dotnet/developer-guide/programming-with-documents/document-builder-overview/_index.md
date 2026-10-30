---
title: Document Builder Overview in Node.js
second_title: Aspose.Words for Node.js via .NET
articleTitle: Document Builder Overview
linktitle: Document Builder Overview
type: docs
description: "DocumentBuilder allows you to build dynamic documents from scratch or add new elements to existing ones using Node.js. DocumentBuilder provides methods to insert text, checkboxes, tables, images, and other content elements in Node.js."
weight: 30
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/document-builder-overview/
timestamp: 2025-07-09-10-05-05
---

[DocumentBuilder](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/) is a powerful class that associates with [Document](https://reference.aspose.com/words/nodejs-net/aspose.words/document/) and enables you to build dynamic documents from scratch or add new elements to an existing one.

[DocumentBuilder](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/) provides methods to insert text, checkboxes, ole objects, paragraphs, lists, tables, images, and other content elements. It allows you to specify fonts, paragraph or section formatting, and perform other operations.

## Document Builder or Aspose.Words DOM

[DocumentBuilder](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/) complements classes and methods available in the Aspose.Words Document Object Model (DOM) to simplify the most common document building tasks. That is, you can create and modify the content of documents both through the Aspose.Words DOM, which requires a good understanding of the tree structure, and using the DocumentBuilder. The `DocumentBuilder` is a "facade" for the complex **Document** structure that allows you to quickly and easily insert content and formatting.

Operations that are possible with [DocumentBuilder](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/) are also possible when using the classes of the Aspose.Words DOM directly. However, using Aspose.Words DOM classes directly usually requires more lines of code than using [DocumentBuilder](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/).

## Document Navigation

Document navigation is based on the concept of a virtual cursor, with which you can move to another location in the document using various **DocumentBuilder.moveToXXX** methods such as [moveToDocumentStart](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/moveToDocumentStart/) and [moveToField](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/moveToField/). This virtual cursor indicates where the text will be inserted when calling the methods [write](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/write/), [writeln](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/writeln/), [insertBreak](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertBreak/#breaktype), and others. See the following article "Navigation with Cursor" to learn more about the virtual cursor.

The following code example shows how to navigate to a bookmark:

{{< gist "aspose-words-gists" "410919c9c1056a587ed5f2a86f328e7a" "move-to-bookmark-end.js" >}}

## Document Building and Modifying

Aspose.Words API provides several classes that are responsible for formatting various elements of a document. Each of the classes encapsulates formatting properties related to a specific document element, such as text, paragraph, section, and others. For example, the [Font](https://reference.aspose.com/words/nodejs-net/aspose.words/font/) class represents character formatting properties, the [ParagraphFormat](https://reference.aspose.com/words/nodejs-net/aspose.words/paragraphformat/) class represents paragraph formatting properties, and so on. Objects of these classes are returned by the corresponding [DocumentBuilder](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/) properties, which have the same names as the classes. Therefore, you can access them and set the desired formatting during the document build.

You can also insert text, checkbox, ole object, images, bookmarks, form fields, and other document elements at the cursor position using the `Write` method or any of the **DocumentBuilder.insertXXX** methods, such as [insertField](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertField/), [insertHtml](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertHtml/#string), and similar methods.

Let's see how to create a simple document using the [DocumentBuilder](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/).

### Create a Document using DocumentBuilder

To start, you need to create a [DocumentBuilder](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/) and associate it with a [Document](https://reference.aspose.com/words/nodejs-net/aspose.words/document/) object. You create a new instance of [DocumentBuilder](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/) by calling its constructor and pass it to a [Document](https://reference.aspose.com/words/nodejs-net/aspose.words/document/) object for attachment to the builder.

To insert a text, pass the string of text you need to insert into the document to the [write](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/write/) method.

The following code example shows how to create a simple document using a document builder.

{{< gist "aspose-words-gists" "96e42cb4a611465927f8e7b1b3d546d3" "create-new-document.js" >}}

### Specify Document Formatting

The [font](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/font/) property defines text formatting. This object contains different font attributes (font name, font size, color, and so on). Some important font attributes are also represented by [DocumentBuilder](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/) properties to allow you to access them directly. These are the [Font.bold](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/bold/), [Font.italic](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/italic/), and [Font.underline](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/underline/) boolean properties.

The following code example shows how to insert a formatted text using [DocumentBuilder](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/):

{{< gist "aspose-words-gists" "410919c9c1056a587ed5f2a86f328e7a" "insert-paragraph.js" >}}

{{% alert color="primary" %}}

- [font](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/font/) specifies the character formatting that will be applied to all text inserted from the current position in the document onwards.
- [paragraphFormat](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/paragraphFormat/) specifies the paragraph formatting for the current and all paragraphs to be inserted.
- [pageSetup](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/pageSetup/) specifies the page and section properties for the current section and the entire section that will be inserted.
- [cellFormat](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/cellFormat/) and [rowFormat](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/rowFormat/) specify formatting properties that will be applied to table cells and rows from the current position in the document onwards.

In this situation, "current" means the position, paragraph, section, cell, or row in which the cursor is.

{{% /alert %}}

{{% alert color="primary" %}}

Note that the [font](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/font/), [paragraphFormat](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/paragraphFormat/), and [pageSetup](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/pageSetup/) properties are updated whenever you navigate to a different location in the document to reflect the formatting properties of this location.

{{% /alert %}}

------  

## FAQ

1. **Q:** How do I apply a license to Aspose.Words for Node.js?  
   **A:** Create a `License` object and call `setLicense` with the path to your `.lic` file before using any Aspose.Words classes. Example:  
   ```javascript
   const aw = require('@aspose/words');
   let license = new aw.License();
   license.setLicense("Aspose.Words.lic");
   ```

2. **Q:** How can I insert an image at the current cursor position?  
   **A:** Use `DocumentBuilder.insertImage` and provide the image file path or a stream. Example:  
   ```javascript
   let builder = new aw.DocumentBuilder(document);
   builder.insertImage("sample.png");
   ```

3. **Q:** What is the correct way to move the cursor to a bookmark before inserting content?  
   **A:** Call `moveToBookmark` with the bookmark name. After moving, any subsequent insertions occur at that location. Example:  
   ```javascript
   let builder = new aw.DocumentBuilder(document);
   builder.moveToBookmark("MyBookmark");
   builder.writeln("Text after the bookmark");
   ```

4. **Q:** How do I add a page break using DocumentBuilder?  
   **A:** Use `insertBreak` with `BreakType.PageBreak`. Example:  
   ```javascript
   let builder = new aw.DocumentBuilder(document);
   builder.insertBreak(aw.BreakType.PageBreak);
   ```

5. **Q:** Can I format text (font name, size, bold, color) while writing with DocumentBuilder?  
   **A:** Yes. Set properties on the `font` object of the builder before calling `write` or `writeln`. Example:  
   ```javascript
   let builder = new aw.DocumentBuilder(document);
   builder.font.name = "Arial";
   builder.font.size = 14;
   builder.font.bold = true;
   builder.font.color = "#0000FF"; // blue
   builder.writeln("Formatted text");
   ```