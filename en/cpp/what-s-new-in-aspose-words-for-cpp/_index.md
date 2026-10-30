---
title: What's new
second_title: Aspose.Words for C++
articleTitle: What's new in Aspose.Words for C++
linktitle: What's new in Aspose.Words for C++
type: docs
description: "Aspose.Words for C++ expands and enhances daily. On this page, you can learn about the huge and most interesting features of the product."
weight: 2
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/what-s-new-in-aspose-words-for-cpp/
timestamp: 2026-10-05-11-12-25
---

This page describes the most interesting new Aspose.Words features introduced in recent releases.

## Aspose.Words for C++ 26.9

Aspose.Words 26.9 adds more control over document comparison and digital signature timestamping, and improves PDF accessibility. The release also enhances PDF layout tagging for footnotes and endnotes.

### Rendering

#### Improved PDF Accessibility <sup>26.9</sup>

PDF layout tagging has been improved by placing footnote and endnote tags according to accessibility best practices.

### Other

* The ability to control whether list definition content is included when comparing documents has been introduced by adding the **get_CompareListDefinitions()** property to the AdvancedCompareOptions class. <sup>26.9</sup>
* The ability to add RFC 3161 timestamps to digital signatures has been introduced by adding the **get_TimestampSettings()** property to the SignOptions class. <sup>26.9</sup>

{{% alert color="primary" %}}

