---
title: AI Grammar Checking
second_title: Aspose.Words for C++
articleTitle: Grammar Checking
linktitle: Grammar Checking
type: docs
weight: 40
description: "Check a document grammar. Aspose.Words for C++ allows users to check grammar and detect errors in documents using OpenAI, Google, and Claude models."
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/grammar-checking/
timestamp: 2025-03-17-19-00-00
---

Checking grammar in documents is important to ensure clarity, professionalism, and accuracy. Well-written documents leave a positive impression and avoid misunderstandings. Grammar checks help identify and correct errors quickly, saving time and improving quality.

Aspose.Words allows users to check grammar and detect errors in documents using the OpenAI, Google, and Claude model families listed in the [AiModelType](https://reference.aspose.com/words/cpp/aspose.words.ai/aimodeltype/) enumeration. Use the [CheckGrammar](https://reference.aspose.com/words/cpp/aspose.words.ai/aimodel/checkgrammar/) method, available in the [Aspose.Words.AI](https://reference.aspose.com/words/cpp/aspose.words.ai/) namespace. **CheckGrammar** returns a new document with checked grammar.

The following code example shows how to use the GPT‑4o mini model in Aspose.Words to check grammar:

{{< highlight cpp >}}
void AiGrammar()
{
    auto doc = MakeObject<Document>(MyDir + u"Big document.docx");

    SharedPtr<AiModel> model = AiModel::Create(AiModelType::Gpt4OMini)->WithApiKey(u"API_KEY");

    auto grammarOptions = MakeObject<CheckGrammarOptions>();
    grammarOptions->set_ImproveStylistics(true);

    auto proofedDoc = model->CheckGrammar(doc, grammarOptions);
    proofedDoc->Save(ArtifactsDir + u"AI.AiGrammar.docx");
}
{{< /highlight >}}

{{% alert color="primary" %}}

Checking grammar with Aspose.Words improves the quality of your work and makes it easy to integrate proofreading into your projects. For more information, check the [Aspose.Words.AI](https://reference.aspose.com/words/cpp/aspose.words.ai/) API documentation.

{{% /alert %}}

------ 

## FAQ

1. **Q:** Which AI models can be used with `CheckGrammar`?  
   **A:** The `AiModelType` enumeration includes OpenAI (e.g., GPT‑4o mini), Google (Gemini), and Anthropic Claude families. Choose the model that fits your needs and create it via `AiModel::Create`.

2. **Q:** How do I provide the API key for the selected AI model?  
   **A:** After creating the model instance, call `WithApiKey(u"YOUR_API_KEY")` on the `AiModel` object, as shown in the code example. The key must be valid for the chosen provider.

3. **Q:** Do I need an additional license to use the AI features in Aspose.Words for C++?  
   **A:** No separate license is required; the AI functionality is part of the standard Aspose.Words for C++ library. However, you must have a valid subscription for the external AI service (OpenAI, Google, etc.) whose API you are calling.

4. **Q:** Can I improve the stylistic suggestions returned by `CheckGrammar`?  
   **A:** Yes. Set `CheckGrammarOptions::set_ImproveStylistics(true)` to enable additional stylistic improvements beyond basic grammar corrections.

5. **Q:** What happens if the document is very large?  
   **A:** `CheckGrammar` processes the document in chunks internally, but extremely large files may increase latency or exceed provider request limits. Consider splitting the document or adjusting the provider's request size settings if you encounter time‑outs.
