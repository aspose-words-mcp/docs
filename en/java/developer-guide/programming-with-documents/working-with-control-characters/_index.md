---
title: Working With Control Characters
second_title: Aspose.Words for Java
articleTitle: Working With Control Characters
linktitle: Working With Control Characters
description: "Introduction to working with control characters in Aspose.Words for Java."
type: docs
weight: 400
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-control-characters/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with control characters in Word documents.

{{% /alert %}}

Microsoft Word documents may contain various characters that have a special meaning. Normally they are used for formatting purposes and are not drawn in the normal mode. You can make them visible if you click the Show/Hide Formatting Marks button located on the Standard toolbar.

Sometimes you may need to add or remove characters to/from the text. For instance, when obtaining text programmatically from the document, Aspose.Words preserves most of the control characters, so if you need to work with this text you should probably remove or replace the characters.

The [ControlChar](https://reference.aspose.com/words/java/com.aspose.words/controlchar/) class is a repository for the constants that represent control characters often encountered in documents. It provides both char and string versions of the same constants. For example, string [LINE_BREAK](https://reference.aspose.com/words/java/com.aspose.words/controlchar/#LINE-BREAK) and char [LINE_BREAK_CHAR](https://reference.aspose.com/words/java/com.aspose.words/controlchar/#LINE-BREAK-CHAR) has the same value.

The following code example shows how to use control characters:

{{< gist "aspose-words-gists" "920532ffbf33fbda20b92054f596a8ac" "use-control-characters.java" >}}
