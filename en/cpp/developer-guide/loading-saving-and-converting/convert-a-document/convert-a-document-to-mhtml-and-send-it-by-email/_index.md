---
title: Convert a Document to MHTML and Send It by Email
second_title: Aspose.Words for C++
articleTitle: Convert a Document to MHTML and Send It by Email
linktitle: Convert a Document to MHTML and Send It by Email
description: "Convert a document from almost any format to the MHTML format and send the result document by e-mail."
type: docs
weight: 30
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/convert-a-document-to-mhtml-and-send-it-by-email/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page describes how to convert a document to MHTML and send it via email, demonstrating both conversion settings and SMTP workflow integration.

{{% /alert %}}

Aspose.Words can convert any document to the MHTML (Web Archive) format. This makes it convenient to use Aspose.Words and `Aspose.Email` together. You can load a predefined document in any supported format, such as DOC, OOXML, or RTF, into Aspose.Words, fill it with data, save the resulting document as MHTML, and then send it by e-mail using `Aspose.Email`.

The following code example shows how to convert any document to MHTML and send it by email:

{{< gist "aspose-words-gists" "ce77d307265430a38e77b141bb06f775" "docx-to-mhtml.h" >}}

------ 

## FAQ

1. **Q: Which input document formats can be converted to MHTML?**  
   **A:** Aspose.Words for C++ supports all formats that the library can load, including DOC, DOCX, OOXML, RTF, HTML, EPUB, and many others. Any document that can be opened with `Aspose::Words::Document` can be saved as MHTML using the `Save` method with `SaveFormat::Mhtml`.

2. **Q: Do I need a separate license for Aspose.Email when sending the MHTML file?**  
   **A:** Yes. Converting the document to MHTML uses Aspose.Words, while sending the e‑mail uses Aspose.Email. Both products require their own valid licenses. Apply each license before using the corresponding API (e.g., `Aspose::Words::License` for Words and `Aspose::Email::License` for Email).

3. **Q: How can I set the e‑mail subject, body, and attachment programmatically in C++?**  
   **A:** Use the `Aspose::Email::MailMessage` class. Create a `MailMessage`, set `Subject` and `Body`, then add the MHTML file as an attachment with `msg->get_Attachments()->Add`. Finally, send the message with `SmtpClient`. Example:

   ```cpp
   System::SharedPtr<Aspose::Email::MailMessage> msg = System::MakeObject<Aspose::Email::MailMessage>();
   msg->set_Subject(u"Converted Document");
   msg->set_Body(u"Please find the converted MHTML document attached.");
   msg->get_Attachments()->Add(System::MakeObject<Aspose::Email::Attachment>(u"document.mhtml"));
   ```

4. **Q: Can I embed images in the MHTML output so they appear correctly in the e‑mail?**  
   **A:** Yes. When saving to MHTML, Aspose.Words embeds all images in the file as separate MIME parts, referenced by `Content-Location` (or by `cid:` URLs when `HtmlSaveOptions::set_ExportCidUrlsForMhtmlResources(true)` is set). The resulting MHTML can be opened directly in a browser or attached to an e‑mail without additional handling.

5. **Q: What should I do if the conversion throws an “Unsupported file format” exception?**  
   **A:** Verify that the source file's extension matches a format supported by Aspose.Words and that the file is not corrupted. If the file is in a proprietary format, consider converting it to a supported format (e.g., DOCX) before loading it with Aspose.Words. Also ensure you are using the latest version of the library, as newer releases add support for additional formats.