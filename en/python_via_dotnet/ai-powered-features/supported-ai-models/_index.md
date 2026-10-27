---
title: AI Models Supported by Aspose.Words
second_title: Aspose.Words for Python via .NET
articleTitle: Supported AI Models
linktitle: Supported AI Models
type: docs
weight: 10
description: "Aspose.Words for Python supports OpenAI, Google, and Claude models for document summarization, translation, and grammar checking."
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/supported-ai-models/
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page outlines the AI model families supported by Aspose.Words for Python via .NET and explains how to create `AiModel` instances using the `AiModelType` enumeration.
{{% /alert %}}

Aspose.Words now leverages advanced AI models to enhance document processing and analysis. With the Aspose.Words.AI namespace, developers can access AI‑powered features such as document summarization and analysis, document translation, and grammar checking by integrating generative language models from industry leaders.

## Supported Model Types

Aspose.Words library currently supports integration with:

* OpenAI,
* Google,
* and Claude models' families.

These models bring powerful capabilities for working with documents. By enabling seamless interaction with these AI tools, Aspose.Words simplifies complex tasks and enhances productivity for developers.

{{% alert color="primary" %}}

The full list of supported model types is listed in the [AiModelType](https://reference.aspose.com/words/python-net/aspose.words.ai/aimodeltype/) enumeration.

{{% /alert %}}

You can create a model instance using the [create](https://reference.aspose.com/words/python-net/aspose.words.ai/aimodel/create/) method of the [AiModel](https://reference.aspose.com/words/python-net/aspose.words.ai/aimodel/) class. 

The following code example shows how to create a new instance of **AiModel** class.

{{< highlight python >}}
model = aw.ai.AiModel.create(aw.ai.AiModelType.GPT_4O_MINI).with_api_key("API_KEY")
{{< /highlight >}}

{{% alert color="primary" %}}

For more information, check the [aspose.words.ai](https://reference.aspose.com/words/python-net/aspose.words.ai/) API documentation.

{{% /alert %}}

------ 

## FAQ

1. **Q:** Which AI model families are currently supported by Aspose.Words for Python?  
   **A:** Aspose.Words supports models from OpenAI, Google (Gemini), and Anthropic (Claude). The available models are listed in the `AiModelType` enumeration.

2. **Q:** How do I create an `AiModel` instance for a particular model type?  
   **A:** Use the static `create` method of the `AiModel` class and pass a value from the `AiModelType` enumeration. Example:  

   ```python
   model = aw.ai.AiModel.create(aw.ai.AiModelType.GPT_4O_MINI).with_api_key("API_KEY")
   ```

3. **Q:** Where can I find the current list of supported model types?
   **A:** Refer to the [AiModelType](https://reference.aspose.com/words/python-net/aspose.words.ai/aimodeltype/) API reference for the current list of supported values.

4. **Q:** Is it possible to switch the AI model used for summarization at runtime?  
   **A:** Create a new `AiModel` with the desired `AiModelType` and use that model to call the summarization API.

5. **Q:** How do I know which current provider models are available?
   **A:** Check the `AiModelType` API reference because the supported model list evolves as providers update their services.
