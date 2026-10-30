---
title: Compare Documents in C#
second_title: Aspose.Words for .NET
articleTitle: Compare Documents
linktitle: Compare Documents
description: "Compare two documents in any supported formats and shows content changes using C#. You can apply advanced options when comparing."
type: docs
weight: 60
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/compare-documents/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page outlines how to compare two Word documents for differences using Aspose.Words.

{{% /alert %}}

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

Note that you can compare any two documents within the [supported file formats](/words/net/supported-document-formats/). Basically, you can compare document objects and even you can create those objects from scratch without having any specific format.

{{% /alert %}}

## Compare Two Documents {#compare-two-documents}

When you compare documents, differences of the latter document from the former show up as revisions to the former. When you modify a document, each edit will have its own revision after running the compare method.

Aspose.Words allows you to identify documents differences using the [Compare](https://reference.aspose.com/words/net/aspose.words/document/compare/#compare/) method – this is similar to the Microsoft Word document compare feature. It allows you to check documents or document versions to find differences and changes, including formatting modifications such as font changes, spacing changes, the addition of words and paragraphs.

As a result of comparison, documents can be determined as equal or not equal. The term “equal” documents means that the comparison method is not able to represent changes as revisions. This means that both document text and text formatting are the same. But there can be other differences between documents. For example, Microsoft Word supports only format revisions for styles, and you cannot represent style insertion/deletion. So documents can have a different set of styles, and the **Compare** method still produces no revisions.

The following code example shows how to check if two documents are equal or not:

{{< gist "aspose-words-gists" "66cba61d079d8ef1e676820633ba4586" "compare-for-equal.cs" >}}

## Specify Advanced Comparison Options {#specify-advanced-comparing-properties}

There are many different properties of the [CompareOptions](https://reference.aspose.com/words/net/aspose.words.comparing/compareoptions/) class which you can apply when you want to compare documents.

For example, Aspose.Words allows you to ignore changes made during a comparison operation for certain types of objects within the original document. You can select the appropriate property for the object type, such as [IgnoreHeadersAndFooters](https://reference.aspose.com/words/net/aspose.words.comparing/compareoptions/ignoreheadersandfooters/), [IgnoreFormatting](https://reference.aspose.com/words/net/aspose.words.comparing/compareoptions/ignoreformatting/), [IgnoreComments](https://reference.aspose.com/words/net/aspose.words.comparing/compareoptions/ignorecomments/), and others by setting them to "true".

In addition, Aspose.Words provides the [Granularity](https://reference.aspose.com/words/net/aspose.words.comparing/compareoptions/granularity/) property with which you can specify whether to track changes by character or by word.

Another common property is a choice in which document to show comparison changes. For example, the “Compare documents dialogue box” in Microsoft Word has the option “Show changes in” – this also affects the comparison results. Aspose.Words provides the [Target](https://reference.aspose.com/words/net/aspose.words.comparing/compareoptions/target/) property that serves this purpose.

The following code example shows how to set the advanced comparing properties:

{{< gist "aspose-words-gists" "66cba61d079d8ef1e676820633ba4586" "compare-options.cs" >}}

## Related APIs


- [Document.Compare](https://reference.aspose.com/words/net/aspose.words/document/compare/#compare/) – compares two documents and records differences as revisions
- [CompareOptions](https://reference.aspose.com/words/net/aspose.words.comparing/compareoptions/) – specifies comparison behavior (e.g., ignore headers, formatting, comments)
- [Granularity](https://reference.aspose.com/words/net/aspose.words.comparing/compareoptions/granularity/) – controls whether changes are tracked by character or by word
- [CompareOptions.Target](https://reference.aspose.com/words/net/aspose.words.comparing/compareoptions/target/) – determines which document displays the changes
- [Revision](https://reference.aspose.com/words/net/aspose.words/revision/) – represents a single change detected during comparison
- [Revisions](https://reference.aspose.com/words/net/aspose.words/revisioncollection/) – collection of all changes recorded in the document after comparison

## FAQ

1. **Q:** Which file formats can be compared with Aspose.Words?  
   **A:** Any format listed in the [supported document formats](/words/net/supported-document-formats/) can be used for comparison, including DOC, DOCX, ODT, RTF, HTML, PDF (as source) and others. The API works with `Document` objects, so you can load a file of any supported type and compare it directly.

2. **Q:** Do the source documents need to be free of revisions before calling `Compare`?  
   **A:** Yes. Aspose.Words follows the same limitation as Microsoft Word: the documents must not contain existing revisions when `Compare` is invoked. Remove revisions first (e.g., `document.AcceptAllRevisions();`) to avoid unexpected results.

3. **Q:** How can I ignore changes in headers, footers, or formatting during comparison?  
   **A:** Use the `CompareOptions` class. Set properties such as `IgnoreHeadersAndFooters = true`, `IgnoreFormatting = true`, or `IgnoreComments = true` before calling `document.Compare(otherDoc, author, date, compareOptions);`.

4. **Q:** How do I determine programmatically whether two documents are identical after comparison?  
   **A:** After calling `Compare`, inspect the `Revisions` collection of the first document. If `document.Revisions.Count == 0`, the documents are considered equal (no detectable changes).

5. **Q:** What is the difference between the `Granularity` and `Target` options?  
   **A:** `Granularity` controls the level of change tracking—`Granularity.CharLevel` tracks changes per character, while `Granularity.WordLevel` tracks per word. `Target` specifies which document will display the revisions (e.g., `CompareOptions.Target = ComparisonTargetType.New;` shows changes in the second document). Adjust both to match the desired comparison behavior.