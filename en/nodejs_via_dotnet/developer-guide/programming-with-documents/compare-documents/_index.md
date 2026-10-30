---
title: Compare Documents in Node.js
second_title: Aspose.Words for Node.js via .NET
articleTitle: Compare Documents
linktitle: Compare Documents
description: "Compare two documents in any supported formats and shows content changes using Node.js. You can apply advanced options when comparing."
type: docs
weight: 60
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/compare-documents/
timestamp: 2025-07-09-10-05-05
---

Comparing documents is a process that identifies changes between two documents and contains the changes as revisions. This process compares any two documents, including versions of one specific document, then the changes between both documents will be shown as revisions in the first document.

The comparison method is achieved by comparing words at character level or at word level. If a word contains a change of at least one character, in the result, the difference will be displayed as a change of the entire word, not a character. This process of comparison is a usual task in the legal and financial industries.

Instead of manually searching for differences between documents or between different versions of them, you can use Aspose.Words for comparing documents and getting content changes in formatting, header/footer, tables, and more.

This article explains how to compare documents and how to specify the advanced comparing properties.

{{% alert color="primary" %}}

**Try online**

You can compare two documents online by using the [Document comparison online](https://products.aspose.app/words/comparison) tool.

Note that the comparison method, described below, is used in this tool to ensure getting equal results. So you will get the same results even by using the online comparison tool or by using the comparison method in Aspose.Words.

{{% /alert %}}

## Limitations and Supported File Formats {#limitations-and-supported-file-formats}

Comparing documents is a very complex feature. There are varied parts of content combination that need to be analyzed to recognize all differences. The reason for this complexity is due to the fact that Aspose.Words aims to get the same comparison results as the Microsoft Word comparison algorithm.

The general limitation for two documents being compared is that they must not have revisions before calling the compare method as this limitation exists in Microsoft Word.

{{% alert color="primary" %}}

Note that you can compare any two documents within the [supported file formats](/words/nodejs-net/supported-document-formats/). Basically, you can compare document objects and even you can create those objects from scratch without having any specific format.

{{% /alert %}}

## Compare Two Documents {#compare-two-documents}

When you compare documents, differences of the latter document from the former show up as revisions to the former. When you modify a document, each edit will have its own revision after running the compare method.

Aspose.Words allows you to identify documents differences using the [compare](https://reference.aspose.com/words/nodejs-net/aspose.words/document/compare/) method – this is similar to the Microsoft Word document compare feature. It allows you to check documents or document versions to find differences and changes, including formatting modifications such as font changes, spacing changes, the addition of words and paragraphs.

As a result of comparison, documents can be determined as equal or not equal. The term "equal" documents means that the comparison method is not able to represent changes as revisions. This means that both document text and text formatting are the same. But there can be other differences between documents. For example, Microsoft Word supports only format revisions for styles, and you cannot represent style insertion/deletion. So documents can have a different set of styles, and the [compare](https://reference.aspose.com/words/nodejs-net/aspose.words/document/compare/) method still produces no revisions.

The following code example shows how to check if two documents are equal or not:

{{< gist "aspose-words-gists" "57808d29628dd1680d4c229e84c5456c" "compare-for-equal.js" >}}

## Specify Advanced Comparing Properties {#specify-advanced-comparing-properties}

There are many different properties of the [CompareOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.comparing/compareoptions/) class which you can apply when you want to compare documents.

For example, Aspose.Words allows you to ignore changes made during a comparison operation for certain types of objects within the original document. You can select the appropriate property for the object type, such as [ignoreHeadersAndFooters](https://reference.aspose.com/words/nodejs-net/aspose.words.comparing/compareoptions/ignoreHeadersAndFooters/), [ignoreFormatting](https://reference.aspose.com/words/nodejs-net/aspose.words.comparing/compareoptions/ignoreFormatting/), [ignoreComments](https://reference.aspose.com/words/nodejs-net/aspose.words.comparing/compareoptions/ignoreComments/), and others by setting them to `True`.

In addition, Aspose.Words provides the [granularity](https://reference.aspose.com/words/nodejs-net/aspose.words.comparing/compareoptions/granularity/) property with which you can specify whether to track changes by character or by word.

Another common property is a choice in which document to show comparison changes. For example, the “Compare documents dialogue box” in Microsoft Word has the option “Show changes in” – this also affects the comparison results. Aspose.Words provides the [target](https://reference.aspose.com/words/nodejs-net/aspose.words.comparing/compareoptions/target/) property that serves this purpose.

The following code example shows how to set the advanced comparing properties:

{{< gist "aspose-words-gists" "57808d29628dd1680d4c229e84c5456c" "compare-options.js" >}}




------ 

## FAQ

1. **Q:** How do I apply my Aspose.Words license before performing a document comparison?  
   **A:** Load the license file using the `License` class before creating any `Document` objects. For example:  

   ```javascript
   const aw = require('@aspose/words');
   let license = new aw.License();
   license.setLicense("Aspose.Words.lic");
   ```

   This ensures that all subsequent operations, including comparison, run without evaluation limitations.

2. **Q:** How can I determine programmatically whether two documents are identical after comparison?  
   **A:** After calling `document1.compare(document2, "Author", new Date(), compareOptions)`, inspect the `revisions` collection of the first document. If `document1.revisions.count` is zero, the documents are considered equal.

3. **Q:** Which option should I use to ignore formatting changes during comparison?  
   **A:** Set the `ignoreFormatting` property of `CompareOptions` to `true`. This tells the engine to treat font, style, and other formatting modifications as non‑significant, so only textual changes appear as revisions.

4. **Q:** Can I compare documents that are loaded from streams or have no file extension?  
   **A:** Yes. Use the `Document` constructor that accepts a stream or a byte array, optionally providing a `LoadOptions` object to specify the format. Example:  

   ```javascript
   let stream = fs.readFileSync("doc1");
   let doc1 = new aw.Document(stream, new aw.Loading.LoadOptions());
   ```

5. **Q:** What file formats are supported for document comparison?  
   **A:** Aspose.Words can compare any formats it can load, including DOC, DOCX, ODT, RTF, HTML, PDF (as source), and many others. The comparison result is always produced as a Word document (DOCX) with revisions.