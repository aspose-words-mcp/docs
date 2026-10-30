---
title: Clean Up a Document in Java
second_title: Aspose.Words for Java
articleTitle: Clean Up a Document
linktitle: Clean Up a Document
description: "Remove unused or duplicate information to reduce output size and processing time using Java. Remove unused styles, unused built-in styles, duplicate styles, or unused lists."
type: docs
weight: 30
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/clean-up-a-document/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page outlines how to clean up unnecessary or redundant content in a Word document using Aspose.Words.

{{% /alert %}}

Sometimes you may need to remove unused or duplicate information to reduce the size of the output document and processing time.

While you can find and remove unused data, such as styles or lists, or duplicate information manually, it will be much more convenient to do this using features and capabilities provided by Aspose.Words.

The [CleanupOptions](https://reference.aspose.com/words/java/com.aspose.words/cleanupoptions/) class allows you to specify options for document cleaning. To remove duplicate styles or just unused styles or lists from the document, you can use the [cleanup()](https://reference.aspose.com/words/java/com.aspose.words/document/#cleanup) method.

## Remove Unused Information from a Document

You can use the [getUnusedStyles()](https://reference.aspose.com/words/java/com.aspose.words/cleanupoptions/#getUnusedStyles) and [getUnusedBuiltinStyles()](https://reference.aspose.com/words/java/com.aspose.words/cleanupoptions/#getUnusedBuiltinStyles) properties to detect and remove styles that are marked as "unused".

You can use the [getUnusedLists()](https://reference.aspose.com/words/java/com.aspose.words/cleanupoptions/#getUnusedLists) property to detect and remove lists and list definitions that are marked as "unused".

The following code example shows how to remove only unused styles from a document:

{{< gist "aspose-words-gists" "01b0f3024b265f429ec00ffd6ec30407" "cleanup-unused-styles-and-lists.java" >}}

## Remove Duplicate Information from a Document

You can also use the [getDuplicateStyle()](https://reference.aspose.com/words/java/com.aspose.words/cleanupoptions/#getDuplicateStyle) property to substitute all duplicate styles with the original one and remove duplicates from a document.

The following code example shows how to remove duplicate styles from a document:

{{< gist "aspose-words-gists" "01b0f3024b265f429ec00ffd6ec30407" "cleanup-duplicate-style.java" >}}

## FAQ

1. **Q:** How can I remove unused styles from a Word document using Aspose.Words for Java?  
   **A:** Create a `CleanupOptions` instance, set `setUnusedStyles(true)`, and call `document.cleanup(options)`. This removes any style definitions that are not applied in the document.

2. **Q:** How do I delete duplicate styles in a document?  
   **A:** Enable the `setDuplicateStyle(true)` option on `CleanupOptions` and invoke `document.cleanup(options)`. Aspose.Words will replace duplicate style definitions with the original one and remove the extras.

3. **Q:** Can I also clean up unused built‑in styles and lists?  
   **A:** Yes. Set `setUnusedBuiltinStyles(true)` and/or `setUnusedLists(true)` on the same `CleanupOptions` object before calling `cleanup`. All specified unused elements will be removed in one pass.

4. **Q:** Does the cleanup process affect the document's visible content?  
   **A:** No. Cleanup only removes unused or duplicate style and list definitions; it does not modify the actual text, images, or other visible content of the document.

5. **Q:** Is it possible to combine multiple cleanup options in a single call?  
   **A:** Absolutely. You can enable several options (e.g., `getUnusedStyles()`, `getUnusedLists()`, `getDuplicateStyle()`) on one `CleanupOptions` instance and call `document.cleanup(options)` once to apply all selected clean‑up actions.