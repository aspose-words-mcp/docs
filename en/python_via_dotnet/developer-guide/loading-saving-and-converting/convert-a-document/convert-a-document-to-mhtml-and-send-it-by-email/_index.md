---
title: Convert File to MHTML and Send It by Email
second_title: Aspose.Words for Python via .NET
articleTitle: Convert a Document to MHTML and Send It by Email
linktitle: Convert a Document to MHTML and Send It by Email
description: "Convert a document from almost any format to the MHTML format and send the result document by e-mail using Python."
type: docs
weight: 30
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/convert-a-document-to-mhtml-and-send-it-by-email/
timestamp: 2026-08-10-12-42-15
---

{{% alert color="grey" %}}

## Purpose Summary

This page describes how to convert a document to MHTML and send it via email, demonstrating both conversion settings and SMTP workflow integration.

{{% /alert %}}

Aspose.Words can convert any document to the MHTML (Web Archive) format. This makes it convenient to use Aspose.Words and `Aspose.Email` together. You can load a predefined document in any supported format, such as DOC, OOXML, or RTF, into Aspose.Words, fill it with data, save the resulting document as MHTML, and then send it by e‑mail using `Aspose.Email`.

The following code example shows how to convert any document to MHTML and send it by email:

{{< gist "aspose-words-gists" "16caeb7d9781fa093a70df33f232dbaa" "docx-to-mhtml.py" >}}

## FAQ

1. **Q:** Which document formats can be converted to MHTML with Aspose.Words?  
   **A:** Aspose.Words supports conversion from all formats it can load, including DOC, DOCX, RTF, HTML, ODT, and many others. Any of these can be saved directly as MHTML.

2. **Q:** Do I need a separate license for Aspose.Email when sending the MHTML file?  
   **A:** Yes. Aspose.Words handles the conversion, while Aspose.Email is a separate product used for SMTP operations. Both products require their own valid licenses.

3. **Q:** Can I customize the MIME type or encoding of the MHTML attachment?  
   **A:** After saving the document as MHTML (`document.save("output.mht", aw.SaveFormat.MHTML)`), you can create an `aspose.email.MailMessage`, set the `content_type` of the attachment, and specify the desired charset before sending.

4. **Q:** Is it possible to convert a document to MHTML without loading the entire file into memory?  
   **A:** No. Aspose.Words always loads the whole document into memory. You can still open the source document from a stream (`doc = aw.Document(stream)`) and save it directly to a stream in MHTML format, so no temporary files are needed.

5. **Q:** How can I ensure the generated MHTML preserves the original document’s fonts and images?  
   **A:** Images and CSS are embedded into the MHTML file automatically. Fonts are not exported by default: save with `aw.saving.HtmlSaveOptions(aw.SaveFormat.MHTML)` and set its `export_font_resources` property to `True` to embed them.