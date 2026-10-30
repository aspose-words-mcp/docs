---
title: Insert and Append Documents
second_title: Aspose.Words for Python via .NET
articleTitle: Insert and Append Documents
linktitle: Insert and Append Documents
description: "Combine documents into one: insert or append a document into a new or existing one using find and replace, merge field, bookmark, or simply at the document end in Python."
type: docs
weight: 80
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/insert-and-append-documents/
aliases:
 - /python/join-and-append-documents/
 - /python/insert-and-append-documents/
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page demonstrates how to use Aspose.Words for Python via .NET to insert or append one document into another, covering methods such as `insert_document`, `insert_document_inline`, `append_document`, and manual node import with options for formatting and placement.
{{% /alert %}}

Sometimes it is required to combine several documents into one. You can do this manually or you can use Aspose.Words insert or append feature.

The insert operation allows you to insert the content of previously created documents into a new or existing one.

In turn, the append feature allows you to add a document only at the end of another document.

This article explains how to insert or append a document to another one in different ways and describes the common properties that you can apply while inserting or appending documents.

## Insert a Document {#insert-a-document}

As mentioned above, in Aspose.Words a document is represented as a tree of nodes, and the operation of inserting one document into another is copying nodes from the first document tree to the second one.

You can insert documents in a variety of locations in different ways. For example, you can insert a document through a replace operation, a merge field during a merge operation, or via a bookmark.

