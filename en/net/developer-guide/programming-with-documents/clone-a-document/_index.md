---
title: Clone a Document in C#
second_title: Aspose.Words for .NET
articleTitle: Clone a Document
linktitle: Clone a Document
type: docs
description: "Clone a document to get its identical copy using C#. When creating a copy, nodes and properties of the original document are cloned."
weight: 70
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/clone-a-document/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page describes how to clone (deep-copy) a document or parts of it using Aspose.Words.

{{% /alert %}}

Cloning a document is the process of creating an identical copy of an original document, which can improve performance and save you from potential memory leaks.

This article will explain the main use cases of cloning a document and how to create a document clone using Aspose.Words.

## Operations with Cloning Documents

The clone operation allows you to make the process of creating documents faster as you will not need to load and parse a document from a file every time.

After creating a clone of your document, you will be able to edit it and perform different operations on it, for example, compare it with the original document, append or insert it into another document. You can also modify cloned elements or their content before inserting them into another document.

## Creating a Document Clone

Aspose.Words allows you to clone a document using the [Clone](https://reference.aspose.com/words/net/aspose.words/document/clone/) method that performs a deep copy of the document and returns it. In other words, it will get a full copy of the DOM. The `Clone` method speeds up the documents generation, and you only need one line of code to get a copy of your document.

Cloning produces a new document with the same contents as the original, but with a unique copy of each of the original document's [nodes](https://reference.aspose.com/words/net/aspose.words/node/). You can also apply the clone operation to a document node by using the node [Clone](https://reference.aspose.com/words/net/aspose.words/node/clone/) method, which allows you to duplicate composite document nodes with and without their child nodes.

{{% alert color="primary" %}}

Note that when applying the cloning method all document properties will be cloned.

{{% /alert %}}

The following code example shows how to clone a document and create a duplicate of a section in that document:

{{< gist "aspose-words-gists" "b2f62f736a2090163de7b0f221cf46d4" "clone-document.cs" >}}

## Related APIs

- [Document.Clone()](https://reference.aspose.com/words/net/aspose.words/document/clone/)
- [Node.Clone()](https://reference.aspose.com/words/net/aspose.words/node/clone/)
- [Node.Clone(Boolean)](https://reference.aspose.com/words/net/aspose.words/node/clone/)

## FAQ

1. **Q:** When should I use `Document.Clone` instead of loading the same file again?  
   **A:** Use `Clone` when you need a copy of a document that you already have in memory and want to modify it without affecting the original. Cloning avoids the overhead of reading the file from disk and parsing it again, which can improve performance in scenarios such as generating multiple similar documents.

2. **Q:** Does cloning copy all document settings such as page layout, styles, and custom properties?  
   **A:** Yes. The `Clone` method performs a deep copy of the entire document object model, including page setup, styles, custom document properties, headers/footers, and any other settings. The cloned document is an independent replica that can be saved or edited separately.

3. **Q:** How can I clone only a specific part of a document, like a section or a paragraph?  
   **A:** Individual nodes also implement a `Clone` method. Retrieve the node you want to duplicate (e.g., a `Section` or `Paragraph`) and call its `Clone(bool isCloneChildren)` method: `true` copies the node with all its child nodes, `false` copies only the node itself. The clone belongs to the same document; to insert a node into another document, use `ImportNode` on the target document instead.

4. **Q:** Will cloning a protected document retain its protection settings, and can I modify them after cloning?  
   **A:** The protection settings are part of the document's properties, so they are cloned as well. After cloning, you can change or remove protection on the cloned document using the `Protection` API without affecting the original document's protection.