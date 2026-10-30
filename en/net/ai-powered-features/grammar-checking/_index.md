---
title: AI Grammar Checking
second_title: Aspose.Words for .NET
articleTitle: Grammar Checking
linktitle: Grammar Checking
type: docs
weight: 40
description: "Check a document grammar. Aspose.Words for .NET allows users to check grammar and detect errors in documents using OpenAI, Google, and Claude models."
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/grammar-checking/
timestamp: 2025-03-17-19-00-00
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains the grammar checking capabilities available in Aspose.Words.

{{% /alert %}}

Checking grammar in documents is important to ensure clarity, professionalism, and accuracy. Well-written documents leave a positive impression and avoid misunderstandings. Grammar checks help identify and correct errors quickly, saving time and improving quality.

Aspose.Words allows users to check grammar and detect errors in documents using the OpenAI, Google, and Claude models' families listed in the [AiModelType](https://reference.aspose.com/words/net/aspose.words.ai/aimodeltype/) enumeration. Use the [CheckGrammar](https://reference.aspose.com/words/net/aspose.words.ai/aimodel/checkgrammar/) method, available in the [Aspose.Words.AI](https://reference.aspose.com/words/net/aspose.words.ai/) namespace. **CheckGrammar** analyzes the text in a document and highlights grammatical problems.

The following code example shows how to use the GPT‑4o mini model in Aspose.Words to check grammar:

{{< gist "aspose-words-gists" "98a646d19cd7708ed0cd3d97b993a053" "ai-grammar.cs" >}}

{{% alert color="primary" %}}

Checking grammar with Aspose.Words improves the quality of your work and makes it easy to integrate proofreading into your projects. For more information, check the [Aspose.Words.AI](https://reference.aspose.com/words/net/aspose.words.ai/) API documentation.

{{% /alert %}}

------

## FAQ


1. **Q:** Which AI models can be used with the `CheckGrammar` method?  
   **A:** `CheckGrammar` supports the models defined in the `AiModelType` enumeration, which includes OpenAI (e.g., GPT‑4o mini), Google Gemini, and Anthropic Claude families. Choose the model that best fits your accuracy, latency, and cost requirements.

2. **Q:** How do I provide authentication (API key) for the AI service used by Aspose.Words?  
   **A:** Set the `apiKey` before calling `CheckGrammar`. For example:  

   ```csharp
   string apiKey = Environment.GetEnvironmentVariable("API_KEY");
   // Use OpenAI generative language models.
   AiModel model = AiModel.Create(AiModelType.Gpt4OMini).WithApiKey(apiKey);
   ```

3. **Q:** What document formats are supported for grammar checking?  
   **A:** Grammar checking works on any format that Aspose.Words can load, such as DOC, DOCX, RTF, HTML, and PDF (when converted to a Word document first). The content is extracted from the loaded `Document` object, so the original format does not affect the grammar analysis.

4. **Q:** How should I handle large documents to avoid performance issues?  
   **A:** For very large files, consider processing the document in sections or pages. Use `Document.ExtractPages` to create smaller `Document` instances, run `CheckGrammar` on each part, and then merge the results.



