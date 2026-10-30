---
title: Save a Document in Python
second_title: Aspose.Words for Python via .NET
articleTitle: Save a Document
linktitle: Save a Document
aliases: [/python/saving-a-document/]
type: docs
description: "Save a document in any supported format using Python."
keywords: "save a document python, save a document to file python, save a document to stream python, save a document Aspose python, save formats supported by Aspose.Words python"
weight: 20
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/save-a-document/
aliases: [/python/save-a-document/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}

*Purpose Summary. What is this page about?*

This page demonstrates how to use Aspose.Words for Python via .NET to save a Document, providing code examples for saving to a file, to a stream, and to PCL format, and explains the required methods and options.

{{% /alert %}}

Most of the tasks you need to perform with Aspose.Words involve saving a document. To save a document Aspose.Words provides the [save](https://reference.aspose.com/words/python-net/aspose.words/document/save/) method of the [Document](https://reference.aspose.com/words/python-net/aspose.words/document/) class. There are overloads that allow saving a document to a file or stream. The document can be saved in any save format supported by Aspose.Words. For the list of all supported save formats, see the [SaveFormat](https://reference.aspose.com/words/python-net/aspose.words/saveformat/) enumeration.

## Save to a File {#save-a-document-to-a-file}

Simply use the [save](https://reference.aspose.com/words/python-net/aspose.words/document/save/) method with a file name. Aspose.Words will determine the save format from the file extension that you specify.

The following code example shows how to load and save a document to a file:

{{< gist "aspose-words-gists" "1ea924a385a086092413b7fc5ea0f5e9" "load-and-save.py" >}}

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Python-via-.NET/blob/master/Examples/Data/Document.docx).

{{% /alert %}}

## Save to a Stream {#save-a-document-to-a-stream}

Pass a stream object to the [save](https://reference.aspose.com/words/python-net/aspose.words/document/save/) method. It's necessary to specify the save format explicitly when saving to a stream.

The following code example shows how to load and save a document to a stream:

{{< gist "aspose-words-gists" "1ea924a385a086092413b7fc5ea0f5e9" "load-and-save-to-stream.py" >}}

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Python-via-.NET/blob/master/Examples/Data/Document.docx).

{{% /alert %}}

## Send a Document to a Client Browser {#sending-a-document-to-a-client-browser}

To send a document to a client browser, save it to an in-memory stream and then write the bytes to your web framework's response. Use the `Content-Disposition` HTTP header to control how the document is presented to the user: `attachment` prompts a download, while `inline` lets the browser open the document directly, or hand it to the application associated with the file extension.

```python
import io
import aspose.words as aw

doc = aw.Document("Document.docx")

stream = io.BytesIO()
doc.save(stream, aw.SaveFormat.DOCX)
data = stream.getvalue()
```

Then return `data` from your web framework. For example, using Flask:

```python
from flask import Response

return Response(
    data,
    mimetype="application/vnd.openxmlformats-officedocument.wordprocessingml.document",
    headers={"Content-Disposition": "attachment; filename=Document.docx"})
```

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Python-via-.NET/blob/master/Examples/Data/Document.docx).

{{% /alert %}}

## Save to PCL {#save-a-document-to-pcl}

Aspose.Words supports saving a document into PCL (Printer Command Language). Aspose.Words can save documents into PCL 6 (PCL 6 Enhanced or PCL XL) format. The [PclSaveOptions](https://reference.aspose.com/words/python-net/aspose.words.saving/pclsaveoptions/) class can be used to specify additional options when saving a document into the PCL format.

The following code example shows how to save a document to PCL using save options:

{{< gist "aspose-words-gists" "1ea924a385a086092413b7fc5ea0f5e9" "rasterize-transformed-elements.py" >}}

## FAQ

1. **Q:** How does Aspose.Words decide which format to use when I call `document.save("output.docx")`?  
   **A:** When saving to a file, Aspose.Words infers the format from the file extension. The extension “.docx” maps to `SaveFormat.DOCX`, “.pdf” to `SaveFormat.PDF`, and so on.

2. **Q:** Do I need to specify a `SaveFormat` when saving a document to a stream?  
   **A:** Yes. When the destination is a stream, the format cannot be inferred, so you must pass the desired `SaveFormat` (e.g., `SaveFormat.PDF`) as the second argument to `save`.

3. **Q:** Can I save a document directly to a memory stream for further processing?  
   **A:** Absolutely. Create an `io.BytesIO` stream, call `doc.save(stream, aw.SaveFormat.PDF)`, and then use the stream’s contents as needed, such as sending it over a network or attaching it to an email.

4. **Q:** What options are available when saving a document to PCL?  
   **A:** Use the `PclSaveOptions` class to control PCL‑specific settings, such as rasterizing transformed elements (`rasterize_transformed_elements`), the fallback font (`fallback_font_name`), or printer fonts (`add_printer_font`). Pass an instance of this class to `document.save(stream, pcl_save_options)`.

5. **Q:** Is it possible to change the font size of the entire document while saving?  
   **A:** Font size changes must be applied to the document’s content before calling `save`. You can iterate through all `Run` nodes, modify their `Font.size` property, and then save the document in the desired format.
