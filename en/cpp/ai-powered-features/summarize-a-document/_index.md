---
title: Summarize a Document
second_title: Aspose.Words for C++
articleTitle: Summarize a Document
linktitle: Summarize a Document
type: docs
weight: 20
description: "Summarize a document. Aspose.Words for C++ simplifies document summarization using OpenAI and Google AI models by allowing you to specify the summary length."
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/summarize-a-document/
timestamp: 2025-03-17-19-00-00
---

Summarizing documents is a valuable tool for content review, quick insights, or preparing abstracts. Aspose.Words supports document summarization using AI-powered models, making it easier to process long text. This feature, available in the [Aspose.Words.AI](https://reference.aspose.com/words/cpp/aspose.words.ai/) namespace, integrates advanced generative language models from *OpenAI* and *Google*, as well as *Claude's* anthropic generative language models. The list of supported models is available in the [AiModelType](https://reference.aspose.com/words/cpp/aspose.words.ai/aimodeltype/) enumeration.

You can specify various options for summarizing document content. Use the [Summarize](https://reference.aspose.com/words/cpp/aspose.words.ai/aimodel/summarize/) method to generate a summary of your document. You can also set summary length using the [get_SummaryLength()](https://reference.aspose.com/words/cpp/aspose.words.ai/summarizeoptions/get_summarylength/) property.

With Aspose.Words, implementing document summarization is straightforward. The following code example shows how to summarize a document using GPT-4o model:

{{< highlight cpp >}}
void AiSummarize()
{
    auto firstDoc = MakeObject<Document>(MyDir + u"Big document.docx");
    auto secondDoc = MakeObject<Document>(MyDir + u"Document.docx");

    SharedPtr<AiModel> model = AiModel::Create(AiModelType::Gpt4OMini)->WithApiKey(u"API_KEY");

    auto options = MakeObject<SummarizeOptions>();

    options->set_SummaryLength(SummaryLength::Short);
    auto firstDocumentSummary = model->Summarize(firstDoc, options);
    firstDocumentSummary->Save(ArtifactsDir + u"AI.AiSummarize.One.docx");

    System::ArrayPtr<System::SharedPtr<Document>> documents = System::MakeArray<System::SharedPtr<Document>>(2);
    documents[0] = firstDoc;
    documents[1] = secondDoc;

    options->set_SummaryLength(SummaryLength::Long);
    auto multiDocumentSummary = model->Summarize(documents, options);
    multiDocumentSummary->Save(ArtifactsDir + u"AI.AiSummarize.Multi.docx");
}
{{< /highlight >}}

{{% alert color="primary" %}}

Summarizing documents with Aspose.Words saves time and helps you focus on essential information. For more information, check the [Aspose.Words.AI](https://reference.aspose.com/words/cpp/aspose.words.ai/) API documentation.

{{% /alert %}}

------ 

## FAQ

1. **Q:** How do I choose which AI model to use for summarization?  
   **A:** Select a model from the `AiModelType` enumeration and create it with `AiModel::Create`. The supported families include OpenAI, Google (Gemini), and Anthropic (Claude). Choose a model available through your provider account.

2. **Q:** Can I summarize multiple documents in a single call?  
   **A:** Yes. Pass an array of `Document` objects to the `Summarize` method. It returns a single `Document` containing the combined summary.

3. **Q:** How can I control the length of the generated summary?  
   **A:** Set the `SummaryLength` property of `SummarizeOptions` to `VeryShort`, `Short`, `Medium`, `Long`, or `VeryLong`.

4. **Q:** What authentication is required for AI models?

   **A:** Provide an API key for the selected OpenAI, Google, or Anthropic service via `WithApiKey`. OpenAI models also allow optional organization and project settings using `WithOrganization` and `WithProject`.

5. **Q:** Is it possible to summarize a document without using AI models?  
   **A:** The `Summarize` API is built on AI models, so it requires an AI provider. For simple text extraction or keyword summarization, you would need to implement custom logic using other Aspose.Words features such as `DocumentVisitor` or manual text processing.
