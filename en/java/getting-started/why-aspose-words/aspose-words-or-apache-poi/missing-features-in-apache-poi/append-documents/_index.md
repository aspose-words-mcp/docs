---
title: Append Documents
second_title: Aspose.Words for Java
articleTitle: Append Documents
linktitle: Append Documents
description: "Combine documents and append one document to another. Apache POI does not provide an opportunity to merge or append documents."
type: docs
weight: 40
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/append-documents/
timestamp: 2024-01-31-14-23-37
---

{{% alert color="primary" %}}

**Try online**

You can add a watermark online by using the [Document and Image Merger](https://products.aspose.app/words/merger) tool.

{{% /alert %}}

{{% alert color="primary" %}}

See more details in the [Insert and Append Documents](/words/java/insert-and-append-documents/) article.

{{% /alert %}}

To append documents using Aspose.Words, simply invoke the [appendDocument()](https://reference.aspose.com/words/java/com.aspose.words/document/#appendDocument-com.aspose.words.Document-int) method of the [Document](https://reference.aspose.com/words/java/com.aspose.words/document/) class and specify the second document to append it at the end of the first one.

The following code example shows how to append a document:

{{< highlight java >}}
Document doc1 = new Document(dataDir + "doc1.doc");
Document doc2 = new Document(dataDir + "doc2.doc");

doc1.appendDocument(doc2, ImportFormatMode.KEEP_SOURCE_FORMATTING);
{{< /highlight >}}

See also:

* [GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Plugins/Aspose_Words_for_Apache_POI/src/main/java/com/aspose/words/examples/asposefeatures/workingwithdocument/appenddoc/AsposeAppendDocs.java) for code example
* [GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Plugins/Aspose_Words_for_Apache_POI/src/main/java/com/aspose/words/examples/asposefeatures/workingwithdocument/appenddoc/AsposeAppendDocs.java) for running code
