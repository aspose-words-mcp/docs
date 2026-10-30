---
title: Summarize a Document
second_title: Aspose.Words for .NET
articleTitle: Summarize a Document
linktitle: Summarize a Document
type: docs
weight: 20
description: "Summarize a document. Aspose.Words for .NET simplifies document summarization using OpenAI and Google AI models by allowing you to specify the summary length."
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/summarize-a-document/
timestamp: 2025-03-17-19-00-00
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to generate document summaries automatically.

{{% /alert %}}

Summarizing documents is a valuable tool for content review, quick insights, or preparing abstracts. Aspose.Words supports document summarization using AI-powered models, making it easier to process long text. This feature, available in the [Aspose.Words.AI](https://reference.aspose.com/words/net/aspose.words.ai/) namespace, integrates advanced generative language models from *OpenAI* and *Google*, as well as *Claude's* anthropic generative language models. The list of supported models is available in the [AiModelType](https://reference.aspose.com/words/net/aspose.words.ai/aimodeltype/) enumeration. 

You can specify various options for summarizing document content. Use the [Summarize](https://reference.aspose.com/words/net/aspose.words.ai/aimodel/summarize/) method to generate a summary of your document. You can also set summary length using the [SummaryLength](https://reference.aspose.com/words/net/aspose.words.ai/summarizeoptions/summarylength/) property.

With Aspose.Words, implementing document summarization is straightforward. The following code example shows how to summarize a document using GPT-4o model:

{{< gist "aspose-words-gists" "1e379bedb2b759c1be24c64aad54d13d" "ai-summarize.cs" >}}

{{% alert color="primary" %}}

Summarizing documents with Aspose.Words saves time and helps you focus on essential information. For more information, check the [Aspose.Words.AI](https://reference.aspose.com/words/net/aspose.words.ai/) API documentation.

{{% /alert %}}

------

## FAQ

1. **Q:** Which document formats can be summarized with Aspose.Words AI?  
   **A:** Any format that Aspose.Words can load can be summarized, including DOC, DOCX, RTF, HTML, EPUB, and PDF (when loaded as a Word document). The summarization engine works on the internal document model, so the original file type does not matter as long as it is supported by Aspose.Words.

2. **Q:** What AI models are available for summarization?  
   **A:** The `AiModelType` enumeration lists all supported models, such as `Gpt4O`, `GeminiProLatest`, and `Claude35Sonnet`. You select the model when you create it, for example `AiModel model = AiModel.Create(AiModelType.Gpt4OMini).WithApiKey(apiKey);`, and then call `model.Summarize(doc, options)`.

3. **Q:** Do I need a separate license to use the summarization feature?  
   **A:** No additional license is required beyond a regular Aspose.Words license. The AI functionality is included in the Aspose.Words for .NET product, but you must have an active subscription that includes the AI add‑on. Licensing for older versions is retro‑compatible as long as the version supports the AI namespace.

4. **Q:** How can I control the length of the generated summary?  
   **A:** Use the `SummaryLength` property of `SummarizeOptions`. It accepts values from the `SummaryLength` enumeration (`VeryShort`, `Short`, `Medium`, `Long`, `VeryLong`); each value stands for an approximate number of sentences (for example, `Short` is 3–4 sentences). The chosen length influences how much content the model returns.

5. **Q:** What happens if the document contains no textual content?  
   **A:** `Summarize` returns a `Document`, not a string. To avoid an unnecessary API call, check the document's text length beforehand using `Document.GetText()` and skip empty documents.