---
title: Summarize a Document
second_title: Aspose.Words for Python via .NET
articleTitle: Summarize a Document
linktitle: Summarize a Document
type: docs
weight: 20
description: "Summarize a document. Aspose.Words for Python simplifies document summarization using OpenAI and Google AI models by allowing you to specify the summary length."
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/summarize-a-document/
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page demonstrates how to use Aspose.Words for Python via .NET's AI capabilities to generate summaries of single or multiple documents, including selecting AI models and configuring summary length.
{{% /alert %}}

Summarizing documents is a valuable tool for content review, quick insights, or preparing abstracts. Aspose.Words supports document summarization using AI-powered models, making it easier to process long text. This feature, available in the [aspose.words.ai](https://reference.aspose.com/words/python-net/aspose.words.ai/) module, integrates advanced generative language models from *OpenAI* and *Google*, as well as *Claude's* anthropic generative language models. The list of supported models is available in the [AiModelType](https://reference.aspose.com/words/python-net/aspose.words.ai/aimodeltype/) enumeration.

You can specify various options for summarizing document content. Use the [summarize](https://reference.aspose.com/words/python-net/aspose.words.ai/aimodel/summarize/) method to generate a summary of your document. You can also set summary length using the [summary_length](https://reference.aspose.com/words/python-net/aspose.words.ai/summarizeoptions/summary_length/) property.

With Aspose.Words, implementing document summarization is straightforward. The following code example shows how to summarize a document using GPT-4o model:

{{< highlight python >}}
first_doc = aw.Document(MY_DIR + "Big document.docx")
second_doc = aw.Document(MY_DIR + "Document.docx")
api_key = system_helper.environment.Environment.get_environment_variable("API_KEY")
# Use an OpenAI generative language model.
model = aw.ai.AiModel.create(aw.ai.AiModelType.GPT_4O_MINI).with_api_key(api_key)
options = aw.ai.SummarizeOptions()
options.summary_length = aw.ai.SummaryLength.SHORT
one_document_summary = model.summarize(source_document=first_doc, options=options)
one_document_summary.save(ARTIFACTS_DIR + "AI.AiSummarize.One.docx")
options.summary_length = aw.ai.SummaryLength.LONG
multi_document_summary = model.summarize(source_documents=[first_doc, second_doc], options=options)
multi_document_summary.save(ARTIFACTS_DIR + "AI.AiSummarize.Multi.docx")
{{< /highlight >}}

{{% alert color="primary" %}}

Summarizing documents with Aspose.Words saves time and helps you focus on essential information. For more information, check the [aspose.words.ai](https://reference.aspose.com/words/python-net/aspose.words.ai/) API documentation.

{{% /alert %}}

------ 

## FAQ

1. **Q:** Which AI models can I use for document summarization?  
   **A:** Aspose.Words for Python via .NET supports OpenAI models (e.g., GPT‑4o, GPT‑4o‑mini), Google Gemini models, and Anthropic Claude models. The full list is defined in the `aw.ai.AiModelType` enumeration.

2. **Q:** How do I control the length of the generated summary?  
   **A:** Set the `summary_length` property of `aw.ai.SummarizeOptions` to `VERY_SHORT`, `SHORT`, `MEDIUM`, `LONG`, or `VERY_LONG`.

3. **Q:** Can I summarize more than one document in a single request?  
   **A:** Yes. Pass a list of `aw.Document` objects to the `summarize` method. It returns a single document containing the combined summary.

4. **Q:** Do I need a separate license for using the AI summarization feature?  
   **A:** No additional license is required beyond a valid Aspose.Words for Python via .NET license. The AI features are included with the standard product license.

5. **Q:** Is the summarization feature available on Linux platforms?  
   **A:** Yes. Aspose.Words for Python via .NET runs on Linux, and the AI summarization APIs work the same way as on Windows, provided the required runtime dependencies are installed.
