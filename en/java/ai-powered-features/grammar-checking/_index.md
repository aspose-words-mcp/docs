---
title: AI Grammar Checking
second_title: Aspose.Words for Java
articleTitle: Grammar Checking
linktitle: Grammar Checking
type: docs
weight: 40
description: "Check a document grammar. Aspose.Words for Java allows users to check grammar and detect errors in documents using OpenAI, Google, and Claude models."
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/grammar-checking/
timestamp: 2025-03-17-19-00-00
---

Checking grammar in documents is important to ensure clarity, professionalism, and accuracy. Well-written documents leave a positive impression and avoid misunderstandings. Grammar checks help identify and correct errors quickly, saving time and improving quality.

Aspose.Words allows users to check grammar and detect errors in documents using the OpenAI, Google, and Claude models' families listed in the [AiModelType](https://reference.aspose.com/words/java/com.aspose.words/aimodeltype/) enumeration. Use the [checkGrammar()](https://reference.aspose.com/words/java/com.aspose.words/iaimodeltext/#checkGrammar-com.aspose.words.Document-com.aspose.words.CheckGrammarOptions) method to analyze the text in a document and highlights grammatical problems.

The following code example shows how to use the GPT-4o mini model in Aspose.Words to check grammar:

{{< highlight java >}}
 Document doc = new Document("Big document.docx");

 String apiKey = System.getenv("API_KEY");
 // Use OpenAI generative language models.
 IAiModelText model = (OpenAiModel)AiModel.create(AiModelType.GPT_4_O_MINI).withApiKey(apiKey);

 CheckGrammarOptions grammarOptions = new CheckGrammarOptions();
 grammarOptions.setImproveStylistics(true);

 Document proofedDoc = model.checkGrammar(doc, grammarOptions);
 proofedDoc.save("AI.AiGrammar.docx");
{{< /highlight >}}

{{% alert color="primary" %}}

Checking grammar with Aspose.Words improves the quality of your work and makes it easy to integrate proofreading into your projects. For more information, check the [Java API documentation](https://reference.aspose.com/words/java/com.aspose.words/).

{{% /alert %}}

------ 

## FAQ

1. **Q:** Which AI models can I use for grammar checking with Aspose.Words for Java?  
   **A:** The `AiModelType` enumeration lists all supported families, including OpenAI (e.g., `GPT_4_O_MINI`, `GPT_4_TURBO`), Google (e.g., `GEMINI_PRO_LATEST`), and Anthropic Claude models. Choose the model that fits your accuracy and cost requirements.

2. **Q:** How do I provide the API key for the selected AI model?  
   **A:** Create the model instance with `AiModel.create(...).withApiKey(yourKey)`. The key can be read from an environment variable, configuration file, or any secure store. Example:  
   ```java
   String apiKey = System.getenv("API_KEY");
   IAiModelText model = (OpenAiModel)AiModel.create(AiModelType.GPT_4_O_MINI).withApiKey(apiKey);
   ```

3. **Q:** Can I run `checkGrammar` on a document that is loaded from a stream instead of a file path?  
   **A:** Yes. Load the document from any `InputStream` using `new Document(inputStream)`, then pass the `Document` object to `model.checkGrammar`. The API works the same regardless of how the document was created.

4. **Q:** Does the `checkGrammar` method modify the original `Document` instance?  
   **A:** No. `checkGrammar` returns a new `Document` containing the proofed content, leaving the original document unchanged. Save the returned document to persist the corrections.

5. **Q:** What licensing is required to use the AI grammar‑checking feature?  
   **A:** You need a valid Aspose.Words for Java license for the core library and a separate subscription or API key for the chosen AI service (OpenAI, Google, or Claude). The AI models are billed by the provider, not by Aspose. Ensure both licenses are active before invoking `checkGrammar`.