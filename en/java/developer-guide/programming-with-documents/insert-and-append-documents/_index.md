---
title: Insert and Append Documents in Java
second_title: Aspose.Words for Java
articleTitle: Insert and Append Documents
linktitle: Insert and Append Documents
description: "Combine documents into one: insert or append a document into a new or existing one using find and replace, merge field, bookmark, or simply at the document end in Java."
type: docs
weight: 80
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/insert-and-append-documents/
aliases: 
 - /java/joining-and-appending-documents/
 - /java/join-and-append-documents/
 - /java/appending-documents/
 - /java/how-to-insert-a-document-into-another-document/
 - /java/joining-documents/
 - /java/joining-documents-with-different-formatting/
 - /java/joining-documents-with-headers-and-footers/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to insert and append documents programmatically.

{{% /alert %}}

Sometimes it is required to combine several documents into one. You can do this manually or you can use Aspose.Words insert or append feature.

The insert operation allows you to insert the content of previously created documents into a new or existing one.

In turn, the append feature allows you to add a document only at the end of another document.

This article explains how to insert or append a document to another one in different ways and describes the common properties that you can apply while inserting or appending documents.

## Insert a Document {#insert-a-document}

As mentioned above, in Aspose.Words a document is represented as a tree of nodes, and the operation of inserting one document into another is copying nodes from the first document tree to the second one.

You can insert documents in a variety of locations in different ways. For example, you can insert a document through a replace operation, a merge field during a merge operation, or via a bookmark.

You can also use the [insertDocument()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertDocument-com.aspose.words.Document-int) or the [insertDocumentInline()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertDocumentInline-com.aspose.words.Document-int-com.aspose.words.ImportFormatOptions) method, which is similar to inserting a document in Microsoft Word, to insert a whole document at the current cursor position without any previous importing.

The following code example shows how to insert a document using the **insertDocument()** method:

{{< gist "aspose-words-gists" "6e5c8fd2462c6d7ba26da4d9f66ff77b" "insert-document-with-builder.java" >}}

The following code example shows how to insert a document using the **insertDocumentInline()** method:

{{< gist "aspose-words-gists" "6e5c8fd2462c6d7ba26da4d9f66ff77b" "insert-document-inline-with-builder.java" >}}

The following subsections describe the options during which you can insert one document into another.

### Insert a Document During Find and Replace Operation {#insert-a-document-during-find-and-replace-operation}

You can insert documents while performing find and replace operations. For example, a document can contain paragraphs with the text `INTRODUCTION` and `CONCLUSION`. But in the final document, you need to replace those paragraphs with the content obtained from another external document. To achieve that, you will need to create a handler for the replace event.

The following code example shows how to create a handler for the replacing event to use it later in the inserting process:

{{< gist "aspose-words-gists" "6e5c8fd2462c6d7ba26da4d9f66ff77b" "insert-document-at-replace-handler.java" >}}

The following code example shows how insert content of one document into another during a find and replace operation:

{{< gist "aspose-words-gists" "6e5c8fd2462c6d7ba26da4d9f66ff77b" "insert-document-at-replace.java" >}}

### Insert a Document During Mail Merge Operation {#insert-a-document-during-mail-merge-operation}

You can insert a document into a merge field during a Mail Merge operation. For example, a Mail Merge template can contain a merge field such as `Summary`. But in the final document, you need to insert content obtained from another external document into this merge field. To achieve that, you will need to create a handler for the merge event.

The following code example shows how to create a handler for the merging event to use it later in the inserting process:

{{< gist "aspose-words-gists" "6e5c8fd2462c6d7ba26da4d9f66ff77b" "insert-document-at-mail-merge-handler.java" >}}

The following code example shows how to insert a document into the merge field using the created handler:

{{< gist "aspose-words-gists" "6e5c8fd2462c6d7ba26da4d9f66ff77b" "insert-document-at-mail-merge.java" >}}

### Insert a Document at Bookmark {#insert-a-document-at-bookmark}

You can import a text file into a document and insert it right after a bookmark that you have defined in the document. To do this, create a bookmarked paragraph where you want the document to be inserted.

The following coding example shows how to insert the contents of one document to a bookmark in another document:

