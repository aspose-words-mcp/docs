---
title: AI Grammar Checking
second_title: Aspose.Words for Python via .NET
articleTitle: Grammar Checking
linktitle: Grammar Checking
type: docs
weight: 40
description: "Check a document grammar. Aspose.Words for Python allows users to check grammar and detect errors in documents using OpenAI, Google, and Claude models."
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/grammar-checking/
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page shows how to use Aspose.Words AI's `check_grammar` method in Python via .NET to perform grammar checking on a document with AI models, including sample code and configuration options.
{{% /alert %}}

Checking grammar in documents is important to ensure clarity, professionalism, and accuracy. Well-written documents leave a positive impression and avoid misunderstandings. Grammar checks help identify and correct errors quickly, saving time and improving quality.

Aspose.Words allows users to check grammar and detect errors in documents using the OpenAI, Google, and Claude model families listed in the [AiModelType](https://reference.aspose.com/words/python-net/aspose.words.ai/aimodeltype/) enumeration. Use the [check_grammar](https://reference.aspose.com/words/python-net/aspose.words.ai/aimodel/check_grammar/) method, available in the [aspose.words.ai](https://reference.aspose.com/words/python-net/aspose.words.ai/) module. **check_grammar** returns a new document with checked grammar.

The following code example shows how to use the GPT-4o mini model in Aspose.Words to check grammar:

{{< highlight python >}}
doc = aw.Document(file_name=MY_DIR + 'Big document.docx')

api_key = system_helper.environment.Environment.get_environment_variable('API_KEY')
# Use OpenAI generative language models.
model = aw.ai.AiModel.create(aw.ai.AiModelType.GPT_4O_MINI).with_api_key(api_key)

grammar_options = aw.ai.CheckGrammarOptions()
grammar_options.improve_stylistics = True

proofed_doc = model.check_grammar(doc, grammar_options)
proofed_doc.save(file_name='AI.AiGrammar.docx')
{{< /highlight >}}

{{% alert color="primary" %}}

Checking grammar with Aspose.Words improves the quality of your work and makes it easy to integrate proofreading into your projects. For more information, check the [Aspose.Words.AI](https://reference.aspose.com/words/python-net/aspose.words.ai/) API documentation.

{{% /alert %}}
