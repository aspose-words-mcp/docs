---
title: Insert and Append Documents
second_title: Aspose.Words for Node.js via .NET
articleTitle: Insert and Append Documents
linktitle: Insert and Append Documents
description: "Combine documents into one: insert or append a document into a new or existing one using find and replace, merge field, bookmark, or simply at the document end in Node.js."
type: docs
weight: 80
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/insert-and-append-documents/
timestamp: 2025-07-09-10-05-05
---

Sometimes it is required to combine several documents into one. You can do this manually or you can use Aspose.Words insert or append feature.

The insert operation allows you to insert the content of previously created documents into a new or existing one.

In turn, the append feature allows you to add a document only at the end of another document.

This article explains how to insert or append a document to another one in different ways and describes the common properties that you can apply while inserting or appending documents.

## Insert a Document

As mentioned above, in Aspose.Words a document is represented as a tree of nodes, and the operation of inserting one document into another is copying nodes from the first document tree to the second one.

You can insert documents in a variety of locations in different ways. For example, you can insert a document through a replace operation, a merge field during a merge operation, or via a bookmark.

You can also use the [insertDocument](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertDocument/) or [insertDocumentInline](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertDocumentInline/) method, which is similar to inserting a document in Microsoft Word, to insert a whole document at the current cursor position without any previous importing.

The following code example shows how to insert a document using the **insertDocument** method:

{{< gist "aspose-words-gists" "814f45acd0c15059a9680cb661081d0f" "insert-document-with-builder.js" >}}

The following code example shows how to insert a document using the **insertDocumentInline** method:

{{< gist "aspose-words-gists" "814f45acd0c15059a9680cb661081d0f" "insert-document-inline-with-builder.js" >}}

The following subsections describe the options during which you can insert one document into another.

### Insert a Document at Bookmark

You can import a text file into a document and insert it right after a bookmark that you have defined in the document. To do this, create a bookmarked paragraph where you want the document to be inserted.

The following coding example shows how to insert the contents of one document to a bookmark in another document:

{{< gist "aspose-words-gists" "814f45acd0c15059a9680cb661081d0f" "insert-document-at-bookmark.js" >}}

{{% alert color="primary" %}}

Note that the bookmark should not enclose multiple paragraphs or text that you want them to appear in your final resulting document.

{{% /alert %}}

## Append a Document

