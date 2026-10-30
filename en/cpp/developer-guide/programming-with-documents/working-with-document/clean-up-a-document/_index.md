---
title: Clean Up a Document in C++
second_title: Aspose.Words for C++
articleTitle: Clean Up a Document
linktitle: Clean Up a Document
description: "Remove unused or duplicate information to reduce output size and processing time using C++. Remove unused styles, unused built-in styles, duplicate styles, or unused lists."
type: docs
weight: 30
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/clean-up-a-document/
timestamp: 2024-01-27-14-07-04
---

Sometimes you may need to remove unused or duplicate information to reduce the size of the output document and processing time.

While you can find and remove unused data, such as styles or lists, or duplicate information manually, it will be much more convenient to do this using features and capabilities provided by Aspose.Words.

The [CleanupOptions](https://reference.aspose.com/words/cpp/aspose.words/cleanupoptions/) class allows you to specify options for document cleaning. To remove duplicate styles or just unused styles or lists from the document, you can use the [Cleanup](https://reference.aspose.com/words/cpp/aspose.words/document/cleanup/) method.

## Remove Unused Information from a Document

You can use the [get_UnusedStyles()](https://reference.aspose.com/words/cpp/aspose.words/cleanupoptions/get_unusedstyles/) and [get_UnusedBuiltinStyles()](https://reference.aspose.com/words/cpp/aspose.words/cleanupoptions/get_unusedbuiltinstyles/) properties to detect and remove styles that are marked as "unused".

You can use the [get_UnusedLists()](https://reference.aspose.com/words/cpp/aspose.words/cleanupoptions/get_unusedlists/) property to detect and remove lists and list definitions that are marked as "unused".

The following code example shows how to remove only unused styles from a document:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "Examples-DocsExamples-source-Programming with Documents-Working with Document-Working with document options and settings-CleanupUnusedStylesandLists.h" >}}

## Remove Duplicate Information from a Document

You can also use the [get_DuplicateStyle()](https://reference.aspose.com/words/cpp/aspose.words/cleanupoptions/get_duplicatestyle/) property to substitute all duplicate styles with the original one and remove duplicates from a document.

The following code example shows how to remove duplicate styles from a document:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "Examples-DocsExamples-source-Programming with Documents-Working with Document-Working with document options and settings-CleanupDuplicateStyle.h" >}}

------ 

## FAQ

1. **Q:** What does the `Document::Cleanup` method do?  
   **A:** `Document::Cleanup` analyses the document according to the options set in a `CleanupOptions` object and removes or consolidates unused or duplicate elements such as styles, built‑in styles, lists, and duplicate style definitions. It does not alter the visible content of the document.

2. **Q:** How can I remove only unused custom styles from a document?  
   **A:** Create a `CleanupOptions` instance, set `set_UnusedStyles()` to `true`, and pass it to `Document::Cleanup`. Example:  
   ```cpp
   auto options = System::MakeObject<Aspose::Words::CleanupOptions>();
   options->set_UnusedStyles(true);
   doc->Cleanup(options);
   ```

3. **Q:** How do I eliminate duplicate styles while keeping the original style intact?  
   **A:** Enable the `get_DuplicateStyle()` option in `CleanupOptions`. The method will replace all occurrences of duplicate styles with the first (original) style and then delete the duplicates.  
   ```cpp
   auto options = System::MakeObject<Aspose::Words::CleanupOptions>();
   options->set_DuplicateStyle(true);
   doc->Cleanup(options);
   ```

4. **Q:** Can the cleanup process also remove unused built‑in styles and lists?  
   **A:** Yes. Set `set_UnusedBuiltinStyles()` and/or `get_UnusedLists()` to `true` in the `CleanupOptions` object before calling `Cleanup`. This will purge any built‑in styles or list definitions that are not referenced in the document.

5. **Q:** Will using `Cleanup` affect the formatting or layout of the document?  
   **A:** No. Cleanup only removes or merges internal definitions that are not used. The visible text, formatting, and layout remain unchanged, but the file size may be reduced and processing can become faster.