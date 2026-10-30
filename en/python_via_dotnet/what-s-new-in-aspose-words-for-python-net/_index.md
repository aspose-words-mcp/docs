---
title: What's new
second_title: Aspose.Words for Python via .NET
articleTitle: What's new in Aspose.Words for Python via .NET
linktitle: What's new in Aspose.Words for Python via .NET
type: docs
description: "Aspose.Words for Python via .NET expands and enhances daily. On this page, you can learn about the huge and most interesting features of the product."
weight: 5
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/what-s-new-in-aspose-words-for-python-net/
timestamp: 2026-10-29-03-12-25
---

{{% alert color="grey" %}}

*Purpose Summary. What is this page about?*

This page lists the most notable new features and enhancements introduced in recent Aspose.Words for Python via .NET releases, organized by version and feature category.

{{% /alert %}}

This page describes the most interesting new Aspose.Words features introduced in recent releases.

## Aspose.Words for Python via .NET 26.9, 26.10

Aspose.Words 26.9 adds more control over document comparison and digital signature timestamping, and improves PDF accessibility. The release also enhances PDF layout tagging for footnotes and endnotes.

Aspose.Words 26.10 introduces on-premise AI-powered document processing, improves floating table positioning, and expands chart customization capabilities. The release also enhances MathML and mathematical formula rendering and strengthens PDF/UA-2 compliance.

### AI-powered Features

#### On-premise AI Engine Integration <sup>26.10</sup>

The ability to process documents using AI without sending document content outside the machine has been introduced by integrating Aspose.LLM into Aspose.Words, enabling on-premise inference entirely within the current process.

### Converting, Loading, and Saving Documents

#### PDF/UA-2 Compliance <sup>26.10</sup>

PDF export has been enhanced by implementing structure destination (`/SD`) generation for document outline entries, ensuring compliance with PDF/UA-2 requirements.

### Rendering

#### Improved PDF Accessibility <sup>26.9</sup>

PDF layout tagging has been improved by placing footnote and endnote tags according to accessibility best practices.

#### Improved Floating Table Positioning <sup>26.10</sup>

Floating table positioning has been improved by implementing Microsoft Word-like behavior when balancing floating tables against footnotes, resulting in more accurate document layout.

#### Enhanced Chart Plot Area Formatting <sup>26.10</sup>

The ability to customize the fill and line formatting of a chart's plot area has been introduced, providing greater control over chart appearance.

#### Waterfall Chart Total Data Points <sup>26.10</sup>

The ability to determine whether a data point represents a total in a waterfall chart has been introduced, enabling more precise identification of total columns.

#### MathML Background Color Remapping <sup>26.10</sup>

MathML background rendering has been improved by implementing color remapping according to compatibility settings, ensuring more accurate rendering across different document compatibility modes.

#### Rendering FormCheckBox Fields in OfficeMath <sup>26.10</sup>

The ability to render `FormCheckBox` fields located within `OfficeMath` formulas has been introduced, improving the rendering of documents containing mathematical expressions and form fields.

### Other

* The ability to control whether list definition content is included when comparing documents has been introduced by adding the **compare_list_definitions** property to the AdvancedCompareOptions class. <sup>26.9</sup>
* The ability to add RFC 3161 timestamps to digital signatures has been introduced by adding the **timestamp_settings** property to the SignOptions class. <sup>26.9</sup>

{{% alert color="primary" %}}

