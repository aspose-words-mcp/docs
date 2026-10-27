---
title: AI Models Supported by Aspose.Words
second_title: Aspose.Words for C++
articleTitle: Supported AI Models
linktitle: Supported AI Models
type: docs
weight: 10
description: "Aspose.Words for C++ supports OpenAI, Google, and Claude models for document summarization, translation, and grammar checking."
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/supported-ai-models/
timestamp: 2025-08-07-08-12-25
---

Aspose.Words now leverages advanced AI models to enhance document processing and analysis. With the Aspose.Words.AI namespace, developers can access AI-powered features such as document summarization and analysis, document translation, and grammar checking by integrating generative language models from industry leaders.

## Supported Model Types

Aspose.Words library currently supports integration with:

* OpenAI,
* Google,
* and Claude models' families.

These models bring powerful capabilities for working with documents. By enabling seamless interaction with these AI tools, Aspose.Words simplifies complex tasks and enhances productivity for developers.

{{% alert color="primary" %}}

The full list of supported model types is listed in the [AiModelType](https://reference.aspose.com/words/cpp/aspose.words.ai/aimodeltype/) enumeration.

{{% /alert %}}

You can create a model instance using the [Create](https://reference.aspose.com/words/cpp/aspose.words.ai/aimodel/create/) method of the [AiModel](https://reference.aspose.com/words/cpp/aspose.words.ai/aimodel/) class.

The following code example shows how to create a new instance of **AiModel** class:

{{< highlight cpp >}}
SharedPtr<AiModel> model = AiModel::Create(AiModelType::Gpt4OMini)->WithApiKey(u"API_KEY");
{{< /highlight >}}

{{% alert color="primary" %}}

For more information, check the [Aspose.Words.AI](https://reference.aspose.com/words/cpp/aspose.words.ai/) API documentation.

{{% /alert %}}

## Using Self-hosted LLM Implementations

With Aspose.Words, developers can also integrate self-hosted LLMs (Large Language Models), providing an alternative to OpenAI/Anthropic/Google's hosted services.

The following code example shows how to configure an OpenAI-compatible endpoint:

{{< highlight cpp >}}
void ChangeDefaultUrl()
{
    SharedPtr<AiModel> model = AiModel::Create(AiModelType::Gpt4OMini)->WithApiKey(u"API_KEY");
    model->set_Url(u"https://my.a.com/");
}
{{< /highlight >}}
