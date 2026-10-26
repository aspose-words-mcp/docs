---
title: Translate a Document
second_title: Aspose.Words for Python via .NET
articleTitle: Translate a Document
linktitle: Translate a Document
type: docs
weight: 30
description: "Translate a document. Aspose.Words for Python simplifies document translation using Google AI models, allowing you to specify the target language."
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/translate-a-document/
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}

*Purpose Summary. What is this page about?*

This page shows how to translate a document with Aspose.Words for Python via .NET using Google generative AI models, including a code example with the Gemini Flash Latest model.

{{% /alert %}}

Document translation is a frequently needed option in the age of high digitalization. Aspose.Words supports document translation using *Google* generative language models, which allows developers to translate texts content into more than 300 languages.

Use the [translate](https://reference.aspose.com/words/python-net/aspose.words.ai/aimodel/translate/) method to translate your documents into any language represented in the [Language](https://reference.aspose.com/words/python-net/aspose.words.ai/language/) enumeration. Note that if the source document contains several languages, the Google AI-based model will be able to translate all supported languages. If the model cannot recognize the language in some text fragments, then you will be returned a document with these untranslated fragments and with the rest of the text translated.

The following code example shows how to use a Google Gemini model to translate a document into Arabic:

{{< highlight python >}}
doc = aw.Document(file_name=MY_DIR + "Document.docx")

api_key = system_helper.environment.Environment.get_environment_variable("API_KEY")
# Use Google generative language models.
model = aw.ai.AiModel.create(aw.ai.AiModelType.GEMINI_FLASH_LATEST).with_api_key(api_key)

translated_doc = model.translate(doc, aw.ai.Language.ARABIC)
translated_doc.save(file_name=ARTIFACTS_DIR + "AI.AiTranslate.docx")
{{< /highlight >}}

{{% alert color="primary" %}}

Translating documents with Aspose.Words saves time and makes it easy to integrate translation functionality into your projects. For more information, check the [Aspose.Words.AI](https://reference.aspose.com/words/python-net/aspose.words.ai/) API documentation.

{{% /alert %}}

------ 

## FAQ

1. **Q:** Which languages can be used with the `Translate` method?  
   **A:** The method supports any language defined in the `aw.ai.Language` enumeration, which currently includes over 300 languages provided by Google generative models.

2. **Q:** Do I need a Google API key to use document translation?  
   **A:** Yes. The AI model must be created with a valid Google API key using `with_api_key`. Without the key the translation request will fail.

3. **Q:** Can a single document contain multiple source languages and still be translated correctly?  
   **A:** Yes. The Google AI model attempts to detect each language segment in the source document and translates each fragment to the target language. Segments it cannot recognise remain untranslated.

4. **Q:** Is translation available for all file formats supported by Aspose.Words?  
   **A:** Translation works on any document that can be loaded into an `aw.Document` object (e.g., DOCX, DOC, RTF, HTML, PDF). The output format is determined by the format you save the translated document in.

5. **Q:** How can I change the AI model used for translation?  
   **A:** Select another supported Google model from `AiModelType` when calling `AiModel.create`. The rest of the code remains the same.
