---
title: Working with Hyperlinks in C#
second_title: Aspose.Words for .NET
articleTitle: Add or Modify Hyperlinks
linktitle: Add or Modify Hyperlinks
description: "How to add a hyperlink into your document in C# using Aspose.Words for .NET."
type: docs
weight: 50
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/working-with-hyperlinks/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with hyperlinks inside Word documents.

{{% /alert %}}

A hyperlink in Microsoft Word documents is the `HYPERLINK` field. In Aspose.Words, hyperlinks are implemented through the [FieldHyperlink](https://reference.aspose.com/words/net/aspose.words.fields/fieldhyperlink/) class.

## Insert a Hyperlink

Use the [InsertHyperlink](https://reference.aspose.com/words/net/aspose.words/documentbuilder/inserthyperlink/) method to insert a hyperlink into the document. This method accepts three parameters:

1. Text of the link to be displayed in the document
2. Link destination (URL or a name of a bookmark inside the document)
3. Boolean parameter that should be true if the `URL` is a name of a bookmark inside a document

The **InsertHyperlink** method always adds apostrophes at the beginning and end of the URL. 

{{% alert color="primary" %}}

Note that you need to specify font formatting for the hyperlink display text explicitly using the `Font` property.

{{% /alert %}}

The following code example shows how to insert a hyperlink into a document using [DocumentBuilder](https://reference.aspose.com/words/net/aspose.words/documentbuilder/):

{{< gist "aspose-words-gists" "0213851d47551e83af42233f4d075cf6" "insert-hyperlink.cs" >}}

## Replace or Modify Hyperlinks

Hyperlink in Microsoft Word documents is a field. A field in a Word document, as we said earlier, is a complex structure consisting of multiple nodes that include field start, field code, field separator, field result and field end. Fields can be nested, contain rich content and span multiple paragraphs or sections in a document.

To replace or modify hyperlinks, it is need to find the hyperlinks in the document and replace either their text, URLs, or both.

The following code example shows how to find all hyperlinks in Word document and changes their `URL` and display name:

{{< gist "aspose-words-gists" "0213851d47551e83af42233f4d075cf6" "replace-hyperlinks.cs" >}}

## Related APIs


- [FieldHyperlink](https://reference.aspose.com/words/net/aspose.words.fields/fieldhyperlink/)
- [DocumentBuilder.InsertHyperlink](https://reference.aspose.com/words/net/aspose.words/documentbuilder/inserthyperlink/)

## FAQ

1. **Q:** How do I insert a hyperlink that points to an external URL?  
   **A:** Use `DocumentBuilder.InsertHyperlink` with the display text, the full URL (e.g., `https://www.example.com`), and set the third parameter to `false`. After insertion, you can format the link text via `builder.Font` (e.g., set `builder.Font.Color = Color.Blue; builder.Font.Underline = Underline.Single;`).

2. **Q:** How can I create a hyperlink that points to a bookmark inside the same document?  
   **A:** Pass the bookmark name as the second argument to `InsertHyperlink` and set the third argument to `true`. The method will treat the second argument as a bookmark reference rather than an external URL.

3. **Q:** What is the recommended way to change the display text of an existing hyperlink?  
   **A:** Locate the `FieldHyperlink` object, access its `Result` node (which holds the displayed text), and replace the text with the new string. After updating, you may need to re‑apply font formatting if the style should differ.

4. **Q:** How can I modify the URL of a hyperlink that is already in the document?  
   **A:** Find the `FieldHyperlink` instance, then update its `Address` property (or `SubAddress` for a link to a bookmark) with the new value. Call `field.Update()` to refresh the field result so the change is reflected in the document.

5. **Q:** Is there a way to remove a hyperlink while keeping its display text?  
   **A:** Yes. Call `Unlink()` on the hyperlink field (for example `doc.Range.Fields[0].Unlink()`). It replaces the field with its current result, so the display text stays in the document as plain text.