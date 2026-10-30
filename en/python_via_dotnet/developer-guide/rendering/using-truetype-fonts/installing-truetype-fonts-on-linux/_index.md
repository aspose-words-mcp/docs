---
title: Install TrueType Fonts on Linux
second_title: Aspose.Words for Python via .NET
articleTitle: Install TrueType Fonts on Linux
linktitle: Install TrueType Fonts on Linux
description: "Aspose.Words for Python allows rendering a document created using Microsoft Word on a Linux machine with the best accuracy. To accomplish this, copy font files from a Windows machine or Install a `TrueType` font package onto your Linux machine."
type: docs
weight: 20
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/installing-truetype-fonts-on-linux/
aliases: [/python/installing-truetype-fonts-on-linux/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page explains how to provide Windows TrueType fonts on a Linux system for Aspose.Words for Python via .NET, describing two approaches: copying font files from a Windows machine and installing a TrueType font package, and how to configure the library to use them.  
{{% /alert %}}

Most often, you will use Aspose.Words to convert DOC or DOCX documents to PDF format. If you need to do this on a Linux machine, this topic will help you to learn how to ensure Aspose.Words is rendering your documents with the best accuracy.

Most frequently, the DOC and DOCX documents, which need to be converted were created using Microsoft Word, on a Windows or Mac OS operating system. Therefore, most fonts used in DOC and DOCX documents are "Windows fonts" or "Office fonts", that are the fonts installed with Microsoft Windows or Microsoft Office. These fonts include Arial, Calibri, Cambria, Century Gothic, Courier New, Garamond, Tahoma, Verdana, Wingdings, and many others.

The problem is that the `TrueType` fonts listed above are not installed by default on Linux distributions. If you take a typical DOCX document that is formatted with the Cambria font and try to convert it to PDF format on Linux, Aspose.Words will use a different font because Cambria is not available. As a result, the PDF document will look different, in comparison to the original DOCX document. To make sure that documents converted by Aspose.Words appear as close as possible to the original, you need to install "Windows fonts" on your Linux system.

There are two main ways to get TrueType fonts on a Linux system:

- Copy .TTF and .TTC files from a Windows machine onto your Linux machine
- Install a `TrueType` font package, such as *msttcorefonts*

## Copying Fonts from a Windows Machine

An easy and quick way to get TrueType fonts on a Linux system is to copy .TTF and .TTC files from the `C:\Windows\Fonts` directory on a Windows machine to some directory on your Linux machine. You do not need to install or register these fonts on Linux in any way; you just need to specify the location of the fonts using the [FontSettings](https://reference.aspose.com/words/python-net/aspose.words.fonts/fontsettings/) class in Aspose.Words.

{{% alert color="primary" %}}

Verify whether font licensing is required, and read the EULA carefully before installing MS Fonts on any Linux operating system.

{{% /alert %}}

## Install a `TrueType` Fonts Package

There are a number of Linux packages, containing Microsoft TrueType fonts, that you can download and install onto your Linux machine. The exact steps may be different on various Linux distributions.

- On Ubuntu, use Synaptic Package Manager to find and install the *ttf-mscorefonts-installer* package.
- On openSUSE, use Yast2 → Software Management to find and install the *fetchmsttfonts* package.
- Use Liberation Fonts licensed under OFL, as an alternative to standard Windows fonts: Arial, Times New Roman, and Courier New.
- For font packages suitable to other Linux distributions, search available documentation on the internet.

After installing the package, Aspose.Words will find these fonts in the folders on your system and use them when working with documents.

## See Also

- [Liberation Fonts](https://pagure.io/liberation-fonts) as an alternative to standard Windows fonts

## Related APIs

- [FontSettings](https://reference.aspose.com/words/python-net/aspose.words.fonts/fontsettings/)
- [FontSettings.set_fonts_sources()](https://reference.aspose.com/words/python-net/aspose.words.fonts/fontsettings/set_fonts_sources/)
- [FontSubstitutionSettings](https://reference.aspose.com/words/python-net/aspose.words.fonts/fontsubstitutionsettings/)
- [FontInfo](https://reference.aspose.com/words/python-net/aspose.words.fonts/fontinfo/) 

## FAQ

1. **Q:** Does Aspose.Words for Python via .NET run on Linux?  
   **A:** Yes. Aspose.Words for Python via .NET is fully supported on Linux distributions. The only additional requirement is that the fonts used in the source documents must be available on the Linux machine, either by copying them or by installing a TrueType font package.

2. **Q:** How can I tell Aspose.Words where my custom fonts are located?  
   **A:** Use the `FontSettings` class to point to the folder that contains the `.ttf`/`.ttc` files. Example:

   ```python
   import aspose.words as aw

   font_settings = aw.fonts.FontSettings()
   font_settings.set_fonts_folder("/home/user/custom_fonts", True)   # True = search sub‑folders

   doc = aw.Document("input.docx")
   doc.font_settings = font_settings
   doc.save("output.pdf")
   ```

3. **Q:** What happens if a required font is missing on Linux?  
   **A:** Aspose.Words substitutes the missing font with a fallback font that is available on the system. This can change the appearance of the resulting PDF or rendered document, so installing the original Windows fonts is recommended for accurate rendering.

4. **Q:** Is it necessary to register the copied fonts with the Linux operating system?  
   **A:** No. When you use `FontSettings.set_fonts_folder`, Aspose.Words loads the fonts directly from the specified directory without requiring system‑wide registration.

5. **Q:** Can I use open‑source fonts such as Liberation fonts instead of Microsoft fonts?  
   **A:** Yes. Liberation fonts provide metric‑compatible replacements for Arial, Times New Roman, and Courier New. Installing them via the Linux package manager works the same way as installing Microsoft fonts, and Aspose.Words will automatically use them if they are available.