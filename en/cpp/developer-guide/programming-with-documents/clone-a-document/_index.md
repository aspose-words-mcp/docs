---
title: Clone a Document in C++
second_title: Aspose.Words for C++
articleTitle: Clone a Document
linktitle: Clone a Document
type: docs
description: "Clone a document to get its identical copy using C++. When creating a copy, nodes and properties of the original document are cloned."
weight: 70
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/clone-a-document/
aliases: [/cpp/clone-and-combine-documents/]
timestamp: 2024-01-27-14-07-04
---

Cloning a document is the process of creating an identical copy of an original document, which can improve performance and save you from potential memory leaks.

This article will explain the main use cases of cloning a document and how to create a document clone using Aspose.Words.

## Operations with Cloning Documents

The clone operation allows you to make the process of creating documents faster as you will not need to load and parse a document from a file every time.

After creating a clone of your document, you will be able to edit it and perform different operations on it, for example, compare it with the original document, append or insert it into another document. You can also modify cloned elements or their content before inserting them into another document.

## Creating a Document Clone

Aspose.Words allows you to clone a document using the [Clone](https://reference.aspose.com/words/cpp/aspose.words/document/clone/) method that performs a deep copy of the document and returns it. In other words, it will get a full copy of the DOM. The `Clone` method speeds up the documents generation, and you only need one line of code to get a copy of your document.

Cloning produces a new document with the same contents as the original, but with a unique copy of each of the original document's [nodes](https://reference.aspose.com/words/cpp/aspose.words/node/). You can also apply the clone operation to a document node by using the node [Clone](https://reference.aspose.com/words/cpp/aspose.words/node/clone/) method, which allows you to duplicate composite document nodes with and without their child nodes.

{{% alert color="primary" %}}

Note that when applying the cloning method all document properties will be cloned.

{{% /alert %}}

The following code example shows how to clone a document and create a duplicate of a section in that document:
{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Document-CloningDocument-CloningDocument.cpp" >}}

------

## FAQ


1. **Q:** Does `Document::Clone()` copy all document settings such as page layout, styles, and custom properties?  
   **A:** Yes. `Clone()` performs a deep copy of the entire document object model, which includes page setup, styles, custom document properties, headers/footers, and any other settings present in the original document.

2. **Q:** Can I clone only a part of a document, for example a single section or a paragraph?  
   **A:** Yes. You can clone individual nodes using the `Node::Clone(bool)` method. Retrieve the node you want (e.g., a `Section` or `Paragraph`) and call `Clone(true)` on it to obtain an independent copy that can be inserted elsewhere.

3. **Q:** Is the cloned document independent of the original, so changes to one do not affect the other?  
   **A:** Yes. The clone is a separate `Document` instance with its own copy of all nodes. Modifying the clone will not impact the original document and vice versa.

4. **Q:** How does cloning affect memory usage, and are there any best‑practice tips?  
   **A:** Cloning creates a full copy of the document in memory, which increases memory consumption proportionally to the document size. Use cloning when reusing a template multiple times; otherwise, consider loading the document from disk each time to minimize memory usage.
