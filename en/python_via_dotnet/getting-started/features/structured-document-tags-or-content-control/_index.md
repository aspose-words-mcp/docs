---
title: Structured Document Tags
second_title: Aspose.Words for Python via .NET
articleTitle: Structured Document Tags or Content Control
linktitle: Structured Document Tags or Content Control
description: "Embed customer-defined semantics as well as its behavior and appearance into a document using Structured document tags (SDT or content control) in Python."
type: docs
weight: 50
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/structured-document-tags-or-content-control/
aliases: [/python/structured-document-tags-or-content-control/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}

*Purpose Summary. What is this page about?*

This page describes Structured Document Tags (content controls) in Aspose.Words for Python via .NET, including where they can be placed in a document and the various tag types supported.

{{% /alert %}}

Structured document tags (SDT or content control) allow to embed customer-defined semantics as well as its behavior and appearance into a document.

[StructuredDocumentTag](https://reference.aspose.com/words/python-net/aspose.words.markup/structureddocumenttag/) can occur in a document in the following places:

- Block-level – Among paragraphs and tables, as a child of a [Body](https://reference.aspose.com/words/python-net/aspose.words/body/), [HeaderFooter](https://reference.aspose.com/words/python-net/aspose.words/headerfooter/), [Comment](https://reference.aspose.com/words/python-net/aspose.words/comment/), [Footnote](https://reference.aspose.com/words/python-net/aspose.words.notes/footnote/) or a [Shape](https://reference.aspose.com/words/python-net/aspose.words.drawing/shape/) node.
- Row-level – Among rows in a table, as a child of a [Table](https://reference.aspose.com/words/python-net/aspose.words.tables/table/) node.
- Cell-level – Among cells in a table row, as a child of a [Row](https://reference.aspose.com/words/python-net/aspose.words.tables/row/) node.
- Inline-level – Among inline content inside, as a child of a [Paragraph](https://reference.aspose.com/words/python-net/aspose.words/paragraph/).
- Nested inside another [StructuredDocumentTag](https://reference.aspose.com/words/python-net/aspose.words.markup/structureddocumenttag/).

Aspose.Words supports the creation of following types of Structured document tags:

- DropDownList
- ComboBox
- Checkbox
- Date
- BuildingBlockGallery
- Group
- `Picture`
- RichText
- PlainText