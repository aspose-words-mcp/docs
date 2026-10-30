---
title: Hello, World!
second_title: Simple example how to use Aspose.Words for .NET
articleTitle: Hello, World!
linktitle: Hello World
description: "Create, edit and save your first document in any supported format using Aspose.Words for .NET to experience its simplicity and power in C#."
type: docs
weight: 20
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/hello-world/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page describes a basic Hello World example.

{{% /alert %}}

A "Hello, World!" code is often the first simple example to write uisng "Aspose.Words for .NET", and it can also be used as a sanity test to ensure the software intended to compile or run source code is correctly installed.

"Aspose.Words for .NET" C# library gives developers direct access to create, modify, merge, convert, compare Word and Web documents. PDF, DOCX, DOC, RTF, ODT, EPUB, HTML and many other file formats are [supported](/words/net/supported-document-formats/).

Below code snippet follows these steps:

1. Create a new empty [Document](https://reference.aspose.com/words/net/aspose.words/document)
1. Initialize a [DocumentBuilder](https://reference.aspose.com/words/net/aspose.words/documentbuilder/) class
1. Insert text to the document start using simple [Write](https://reference.aspose.com/words/net/aspose.words/documentbuilder/write/) method
1. Open an existing [Document](https://reference.aspose.com/words/net/aspose.words/document/document/) from a file. Automatically detects the file format
1. [Append](https://reference.aspose.com/words/net/aspose.words/document/appenddocument/) document "A" to the and of the document "B"
1. [Save](https://reference.aspose.com/words/net/aspose.words/document/save/) the output as PDF

The following code snippet is a "Hello, World!" example to exhibit working of "Aspose.Words for .NET" API:

{{< gist "aspose-words-gists" "542a463e1857480986d18ec296ed43d5" "hello-world.cs" >}}

------

## FAQ

1. **Q:** How do I apply my Aspose.Words license to avoid evaluation restrictions?  
   **A:** Download the license file (`.lic`) from your Aspose account and set it before using any API calls:  

   ```csharp
   License license = new License();
   license.SetLicense("Aspose.Words.lic");
   ```  

   This must be done once per application start‑up. Without a license, Aspose.Words runs in evaluation mode: it adds an evaluation watermark and limits the document size.

2. **Q:** Which file formats can I save the document to directly from the Hello World example?  
   **A:** The `Document.Save` method supports all formats listed on the **Supported Document Formats** page, including PDF, DOCX, DOC, RTF, ODT, EPUB, HTML, and more. Specify the desired format by using the appropriate file extension, e.g., `document.Save("output.pdf");`.

3. **Q:** How can I convert the created document to PDF without changing the code that writes the text?  
   **A:** After building the document, simply call `Save` with a `.pdf` extension:  

   ```csharp
   Document doc = new Document();
   DocumentBuilder builder = new DocumentBuilder(doc);
   builder.Write("Hello, World!");
   doc.Save("HelloWorld.pdf");
   ```  

   Aspose.Words automatically performs the conversion.

4. **Q:** Why do I get a “File not found” error when the example tries to open an existing document?  
   **A:** The `Document` constructor expects a valid path. Ensure the file exists relative to the application's working directory or provide an absolute path. You can also verify the path with `System.IO.File.Exists(path)` before loading. If the file is embedded as a resource, load it via a stream instead of a file path.