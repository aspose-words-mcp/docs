---
title: AI Grammar Checking
second_title: Aspose.Words for Node.js via .NET
articleTitle: Grammar Checking
linktitle: Grammar Checking
type: docs
weight: 40
description: "Check a document grammar. Aspose.Words for Node.js via .NET allows users to check grammar and detect errors in documents using OpenAI, Google, and Anthropic models."
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/grammar-checking/
timestamp: 2025-05-16-12-00-00
---

Checking grammar in documents is important to ensure clarity, professionalism, and accuracy. Well-written documents leave a positive impression and avoid misunderstandings. Grammar checks help identify and correct errors quickly, saving time and improving quality.

Aspose.Words allows users to check grammar and detect errors in documents using the OpenAI, Google, and Anthropic models' families listed in the [AiModelType](https://reference.aspose.com/words/nodejs-net/aspose.words.ai/aimodeltype/) enumeration. Use the [checkGrammar](https://reference.aspose.com/words/nodejs-net/aspose.words.ai/aimodel/checkGrammar/) method, available in the [Aspose.Words.AI](https://reference.aspose.com/words/nodejs-net/aspose.words.ai/) namespace. **checkGrammar** analyzes the text in a document and highlights grammatical problems.

The following code example shows how to use the GPT‑4o mini model in Aspose.Words to check grammar:

{{< gist "aspose-words-gists" "757cf7d3534a39730cf3290d418681ab" "ai-grammar.js" >}}

{{% alert color="primary" %}}

Checking grammar with Aspose.Words improves the quality of your work and makes it easy to integrate proofreading into your projects. For more information, check the [Aspose.Words.AI](https://reference.aspose.com/words/nodejs-net/aspose.words.ai/) API documentation.

{{% /alert %}}

------ 

## FAQ

1. **Q:** Which AI models can I use with `checkGrammar`?  
   **A:** The `AiModelType` enumeration lists the supported families: OpenAI (e.g., `Gpt4OMini`), Google (e.g., `GeminiProLatest`), and Anthropic (e.g., `Claude35Haiku`). Pass the value to `aw.AI.AiModel.create(...)` (or use a factory method such as `createGpt4OMini()`) and call `checkGrammar` on the returned model.

2. **Q:** Do I need a separate license for the AI features?  
   **A:** No. AI capabilities are included with a regular Aspose.Words license. Ensure your license file is applied before invoking `checkGrammar`.

3. **Q:** What should I do if my document is very large?  
   **A:** `checkGrammar` works on the whole document, but very large files may exceed service limits. Split the document into smaller sections (e.g., by chapter) and call `checkGrammar` on each part, then combine the results.

4. **Q:** How can I tell whether any grammar issues were found?  
   **A:** The method returns a new `Document` with the corrected text. With `CheckGrammarOptions.makeRevisions` set to `true`, the corrections are made as revisions, and `result.revisions.count` equal to zero means that no issues were detected.