Learn more about [Aspose.Words for C++ 26.9 Release Notes](https://releases.aspose.com/words/cpp/release-notes/2026/aspose-words-for-cpp-26-9-release-notes/).

{{% /alert %}}

## Aspose.Words for C++ 26.5, 26.6, 26.7, 26.8

Aspose.Words 26.5 introduces new digital signing and document importing capabilities, improves HTML and field rendering, and enhances support for AAT-enabled fonts in fixed-page output formats.

Aspose.Words 26.6 expands document customization capabilities, and improves PDF export quality and form field handling. This release also enhances table layout rendering and PDF hyphenation behavior.

Aspose.Words 26.7 introduces document readability statistics, expands PDF export capabilities, and improves rendering for mathematical equations, OLE objects, textboxes, and repeated table headers.

Aspose.Words 26.8 adds control over XPS compression, and improves PDF export reliability. The release also enhances MathML rendering for inline fractions and improves handling of corrupted JPEG images during PDF export.

### Converting, Loading, and Saving Documents

#### PDF Export

* Seamless export of datetime form fields to PDF, ensuring accurate transfer of date and time data, has been enabled. <sup>26.6</sup>
* Support for JavaScript triggers for date/time fields in PDF AcroForms forms has been introduced. This makes exported forms more interactive and responsive. <sup>26.6</sup>
* Hyphenation rendering has been improved. If the font does not contain an optional hyphen (U+00AD), a visual hyphen is now automatically used, while the text remains fully searchable. <sup>26.6</sup>
* The overall quality of PDF output has been improved by fully preserving date picker content controls. <sup>26.6</sup>
* The ability to export numbering fields as PDF AcroForms has been introduced when rendering documents to PDF. <sup>26.7</sup>
* Link annotation joining has been implemented for tagged PDF output to improve accessibility and document structure. <sup>26.7</sup>
* Improved handling of corrupted JPEG images during PDF export has been introduced through advanced image validation and automatic reprocessing. <sup>26.8</sup>

#### Compression Level When Exporting to XPS <sup>26.8</sup>

The ability to control the compression level of XPS output has been introduced by adding the **CompressionLevel** property.

### Rendering

#### EQ Fields

* Support for Far East vertical orientation in HTML within EQ fields has been introduced. <sup>26.5</sup>
* Improved visual rendering of the EQ field's frame has been implemented. <sup>26.5</sup>
* The rendering of OLE objects within EQ fields has been implemented. <sup>26.7</sup>

#### AAT-enabled Fonts <sup>26.5</sup>

Improved handling of AAT-enabled fonts when rendering to fixed-page formats has been implemented.

#### Repeated Table Header Row Handling <sup>26.7</sup>

Repeated table header row handling has been improved to provide more accurate document layout during rendering.

#### Alternative Text for Inner Shapes <sup>26.7</sup>

The rendering of alternative text for inner shapes contained in textboxes has been implemented.

### Other

* The ability to configure various additional digital signing options has been introduced. <sup>26.5</sup>
* The ability to import nodes with expanded formatting options has been introduced. <sup>26.5</sup>
* The ability to clear custom toolbars and keyboard shortcuts from a document has been introduced by adding a [new method](https://reference.aspose.com/words/cpp/aspose.words/document/removecustomizations/) for resetting and protecting document settings. <sup>26.6</sup>
* The handling of repeated table header rows has been improved to provide more consistent rendering and layout in multi-page tables. <sup>26.6</sup>
* The ability to calculate **Flesch Reading Ease** and **Flesch-Kincaid Grade Level** readability statistics for document text has been introduced by adding the **ReadabilityStatistics** class. <sup>26.7</sup>
* The ability to clear a custom tab stop from a list level has been introduced by adding a new **RemoveTabStop** method. <sup>26.7</sup>
* The wrapping algorithm for mathematical equations has been improved to provide more accurate rendering of complex formulas. <sup>26.7</sup>
* Improved rendering of inline fractions in MathML objects has been introduced to provide more accurate rendering of mathematical content. <sup>26.8</sup>

{{% alert color="primary" %}}

Learn more about [Aspose.Words for C++ 26.5 Release Notes](https://releases.aspose.com/words/cpp/release-notes/2026/aspose-words-for-cpp-26-5-release-notes/).

Learn more about [Aspose.Words for C++ 26.6 Release Notes](https://releases.aspose.com/words/cpp/release-notes/2026/aspose-words-for-cpp-26-6-release-notes/).

Learn more about [Aspose.Words for C++ 26.7 Release Notes](https://releases.aspose.com/words/cpp/release-notes/2026/aspose-words-for-cpp-26-7-release-notes/).

Learn more about [Aspose.Words for C++ 26.8 Release Notes](https://releases.aspose.com/words/cpp/release-notes/2026/aspose-words-for-cpp-26-8-release-notes/).

{{% /alert %}}

## Aspose.Words for C++ 26.1, 26.2, 26.3, 26.4

Aspose.Words 26.1 significantly improves PDF compliance, accessibility, and rendering accuracy for fields and mathematical equations.

Aspose.Words 26.2 improves chart customization, enhances the visual quality of mathematical equations, and aligns table layout behavior more closely with modern Microsoft Word rendering logic.

Aspose.Words 26.3 introduces improvements to AI integration, enhances document optimization capabilities, and updates font fallback handling for improved rendering of CJK Unified Ideographs Extension G range.

Aspose.Words 26.4 introduces improvements in PDF export and chart rendering capabilities, enhancing document structure fidelity and visualization accuracy.

### AI-powered Features

#### Improved OpenAiModel Capabilities <sup>26.3</sup>

The ability to create an instance of the [OpenAiModel](https://reference.aspose.com/words/cpp/aspose.words.ai/openaimodel/) class directly has been introduced, simplifying the integration of OpenAI-based AI features into document processing workflows.

### Converting, Loading, and Saving Documents

#### PDF AcroForm Tagging <sup>26.1</sup>

The ability to improve PDF accessibility has been introduced by adding support for tagging **PDF AcroForms**, making exported documents more accessible to assistive technologies.

#### Improved PDF Logical Structure <sup>26.4</sup>

The ability to improve PDF logical structure by exporting node custom IDs to custom attributes during PDF export has been introduced.

### Rendering

#### Extended PDF Conformance Standards <sup>26.1</sup>

The **PdfSaveOptions** functionality has been extended by the [get_PreserveFormFields()](https://reference.aspose.com/words/cpp/aspose.words.saving/pdfsaveoptions/get_preserveformfields/) property to be compatible with all PDF compliance standards (including PDF/A and PDF/UA).

#### Rendering MathML using an East Asian Font <sup>26.1</sup>

The ability to correctly render **MathML** content with **East Asian characters** has been introduced, while preserving Latin and Hebrew text when an East Asian font is specified.

#### EQ-matrix MathML Elements Rendering <sup>26.2</sup>

The rendering of EQ-matrix MathML elements has been improved to achieve higher visual fidelity in mathematical content.

#### Orientation And Rotation of Chart Titles and Axis Titles <sup>26.2</sup>

The ability to control the [orientation](https://reference.aspose.com/words/cpp/aspose.words.drawing.charts/charttitle/get_orientation/) and [rotation](https://reference.aspose.com/words/cpp/aspose.words.drawing.charts/charttitle/get_rotation/) of chart titles and axis titles has been introduced, allowing more flexible and precise chart layout customization.

#### Font Fallback Table for CJK Unified Ideographs Extension G range <sup>26.3</sup>

Rendering accuracy has been improved by updating the Microsoft Office font fallback table for the CJK Unified Ideographs Extension G range, ensuring more reliable font substitution when rendering documents containing these characters.

#### Enhanced Chart Rendering <sup>26.4</sup>

The ability to enhance chart rendering has been introduced by adding support for funnel chart [data labels](https://reference.aspose.com/words/cpp/aspose.words.drawing.charts/chartdatalabelcollection/), applying chart style settings to leader line rendering, and using locale IDs when rendering default axis titles in DrawingML charts.

### Other

* The handling of adjacent tables has been updated by implementing the latest Microsoft Word logic for merging or separating tables during layout processing. <sup>26.2</sup>
* The document optimization capabilities have been improved by extending the [JoinRunsWithSameFormatting](https://reference.aspose.com/words/cpp/aspose.words/document/joinrunswithsameformatting/) method, enabling more comprehensive content merging. <sup>26.3</sup>

{{% alert color="primary" %}}

Learn more about [Aspose.Words for C++ 26.1 Release Notes](https://releases.aspose.com/words/cpp/release-notes/2026/aspose-words-for-cpp-26-1-release-notes/).

Learn more about [Aspose.Words for C++ 26.2 Release Notes](https://releases.aspose.com/words/cpp/release-notes/2026/aspose-words-for-cpp-26-2-release-notes/).

Learn more about [Aspose.Words for C++ 26.3 Release Notes](https://releases.aspose.com/words/cpp/release-notes/2026/aspose-words-for-cpp-26-3-release-notes/).

Learn more about [Aspose.Words for C++ 26.4 Release Notes](https://releases.aspose.com/words/cpp/release-notes/2026/aspose-words-for-cpp-26-4-release-notes/).

{{% /alert %}}

## Aspose.Words for C++ 25.9, 25.10, 25.11, 25.12

Aspose.Words 25.9 enhances document loading reliability, expands shape and text formatting, improves Markdown export with math support, and strengthens font handling diagnostics.

Aspose.Words 25.10 introduces enhancements to text and PDF exports, improves accessibility compliance, and adds new options for resource management during Markdown export.

Aspose.Words 25.11 expands AI integration capabilities, enhances Markdown export, and introduces advanced control over print operations.

Aspose.Words 25.12 improves rendering accuracy across PDF, HTML-Fixed, and SVG formats, adds support for Variable Fonts and Funnel charts, and enhances text orientation handling in field rendering.

### AI-powered Features

#### Configure AI Model Service Endpoints <sup>25.11</sup>

The ability to configure [AI model](https://reference.aspose.com/words/cpp/aspose.words.ai/aimodel/) service endpoints has been introduced by adding support for specifying **custom URLs** and **request timeouts**, allowing greater flexibility in AI-powered integrations.

### Converting, Loading, and Saving Documents

#### Control How Corrupted Documents Are Opened <sup>25.9</sup>

The ability to control how corrupted documents are opened has been introduced by adding a new **get_RecoveryMode()** option.

#### Export Mathematical Equations to LaTeX Expression <sup>25.9</sup>

The ability to export mathematical equations (Office Math) to LaTeX expressions has been introduced:

* For export to Markdown format using the [MarkdownSaveOptions::get_OfficeMathExportMode()](https://reference.aspose.com/words/cpp/aspose.words.saving/markdownsaveoptions/get_officemathexportmode/) property. <sup>25.9</sup>
* For export to TXT format using the **TxtSaveOptions::OfficeMathExportMode** property. <sup>25.10</sup>

#### Improved Document Conversion Fidelity to Markdown <sup>25.11</sup>

The fidelity of document conversion to Markdown has been improved by enabling the [export of OfficeMath objects](https://reference.aspose.com/words/cpp/aspose.words.saving/markdownofficemathexportmode/) into LaTeX format, ensuring compatibility with MarkItDown renderers.

#### Control Floating Shape Tagging When Exporting to PDF <sup>25.10</sup>

A new save option **get_ExportFloatingShapesAsInlineTag()** has been added to provide precise control over the tagging of floating shapes as either inline or block-level elements, improving layout accuracy and accessibility.

#### Control How Images and Other External Resources are Exported to Markdown <sup>25.10</sup>

A new **resource-saving callback** has been implemented to give developers greater flexibility in controlling how images and other external resources are exported.

#### PDF/UA Export & Accessibility <sup>25.10</sup>

Compliance with PDF/UA standards has been improved by correctly tagging horizontal rules as artifacts, enhancing a better experience for users of assistive technologies.

#### Handle Relative Hyperlinks When Exporting to PDF <sup>25.12</sup>

The ability to correctly resolve and handle relative hyperlinks when exporting to PDF has been introduced by adding Base URI processing during document export.

### Rendering

#### Fine-tune Shadow Effects <sup>25.9</sup>

The ability to fine-tune [shadow effects](https://reference.aspose.com/words/cpp/aspose.words.drawing/shadowformat/) has been enhanced by introducing new public properties.

#### Improve Diagnostics for Font Substitution <sup>25.9</sup>
The ability to improve diagnostics and error handling for **font substitution** has been implemented by adding typed warnings.

#### Support for Variable Fonts When Saving Documents to SVG and Html-Fixed <sup>25.12</sup>

Robust support for Variable Fonts when saving documents to SVG and Html-Fixed formats has been added, ensuring that different font variations (including weight, width, and other parameters) defined within a single font file render correctly.

#### Render Funnel Charts <sup>25.12</sup>

The ability to render Funnel charts in documents has been added.

#### Render VerticalFarEast and HorizontalRotatedFarEast Text Orientations in EQ-field <sup>25.12</sup>

The ability to render **VerticalFarEast** and **HorizontalRotatedFarEast** text orientations in EQ-field elements has been introduced.

### Other

* new advanced print control options have been added: <sup>25.11</sup>

    * **A new callback interface**, similar to `IWarningCallback`, has been introduced to allow programmatic control over page skipping during print operations.
    * A new public property has been added to accurately **retrieve the actual number of pages** rendered by a print job.
    * The ability to specify distinct target printers for **color and monochrome** (black & white) pages within a single print job has also been introduced.

{{% alert color="primary" %}}

Learn more about [Aspose.Words for C++ 25.9 Release Notes](https://releases.aspose.com/words/cpp/release-notes/2025/aspose-words-for-cpp-25-9-release-notes/).

Learn more about [Aspose.Words for C++ 25.10 Release Notes](https://releases.aspose.com/words/cpp/release-notes/2025/aspose-words-for-cpp-25-10-release-notes/).

Learn more about [Aspose.Words for C++ 25.11 Release Notes](https://releases.aspose.com/words/cpp/release-notes/2025/aspose-words-for-cpp-25-11-release-notes/).

Learn more about [Aspose.Words for C++ 25.12 Release Notes](https://releases.aspose.com/words/cpp/release-notes/2025/aspose-words-for-cpp-25-12-release-notes/).

{{% /alert %}}

## Aspose.Words for C++ 25.5, 25.6, 25.7, 25.8

Aspose.Words 25.5 enhances chart customization with new styling options and improves Markdown export by offering control over how empty paragraphs are handled.

Aspose.Words 25.6 enhances rendering precision and visualization features by introducing advanced image export options, improved MathML handling, and better chart representation.

Aspose.Words 25.7 introduces AI enhancements with support for self-hosted LLMs, more precise control during text replacement, flexible table row visibility, and richer typography with OpenType Font Variations.

Aspose.Words 25.8 expands capabilities for Markdown import/export, enhances Find and Replace with an option to ignore Office Math objects, and provides greater control over page extraction.

### AI-powered Features

#### Integrating a Self-Hosted LLM <sup>25.7</sup>

The ability to integrate and use self-hosted LLM (Large Language Model) has been introduced, providing greater privacy and control over AI-powered document features.

### Converting, Loading, and Saving Documents

#### Export Empty Paragraphs to Markdown <sup>25.5</sup>

The ability to control how empty paragraphs are exported to Markdown has been introduced by adding the [MarkdownEmptyParagraphExportMode](https://reference.aspose.com/words/cpp/aspose.words.saving/markdownemptyparagraphexportmode/) enumeration and the [get_EmptyParagraphExportMode()](https://reference.aspose.com/words/cpp/aspose.words.saving/markdownsaveoptions/get_emptyparagraphexportmode/) property.

#### Export Multi-page Documents to Raster Image Formats <sup>25.6</sup>

The ability to export multi-page documents to raster image formats (such as PNG and JPEG) with [customizable layouts](https://reference.aspose.com/words/cpp/aspose.words.saving/multipagelayout/) – Horizontal, Vertical, or Grid – has been introduced by extending image export functionality.

#### Export Non-compatible Tables to Raw HTML <sup>25.8</sup>

The ability to control how non-compatible tables are rendered when exporting to raw HTML has been introduced by adding the new [MarkdownExportAsHtml](https://reference.aspose.com/words/cpp/aspose.words.saving/markdownexportashtml/) enumeration.

#### Specify Character for Soft Line Breaks When Importing to Markdown <sup>25.8</sup>

The ability to specify a character for soft line breaks when importing to Markdown has been introduced by adding the new **get_SoftLineBreakCharacter()** property.

### Rendering

#### Setting the Chart Style <sup>25.5</sup>

The ability to set the chart style has been introduced by adding the [ChartStyle](https://reference.aspose.com/words/cpp/aspose.words.drawing.charts/chartstyle/) enumeration and the [get_Style()](https://reference.aspose.com/words/cpp/aspose.words.drawing.charts/chart/get_style/) property.

#### Rendering Connector Lines in MathML Expressions <sup>25.6</sup>

The rendering of connector lines in MathML expressions has been implemented to ensure more accurate and visually consistent display of mathematical formulas.

#### Rendering Legends for Waterfall Charts <sup>25.6</sup>

The rendering of legends for ["Waterfall" charts](https://reference.aspose.com/words/cpp/aspose.words.drawing.charts/chartseriestype/) has been introduced, increasing data transparency and improving the interpretability of these charts.

#### Support for OpenType Font Variations <sup>25.7</sup>

Initial support for OpenType Font Variations has been implemented, allowing for more flexible and expressive typographic rendering.

### Other

* The ability to wrap mathematical formulas containing multiple slashes has been enhanced, improving layout clarity and formula legibility. <sup>25.6</sup>
* A new [ReplacingArgs::get_MatchEndNode()](https://reference.aspose.com/words/cpp/aspose.words.replacing/replacingargs/get_matchendnode/) property has been added to enable more precise control during text replacement operations across document content. <sup>25.7</sup>
* The ability to programmatically show or hide specific table rows has been introduced by adding the [Row::get_Hidden()](https://reference.aspose.com/words/cpp/aspose.words.tables/row/get_hidden/) property. <sup>25.7</sup>
* A new **get_IgnoreOfficeMath()** property has been added to ignore Office Math objects when searching and replacing. <sup>25.8</sup>
* New options have been added to the **PageExtractOptions** class to provide more control over the page extraction process. <sup>25.8</sup>

{{% alert color="primary" %}}

Learn more about [Aspose.Words for C++ 25.5 Release Notes](https://releases.aspose.com/words/cpp/release-notes/2025/aspose-words-for-cpp-25-5-release-notes/).

Learn more about [Aspose.Words for C++ 25.6 Release Notes](https://releases.aspose.com/words/cpp/release-notes/2025/aspose-words-for-cpp-25-6-release-notes/).

Learn more about [Aspose.Words for C++ 25.7 Release Notes](https://releases.aspose.com/words/cpp/release-notes/2025/aspose-words-for-cpp-25-7-release-notes/).

Learn more about [Aspose.Words for C++ 25.8 Release Notes](https://releases.aspose.com/words/cpp/release-notes/2025/aspose-words-for-cpp-25-8-release-notes/).

{{% /alert %}}

## Aspose.Words for C++ 25.1, 25.2, 25.3, 25.4

Aspose.Words 25.1 introduces AI-powered grammar checking and enhances document saving with advanced options for HTML, SVG, and Markdown formats.

Aspose.Words 25.2 introduces text summarization with Anthropic AI models, adds MsWorks format support, enhances typographic control, and improves PDF structure and list handling.

Aspose.Words 25.3 enhances an AI-powered grammar checker and font selection with the `get_UpdateAmbiguousTextFont()` property, as well as improves PDF attachments export.

Aspose.Words 25.4 introduces support for new paper sizes, enables advanced HTML export control, improves watermark handling, and enhances the usability of the LowCode API.

### AI-powered Features

#### Document AI Grammar Checking

* The ability to check the grammar of the provided document using OpenAI generative models has been introduced by adding a new [CheckGrammar](https://reference.aspose.com/words/cpp/aspose.words.ai/aimodel/checkgrammar/) method. <sup>25.1</sup>
* The AI-powered Grammar Checking feature has been updated to support all models available in the [AiModelType](https://reference.aspose.com/words/cpp/aspose.words.ai/aimodeltype/) enumeration. <sup>25.3</sup>

#### Summarization Using Anthropic Generative Language Models <sup>25.2</sup>

Text summarization using Anthropic generative language models has been enabled by introducing a new public class [AnthropicAiModel](https://reference.aspose.com/words/cpp/aspose.words.ai/).

### Low Code

#### Low Code API Usability <sup>25.4</sup>

Significant improvements to the usability of the **LowCode API** have been introduced, simplifying document processing and reducing the need for repetitive code.

### Supported Formats <sup>25.2</sup>

Starting from version 25.2, compatibility with the new MsWorks load format for Microsoft Works documents has been added.

### Converting, Loading, and Saving Documents

#### Improved Saving to HTML and SVG Formats <sup>25.1</sup>

Saving to HTML and SVG formats has been enhanced by adding **get_IdPrefix()** and **get_RemoveJavaScriptFromLinks()** properties to both the [HtmlFixedSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/htmlfixedsaveoptions/) and [SvgSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/svgsaveoptions/) classes.

#### Set Image Resolution and OfficeMath Output Mode When Saving to Markdown <sup>25.1</sup>

- A new [get_ImageResolution()](https://reference.aspose.com/words/cpp/aspose.words.saving/markdownsaveoptions/get_imageresolution/) option has been added to the [MarkdownSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/markdownsaveoptions/) class to set the image resolution.
- A new [get_OfficeMathExportMode()](https://reference.aspose.com/words/cpp/aspose.words.saving/markdownsaveoptions/get_officemathexportmode/) option and [MarkdownOfficeMathExportMode](https://reference.aspose.com/words/cpp/aspose.words.saving/markdownofficemathexportmode/) enumeration have been and added to the [MarkdownSaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/markdownsaveoptions/) class to set OfficeMath output mode.
- The ability to set an image watermark from a stream has been introduced by adding a new overload to the [SetImage](https://reference.aspose.com/words/cpp/aspose.words/watermark/setimage/#watermarksetimageconst-systemsharedptrsystemiostream-const-systemsharedptrasposewordsimagewatermarkoptions-method) method. <sup>25.4</sup>

### Rendering

#### Improved Typographic Control <sup>25.2</sup>

The [get_NumberSpacing()](https://reference.aspose.com/words/cpp/aspose.words/font/get_numberspacing/) property has been added for improved typographic control.

#### Controlling Font Selection for Ambiguous Characters <sup>25.3</sup>

A new public property [get_UpdateAmbiguousTextFont()](https://reference.aspose.com/words/cpp/aspose.words.saving/saveoptions/get_updateambiguoustextfont/) has been added to the [SaveOptions](https://reference.aspose.com/words/cpp/aspose.words.saving/saveoptions/) class to control the font selection according to the character code used.

#### Paper Size Options <sup>25.4</sup>

The ability to use JIS B4 and JIS B5 paper sizes has been introduced by adding new values to the [PaperSize](https://reference.aspose.com/words/cpp/aspose.words/papersize/) enumeration.

#### HTML Output Control <sup>25.4</sup>

The ability to remove JavaScript from hyperlink URLs during HTML export has been introduced by adding the [get_RemoveJavaScriptFromLinks()](https://reference.aspose.com/words/cpp/aspose.words.saving/htmlsaveoptions/get_removejavascriptfromlinks/) property.

### Other

* PDF logical structure has been improved with support for TOA, BIBLIOGRAPHY, and INDEX fields. <sup>25.2</sup>
* The [AddSingleLevelList](https://reference.aspose.com/words/cpp/aspose.words.lists/listcollection/addsinglelevellist/) method has been introduced for improved list handling. <sup>25.2</sup>
* A new property [get_AttachmentsEmbeddingMode()](https://reference.aspose.com/words/cpp/aspose.words.saving/pdfsaveoptions/get_attachmentsembeddingmode/) has been added to replace **EmbedAttachments** to improve PDF attachments' export. Also, new values have been added to the [PdfCompliance](https://reference.aspose.com/words/cpp/aspose.words.saving/pdfcompliance/) enumeration to support PDF/A version attachments. Additionally, attachments are now supported with encryption. <sup>25.3</sup>

{{% alert color="primary" %}}

Learn more about [Aspose.Words for C++ 25.1 Release Notes](https://releases.aspose.com/words/cpp/release-notes/2025/aspose-words-for-cpp-25-1-release-notes/).

Learn more about [Aspose.Words for C++ 25.2 Release Notes](https://releases.aspose.com/words/cpp/release-notes/2025/aspose-words-for-cpp-25-2-release-notes/).

Learn more about [Aspose.Words for C++ 25.3 Release Notes](https://releases.aspose.com/words/cpp/release-notes/2025/aspose-words-for-cpp-25-3-release-notes/).

Learn more about [Aspose.Words for C++ 25.4 Release Notes](https://releases.aspose.com/words/cpp/release-notes/2025/aspose-words-for-cpp-25-4-release-notes/).

{{% /alert %}}

## See Also

{{% alert color="primary" %}}

This page contains the latest release news for the past 2 years. For details on earlier releases, see the [Release Notes'](https://releases.aspose.com/words/cpp/release-notes/) pages in the relevant sections.

{{% /alert %}}
