---
title: Save a Document in C++
second_title: Aspose.Words for C++
articleTitle: Save a Document
linktitle: Save a Document
type: docs
description: "Save a document in any supported format using C++."
keywords: "save a document c++, save a document to file c++, save a document to stream c++, save a document Aspose C++, save formats supported by Aspose.Words C++"
weight: 20
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/save-a-document/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to save a document in different formats using Aspose.Words.

{{% /alert %}}

Most of the tasks you need to perform with Aspose.Words involve saving a document. To save a document Aspose.Words provides the [Save](https://reference.aspose.com/words/cpp/aspose.words/document/save/) method of the [Document](https://reference.aspose.com/words/cpp/aspose.words/document/) class. The document can be saved in any save format supported by Aspose.Words. For the list of all supported save formats, see the [SaveFormat](https://reference.aspose.com/words/cpp/aspose.words/saveformat/) enumeration.

## Save to a File {#save-a-document-to-a-file}

Simply use the [Save](https://reference.aspose.com/words/cpp/aspose.words/document/save/) method with a file name. Aspose.Words will determine the save format from the file extension that you specify.

The following code example shows how to load and save a document to a file:

{{< gist "aspose-words-gists" "5938495d10e6b402f1e42ce5a45926ca" "load-and-save.h" >}}

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-C/blob/master/Examples/Data/Document.doc).

{{% /alert %}}

## Save to a Stream {#save-a-document-to-a-stream}

Pass a stream object to the [Save](https://reference.aspose.com/words/cpp/aspose.words/document/save/) method. It's necessary to specify the save format explicitly when saving to a stream.

The following code example shows how to load and save a document to a stream:

{{< gist "aspose-words-gists" "5938495d10e6b402f1e42ce5a45926ca" "load-and-save-to-stream.h" >}}

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-C/blob/master/Examples/Data/Document.docx).

{{% /alert %}}

## Save to PCL {#save-a-document-to-pcl}

Aspose.Words supports saving a document into PCL (Printer Command Language). Aspose.Words can save documents into PCL 6 (PCL 6 Enhanced or PCL XL) format. The `PclSaveOptions` class can be used to specify additional options when saving a document into the PCL format.

The following code example shows how to save a document to PCL using save options:

{{< gist "aspose-words-gists" "5938495d10e6b402f1e42ce5a45926ca" "rasterize-transformed-elements.h" >}}

------ 

## FAQ

1. **Q:** How does Aspose.Words determine the file format when I call `Document::Save(u"output.pdf")`?  
   **A:** The library infers the format from the file extension. In the example, the `.pdf` extension tells Aspose.Words to save the document as PDF. If you need to override this behavior, pass a `SaveOptions` object with the desired `SaveFormat`.

2. **Q:** Can I save a document directly to a memory stream in C++?  
   **A:** Yes. Create a `System::IO::MemoryStream`, then call `doc->Save(memoryStream, SaveFormat::Pdf)` (or any other format). After saving, you can retrieve the byte array with `memoryStream->ToArray()`.

3. **Q:** Which file formats are supported for saving with Aspose.Words for C++?  
   **A:** All formats listed in the `SaveFormat` enumeration are supported, including DOC, DOCX, PDF, XPS, PCL, HTML, EPUB, and many others. Refer to the [SaveFormat](https://reference.aspose.com/words/cpp/aspose.words/saveformat/) documentation for the complete list.

4. **Q:** How can I customize the PDF output when saving a document?  
   **A:** Use `PdfSaveOptions` to control PDF-specific settings such as compliance level, image compression, font embedding, and document security. Pass the configured options to `Document::Save(stream, pdfOptions)`.

5. **Q:** Is it possible to obtain the saved document as a byte array without writing to disk?  
   **A:** Yes. Save the document to a `MemoryStream` as described above, then call `memoryStream->ToArray()` to get the raw bytes, which you can send over a network, store in a database, or process further.