Learn more about [Aspose.Words for Python via .NET 26.9 Release Notes](https://releases.aspose.com/words/python/release-notes/2026/aspose-words-for-python-via-dotnet-26-9-release-notes/).

Learn more about [Aspose.Words for Python via .NET 26.10 Release Notes](https://releases.aspose.com/words/python/release-notes/2026/aspose-words-for-python-via-dotnet-26-10-release-notes/).

{{% /alert %}}

## Aspose.Words for Python via .NET 26.5, 26.6, 26.7, 26.8

Aspose.Words 26.5 introduces new digital signing and document importing capabilities, improves HTML and field rendering, and enhances support for AAT-enabled fonts in fixed-page output formats.

Aspose.Words 26.6 introduces printing support for Windows-specific .NET target frameworks, expands document customization capabilities, and improves PDF export quality and form field handling. This release also enhances table layout rendering and PDF hyphenation behavior.

Aspose.Words 26.7 expands PDF export capabilities, and improves rendering for mathematical equations, OLE objects, and textboxes.

Aspose.Words 26.8 expands digital signature capabilities with support for post-quantum ML-DSA certificates, adds control over XPS compression, and improves PDF export reliability. The release also enhances MathML rendering for inline fractions and improves handling of corrupted JPEG images during PDF export.

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

The ability to control the compression level of XPS output has been introduced by adding the **compression_level** property.

### Rendering

#### EQ Fields

* Support for Far East vertical orientation in HTML within EQ fields has been introduced. <sup>26.5</sup>
* Improved visual rendering of the EQ field's frame has been implemented. <sup>26.5</sup>
* The rendering of OLE objects within EQ fields has been implemented. <sup>26.7</sup>

#### AAT-enabled Fonts <sup>26.5</sup>

Improved handling of AAT-enabled fonts when rendering to fixed-page formats has been implemented.

#### Alternative Text for Inner Shapes <sup>26.7</sup>

The rendering of alternative text for inner shapes contained in textboxes has been implemented.

### Other

* The ability to configure various additional digital signing options has been introduced. <sup>26.5</sup>
* The ability to import nodes with expanded formatting options has been introduced. <sup>26.5</sup>
* The ability to clear custom toolbars and keyboard shortcuts from a document has been introduced by adding a **new method** for resetting and protecting document settings. <sup>26.6</sup>
* The handling of repeated table header rows has been improved to provide more consistent rendering and layout in multi-page tables. <sup>26.6</sup>
* The ability to clear a custom tab stop from a list level has been introduced by adding a new [remove_tab_stop](https://reference.aspose.com/words/python-net/aspose.words.lists/listlevel/remove_tab_stop/#default) method. <sup>26.7</sup>
* The wrapping algorithm for mathematical equations has been improved to provide more accurate rendering of complex formulas. <sup>26.7</sup>
* Support for post-quantum PFX certificates based on ML-DSA has been introduced by [enhancing the digital signature functionality](https://reference.aspose.com/words/python-net/aspose.words.digitalsignatures/digitalsignatureutil/) to allow documents to be signed with post-quantum certificates. <sup>26.8</sup>
* Improved rendering of inline fractions in MathML objects has been introduced to provide more accurate rendering of mathematical content. <sup>26.8</sup>

{{% alert color="primary" %}}

Learn more about [Aspose.Words for Python via .NET 26.5 Release Notes](https://releases.aspose.com/words/python/release-notes/2026/aspose-words-for-python-via-dotnet-26-5-release-notes/).

Learn more about [Aspose.Words for Python via .NET 26.6 Release Notes](https://releases.aspose.com/words/python/release-notes/2026/aspose-words-for-python-via-dotnet-26-6-release-notes/).

Learn more about [Aspose.Words for Python via .NET 26.7 Release Notes](https://releases.aspose.com/words/python/release-notes/2026/aspose-words-for-python-via-dotnet-26-7-release-notes/).

Learn more about [Aspose.Words for Python via .NET 26.8 Release Notes](https://releases.aspose.com/words/python/release-notes/2026/aspose-words-for-python-via-dotnet-26-8-release-notes/).

{{% /alert %}}

## Aspose.Words for Python via .NET 26.1, 26.2, 26.3, 26.4

Aspose.Words 26.1 introduces Docling JSON export, enhances AI and document merging capabilities, and significantly improves PDF compliance for fields.

Aspose.Words 26.2 improves chart customization, enhances the visual quality of mathematical equations, and aligns table layout behavior more closely with modern Microsoft Word rendering logic.

Aspose.Words for .NET 26.3 introduces improvements to AI integration, enhances document optimization capabilities, and updates font fallback handling for improved rendering of CJK Unified Ideographs Extension G range.

Aspose.Words 26.4 introduces improvements in PDF export and chart rendering capabilities.

### AI-powered Features

#### Direct Instantiation of Google AI Models <sup>26.1</sup>

The ability to work directly with Google AI models has been introduced by enabling [direct instantiation of the GoogleAiModel class](https://reference.aspose.com/words/python-net/aspose.words.ai/googleaimodel/__init__/) in the **Aspose.Words.AI** namespace.

#### Improved OpenAiModel Capabilities <sup>26.3</sup>

The ability to create an instance of the [OpenAiModel](https://reference.aspose.com/words/python-net/aspose.words.ai/openaimodel/) class directly has been introduced, simplifying the integration of OpenAI-based AI features into document processing workflows.

### Supported Formats

#### New Docling JSON Export Format <sup>26.1</sup>

The ability to export documents to the **Docling JSON format** has been introduced.

### Converting, Loading, and Saving Documents

#### Improved PDF Logical Structure <sup>26.4</sup>

The ability to improve PDF logical structure by exporting node custom IDs to custom attributes during PDF export has been introduced.

### Rendering

#### Extended PDF Conformance Standards <sup>26.1</sup>

The **PdfSaveOptions** functionality has been extended by the [preserve_form_fields](https://reference.aspose.com/words/python-net/aspose.words.saving/pdfsaveoptions/preserve_form_fields/) property to be compatible with all PDF compliance standards (including PDF/A and PDF/UA).

#### EQ-matrix MathML Elements Rendering <sup>26.2</sup>

The rendering of EQ-matrix MathML elements has been improved to achieve higher visual fidelity in mathematical content.

#### Orientation And Rotation of Chart Titles and Axis Titles <sup>26.2</sup>

The ability to control the [orientation](https://reference.aspose.com/words/python-net/aspose.words.drawing.charts/charttitle/orientation/) and [rotation](https://reference.aspose.com/words/python-net/aspose.words.drawing.charts/charttitle/rotation/) of chart titles and axis titles has been introduced, allowing more flexible and precise chart layout customization.

#### Font Fallback Table for CJK Unified Ideographs Extension G range <sup>26.3</sup>

Rendering accuracy has been improved by updating the Microsoft Office font fallback table for the CJK Unified Ideographs Extension G range, ensuring more reliable font substitution when rendering documents containing these characters.

#### Enhanced Chart Rendering <sup>26.4</sup>

The ability to enhance chart rendering has been introduced by adding support for funnel chart [data labels](https://reference.aspose.com/words/python-net/aspose.words.drawing.charts/chartdatalabelcollection/), applying chart style settings to leader line rendering, and using locale IDs when rendering default axis titles in DrawingML charts.

### Other

* The handling of adjacent tables has been updated by implementing the latest Microsoft Word logic for merging or separating tables during layout processing. <sup>26.2</sup>
* The document optimization capabilities have been improved by extending the [join_runs_with_same_formatting](https://reference.aspose.com/words/python-net/aspose.words/document/join_runs_with_same_formatting/#default) method, enabling more comprehensive content merging. <sup>26.3</sup>

{{% alert color="primary" %}}

Learn more about [Aspose.Words for Python via .NET 26.1 Release Notes](https://releases.aspose.com/words/python/release-notes/2026/aspose-words-for-python-via-dotnet-26-1-release-notes/).

Learn more about [Aspose.Words for Python via .NET 26.2 Release Notes](https://releases.aspose.com/words/python/release-notes/2026/aspose-words-for-python-via-dotnet-26-2-release-notes/).

Learn more about [Aspose.Words for Python via .NET 26.3 Release Notes](https://releases.aspose.com/words/python/release-notes/2026/aspose-words-for-python-via-dotnet-26-3-release-notes/).

Learn more about [Aspose.Words for Python via .NET 26.4 Release Notes](https://releases.aspose.com/words/python/release-notes/2026/aspose-words-for-python-via-dotnet-26-4-release-notes/).

{{% /alert %}}

## Aspose.Words for Python via .NET 25.9, 25.10, 25.11, 25.12

Aspose.Words 25.9 enhances document loading reliability, expands shape and text formatting, and improves Markdown export with math support.

Aspose.Words 25.10 introduces enhancements to text and PDF exports and improves accessibility compliance.

Aspose.Words 25.11 expands AI integration capabilities, as well as enhances Markdown export.

Aspose.Words 25.12 improves rendering accuracy across PDF, HTML-Fixed, and SVG formats, adds support for Variable Fonts and Funnel charts, and enhances text orientation handling in field rendering.

### AI-powered Features

#### Configure AI Model Service Endpoints <sup>25.11</sup>

The ability to configure [AI model](https://reference.aspose.com/words/python-net/aspose.words.ai/aimodel/) service endpoints has been introduced by adding support for specifying [custom URLs](https://reference.aspose.com/words/python-net/aspose.words.ai/aimodel/url/) and [request timeouts](https://reference.aspose.com/words/python-net/aspose.words.ai/aimodel/timeout/), allowing greater flexibility in AI-powered integrations.

### Converting, Loading, and Saving Documents

#### Control How Corrupted Documents Are Opened <sup>25.9</sup>

The ability to control how corrupted documents are opened has been introduced by adding a new [recovery_mode](https://reference.aspose.com/words/python-net/aspose.words.loading/loadoptions/recovery_mode/) option.

#### Export Mathematical Equations to LaTeX Expression

The ability to export mathematical equations (Office Math) to LaTeX expressions has been introduced:

* For export to Markdown format using the [MarkdownSaveOptions.office_math_export_mode](https://reference.aspose.com/words/python-net/aspose.words.saving/markdownsaveoptions/office_math_export_mode/) property. <sup>25.9</sup>
* For export to TXT format using the [TxtSaveOptions.office_math_export_mode](https://reference.aspose.com/words/python-net/aspose.words.saving/txtsaveoptions/office_math_export_mode/) property. <sup>25.10</sup>

#### Improved Document Conversion Fidelity to Markdown <sup>25.11</sup>

The fidelity of document conversion to Markdown has been improved by enabling the [export of OfficeMath objects](https://reference.aspose.com/words/python-net/aspose.words.saving/markdownofficemathexportmode/) into LaTeX format, ensuring compatibility with MarkItDown renderers.

#### Control Floating Shape Tagging When Exporting to PDF <sup>25.10</sup>

A new save option [export_floating_shapes_as_inline_tag](https://reference.aspose.com/words/python-net/aspose.words.saving/pdfsaveoptions/export_floating_shapes_as_inline_tag/) has been added to provide precise control over the tagging of floating shapes as either inline or block-level elements, improving layout accuracy and accessibility.

#### PDF/UA Export & Accessibility <sup>25.10</sup>

Compliance with PDF/UA standards has been improved by correctly tagging horizontal rules as artifacts, enhancing a better experience for users of assistive technologies.

#### Handle Relative Hyperlinks When Exporting to PDF <sup>25.12</sup>

The ability to correctly resolve and handle relative hyperlinks when exporting to PDF has been introduced by adding Base URI processing during document export.

### Rendering

#### Fine-tune Shadow Effects <sup>25.9</sup>

The ability to fine-tune [shadow effects](https://reference.aspose.com/words/python-net/aspose.words.drawing/shadowformat/) has been enhanced by introducing new public properties.

#### Support for Variable Fonts When Saving Documents to SVG and Html-Fixed <sup>25.12</sup>

Robust support for Variable Fonts when saving documents to SVG and Html-Fixed formats has been added, ensuring that different font variations (including weight, width, and other parameters) defined within a single font file render correctly.

#### Render Funnel Charts <sup>25.12</sup>

The ability to render Funnel charts in documents has been added.

#### Render VerticalFarEast and HorizontalRotatedFarEast Text Orientations in EQ-field <sup>25.12</sup>

The ability to render **VERTICAL_FAR_EAST** and **HORIZONTAL_ROTATED_FAR_EAST** text orientations in EQ-field elements has been introduced.

{{% alert color="primary" %}}

Learn more about [Aspose.Words for Python via .NET 25.9 Release Notes](https://releases.aspose.com/words/python/release-notes/2025/aspose-words-for-python-via-dotnet-25-9-release-notes/).

Learn more about [Aspose.Words for Python via .NET 25.10 Release Notes](https://releases.aspose.com/words/python/release-notes/2025/aspose-words-for-python-via-dotnet-25-10-release-notes/).

Learn more about [Aspose.Words for Python via .NET 25.11 Release Notes](https://releases.aspose.com/words/python/release-notes/2025/aspose-words-for-python-via-dotnet-25-11-release-notes/).

Learn more about [Aspose.Words for Python via .NET 25.12 Release Notes](https://releases.aspose.com/words/python/release-notes/2025/aspose-words-for-python-via-dotnet-25-12-release-notes/).

{{% /alert %}}

## See Also

{{% alert color="primary" %}}

This page contains the latest release news for the past 2 years. For details on earlier releases, see the [Release Notes'](https://releases.aspose.com/words/python/release-notes/) pages in the relevant sections.

{{% /alert %}}