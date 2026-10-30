---
title: Translate a Document
second_title: Aspose.Words for Node.js via .NET
articleTitle: Translate a Document
linktitle: Translate a Document
type: docs
weight: 30
description: "Translate a document. Aspose.Words for Node.js via .NET simplifies document translation using AI models, allowing you to specify the target language."
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/translate-a-document/
timestamp: 2025-05-16-12-00-00
---

Document translation is a frequently needed option in the age of high digitalization. Aspose.Words supports document translation using *Google*, *OpenAI* and *Anthropic* generative language models, which allows developers to translate texts content into more than 300 languages.

Use the [translate](https://reference.aspose.com/words/nodejs-net/aspose.words.ai/aimodel/translate/) method to translate your documents into any language represented in the [Language](https://reference.aspose.com/words/nodejs-net/aspose.words.ai/language/) enumeration. Note that if the source document contains several languages, the AI-based model will be able to translate all supported languages. If the model cannot recognize the language in some text fragments, then you will be returned a document with these untranslated fragments and with the rest of the text translated.

The following code example shows how to use the *Gemini 1.5 Flash* model in Aspose.Words to translate a document into Arabic:

{{< gist "aspose-words-gists" "757cf7d3534a39730cf3290d418681ab" "ai-translate.js" >}}

{{% alert color="primary" %}}

Translating documents with Aspose.Words saves time and makes it easy to integrate translation functionality into your projects. For more information, check the [Aspose.Words.AI](https://reference.aspose.com/words/nodejs-net/aspose.words.ai/) API documentation.

{{% /alert %}}

------ 

## FAQ

1. **Q:** How do I translate a document using Aspose.Words for Node.js via .NET?  
   **A:** Call the `translate` method of an `AiModel` instance (e.g., created with `aw.AI.AiModel.createGemini15Flash()`), passing the source `Document` and a target language from the `Language` enumeration. The method returns a new `Document` containing the translated content.

2. **Q:** Which AI models can be used for translation?  
   **A:** Aspose.Words supports models from Google, OpenAI, and Anthropic. The example uses the Gemini 1.5 Flash model, but you can select any supported model by creating it with the corresponding `AiModel` factory method (e.g., `aw.AI.AiModel.createGpt4OMini()`) and calling `translate` on that model.

3. **Q:** What happens if the source document contains multiple languages?  
   **A:** The translation engine attempts to detect each language fragment and translate it to the target language. Fragments that cannot be recognized remain unchanged in the output document.

4. **Q:** Why are some parts of my document not translated?  
   **A:** Untranslated fragments may be due to unsupported source languages, extremely short text that the model cannot identify, or formatting that interferes with language detection. Verify that the source language is among the supported list and consider preprocessing the document to isolate translatable text.

5. **Q:** Do I need a separate license for the translation feature?  
   **A:** No additional Aspose.Words license is required. However, you must have valid credentials (API key, token, etc.) for the chosen AI provider (Google, OpenAI, or Anthropic) because the translation is performed by their external service.