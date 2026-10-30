---
title: Supported Features on Document Save
second_title: Aspise.Words for Python via .NET
articleTitle: Supported Features on Document Save
linktitle: Supported Features on Document Save
description: "Save your document to any supported format using Python. Convert and export a document of any size."
type: docs
weight: 30
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/supported-features-on-document-save/
aliases: 
  - /python/document-saving-overview/
  - /python/supported-features-on-document-save/
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}

*Purpose Summary. What is this page about?*

This page describes the document‑save capabilities of Aspose.Words for Python via .NET, including supported format conversions and options for saving large documents with limited memory by specifying a temporary folder.

{{% /alert %}}

Aspose.Words has some of the most advanced conversion support of the common word processing formats.

All imported documents loaded into Aspose.Words can be exported to any other supported format. Features are preserved during conversion. Conversion between formats gives some of the best conversion results out there. 

Aspose.Words can convert a document of any size as long as there is sufficient working memory to complete the operation. Additionally, if available memory is low, you can choose a temporary folder during export to DOC or DOCX format. This allows resources during conversion to be stored temporarily to disk. These files are removed after conversion is complete. This allows large documents to be saved even when there is not much memory available.

{{% alert color="primary" %}}

For more information and a description of the features available for the different formats, see the [Supported Features on Document Save](/words/net/supported-features-on-document-save/) section in the Aspose.Words for .NET documentation.

{{% /alert %}}

------ 

## FAQ

1. **Q:** How can I specify a temporary folder for saving large documents when memory is low?  
   **A:** Use the `SaveOptions` object for the target format and set its `temp_folder` property to a folder path with sufficient disk space. Aspose.Words will write intermediate data there and delete the files after the save operation completes.

2. **Q:** Which document formats preserve most of the original features during a save operation?  
   **A:** Formats such as DOCX, DOC, RTF, HTML, and PDF retain the majority of layout, styling, and content features. The exact preservation level varies per format; for example, PDF keeps visual fidelity, while HTML preserves structural elements.

3. **Q:** Can I save a very large document (e.g., hundreds of megabytes) on a machine with limited RAM?  
   **A:** Yes. By configuring a temporary folder as described above, Aspose.Words off‑loads part of the processing to disk, allowing large documents to be saved even when available RAM is limited.

4. **Q:** Does saving to PDF keep embedded fonts and images intact?  
   **A:** When saving to PDF, Aspose.Words embeds fonts and images by default, ensuring that the visual appearance of the document remains consistent across different viewers.

5. **Q:** Are there any format‑specific limitations I should be aware of when saving?  
   **A:** Some formats have inherent restrictions (e.g., plain text loses formatting, and older DOC files may not support newer Word features). Review the format‑specific documentation for details on what features are supported or may be downgraded.