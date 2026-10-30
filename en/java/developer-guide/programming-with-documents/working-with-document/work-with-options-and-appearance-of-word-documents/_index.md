---
title: Options and Appearance Word Document
second_title: Aspose.Words for Java
articleTitle: Work with Options and Appearance of Word Documents
linktitle: Work with Options and Appearance of Word Documents
description: "Control the appearance of Word documents taking into account the difference between various Microsoft Word versions using Java."
type: docs
weight: 40
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/work-with-word-document-options-and-appearance/
aliases: [/java/work-with-document-options-and-settings/]
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains Word document options that affect appearance such as view, zoom, and compatibility settings.

{{% /alert %}}

Sometimes you may need to change the appearance of a document, for example, set language preferences or the number of lines per page. Aspose.Words provides the ability to control how the document will be displayed, as well as some additional options. This article describes such possibilities.

## Set Document Display Options

You can control how a document will be displayed in Microsoft Word using the [ViewOptions](https://reference.aspose.com/words/java/com.aspose.words/viewoptions/) class. For example, you can set a document zoom value using the [getZoomPercent()](https://reference.aspose.com/words/java/com.aspose.words/viewoptions/#getZoomPercent) property, or the view mode using the [getViewType()](https://reference.aspose.com/words/java/com.aspose.words/viewoptions/#getViewType) property.

The following code example shows how to ensure that a document is displayed at 50% when opened in Microsoft Word:

{{< gist "aspose-words-gists" "2e73ea09c5fcbcb9f7b99f01602ecd34" "set-view-option.java" >}}

{{% alert color="primary" %}}

You can download the template file for this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Examples/Data/Document.docx).

{{% /alert %}}

{{% alert color="primary" %}}

Microsoft Word 2013 does not write any zoom factor to a document and no longer sets the default zoom from the value written to the document, instead, it seems to use the zoom factor of the last open document.

{{% /alert %}}

## Set Page Display Options

If you want to set the number of characters per line, use the [getCharactersPerLine()](https://reference.aspose.com/words/java/com.aspose.words/pagesetup/#getCharactersPerLine) property. You can also set the number of lines per page for a Word document – use the [getLinesPerPage()](https://reference.aspose.com/words/java/com.aspose.words/pagesetup/#getLinesPerPage) property to get or set the number of lines per page in the document grid.

{{% alert color="primary" %}}

In Microsoft Word, you can set the same parameters using the "Document Grid" tab in the "Page Setup" dialog box only when Asian language support is installed.

{{% /alert %}}

The following code example shows how to set the number of characters per line and the number of lines per page for a Microsoft Word document:

{{< gist "aspose-words-gists" "2e73ea09c5fcbcb9f7b99f01602ecd34" "document-page-setup.java" >}}

## Set Language Preferences

Displaying a document in Microsoft Word depends on which languages are set as defaults for this document. If no languages are set in defaults, Microsoft Word takes information from the "Set Office Language Preferences" dialog box, which, for example, can be found under "File → Options → Language" in Microsoft Word 2019.

With Aspose.Words, you can also set up language preferences using the [LanguagePreferences](https://reference.aspose.com/words/java/com.aspose.words/languagepreferences/) class. Also note that for the correct display of your document it is necessary to set the Microsoft Word version that the document loading process should match – this can be done using the [getMswVersion()](https://reference.aspose.com/words/java/com.aspose.words/loadoptions/#getMswVersion) property.

{{% alert color="primary" %}}

If your Aspose.Words generated document does not look as expected, check the **LanguagePreferences** and **getMswVersion()** values and adjust them if necessary to match the settings for your Microsoft Word version.

{{% /alert %}}

The following code example shows how to add Japanese to editing languages:

{{< gist "aspose-words-gists" "9216df344e0dc0025f5eda608b9f33d8" "add-editing-language.java" >}}

The following code example shows how to set Russian as the default editing language:

{{< gist "aspose-words-gists" "2e73ea09c5fcbcb9f7b99f01602ecd34" "set-russian-as-default-editing-language.java" >}}

## Optimize a Document for a Particular Word Version

The [optimizeFor()](https://reference.aspose.com/words/java/com.aspose.words/compatibilityoptions/#optimizeFor-int) method allows optimizing document content, as well as default Aspose.Words behaviour for a particular version of Microsoft Word. You can use this method to prevent Microsoft Word from displaying the “Compatibility mode” ribbon upon document loading. Note that you may also need to set the `Compliance` property to Iso29500_2008_Transitional or higher.

The following code example shows how to optimize document content for Microsoft Word 2016:

{{< gist "aspose-words-gists" "2e73ea09c5fcbcb9f7b99f01602ecd34" "optimize-for.java" >}}

## Related APIs

- [ViewOptions](https://reference.aspose.com/words/java/com.aspose.words/viewoptions/)
- [PageSetup](https://reference.aspose.com/words/java/com.aspose.words/pagesetup/)
- [LanguagePreferences](https://reference.aspose.com/words/java/com.aspose.words/languagepreferences/)
- [LoadOptions](https://reference.aspose.com/words/java/com.aspose.words/loadoptions/)
- [CompatibilityOptions](https://reference.aspose.com/words/java/com.aspose.words/compatibilityoptions/) 

## FAQ

1. **Q:** How can I set the zoom level that Word uses when opening a document?  
   **A:** Use the `ViewOptions` class. Get the document's `ViewOptions` with `doc.getViewOptions()` and call `setZoomPercent` (e.g., `50`). The document will open at the specified zoom percentage in supported Word versions.

2. **Q:** Which properties control the number of lines per page or characters per line?  
   **A:** These are part of the `PageSetup` class. Use `pageSetup.setLinesPerPage(int)` to define lines per page and `pageSetup.setCharactersPerLine(int)` for characters per line. They affect the document grid, which is visible when Asian language support is installed.

3. **Q:** How do I specify editing and default languages for a document?  
   **A:** Use the `LanguagePreferences` object of `LoadOptions`: call `loadOptions.getLanguagePreferences().addEditingLanguage(EditingLanguage.JAPANESE)` or `setDefaultEditingLanguage(EditingLanguage.RUSSIAN)`, then load the document with these `LoadOptions`. This ensures Word displays the document with the correct language settings.

4. **Q:** What is the purpose of the `optimizeFor()` method and when should I use it?  
   **A:** `optimizeFor()` configures the document to target a specific Word version (e.g., `MsWordVersion.WORD_2016`). It removes compatibility features that would otherwise trigger Word's “Compatibility mode” ribbon. Use it when you know the target Word version and want the document to behave as a native file for that version.

5. **Q:** How can I change the view mode (Print Layout, Web Layout, etc.) of a document programmatically?  
   **A:** Call `doc.getViewOptions().setViewType(...)` with one of the `ViewType` values such as `ViewType.PAGE_LAYOUT` or `ViewType.WEB`. Word will open the file using the specified view mode.