{{< gist "aspose-words-gists" "6e5c8fd2462c6d7ba26da4d9f66ff77b" "insert-document-at-bookmark.java" >}}

{{% alert color="primary" %}}

Note that the bookmark should not enclose multiple paragraphs or text that you want them to appear in your final resulting document.

{{% /alert %}}

## Append a Document {#append-a-document}

You may have a use case where you need to include additional pages from a document to the end of an existing document. To do this, you just need to call the [appendDocument()](https://reference.aspose.com/words/java/com.aspose.words/document/#appendDocument-com.aspose.words.Document-int) method to add a document to the end of another one.

{{% alert color="primary" %}}

Note that [appendChild()](https://reference.aspose.com/words/java/com.aspose.words/document/#appendChild-com.aspose.words.Node) is a node level method within a document. For example, you can create a paragraph, set formatting properties, and then append it as a child to the body using the **appendChild()** method.

{{% /alert %}}

The following code example shows how to append a document to the end of another document:

{{< gist "aspose-words-gists" "6e5c8fd2462c6d7ba26da4d9f66ff77b" "keep-source-formatting.java" >}}

## Import and Insert Nodes Manually {#import-and-insert-nodes-manually}

Aspose.Words allows you to insert and append documents automatically without any previous importing requirements. However, if you need to insert or append a specific node of your document, such as a section or a paragraph, then first you need to import this node manually.

When you need to insert or append one section or paragraph to another, you essentially need to import the nodes of the first document node tree into the second one using the [importNode()](https://reference.aspose.com/words/java/com.aspose.words/document/#importNode-com.aspose.words.Node-boolean) method. After importing your nodes, you need to use the [InsertAfter](https://reference.aspose.com/words/java/com.aspose.words/document/#insertBefore-com.aspose.words.Node-com.aspose.words.Node) / [insertBefore()](https://reference.aspose.com/words/java/com.aspose.words/compositenode/#insertBefore-com.aspose.words.Node-com.aspose.words.Node) method to insert a new node after/before the reference node. This allows you to customize the inserting process by importing nodes from a document and inserting it at given positions.

You can also use the [appendChild()](https://reference.aspose.com/words/java/com.aspose.words/document/#appendChild-com.aspose.words.Node) method to add a new specified node to the end of the list of child nodes, for example, if you want to append content at the paragraph level instead of at the section level.

The following code example shows how to manually import nodes and insert them after a specific node using the **insertAfter()** method:

{{< gist "aspose-words-gists" "6e5c8fd2462c6d7ba26da4d9f66ff77b" "insert-document-as-nodes.java" >}}

{{% alert color="primary" %}}

The import creates a new node that is a copy of the original node and suitable for insertion into the destination document.

{{% /alert %}}

Content is imported into the destination document section by section, which means that settings, such as page setup and headers or footers, are preserved during import. It is also useful to note that you can define formatting settings when you insert or append a document to specify how two documents are joined together.

## Common Properties for Insert and Append Documents {#common-properties-for-insert-and-append-documents}

Both [insertDocument()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertDocument-com.aspose.words.Document-int) and [appendDocument()](https://reference.aspose.com/words/java/com.aspose.words/document/#appendDocument-com.aspose.words.Document-int) methods accept [ImportFormatMode](https://reference.aspose.com/words/java/com.aspose.words/importformatmode/) and [ImportFormatOptions](https://reference.aspose.com/words/java/com.aspose.words/importformatoptions/) as input parameters. The **ImportFormatMode** allows you to control how document formatting is merged when you import content from one document into another by selecting different format modes such as [USE_DESTINATION_STYLES](https://reference.aspose.com/words/java/com.aspose.words/importformatmode/#USE-DESTINATION-STYLES), [KEEP_SOURCE_FORMATTING](https://reference.aspose.com/words/java/com.aspose.words/importformatmode/#KEEP-SOURCE-FORMATTING), and [KEEP_DIFFERENT_STYLES](https://reference.aspose.com/words/java/com.aspose.words/importformatmode/#KEEP-DIFFERENT-STYLES). The **ImportFormatOptions** allows you to select different import options such as [getIgnoreHeaderFooter()](https://reference.aspose.com/words/java/com.aspose.words/importformatoptions/#getIgnoreHeaderFooter), [getIgnoreTextBoxes()](https://reference.aspose.com/words/java/com.aspose.words/importformatoptions/#getIgnoreTextBoxes), [getKeepSourceNumbering()](https://reference.aspose.com/words/java/com.aspose.words/importformatoptions/#getKeepSourceNumbering), [getMergePastedLists()](https://reference.aspose.com/words/java/com.aspose.words/importformatoptions/#getMergePastedLists), and [getSmartStyleBehavior()](https://reference.aspose.com/words/java/com.aspose.words/importformatoptions/#getSmartStyleBehavior).

Aspose.Words allows you to adjust the visualization of a resulting document when two documents are added together in an insert or append operation by using the [Section](https://reference.aspose.com/words/java/com.aspose.words/section/) and [PageSetup](https://reference.aspose.com/words/java/com.aspose.words/pagesetup/) properties. The **PageSetup** property contains all the attributes of a section such as [getSectionStart()](https://reference.aspose.com/words/java/com.aspose.words/pagesetup/#getSectionStart), [getRestartPageNumbering()](https://reference.aspose.com/words/java/com.aspose.words/pagesetup/#getRestartPageNumbering), [getPageStartingNumber()](https://reference.aspose.com/words/java/com.aspose.words/pagesetup/#getPageStartingNumber), [getOrientation()](https://reference.aspose.com/words/java/com.aspose.words/pagesetup/#getOrientation), and others. The most common use case is to set the **SectionStart** property to define if the added content will appear on the same page or split into a new one.

{{% alert color="primary" %}}

Note that the **Section** and **PageSetup** properties do not control how two documents are inserted/appended together. They only allow you to change the appearance of your result document.

{{% /alert %}}

The following code example shows how to append one document to another while keeping the content from splitting across two pages:

{{< gist "aspose-words-gists" "6e5c8fd2462c6d7ba26da4d9f66ff77b" "different-page-setup.java" >}}

## FAQ

1. **Q:** How can I insert a whole document at the current cursor position using `DocumentBuilder`?  
   **A:** Create a `DocumentBuilder` for the destination document, load the source document, and call `builder.insertDocument(sourceDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);`. The `ImportFormatMode` determines how styles are merged.

2. **Q:** How do I insert a document while performing a find‑and‑replace operation?  
   **A:** Implement the `IReplacingCallback` interface. In the `replacing` method, create a `DocumentBuilder` for the document (`new DocumentBuilder((Document) args.getMatchNode().getDocument())`), move it to the match with `builder.moveTo(args.getMatchNode())`, and call `builder.insertDocument(sourceDoc, ImportFormatMode.USE_DESTINATION_STYLES);`. Register the callback with `findReplaceOptions.setReplacingCallback(myCallback);` before calling `document.getRange().replace(pattern, "", findReplaceOptions);`.

3. **Q:** How can I insert a document into a merge field during a Mail Merge?  
   **A:** Implement `IFieldMergingCallback`. In the `fieldMerging` method, move the `DocumentBuilder` to the merge field using `builder.moveToMergeField(fieldName);` and call `builder.insertDocument(sourceDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);`. Assign the callback to `document.getMailMerge().setFieldMergingCallback(myCallback);` before calling `mailMerge.execute(...);`.

4. **Q:** What is the correct way to insert a document at a bookmark?  
   **A:** Use `DocumentBuilder.moveToBookmark("MyBookmark");` to position the builder at the bookmark, then call `builder.insertDocument(sourceDoc, ImportFormatMode.KEEP_DIFFERENT_STYLES);`. The inserted content will appear immediately after the bookmark.

5. **Q:** How can I control formatting when inserting or appending documents?  
   **A:** Pass an `ImportFormatMode` (e.g., `USE_DESTINATION_STYLES`, `KEEP_SOURCE_FORMATTING`, `KEEP_DIFFERENT_STYLES`) to `insertDocument` or `appendDocument`. For finer control, create an `ImportFormatOptions` object and set properties such as `setIgnoreHeaderFooter(true)`, `setIgnoreTextBoxes(true)`, or `setMergePastedLists(true)`, then supply it to the method overload that accepts `ImportFormatOptions`. You can also adjust the resulting layout by modifying the destination section's `PageSetup` (e.g., `section.getPageSetup().setSectionStart(SectionStart.NEW_PAGE);`).