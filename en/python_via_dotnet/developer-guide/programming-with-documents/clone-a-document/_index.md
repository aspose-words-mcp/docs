---
title: Clone a Document in Python
second_title: Aspose.Words for Python via .NET
articleTitle: Clone a Document
linktitle: Clone a Document
type: docs
description: "Clone a document to get its identical copy using Python. When creating a copy, nodes and properties of the original document are cloned."
weight: 70
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/clone-a-document/
aliases: [/python/clone-a-document/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page describes how to create a deep copy of a Word document using Aspose.Words for Python via .NET, including use cases and a code example demonstrating document and node cloning.
{{% /alert %}}

Cloning a document is the process of creating an identical copy of an original document, which can improve performance and save you from potential memory leaks.

This article will explain the main use cases of cloning a document and how to create a document clone using Aspose.Words.

## Operations with Cloning Documents

The clone operation allows you to make the process of creating documents faster as you will not need to load and parse a document from a file every time.

After creating a clone of your document, you will be able to edit it and perform different operations on it, for example, compare it with the original document, append or insert it into another document. You can also modify cloned elements or their content before inserting them into another document.

## Creating a Document Clone

Aspose.Words allows you to clone a document using the [clone](https://reference.aspose.com/words/python-net/aspose.words/document/clone/) method that performs a deep copy of the document and returns it. In other words, it will get a full copy of the DOM. The `clone` method speeds up the documents generation, and you only need one line of code to get a copy of your document.

Cloning produces a new document with the same contents as the original, but with a unique copy of each of the original document's [nodes](https://reference.aspose.com/words/python-net/aspose.words/node/). You can also apply the clone operation to a document node by using the node [clone](https://reference.aspose.com/words/python-net/aspose.words/document/clone/) method, which allows you to duplicate composite document nodes with and without their child nodes.

{{% alert color="primary" %}}

Note that when applying the cloning method all document properties will be cloned.

{{% /alert %}}

The following code example shows how to clone a document and create a duplicate of a section in that document:

{{< gist "aspose-words-gists" "e510e7e7b1fd08239ef592aa440675c1" "clone-document.py" >}}

## Related APIs

- [Document.clone()](https://reference.aspose.com/words/python-net/aspose.words/document/clone/)
- [Node.clone(is_clone_children)](https://reference.aspose.com/words/python-net/aspose.words/node/clone/)  

## FAQ

1. **Q:** How do I clone an entire document in Python?  
   **A:** Use the `Document.clone()` method and cast the result to a `Document` with `.as_document()`. This creates a deep copy of the whole document, including all nodes, styles, and settings. Example: `clone = original_doc.clone().as_document()`.

2. **Q:** Can I clone only a specific node, such as a section or paragraph?  
   **A:** Yes. Every node that derives from `Node` has a `clone()` method. For example, to duplicate a section: `new_section = existing_section.clone()` and then add it to the document with `doc.sections.add(new_section)`.

3. **Q:** Does cloning copy headers, footers, and other document-wide properties?  
   **A:** The clone operation is a deep copy, so all headers, footers, styles, custom properties, and document settings are duplicated in the cloned document. After cloning you can modify any of these independently of the original.

4. **Q:** Is the cloned document independent of the original?  
   **A:** Yes. After cloning, the original and the clone have separate object graphs. Changes made to one (e.g., adding sections, editing text) do not affect the other.

5. **Q:** How can I use a cloned document for comparison with the original?  
   **A:** After cloning, you can pass both `Document` instances to the `Document.compare()` method. The original remains unchanged, while the clone can be edited before or after the comparison. Example: `original_doc.compare(clone, "Author", datetime.now())`.
