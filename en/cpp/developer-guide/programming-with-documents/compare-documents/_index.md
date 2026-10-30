---
title: Compare Documents in C++
second_title: Aspose.Words for C++
articleTitle: Compare Documents
linktitle: Compare Documents
type: docs
description: "Compare two documents in any supported formats and shows content changes using C++. You can apply advanced options when comparing."
weight: 60
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/compare-documents/
timestamp: 2024-01-27-14-07-04
---

Comparing documents is a process that identifies changes between two documents and contains the changes as revisions. This process compares any two documents, including versions of one specific document, then the changes between both documents will be shown as revisions in the first document.

The comparison method is achieved by comparing words at the character level or the word level. If a word contains a change of at least one character, in the result, the difference will be displayed as a change of the entire word, not a character. This process of comparison is a usual task in the legal and financial industries.

Instead of manually searching for differences between documents or between different versions of them, you can use Aspose.Words for comparing documents and getting content changes in formatting, header/footer, tables, and more.

This article explains how to compare documents and how to specify advanced comparing properties.

{{% alert color="primary" %}}

**Try online**

You can compare two documents online by using the [Document comparison online](https://products.aspose.app/words/comparison) tool.

Note that the comparison method, described below, is used in this tool to ensure getting equal results. So you will get the same results even by using the online comparison tool or by using the comparison method in Aspose.Words.

{{% /alert %}}

## Limitations and Supported File Formats {#limitations-and-supported-file-formats}

Comparing documents is a very complex feature. There are varied parts of content combination that need to be analyzed to recognize all differences. The reason for this complexity is due to the fact that Aspose.Words aims to get the same comparison results as the Microsoft Word comparison algorithm.

The general limitation for two documents being compared is that they must not have revisions before calling the compare method as this limitation exists in Microsoft Word.

{{% alert color="primary" %}}

Note that you can compare any two documents within the [supported file formats](/words/cpp/supported-document-formats/). You can compare document objects and even you can create those objects from scratch without having any specific format.

{{% /alert %}}

## Compare Two Documents {#compare-two-documents}

When you compare documents, differences of the latter document from the former show up as revisions to the former. When you modify a document, each edit will have its own revision after running the compare method.

Aspose.Words allows you to identify documents differences using the [Compare](https://reference.aspose.com/words/cpp/aspose.words/document/compare/) method – this is similar to the Microsoft Word document compare feature. It allows you to check documents or document versions to find differences and changes, including formatting modifications such as font changes, spacing changes, the addition of words and paragraphs.

As a result of the comparison, documents can be determined as equal or not equal. The term “equal” documents means that the comparison method is not able to represent changes as revisions. This means that both document text and text formatting are the same. But there can be other differences between documents. For example, Microsoft Word supports only format revisions for styles, and you cannot represent style insertion/deletion. So documents can have a different set of styles, and the **Compare** method still produces no revisions.

The following code example shows how to check if two documents are equal or not:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Document-CompareDocument-CompareForEqual.cpp" >}}

The following code example shows how to simply apply the `Compare` method to two documents:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Document-CompareDocument-CompareWhenDocumentHasRevisions.cpp" >}}

## Specify Advanced Comparison Options {#specify-advanced-comparing-properties}

There are many different properties of the [CompareOptions](https://reference.aspose.com/words/cpp/aspose.words.comparing/compareoptions/) class which you can apply when you want to compare documents.

For example, Aspose.Words allows you to ignore changes made during a comparison operation for certain types of objects within the original document. You can select the appropriate property for the object type, such as [get_IgnoreHeadersAndFooters()](https://reference.aspose.com/words/cpp/aspose.words.comparing/compareoptions/get_ignoreheadersandfooters/), [get_IgnoreFormatting()](https://reference.aspose.com/words/cpp/aspose.words.comparing/compareoptions/get_ignoreformatting/), [get_IgnoreComments()](https://reference.aspose.com/words/cpp/aspose.words.comparing/compareoptions/get_ignorecomments/), and others by setting them to "true".

In addition, Aspose.Words provides the [get_Granularity()](https://reference.aspose.com/words/cpp/aspose.words.comparing/compareoptions/get_granularity/) property with which you can specify whether to track changes by character or by word.

Another common property is a choice in which document to show comparison changes. For example, the “Compare documents dialogue box” in Microsoft Word has the option “Show changes in” – this also affects the comparison results. Aspose.Words provides the [get_Target()](https://reference.aspose.com/words/cpp/aspose.words.comparing/compareoptions/get_target/) property that serves this purpose.

The following code example shows how to set the advanced comparing properties:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Document-CompareDocument-CompareDocumentWithCompareOptions.cpp" >}}

---

## FAQ

1. **Q:** How do I compare two Word documents using Aspose.Words for C++?  
   **A:** Load each document into a `Document` object and call the `Compare` method on the first document, passing the second document, the author name, the date, and optionally a `CompareOptions` instance (e.g., `doc1->Compare(doc2, u"Author", System::DateTime::get_Now(), options);`). The method creates revisions in the first document that represent the differences.

2. **Q:** How can I determine if two documents are identical after comparison?  
   **A:** After calling `Compare`, inspect the `Revisions` collection of the first document. If the collection is empty, the documents are considered equal; otherwise, revisions indicate differences.

3. **Q:** Which options let me ignore changes in headers, footers, or formatting?  
   **A:** Use the `CompareOptions` properties such as `get_IgnoreHeadersAndFooters()`, `get_IgnoreFootnotes()`, `get_IgnoreFormatting()`, and set them to `true` before invoking `Compare`. These options tell the engine to skip those elements when generating revisions.

4. **Q:** How do I control the granularity of the comparison (character vs. word level)?  
   **A:** Set the `Granularity` property of `CompareOptions` to `Granularity::CharLevel` or `Granularity::WordLevel`. Character granularity tracks changes at the character level, while word granularity groups changes by whole words.

5. **Q:** Can I choose which document shows the revision changes?  
   **A:** Yes, set the `Target` property of `CompareOptions` to `ComparisonTargetType::New` or `ComparisonTargetType::Current`. This determines whether the revisions appear in the original (old) document or the new document after comparison.