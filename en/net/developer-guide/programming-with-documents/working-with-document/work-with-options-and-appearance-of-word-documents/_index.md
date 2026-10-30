---
title: Options and Appearance Word Document
second_title: Aspose.Words for .NET
articleTitle: Work with Options and Appearance of Word Documents
linktitle: Work with Options and Appearance of Word Documents
description: "Control the appearance of Word documents taking into account the difference between various Microsoft Word versions using C#."
type: docs
weight: 40
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/work-with-word-document-options-and-appearance/
aliases: [/net/work-with-document-options-and-settings/]
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains Word document options that affect appearance such as view, zoom, and compatibility settings.

{{% /alert %}}

Sometimes you may need to change the appearance of a document, for example, set language preferences or the number of lines per page. Aspose.Words provides the ability to control how the document will be displayed, as well as some additional options. This article describes such possibilities.

## Set Document Display Options

You can control how a document will be displayed in Microsoft Word using the [ViewOptions](https://reference.aspose.com/words/net/aspose.words.settings/viewoptions/) class. For example, you can set a document zoom value using the [ZoomPercent](https://reference.aspose.com/words/net/aspose.words.settings/viewoptions/zoompercent/) property, or the view mode using the [ViewType](https://reference.aspose.com/words/net/aspose.words.settings/viewoptions/viewtype/) property.

The following code example shows how to ensure that a document is displayed at 50% when opened in Microsoft Word:

{{< gist "aspose-words-gists" "5d2997d42c1f1fad79b18873f170855f" "set-view-option.cs" >}}

{{% alert color="primary" %}}

You can download the template file for this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-.NET/blob/master/Examples/Data/Document.docx).

{{% /alert %}}

{{% alert color="primary" %}}

Microsoft Word 2013 does not write any zoom factor to a document and no longer sets the default zoom from the value written to the document, instead, it seems to use the zoom factor of the last open document.

{{% /alert %}}

## Set Page Display Options

If you want to set the number of characters per line, use the [CharactersPerLine](https://reference.aspose.com/words/net/aspose.words/pagesetup/charactersperline/) property. You can also set the number of lines per page for a Word document – use the [LinesPerPage](https://reference.aspose.com/words/net/aspose.words/pagesetup/linesperpage/) property to get or set the number of lines per page in the document grid.

{{% alert color="primary" %}}

In Microsoft Word, you can set the same parameters using the "Document Grid" tab in the "Page Setup" dialog box only when Asian language support is installed.

{{% /alert %}}

The following code example shows how to set the number of characters per line and the number of lines per page for a Microsoft Word document:

{{< gist "aspose-words-gists" "5d2997d42c1f1fad79b18873f170855f" "document-page-setup.cs" >}}

## Set Language Preferences

Displaying a document in Microsoft Word depends on which languages are set as defaults for this document. If no languages are set in defaults, Microsoft Word takes information from the "Set Office Language Preferences" dialog box, which, for example, can be found under "File → Options → Language" in Microsoft Word 2019.

With Aspose.Words, you can also set up language preferences using the [LanguagePreferences](https://reference.aspose.com/words/net/aspose.words.loading/languagepreferences/) class. Also note that for the correct display of your document it is necessary to set the Microsoft Word version that the document loading process should match – this can be done using the [MswVersion](https://reference.aspose.com/words/net/aspose.words.loading/loadoptions/mswversion/) property.

{{% alert color="primary" %}}

If your Aspose.Words generated document does not look as expected, check the **LanguagePreferences** and **MswVersion** values and adjust them if necessary to match the settings for your Microsoft Word version.

{{% /alert %}}

The following code example shows how to add Japanese to editing languages:

{{< gist "aspose-words-gists" "40be8275fc43f78f5e5877212e4e1bf3" "add-editing-language.cs" >}}

The following code example shows how to set Russian as the default editing language:

{{< gist "aspose-words-gists" "5d2997d42c1f1fad79b18873f170855f" "set-russian-as-default-editing-language.cs" >}}

## Optimize a Document for a Particular Word Version

The [OptimizeFor](https://reference.aspose.com/words/net/aspose.words.settings/compatibilityoptions/optimizefor/) method allows optimizing document content, as well as default Aspose.Words behaviour for a particular version of Microsoft Word. You can use this method to prevent Microsoft Word from displaying the “Compatibility mode” ribbon upon document loading. Note that you may also need to set the `Compliance` property to Iso29500_2008_Transitional or higher.

The following code example shows how to optimize document content for Microsoft Word 2016:

{{< gist "aspose-words-gists" "5d2997d42c1f1fad79b18873f170855f" "optimize-for.cs" >}}

## Related APIs


- [ViewOptions](https://reference.aspose.com/words/net/aspose.words.settings/viewoptions/)
- [PageSetup](https://reference.aspose.com/words/net/aspose.words/pagesetup/)
- [LanguagePreferences](https://reference.aspose.com/words/net/aspose.words.loading/languagepreferences/)
- [LoadOptions](https://reference.aspose.com/words/net/aspose.words.loading/loadoptions/)
- [CompatibilityOptions](https://reference.aspose.com/words/net/aspose.words.settings/compatibilityoptions/)

## FAQ

1. **Q:** How can I set the zoom level of a Word document when it opens in Microsoft Word?  
   **A:** Use the `ViewOptions.ZoomPercent` property. Assign the desired percentage (e.g., `50`) to `document.ViewOptions.ZoomPercent` before saving the document. Note that some Word versions, such as Word 2013, ignore the stored zoom value and use the last used zoom instead.

2. **Q:** How do I change the view mode (Print Layout, Web Layout, etc.) programmatically?  
   **A:** Set the `ViewOptions.ViewType` property to one of the `ViewType` enumeration values, for example `ViewType.PageLayout` or `ViewType.Web`. This determines how Word initially displays the document when opened.

3. **Q:** How can I specify language preferences to ensure correct display of Asian characters?  
   **A:** Add the required editing languages to `LoadOptions.LanguagePreferences` (e.g., `loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese)`) and pass the `LoadOptions` to the `Document` constructor when loading. This influences spell‑checking, hyphenation, and character rendering.

4. **Q:** What is the purpose of the `OptimizeFor` method and when should I use it?  
   **A:** `CompatibilityOptions.OptimizeFor` adjusts the document's internal structures to match a specific Microsoft Word version, preventing the Compatibility Mode ribbon from appearing. Call it with the target `MsWordVersion` (e.g., `MsWordVersion.Word2016`) and optionally save with `OoxmlSaveOptions.Compliance` set to `OoxmlCompliance.Iso29500_2008_Transitional` or higher for better standards compliance.

5. **Q:** My document still shows the Compatibility Mode ribbon after calling `OptimizeFor`. What else should I check?  
   **A:** Verify that you save with `OoxmlSaveOptions.Compliance` set to at least `OoxmlCompliance.Iso29500_2008_Transitional`. Also ensure no older compatibility settings remain in the document (e.g., older `CompatibilityOptions` values). Re‑saving the document after applying both settings usually resolves the issue.