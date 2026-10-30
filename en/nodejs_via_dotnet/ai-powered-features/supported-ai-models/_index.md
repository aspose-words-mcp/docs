---
title: AI Models Supported by Aspose.Words
second_title: Aspose.Words for Node.js via .NET
articleTitle: Supported AI Models
linktitle: Supported AI Models
type: docs
weight: 10
description: "Aspose.Words for Node.js supports OpenAI and Google AI models for summarization and translation documents. Use Aspose.Words with Gpt-4o, Gpt-4o mini, Gpt-4 Turbo, GPT-3.5 Turbo, Gemini 1.5 Flash, Gemini 1.5 Flash-8B, Gemini 1.5 Pro."
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/supported-ai-models/
timestamp: 2025-05-12-12-00-00
---

Aspose.Words now leverages advanced AI models to enhance document processing and analysis. With the Aspose.Words.AI namespace, developers can access features that utilize AI for tasks like document summarization and analysis, integrating generative language models from industry leaders.

Aspose.Words library currently supports integration with OpenAI and Google generative language models. These models bring powerful capabilities for working with documents. By enabling seamless interaction with these AI tools, Aspose.Words simplifies complex tasks and enhances productivity for developers.

You can create a model instance using the [create](https://reference.aspose.com/words/nodejs-net/aspose.words.ai/aimodel/create/) method of the [AiModel](https://reference.aspose.com/words/nodejs-net/aspose.words.ai/aimodel/) class. The full list of supported model types is listed in the [AiModelType](https://reference.aspose.com/words/nodejs-net/aspose.words.ai/aimodeltype/) enumeration.

The following code example shows how to create a new instance of **AiModel** class.

{{< highlight js >}}
// Use Google generative language models.
let geminiModel = aw.AI.AiModel.createGemini15Flash();
// Use OpenAI generative language models.
let gptModel = aw.AI.AiModel.createGpt4OMini();
 ...
{{< /highlight >}}

{{% alert color="primary" %}}

For more information, check the [aspose.words.ai](https://reference.aspose.com/words/nodejs-net/aspose.words.ai/) API documentation.

{{% /alert %}}

------ 

## FAQ

1. **Q:** Which AI model types are supported by Aspose.Words for Node.js?  
   **A:** Aspose.Words supports OpenAI models, Google Gemini models, and Anthropic Claude models. The complete list is defined in the `AiModelType` enumeration.

2. **Q:** How do I create an `AiModel` instance for a specific provider?  
   **A:** Use the static factory methods on `AiModel`. For example, `aw.AI.AiModel.createGpt4Turbo()` creates an OpenAI model, while `aw.AI.AiModel.createGemini15Flash()` creates a Google Gemini model. The returned object can then be passed to AI‑enabled APIs such as document summarization.

3. **Q:** Where do I configure the API key or authentication for the selected model?  
   **A:** After creating the model, set the appropriate credentials on the instance, e.g., `model.setApiKey("YOUR_OPENAI_KEY")` for OpenAI or `model.setApiKey("YOUR_GOOGLE_KEY")` for Gemini. The keys are kept only in memory and are not persisted by Aspose.Words.

4. **Q:** Can I use AI features with the trial version of Aspose.Words for Node.js?  
   **A:** Yes, the trial license enables all AI functionality, but documents generated with a trial license will contain a watermark indicating that a trial version is being used.

5. **Q:** Do I need a separate Aspose.Words license to use AI models?  
   **A:** An Aspose.Words license is required for production use of any feature, including AI. The license does not affect which AI models are available; it only removes evaluation limitations.