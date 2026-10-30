---
title: Working with Ranges in C#
second_title: Aspose.Words for .NET
articleTitle: Working with Ranges
linktitle: Working with Ranges
description: "Introduction to Range feature in Aspose.Words for .NET."
type: docs
weight: 130
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/working-with-ranges/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with ranges to manipulate spans of content.

{{% /alert %}}

{{% alert color="primary" %}}

In Aspose.Words, a Range is a “flat window” into an otherwise tree-like model of the document.

{{% /alert %}}

If you have worked with Microsoft Word Automation, you probably know that one of the main tools to examine and modify document content is the **Range** object. **Range** is like a "window" into the document content and formatting.

Aspose.Words also has the [Range](https://reference.aspose.com/words/net/aspose.words/range/) class and it is designed to look and act similarly to **Range** in Microsoft Word. Although **Range** cannot cover an arbitrary portion of a document and does not have a **Start** and **End**, you can access the range covered by any document node including the [Document](https://reference.aspose.com/words/net/aspose.words/document/) itself. In other words, each node has its own range. The **Range** object allows you to access and modify text, bookmarks and form fields within the range.

## Retrieve Plain Text

Use the [Text](https://reference.aspose.com/words/net/aspose.words/range/text/) property to retrieve plain, unformatted text of the range.

The following code example shows how to get a plain, unformatted text of a range:

{{< gist "aspose-words-gists" "9164e9c0658006e51db723b0742c12fc" "ranges-get-text.cs" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-.NET/blob/master/Examples/Data/Document.docx).

{{% /alert %}}

## Delete Text

Range allows the deletion of all characters of the range by calling [Delete](https://reference.aspose.com/words/net/aspose.words/range/delete/).

The following code example shows how to delete all characters of a range:

{{< gist "aspose-words-gists" "9164e9c0658006e51db723b0742c12fc" "ranges-delete-text.cs" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-.NET/blob/master/Examples/Data/Document.docx).

{{% /alert %}}

------

## FAQ

1. **Q:** How can I retrieve the plain text of a specific part of a document using a Range?  
   **A:** Obtain the node that represents the part you are interested in (e.g., a paragraph), then use its `Range.Text` property. The property returns the unformatted text contained in that range.  

2. **Q:** How do I delete a portion of text within a document with a Range?  
   **A:** Identify the node that encloses the text you want to remove and call `Delete()` on its `Range`. This clears all characters inside the range while keeping the node itself in the document tree.  

3. **Q:** How can I replace text inside a Range?  
   **A:** Use the `Replace` method of the `Range` class, providing the text to find and the replacement text. The operation works on the raw text of the range, preserving the original formatting of the surrounding nodes.  

   ```csharp
   Document doc = new Document("Input.docx");
   Range range = doc.Range; // whole document
   range.Replace("old value", "new value", new FindReplaceOptions(FindReplaceDirection.Forward));
   doc.Save("Replaced.docx");
   ```