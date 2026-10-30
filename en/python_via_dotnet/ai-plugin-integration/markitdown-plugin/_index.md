---
title: Aspose.Words for MarkItDown plugin
second_title: Aspose.Words for MarkItDown plugin
articleTitle: Aspose.Words for MarkItDown plugin
linktitle: Aspose.Words for MarkItDown plugin
description: "Use Aspose.Words for MarkItDown plugin for better document convertion"
type: docs
weight: 40
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/markitdown-plugin/
aliases: [/python/markitdown-plugin/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page describes the Aspose.Words for MarkItDown plugin, including its features, installation steps, usage via CLI and Python API, licensing requirements, and how to run its tests.
{{% /alert %}}

**Aspose.Words for MarkItDown** is a free plugin for [MarkItDown](https://github.com/microsoft/markitdown) based on [Aspose.Words for Python via .NET](https://products.aspose.com/words/python-net/) commercial library.  
The plugin is designed for parsing multiple document formats and converting them into Markdown suitable for AI processing.  
The project is located in the [GitHub repository](https://github.com/aspose-words/Aspose.Words-for-MarkItDown).  

## Features

Aspose.Words for MarkItDown supports the following features:

- Parsing new `.doc`, `.rtf`, `.odt`, `.mhtml`, `.mobi` and `.azw3` formats
- Improved conversion of `.docx`, `.pdf`, `.html`, `.epub` and `.txt` documents
- Support all document components, including paragraphs, tables, images, headers, and footers
- Fully integrated with MarkItDown tool. You don't need to change your code to use the Aspose.Words plugin

## Requirements

- [MarkItDown](https://github.com/microsoft/markitdown) version 0.1.0 or higher
- [Aspose.Words for Python via .NET](https://products.aspose.com/words/python-net/). This library is a [commercial product](https://purchase.aspose.com/buy/words/python)

You'll need to obtain valid license for Aspose.Words. The package will install this dependency, but you're responsible for complying with Aspose's licensing terms.

## How to Install Aspose.Words for MarkItDown

To install Aspose.Words for MarkItDown via pip, run the following:

```bash
pip install aspose-words-markitdown
```

## How to Use Aspose.Words for MarkItDown

1. Make sure the plugin is installed correctly:
  - List MarkItDown plugins with the command: `markitdown --list-plugins`
  - Check the plugin is installed:
  ```
  Installed MarkItDown 3rd-party Plugins:
    * aspose_words_markitdown  (package: aspose_words_markitdown)
  ```

2. Use the original `markitdown` CLI in the common way. Just add the `--use-plugins` option to enable the plugin.

3. Convert a Single File:
  ```bash
  markitdown test.doc -o out.md --use-plugins
  ```

4. Use Python API: 
  {{< highlight python >}}  
  from markitdown import MarkItDown  

  md = MarkItDown(enable_plugins=True) # Set to True to enable the plugin  
  result = md.convert("test.doc")  
  print(result.text_content)  
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
from aspose_words_markitdown import LicenseManager

LicenseManager().apply_license("/path/to/license/Aspose.Words.Python.NET.lic")  
{{< /highlight >}}  

## How to Run Tests

To run unit tests for **Aspose.Words for MarkItDown**, follow these steps:

1. Navigate to the package directory:
  From the root of the repository, change into the package directory:
  ```bash
  cd /packages/aspose-words-markitdown/tests
  ```

2. Install test dependencies:
  Make sure `pytest` is installed:
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

2. **Q:** How do I apply the Aspose.Words license when using the MarkItDown plugin in Python?  
   **A:** Set the environment variable `ASPOSE_WORDS_LICENSE_PATH` to the full path of your `Aspose.Words.Python.NET.lic` file, or call the helper class provided by the plugin:  

   ```python
   from aspose_words_markitdown import LicenseManager
   LicenseManager().apply_license("/full/path/to/Aspose.Words.Python.NET.lic")
   ```  

   This must be done before any conversion operation is executed.

3. **Q:** Why do I receive the error **“RuntimeError: Proxy error(InvalidOperationException): The license is not valid for this product.”**?  
   **A:** This error occurs when the license file was issued for another product, for example, a .NET license such as `Aspose.Total.NET.lic`. A modified or corrupted license file gives the “Invalid license signature” error instead, and a missing file gives “Cannot find license”. Verify that you are using a valid **Aspose.Words for Python via .NET** or **Aspose.Total for Python via .NET** license and that the path is correct.

4. **Q:** Does the MarkItDown plugin require a separate license from the Aspose.Words library?  
   **A:** No. The plugin itself is open‑source and distributed under the MIT license. It only depends on the commercial **Aspose.Words for Python via .NET** library, so you need a license only for that library, not for the plugin.

5. **Q:** How can I confirm that the plugin is correctly installed and recognized by MarkItDown?  
   **A:** Run `markitdown --list-plugins`. The output should contain a line similar to:  

   ```
   * aspose_words_markitdown  (package: aspose_words_markitdown)
   ```  

   If the plugin appears in the list, it is installed correctly. You can also perform a quick conversion with `markitdown sample.doc -o out.md --use-plugins` and verify that the output file is generated without errors.