---
title: Translate a Document
second_title: Aspose.Words for C++
articleTitle: Translate a Document
linktitle: Translate a Document
type: docs
weight: 30
description: "Translate a document. Aspose.Words for C++ simplifies document translation using Google AI models, allowing you to specify the target language."
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/translate-a-document/
timestamp: 2025-03-17-19-00-00
---

Document translation is a frequently needed option in the age of high digitalization. Aspose.Words supports document translation using *Google* generative language models, which allows developers to translate texts content into more than 300 languages.

Use the [Translate](https://reference.aspose.com/words/cpp/aspose.words.ai/aimodel/translate/) method to translate your documents into any language represented in the [Language](https://reference.aspose.com/words/cpp/aspose.words.ai/language/) enumeration. Note that if the source document contains several languages, the Google AI-based model will be able to translate all supported languages. If the model cannot recognize the language in some text fragments, then you will be returned a document with these untranslated fragments and with the rest of the text translated.

The following code example shows how to use the *Gemini Flash Latest* model in Aspose.Words to translate a document into Arabic:

{{< highlight cpp >}}
void AiTranslate()
{
    auto doc = MakeObject<Document>(MyDir + u"Document.docx");

    SharedPtr<AiModel> model = AiModel::Create(AiModelType::GeminiFlashLatest)->WithApiKey(u"API_KEY");

    auto translatedDoc = model->Translate(doc, Language::Arabic);
    translatedDoc->Save(ArtifactsDir + u"AI.AiTranslate.docx");
}
{{< /highlight >}}

{{% alert color="primary" %}}

Translating documents with Aspose.Words saves time and makes it easy to integrate translation functionality into your projects. For more information, check the [Aspose.Words.AI](https://reference.aspose.com/words/cpp/aspose.words.ai/) API documentation.

{{% /alert %}}

------ 

## FAQ

1. **Q:** Which languages can I translate a document into with Aspose.Words AI?  
   **A:** The `Translate` method supports any language defined in the `Aspose::Words::AI::Language` enumeration, which currently includes more than 300 languages provided by Google generative models.

2. **Q:** Do I need a Google API key to use the `Translate` method?  
   **A:** Yes. When creating a Google model you must supply a valid Google API key via `WithApiKey`. The key authorizes calls to the underlying Google AI service.

3. **Q:** How does the `Translate` method handle documents that contain multiple source languages?  
   **A:** The Google AI model attempts to detect the language of each text fragment. It translates each fragment to the target language independently, so mixed-language source documents are supported.

4. **Q:** What happens if the AI model cannot recognize the language of a text fragment?  
   **A:** Unrecognizable fragments are left unchanged in the output document, while all other recognizable text is translated. This allows you to identify and handle those fragments manually if needed.

5. **Q:** Can I use a different Google AI model for translation?

   **A:** Yes. Select another supported Google model from `AiModelType` when calling `AiModel::Create`. The rest of the code remains the same.
