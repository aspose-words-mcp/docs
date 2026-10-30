---
title: Working with Hyperlinks
second_title: Aspose.Words for Python via .NET
articleTitle: Add or Modify Hyperlinks
linktitle: Add or Modify Hyperlinks
description: "Add, replace, or modify a hyperlink in a document using Python."
type: docs
weight: 50
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/working-with-hyperlinks/
aliases:
- /python/working-with-hyperlinks-and-html/
- /python-net/working-with-hyperlinks-and-html/
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}

*Purpose Summary. What is this page about?*

This page demonstrates how to insert, replace, and modify hyperlink fields in Word documents using Aspose.Words for Python via .NET, with code examples using `DocumentBuilder.insert_hyperlink` and the `FieldHyperlink` class. It also explains how to apply font formatting to hyperlinks and how to locate and update existing hyperlink nodes.

{{% /alert %}}

A hyperlink in Microsoft Word documents is the `HYPERLINK` field. In Aspose.Words, hyperlinks are implemented through the [FieldHyperlink](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldhyperlink/) class.

## Insert a Hyperlink

Use the [insert_hyperlink](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_hyperlink/) method to insert a hyperlink into the document. This method accepts three parameters:

1. Text of the link to be displayed in the document
2. Link destination (URL or a name of a bookmark inside the document)
3. Boolean parameter that should be true if the `URL` is a name of a bookmark inside a document

The **insert_hyperlink** method always adds apostrophes at the beginning and end of the URL.

{{% alert color="primary" %}}

Note that you need to specify font formatting for the hyperlink display text explicitly using the `Font` property.

{{% /alert %}}

The following code example shows how to insert a hyperlink into a document using [DocumentBuilder](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/):

{{< gist "aspose-words-gists" "0a77287e9106956f00f83347b104d40b" "insert-hyperlink.py" >}}

## Replace or Modify Hyperlinks

Hyperlink in Microsoft Word documents is a field. A field in a Word document, as we said earlier, is a complex structure consisting of multiple nodes that include field start, field code, field separator, field result and field end. Fields can be nested, contain rich content and span multiple paragraphs or sections in a document.

To replace or modify hyperlinks, it is need to find the hyperlinks in the document and replace either their text, URLs, or both.

The following code example shows how to find all hyperlinks in Word document and changes their `URL` and display name:

{{< gist "aspose-words-gists" "0a77287e9106956f00f83347b104d40b" "replace-hyperlinks.py" >}}

## Related APIs

- [FieldHyperlink](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldhyperlink/)
- [DocumentBuilder.insert_hyperlink](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_hyperlink/)  

## FAQ

1. **Q:** How can I insert a hyperlink that points to a bookmark inside the same document?  
   **A:** Pass the bookmark name as the second argument to `insert_hyperlink` and set the third argument (`is_bookmark`) to `True`. Example:  

   ```python
   builder.insert_hyperlink("Go to Intro", "IntroBookmark", True)
   ```

2. **Q:** How do I change the display text of an existing hyperlink without altering its URL?  
   **A:** Locate the `FieldHyperlink` node, modify its `result` property (the displayed text), and then update the document.  

   ```python
   for field in doc.range.fields:
       if field.type == aw.fields.FieldType.FIELD_HYPERLINK:
           field.as_field_hyperlink().result = "New Display Text"
   ```

3. **Q:** Is it possible to remove a hyperlink while keeping the link text?  
   **A:** Yes. Replace the `FieldHyperlink` with a plain `Run` node that contains the same text. Remove the field start, separator, and end nodes, then insert a `Run` with the original result text.

4. **Q:** How can I apply custom font formatting (e.g., color, underline) to a hyperlink?  
   **A:** Set the builder’s `font` properties before calling `insert_hyperlink`; formatting set afterwards applies only to text inserted later. Call `builder.font.clear_formatting()` after the hyperlink.  

   ```python
   builder.font.color = aspose.pydrawing.Color.blue
   builder.font.underline = aw.Underline.SINGLE
   builder.insert_hyperlink("Aspose", "https://www.aspose.com", False)
   builder.font.clear_formatting()
   ```

5. **Q:** Can I retrieve a list of all hyperlink URLs in a document?  
   **A:** Iterate through all `FieldHyperlink` nodes and read their `address` property.  

   ```python
   urls = []
   for field in doc.range.fields:
       if field.type == aw.fields.FieldType.FIELD_HYPERLINK:
           urls.append(field.as_field_hyperlink().address)
   ```