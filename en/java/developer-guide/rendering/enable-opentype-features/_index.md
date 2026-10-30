---
title: Enable OpenType Features in Java
second_title: Aspose.Words for Java
articleTitle: Enable OpenType Features
linktitle: Enable OpenType Features
description: "Advanced typography features using Java."
type: docs
weight: 25
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/enable-opentype-features/
aliases: [/java/how-to-use-opentype-features/]
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to enable OpenType font features such as ligatures and stylistic sets.

{{% /alert %}}

OpenType is a font format, introduced to provide better support for international languages and writing systems as compared to PostScript and TrueType. The layout features of OpenType are commonly known as OpenType features. Aspose.Words.Shaping.HarfBuzz package provides support for OpenType features in Aspose.Words using HarfBuzz text shaping engine.

Aspose.Words is capable of using text shaper objects provided externally. A text shaper represents a font and computes shaping information for a text. A document typically refers to multiple fonts thus a text shaper factory is necessary. This package contains an implementation of a text shaper factory utilized by Aspose.Words.Layout.LayoutOptions.`getTextShaperFactory()` property.

{{% alert color="primary" %}}

Text shaping is only performed when exporting to PDF or XPS formats.

{{% /alert %}}

In a typical application single instance of a text shaper factory is shared among all document instances. Whenever text shaper is created a font file is accessed. Parsing a font file is an expensive operation thus caching is recommended. Aspose.Words implements BasicTextShaperCache class which wraps text shaper factory implementation and caches text shaper instances returned by the wrapped factory.

The following code example shows you how to turn on support of OpenType features.

{{< gist "aspose-words-gists" "046c81231cf8e3ba6df901a38b9c861c" "open-type-features.java" >}}

------

## FAQ

1. **Q:** How do I enable OpenType features for a document?  
   **A:** Set the text shaper factory: `doc.getLayoutOptions().setTextShaperFactory(HarfBuzzTextShaperFactory.getInstance())`. `HarfBuzzTextShaperFactory` comes from the HarfBuzz plugin package, and its `getInstance()` returns a `BasicTextShaperCache` that wraps the HarfBuzz factory. This activates HarfBuzz‑based shaping for all fonts used in the document.

2. **Q:** Are OpenType features applied when exporting to formats other than PDF or XPS?  
   **A:** No. OpenType shaping is currently performed only for PDF and XPS output. Other formats (e.g., DOCX, RTF) will not use the HarfBuzz shaper.

3. **Q:** What can I do to improve performance when using OpenType features?  
   **A:** Reuse a single `BasicTextShaperCache` (or a custom cache) across all documents. The cache avoids repeatedly parsing the same font files, which is an expensive operation.

4. **Q:** Can I provide my own text shaper implementation instead of the built‑in HarfBuzz one?  
   **A:** Yes. Implement the `ITextShaperFactory` interface, create a factory that returns your custom `ITextShaper` instances, and assign it with `doc.getLayoutOptions().setTextShaperFactory(...)`. Aspose.Words will then use your shaper for layout.

5. **Q:** How should I share a text shaper factory among multiple documents?  
   **A:** Instantiate the factory (or cache) once, then set it on each document's `LayoutOptions`. Because the factory is thread‑safe, you can safely reuse it across parallel document processing tasks.