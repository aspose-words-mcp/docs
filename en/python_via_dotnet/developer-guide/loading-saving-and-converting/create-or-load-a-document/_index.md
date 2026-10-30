---
title: Create or Load a Document in Python
second_title: Aspose.Words for Python via .NET
articleTitle: Create or Load a Document
linktitle: Create or Load a Document
type: docs
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/create-or-load-a-document/
aliases:
 - /python/creating-or-loading-a-document/
 - /python/create-or-load-a-document/
description: "Create a blank document or to load it from a file or stream using Python."
keywords: "create a document python, load a document python, create a blank document python, load a document from file python, load a document from stream python, create a document Aspose python, load a document Aspose python, load formats supported by Aspose.Words python"
weight: 10
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}

*Purpose Summary. What is this page about?*

This page shows how to create a new blank document and how to load an existing document from a file or a stream using Aspose.Words for Python via .NET, with code examples for the `Document` and `DocumentBuilder` classes.

{{% /alert %}}

Almost any task that you want to perform with Aspose.Words involves loading a document. The `Document` class represents a document loaded into memory. The document has several overloaded constructors allowing you to create a blank document or to load it from a file or stream. The document can be loaded in any load format supported by Aspose.Words. For the list of all supported load formats, see the [LoadFormat](https://reference.aspose.com/words/python-net/aspose.words/loadformat/) enumeration.

## Create a New Document {#create-a-new-document}

We will call the [Document](https://reference.aspose.com/words/python-net/aspose.words/document/) constructor without parameters to create a new blank document. If you want to generate a document programmatically, the simplest way is to use the [DocumentBuilder](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/) class to add document contents.

The following code example shows how to create a document using the document builder:

{{< gist "aspose-words-gists" "59e45f5041ff6b356c5165164c019a76" "create-new-document.py" >}}

{{% alert color="primary" %}}

Note the default values:

- A blank document contains one section with default parameters, one empty paragraph, some document styles. Actually this document is the same as the result of creating the “New document” in Microsoft Word.
- The document paper size is [PaperSize.LETTER](https://reference.aspose.com/words/python-net/aspose.words/papersize/#letter).**Letter**.

{{% /alert %}}

## Load a Document {#load-a-document}

To load an existing document in any of the [LoadFormat](https://reference.aspose.com/words/python-net/aspose.words/loadformat/) formats, pass the file name or the stream into one of the Document constructors. The format of the loaded document is automatically determined by its extension.

### Load from a File {#load-from-a-file}

Pass a file name as string to the Document constructor to open an existing document from a file.

The following code example shows how to open a document from a file:

{{< gist "aspose-words-gists" "59e45f5041ff6b356c5165164c019a76" "open-document.py" >}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Python-via-.NET/blob/master/Examples/Data/Document.docx).

### Load from a Stream {#load-from-a-stream}

To open a document from a stream, simply pass a stream object that contains the document into the Document constructor.

The following code example shows how to open a document from a stream:

{{< gist "aspose-words-gists" "59e45f5041ff6b356c5165164c019a76" "open-from-stream.py" >}}

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Python-via-.NET/blob/master/Examples/Data/Document.docx).

{{% /alert %}} 

## FAQ

1. **Q:** How do I create a completely blank Word document?  
   **A:** Instantiate the `Document` class without any arguments. The resulting document contains a single empty section and paragraph, which matches the “New document” created by Microsoft Word. Example:  
   ```python
   doc = aw.Document()
   ```

2. **Q:** How can I load an existing document from a file path?  
   **A:** Pass the full file name (including extension) to the `Document` constructor. Aspose.Words automatically detects the format based on the extension. Example:  
   ```python
   doc = aw.Document("C:/Docs/Report.docx")
   ```

3. **Q:** What is the correct way to load a document from a memory stream?  
   **A:** Create a stream (e.g., `io.FileIO`) that contains the document bytes and give that stream to the `Document` constructor. Example:  
   ```python
   stream = io.FileIO(docs_base.my_dir + "Document.docx")

   doc = aw.Document(stream)
   stream.close()
   ```

4. **Q:** Can I use a .NET license file (e.g., `Aspose.Total.NET.lic`) with Aspose.Words for Python via .NET?  
   **A:** No. Licenses are product-specific: a .NET license is not valid for Aspose.Words for Python via .NET. Use an Aspose.Words for Python via .NET license (`Aspose.Words.Python.NET.lic`) or an Aspose.Total for Python via .NET license (`Aspose.Total.Python.NET.lic`). Example:  
   ```python
   license = aw.License()
   license.set_license("C:/Licenses/Aspose.Words.Python.NET.lic")
   ``` 
   After setting the license, all subsequent operations will be licensed for the Python environment.