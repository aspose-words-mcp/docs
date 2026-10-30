---
title: Working with Hyperlinks
second_title: Aspose.Words for Node.js via .NET
articleTitle: Add or Modify Hyperlinks
linktitle: Add or Modify Hyperlinks
description: "Add, replace, or modify a hyperlink in a document using Node.js."
type: docs
weight: 50
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/working-with-hyperlinks/
timestamp: 2025-07-09-10-05-05
---

A hyperlink in Microsoft Word documents is the `HYPERLINK` field. In Aspose.Words, hyperlinks are implemented through the [FieldHyperlink](https://reference.aspose.com/words/nodejs-net/aspose.words.fields/fieldhyperlink/) class.

## Inserting a Hyperlink

Use the [insertHyperlink](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/inserthyperlink/) method to insert a hyperlink into the document. This method accepts three parameters:

1. Text of the link to be displayed in the document
2. Link destination (URL or a name of a bookmark inside the document)
3. Boolean parameter that should be true if the `URL` is a name of a bookmark inside a document

The **insertHyperlink** method always adds apostrophes at the beginning and end of the URL.

{{% alert color="primary" %}}

Note that you need to specify font formatting for the hyperlink display text explicitly using the `Font` property.

{{% /alert %}}

The following code example shows how to insert a hyperlink into a document using [DocumentBuilder](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/):

{{< gist "aspose-words-gists" "9b6efb87f331ae61c0100e106c9c1738" "insert-hyperlink.js" >}}

## Replace or Modify Hyperlinks

Hyperlink in Microsoft Word documents is a field. A field in a Word document is a complex structure consisting of multiple nodes that include field start, field code, field separator, field result and field end. Fields can be nested, contain rich content and span multiple paragraphs or sections in a document.

To replace or modify hyperlinks, it is need to find the hyperlinks in the document and replace either their text, URLs, or both.

The following code example shows how to find all hyperlinks in Word document and changes their `URL` and display name:

{{< gist "aspose-words-gists" "9b6efb87f331ae61c0100e106c9c1738" "replace-hyperlinks.js" >}}
