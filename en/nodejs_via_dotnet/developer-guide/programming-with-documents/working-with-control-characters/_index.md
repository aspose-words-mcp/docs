---
title: Working With Control Characters
second_title: Aspose.Words for Node.js via .NET
articleTitle: Working With Control Characters
linktitle: Working With Control Characters
description: "Introduction to working with control characters in Aspose.Words for Node.js."
type: docs
weight: 400
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/working-with-control-characters/
timestamp: 2025-07-09-10-05-05
---

Microsoft Word documents may contain various characters that have a special meaning. Normally they are used for formatting purposes and are not drawn in the normal mode. You can make them visible if you click the Show/Hide Formatting Marks button located on the Standard toolbar.

Sometimes you may need to add or remove characters to/from the text. For instance, when obtaining text programmatically from the document, Aspose.Words preserves most of the control characters, so if you need to work with this text you should probably remove or replace the characters.

The [ControlChar](https://reference.aspose.com/words/nodejs-net/aspose.words/controlchar/) class is a repository for the constants that represent control characters often encountered in documents. It provides both char and string versions of the same constants. For example, string [ControlChar.lineBreak](https://reference.aspose.com/words/nodejs-net/aspose.words/controlchar/) and char [ControlChar.lineBreakChar](https://reference.aspose.com/words/nodejs-net/aspose.words/controlchar/) has the same value.

The following code example demonstrates how to use control characters:

{{< gist "aspose-words-gists" "3d84715449d1d04a6029964ad5f2fdf0" "use-control-characters.js" >}}