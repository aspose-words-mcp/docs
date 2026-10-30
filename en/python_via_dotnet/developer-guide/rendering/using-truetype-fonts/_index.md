---
title: Using TrueType Fonts in Python
second_title: Aspose.Words for Python via .NET
articleTitle: Using TrueType Fonts
linktitle: Using TrueType Fonts
description: "Aspose.Words for Python via .NET can find the right font or its suitable replacement for correct document rendering. This ensures that the difference between the displayed document and the original is minimal when there is not enough information about a font."
type: docs
weight: 20
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/using-truetype-fonts/
aliases: [/python/using-truetype-fonts/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page explains how to use TrueType fonts with Aspose.Words for Python via .NET, covering loading fonts from custom folders, handling missing fonts through substitution, embedding fonts in output files, setting a default font, and listing available fonts at runtime.
{{% /alert %}}

When working with documents, you often have to use different fonts, styles, and sizes. Documents can contain any number of fonts, which are not necessarily limited to the fonts that are installed in the operating system. The fonts can be completely different, such as fonts taken from other operating systems, purchased, or created by users themselves.

Sometimes, information about the fonts being used is embedded in the document, eliminating display problems during document transfer. In some other cases, only the font name is known, which does not guarantee that the document will look the same way on another computer. In this case, Aspose.Words can find the right font or its suitable replacement, if the required font cannot be found, for correct rendering.

## FAQ

1. **Q:** How can I load TrueType fonts that are stored in a custom folder?  
   **A:** Use the `FontSettings` class to point Aspose.Words to the folder that contains your fonts. Set the folder with `set_fonts_folder` and assign the `FontSettings` object to the `Document` instance.

   ```python
   import aspose.words as aw

   # Create a FontSettings object
   font_settings = aw.fonts.FontSettings()
   # Specify the folder that contains your TrueType fonts
   font_settings.set_fonts_folder(r"C:\MyCustomFonts", False)

   # Load a document and apply the font settings
   doc = aw.Document(r"input.docx")
   doc.font_settings = font_settings
   doc.save(r"output.pdf")
   ```

2. **Q:** What does Aspose.Words do when a required font is missing on the system?  
   **A:** The library automatically substitutes the missing font with a similar one based on the font substitution table. You can customize this behavior by providing your own substitution rules through `FontSettings.substitution_settings.table_substitution`.

   ```python
   # Replace missing "MyFont" with "Arial"
   font_settings.substitution_settings.table_substitution.add_substitutes("MyFont", ["Arial"])
   ```

3. **Q:** Can I embed the TrueType fonts used in a document into the generated PDF or DOCX?  
   **A:** Yes. For PDF, set the `embed_full_fonts` property of `PdfSaveOptions` to `True`. For DOCX, set `doc.font_infos.embed_true_type_fonts = True`. This forces the fonts to be embedded in the output file.

   ```python
   # Save as PDF with embedded fonts
   pdf_options = aw.saving.PdfSaveOptions()
   pdf_options.embed_full_fonts = True
   doc.save(r"output.pdf", pdf_options)
   ```

4. **Q:** How do I change the default font that Aspose.Words uses when a document does not specify one?  
   **A:** Assign a default font name to `FontSettings.substitution_settings.default_font_substitution.default_font_name`. Aspose.Words uses it when no other suitable font is found.

   ```python
   font_settings.substitution_settings.default_font_substitution.default_font_name = "Times New Roman"
   doc.font_settings = font_settings
   ```

5. **Q:** Is there a way to list all fonts that Aspose.Words can access at runtime?  
   **A:** Get the font sources via `FontSettings.get_fonts_sources()` and call `get_available_fonts()` on each source to see each font's name and file path.

   ```python
   for source in font_settings.get_fonts_sources():
       for font_info in source.get_available_fonts():
           print(f"Font: {font_info.full_font_name}, File: {font_info.file_path}")
   ```