You may have a use case where you need to include additional pages from a document to the end of an existing document. To do this, you just need to call the [appendDocument](https://reference.aspose.com/words/nodejs-net/aspose.words/document/appendDocument/) method to add a document to the end of another one.

{{% alert color="primary" %}}

Note that [appendChild](https://reference.aspose.com/words/nodejs-net/aspose.words/compositenode/appendChild/) is a node level method within a document. For example, you can create a paragraph, set formatting properties, and then append it as a child to the body using the [appendChild](https://reference.aspose.com/words/nodejs-net/aspose.words/compositenode/appendChild/) method.

{{% /alert %}}

The following code example shows how to append a document to the end of another document:

{{< gist "aspose-words-gists" "814f45acd0c15059a9680cb661081d0f" "keep-source-formatting.js" >}}

## Import and Insert Nodes Manually

Aspose.Words allows you to insert and append documents automatically without any previous importing requirements. However, if you need to insert or append a specific node of your document, such as a section or a paragraph, then first you need to import this node manually.

When you need to insert or append one section or paragraph to another, you essentially need to import the nodes of the first document node tree into the second one using the [importNode](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbase/importNode/) method. After importing your nodes, you need to use the [insertAfter](https://reference.aspose.com/words/nodejs-net/aspose.words/compositenode/insertAfter/) / [insertBefore](https://reference.aspose.com/words/nodejs-net/aspose.words/compositenode/insertBefore/) method to insert a new node after/before the reference node. This allows you to customize the inserting process by importing nodes from a document and inserting it at given positions.

You can also use the [appendChild](https://reference.aspose.com/words/nodejs-net/aspose.words/compositenode/appendChild/) method to add a new specified node to the end of the list of child nodes, for example, if you want to append content at the paragraph level instead of at the section level.

The following code example shows how to manually import nodes and insert them after a specific node using the [insertAfter](https://reference.aspose.com/words/nodejs-net/aspose.words/compositenode/insertAfter/) method:

{{< gist "aspose-words-gists" "814f45acd0c15059a9680cb661081d0f" "insert-document-as-nodes.js" >}}

{{% alert color="primary" %}}

The import creates a new node that is a copy of the original node and suitable for insertion into the destination document.

{{% /alert %}}

Content is imported into the destination document section by section, which means that settings, such as page setup and headers or footers, are preserved during import. It is also useful to note that you can define formatting settings when you insert or append a document to specify how two documents are joined together.

## Common Properties for Insert and Append Documents

Both [insertDocument](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertDocument/) and [appendDocument](https://reference.aspose.com/words/nodejs-net/aspose.words/document/appendDocument/) methods accept [ImportFormatMode](https://reference.aspose.com/words/nodejs-net/aspose.words/importformatmode/) and [ImportFormatOptions](https://reference.aspose.com/words/nodejs-net/aspose.words/importformatoptions/) as input parameters. The [ImportFormatMode](https://reference.aspose.com/words/nodejs-net/aspose.words/importformatmode/) allows you to control how document formatting is merged when you import content from one document into another by selecting different format modes such as [UseDestinationStyles](https://reference.aspose.com/words/nodejs-net/aspose.words/importformatmode/), [KeepSourceFormatting](https://reference.aspose.com/words/nodejs-net/aspose.words/importformatmode/), and [KeepDifferentStyles](https://reference.aspose.com/words/nodejs-net/aspose.words/importformatmode/). The [ImportFormatOptions](https://reference.aspose.com/words/nodejs-net/aspose.words/importformatoptions/) allows you to select different import options such as [ignoreHeaderFooter](https://reference.aspose.com/words/nodejs-net/aspose.words/importformatoptions/ignoreHeaderFooter/), [ignoreTextBoxes](https://reference.aspose.com/words/nodejs-net/aspose.words/importformatoptions/ignoreTextBoxes/), [keepSourceNumbering](https://reference.aspose.com/words/nodejs-net/aspose.words/importformatoptions/keepSourceNumbering/), [mergePastedLists](https://reference.aspose.com/words/nodejs-net/aspose.words/importformatoptions/mergePastedLists/), and [smartStyleBehavior](https://reference.aspose.com/words/nodejs-net/aspose.words/importformatoptions/smartStyleBehavior/).

Aspose.Words allows you to adjust the visualization of a resulting document when two documents are added together in an insert or append operation by using the [Section](https://reference.aspose.com/words/nodejs-net/aspose.words/section/) and [PageSetup](https://reference.aspose.com/words/nodejs-net/aspose.words/pagesetup/). The [pageSetup](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/pageSetup/) property contains all the attributes of a section such as [sectionStart](https://reference.aspose.com/words/nodejs-net/aspose.words/pagesetup/sectionStart/), [restartPageNumbering](https://reference.aspose.com/words/nodejs-net/aspose.words/pagesetup/restartPageNumbering/), [pageStartingNumber](https://reference.aspose.com/words/nodejs-net/aspose.words/pagesetup/pageStartingNumber/), [orientation](https://reference.aspose.com/words/nodejs-net/aspose.words/pagesetup/orientation/), and others. The most common use case is to set the [sectionStart](https://reference.aspose.com/words/nodejs-net/aspose.words/pagesetup/sectionStart/) property to define if the added content will appear on the same page or split into a new one.

{{% alert color="primary" %}}

Note that the [Section](https://reference.aspose.com/words/nodejs-net/aspose.words/section/) and [PageSetup](https://reference.aspose.com/words/nodejs-net/aspose.words/pagesetup/) do not control how two documents are inserted/appended together. They only allow you to change the appearance of your result document.

{{% /alert %}}

The following code example shows how to append one document to another while keeping the content from splitting across two pages:

{{< gist "aspose-words-gists" "814f45acd0c15059a9680cb661081d0f" "different-page-setup.js" >}}

------ 

## FAQ

1. Q: How do I insert an entire document at the current cursor position using DocumentBuilder in Node.js?  
   A: Load the source document with `new Document("Source.docx")`, create a `DocumentBuilder` for the destination document, and call `builder.insertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting)`. This inserts the source as a separate section while preserving its original formatting.

2. Q: How can I insert a document at a specific bookmark?  
   A: First move the builder to the bookmark with `builder.moveToBookmark("MyBookmark")`, then call `builder.insertDocument(sourceDoc, ImportFormatMode.UseDestinationStyles)` (or another mode). The source content will be placed immediately after the bookmark.

3. Q: What is the difference between `insertDocument` and `insertDocumentInline`?  
   A: `insertDocument` inserts the source document as a distinct section, keeping its own page setup and headers/footers. `insertDocumentInline` merges the source content into the current paragraph as inline nodes, which can be useful when you want the inserted text to flow with surrounding content.

4. Q: How do I append a document to the end of another document?  
   A: Load both documents and call `destinationDoc.appendDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting)`. The source document is added after the last node of the destination document.

5. Q: How can I control formatting when inserting or appending documents?  
   A: Use `ImportFormatMode` to choose how styles are handled (`UseDestinationStyles`, `KeepSourceFormatting`, `KeepDifferentStyles`). Additionally, create an `ImportFormatOptions` object to set options such as `ignoreHeaderFooter`, `ignoreTextBoxes`, `keepSourceNumbering`, `mergePastedLists`, and `smartStyleBehavior`, then pass it to the insert/append method. This lets you fine‑tune which elements are kept or ignored during the operation.