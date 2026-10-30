---
title: Aspose.Words for Docling plugin
second_title: Aspose.Words for Docling plugin
articleTitle: Aspose.Words for Docling plugin
linktitle: Aspose.Words for Docling plugin
description: "Use the Aspose.Words for Docling plugin to prepare documents for AI processing."
type: docs
weight: 40
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/docling-plugin/
aliases: [/python/docling-plugin/]
timestamp: 2026-02-05-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page describes the Aspose.Words for Docling plugin, including its features, installation steps, API usage, licensing requirements, and how to run its tests.
{{% /alert %}}

**Aspose.Words for Docling** is a free plugin for [Docling](https://github.com/docling-project/docling) based on [Aspose.Words for Python via .NET](https://products.aspose.com/words/python-net/) commercial library.  
The plugin is designed for parsing multiple document formats and converting them into Docling Documents suitable for AI processing.  
You can find the project source code in the [GitHub repository](https://github.com/aspose-words/Aspose.Words-for-Docling).  

## Features

Aspose.Words for Docling supports the following features:

- Convert `.doc`, `.rtf`, `.docx`, `.pdf`, `.html`, `.mhtml`, `.mobi`, `.azw3`, `.epub`, `.odt`, `.txt`, `.md` and `.xml` to [DoclingDocument](https://docling-project.github.io/docling/concepts/docling_document/).
- Support all document components, including paragraphs, tables, images, headers, and footers.

## Requirements

- [Docling](https://github.com/docling-project/docling) version 2.60.0 or higher.
- [Aspose.Words for Python via .NET](https://products.aspose.com/words/python-net/). This library is a [commercial product](https://purchase.aspose.com/buy/words/python).  
You'll need to obtain a valid license for Aspose.Words. The package will install this dependency, but you're responsible for complying with Aspose's licensing terms.

## How to Install Aspose.Words for Docling

To install Aspose.Words for Docling via pip, run the following:

```bash
pip install aspose-words-docling
```

## How to Use Aspose.Words for Docling

{{< highlight python >}}  
from aspose_words_docling import AsposeWordsConverter

aspose_converter = AsposeWordsConverter()
docling_document = aspose_converter.convert("test.doc")

md = docling_document.export_to_markdown()
print(md)
{{< /highlight >}}  

## Aspose.Words License

{{% alert color="primary" %}}

This package is licensed under the MIT License. However, it depends on Aspose.Words for Python via .NET library, which is proprietary, closed-source library.

You must obtain valid license for Aspose.Words for Python via .NET library. This repository does not include or distribute any proprietary components.

{{% /alert %}}

To activate your Aspose.Words for Python license, set the corresponding environment variable.  

Refer to the OS-specific instructions below:

**Unix-based (Linux/macOS):**
```
export ASPOSE_WORDS_LICENSE_PATH="/path/to/license/Aspose.Words.Python.NET.lic"
```

**Windows-based:**
```
set ASPOSE_WORDS_LICENSE_PATH=c:\path\to\license\Aspose.Words.Python.NET.lic
```

**Python API:**
{{< highlight python >}}  
from aspose_words_docling import LicenseManager
LicenseManager().apply_license("/path/to/license/Aspose.Words.Python.NET.lic")
{{< /highlight >}}  

## How to Run Tests

To run unit tests for **Aspose.Words for Docling**, follow these steps:

1. Navigate to the package directory. From the root of the repository, change into the package directory:
  ```bash
  cd /packages/aspose-words-docling/tests
  ```

2. Install test dependencies. Make sure `pytest` is installed:
  ```bash
  pip install pytest
  ```

3. Run all the tests using `pytest`:
  ```bash
  pytest
  ```

------  

## FAQ  

1. **Q:** Can an **Aspose.Total.NET** license be used with the Aspose.Words for Python via .NET library?  
   **A:** No. A license issued for a .NET product (e.g., `Aspose.Total.NET.lic`) is not valid for Aspose.Words for Python via .NET. Use an Aspose.Words for Python via .NET license (`Aspose.Words.Python.NET.lic`) or an Aspose.Total for Python via .NET license (`Aspose.Total.Python.NET.lic`). Using a .NET license results in a “license is not valid for this product” error.

2. **Q:** How do I apply the Aspose.Words license when using the Docling plugin in Python?  
   **A:** Set the environment variable `ASPOSE_WORDS_LICENSE_PATH` to the full path of your `Aspose.Words.Python.NET.lic` file, or call the helper class provided by the plugin:  

   ```python
   from aspose_words_docling import LicenseManager
   LicenseManager().apply_license("/path/to/license/Aspose.Words.Python.NET.lic")
   ```  

   This must be done before any conversion operation is executed.

3. **Q:** Why do I receive the error **“RuntimeError: Proxy error(InvalidOperationException): The license is not valid for this product.”**?  
   **A:** This error occurs when the license file was issued for another product, for example, a .NET license such as `Aspose.Total.NET.lic`. A modified or corrupted license file gives the “Invalid license signature” error instead, and a missing file gives “Cannot find license”. Verify that you are using a valid **Aspose.Words for Python via .NET** or **Aspose.Total for Python via .NET** license and that the path is correct.

4. **Q:** Does the Docling plugin require a separate license from the Aspose.Words library?  
   **A:** No. The plugin itself is open‑source and distributed under the MIT license. It only depends on the commercial **Aspose.Words for Python via .NET** library, so you need a license only for that library, not for the plugin.