You can also use the [insert_document](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_document/) or the [insert_document_inline](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_document_inline/#document_importformatmode_importformatoptions) method, which is similar to inserting a document in Microsoft Word, to insert a whole document at the current cursor position without any previous importing.

The following code example shows how to insert a document using the **insert_document** method:

{{< gist "aspose-words-gists" "ffc2b4de06eabf9183a3ed2aa34e939d" "insert-document-with-builder.py" >}}

The following code example shows how to insert a document using the **insert_document_inline** method:

{{< gist "aspose-words-gists" "ffc2b4de06eabf9183a3ed2aa34e939d" "insert-document-inline-with-builder.py" >}}

The following subsections describe the options during which you can insert one document into another.

### Insert a Document During Find and Replace Operation {#insert-a-document-during-find-and-replace-operation}

You can insert documents while performing find and replace operations. For example, a document can contain paragraphs with the text [INTRODUCTION] and [CONCLUSION]. But in the final document, you need to replace those paragraphs with the content obtained from another external document. To achieve that, you will need to create a handler for the replace event.

The following code example shows how to create a handler for the replacing event to use it later in the inserting process:

{{< gist "aspose-words-gists" "ef9ae5b20ccd67e59f9d49d32b534661" "insert-document-at-replace-handler.py" >}}

The following code example shows how insert content of one document into another during a find and replace operation:

{{< gist "aspose-words-gists" "ef9ae5b20ccd67e59f9d49d32b534661" "insert-document-at-replace.py" >}}

### Insert a Document During Mail Merge Operation {#insert-a-document-during-mail-merge-operation}

You can insert a document into a merge field during a Mail Merge operation. For example, a Mail Merge template can contain a merge field such as [Summary]. But in the final document, you need to insert content obtained from another external document into this merge field. To achieve that, you will need to create a handler for the merge event.

The following code example shows how to create a handler for the merging event to use it later in the inserting process:

{{< gist "aspose-words-gists" "ef9ae5b20ccd67e59f9d49d32b534661" "insert-document-at-mail-merge-handler.py" >}}

The following code example shows how to insert a document into the merge field using the created handler:

{{< gist "aspose-words-gists" "ef9ae5b20ccd67e59f9d49d32b534661" "insert-document-at-mail-merge.py" >}}

### Insert a Document at Bookmark {#insert-a-document-at-bookmark}

You can import a text file into a document and insert it right after a bookmark that you have defined in the document. To do this, create a bookmarked paragraph where you want the document to be inserted.

The following coding example shows how to insert the contents of one document to a bookmark in another document:

{{< gist "aspose-words-gists" "ffc2b4de06eabf9183a3ed2aa34e939d" "insert-document-at-bookmark.py" >}}

{{% alert color="primary" %}}

Note that the bookmark should not enclose multiple paragraphs or text that you want them to appear in your final resulting document.

{{% /alert %}}

## Append a Document {#append-a-document}

You may have a use case where you need to include additional pages from a document to the end of an existing document. To do this, you just need to call the [append_document](https://reference.aspose.com/words/python-net/aspose.words/document/append_document/) method to add a document to the end of another one.

{{% alert color="primary" %}}

Note that [append_child](https://reference.aspose.com/words/python-net/aspose.words/compositenode/append_child/) is a node level method within a document. For example, you can create a paragraph, set formatting properties, and then append it as a child to the body using the **append_child** method.

{{% /alert %}}

The following code example shows how to append a document to the end of another document:

{{< gist "aspose-words-gists" "ffc2b4de06eabf9183a3ed2aa34e939d" "keep-source-formatting.py" >}}

## Import and Insert Nodes Manually {#import-and-insert-nodes-manually}

Aspose.Words allows you to insert and append documents automatically without any previous importing requirements. However, if you need to insert or append a specific node of your document, such as a section or a paragraph, then first you need to import this node manually.

When you need to insert or append one section or paragraph to another, you essentially need to import the nodes of the first document node tree into the second one using the [import_node](https://reference.aspose.com/words/python-net/aspose.words/documentbase/import_node/) method. After importing your nodes, you need to use the [insert_after](https://reference.aspose.com/words/python-net/aspose.words/compositenode/insert_after/) / [insert_before](https://reference.aspose.com/words/python-net/aspose.words/compositenode/insert_before/) method to insert a new node after/before the reference node. This allows you to customize the inserting process by importing nodes from a document and inserting it at given positions.

You can also use the [append_child](https://reference.aspose.com/words/python-net/aspose.words/compositenode/append_child/) method to add a new specified node to the end of the list of child nodes, for example, if you want to append content at the paragraph level instead of at the section level.

The following code example shows how to manually import nodes and insert them after a specific node using the **insert_after** method:

{{< gist "aspose-words-gists" "ffc2b4de06eabf9183a3ed2aa34e939d" "insert-document-as-nodes.py" >}}

{{% alert color="primary" %}}

The import creates a new node that is a copy of the original node and suitable for insertion into the destination document.

{{% /alert %}}

Content is imported into the destination document section by section, which means that settings, such as page setup and headers or footers, are preserved during import. It is also useful to note that you can define formatting settings when you insert or append a document to specify how two documents are joined together.

## Common Properties for Insert and Append Documents {#common-properties-for-insert-and-append-documents}

Both [insert_document](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_document/) and [append_document](https://reference.aspose.com/words/python-net/aspose.words/document/append_document/) methods accept [ImportFormatMode](https://reference.aspose.com/words/python-net/aspose.words/importformatmode/) and [ImportFormatOptions](https://reference.aspose.com/words/python-net/aspose.words/importformatoptions/) as input parameters. The **ImportFormatMode** allows you to control how document formatting is merged when you import content from one document into another by selecting different format modes such as [USE_DESTINATION_STYLES](https://reference.aspose.com/words/python-net/aspose.words/importformatmode/#use_destination_styles), [KEEP_SOURCE_FORMATTING](https://reference.aspose.com/words/python-net/aspose.words/importformatmode/#keep_source_formatting), and [KEEP_DIFFERENT_STYLES](https://reference.aspose.com/words/python-net/aspose.words/importformatmode/#keep_different_styles). The **ImportFormatOptions** allows you to select different import options such as [ignore_header_footer](https://reference.aspose.com/words/python-net/aspose.words/importformatoptions/ignore_header_footer/), [ignore_text_boxes](https://reference.aspose.com/words/python-net/aspose.words/importformatoptions/ignore_text_boxes/), [keep_source_numbering](https://reference.aspose.com/words/python-net/aspose.words/importformatoptions/keep_source_numbering/), [merge_pasted_lists](https://reference.aspose.com/words/python-net/aspose.words/importformatoptions/merge_pasted_lists/), and [smart_style_behavior](https://reference.aspose.com/words/python-net/aspose.words/importformatoptions/smart_style_behavior/).

Aspose.Words allows you to adjust the visualization of a resulting document when two documents are added together in an insert or append operation by using the [Section](https://reference.aspose.com/words/python-net/aspose.words/section/) and [PageSetup](https://reference.aspose.com/words/python-net/aspose.words/pagesetup/) properties. The **PageSetup** property contains all the attributes of a section such as [section_start](https://reference.aspose.com/words/python-net/aspose.words/pagesetup/section_start/), [restart_page_numbering](https://reference.aspose.com/words/python-net/aspose.words/pagesetup/restart_page_numbering/), [page_starting_number](https://reference.aspose.com/words/python-net/aspose.words/pagesetup/page_starting_number/), [orientation](https://reference.aspose.com/words/python-net/aspose.words/pagesetup/orientation/), and others. The most common use case is to set the **SectionStart** property to define if the added content will appear on the same page or split into a new one.

{{% alert color="primary" %}}

Note that the **Section** and **PageSetup** properties do not control how two documents are inserted/appended together. They only allow you to change the appearance of your result document.

{{% /alert %}}

The following code example shows how to append one document to another while keeping the content from splitting across two pages:

{{< gist "aspose-words-gists" "ffc2b4de06eabf9183a3ed2aa34e939d" "different-page-setup.py" >}} 

## FAQ

1. **Q:** How can I change the font size of the inserted content when using `insert_document`?  
   **A:** After inserting the document, locate the inserted nodes (e.g., paragraphs) and modify their `font.size` property. You can retrieve the inserted range by storing the builder's current position before the call and then iterating over the nodes that follow.

2. **Q:** Does `insert_document_inline` preserve headers and footers from the source document?  
   **A:** No. `insert_document_inline` inserts the content of the source document inline at the cursor position, as if you copied all content and pasted it in Word. Sections, headers, and footers of the source document are not imported; use `Document.append_document` to add the source sections with their headers and footers.

3. **Q:** How can I insert a document at a specific bookmark without the bookmark's surrounding text being affected?  
   **A:** Place the bookmark in an empty paragraph, move the builder to the bookmark, and then call `insert_document`. The inserted content will be placed after the bookmark's position. Ensure the bookmark does not enclose other paragraphs, otherwise those paragraphs will be moved together with the inserted content.

4. **Q:** What ImportFormatMode should I use to keep the source document's list numbering when appending?  
   **A:** Use `ImportFormatMode.KEEP_SOURCE_FORMATTING` together with `ImportFormatOptions.keep_source_numbering = True`. This combination preserves the original list styles and numbering from the source document.

5. **Q:** Can I append only a single section from another document?  
   **A:** Yes. Import the desired section with `document.import_node(section, True)` and then call `dst.append_child(imported_section)`. This allows you to append a specific part of a document without merging the entire file.