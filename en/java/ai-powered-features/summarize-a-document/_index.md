---
title: Summarize a Document
second_title: Aspose.Words for Java
articleTitle: Summarize a Document
linktitle: Summarize a Document
type: docs
weight: 20
description: "Summarize a document. Aspose.Words for Java simplifies document summarization using OpenAI and Google AI models by allowing you to specify the summary length."
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/summarize-a-document/
timestamp: 2025-03-17-19-00-00
---

Summarizing documents is a valuable tool for content review, quick insights, or preparing abstracts. Aspose.Words supports document summarization using AI-powered models, making it easier to process long text. This feature, available in the AI-based Aspose.Words functionality, integrates advanced generative language models from *OpenAI* and *Google*, as well as *Claude's* anthropic generative language models. The list of supported models is available in the [AiModelType](https://reference.aspose.com/words/java/com.aspose.words/aimodeltype/) enumeration.

You can specify various options for summarizing document content. Use the [summarize()](https://reference.aspose.com/words/java/com.aspose.words/iaimodeltext/#summarize-com.aspose.words.Document-com.aspose.words.SummarizeOptions) method to generate a summary of your document. You can also set summary length using the [getSummaryLength()](https://reference.aspose.com/words/java/com.aspose.words/summarizeoptions/#getSummaryLength) property.

With Aspose.Words, implementing document summarization is straightforward. The following code example shows how to summarize a document using GPT-4o model:

{{< highlight java >}}
Document firstDoc = new Document(getMyDir() + "Big document.docx");
 Document secondDoc = new Document(getMyDir() + "Document.docx");

 String apiKey = System.getenv("API_KEY");
 // Use OpenAI or Google generative language models.
 IAiModelText model = (IAiModelText)AiModel.create(AiModelType.GPT_4_O_MINI).withApiKey(apiKey);

 SummarizeOptions options = new SummarizeOptions();

 options.setSummaryLength(SummaryLength.SHORT);
 Document oneDocumentSummary = model.summarize(firstDoc, options);
 oneDocumentSummary.save(getArtifactsDir() + "AI.AiSummarize.One.docx");

 options.setSummaryLength(SummaryLength.LONG);
 Document multiDocumentSummary = model.summarize(new Document[] { firstDoc, secondDoc }, options);
 multiDocumentSummary.save(getArtifactsDir() + "AI.AiSummarize.Multi.docx");
{{< /highlight >}}

{{% alert color="primary" %}}

Summarizing documents with Aspose.Words saves time and helps you focus on essential information. For more information, check the [Java API documentation](https://reference.aspose.com/words/java/com.aspose.words/).

{{% /alert %}}