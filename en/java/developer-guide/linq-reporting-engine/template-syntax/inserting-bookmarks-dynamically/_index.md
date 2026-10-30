---
title: Inserting Bookmarks Dynamically in Java
second_title: Aspose.Words for Java
articleTitle: Inserting Bookmarks Dynamically
linktitle: Inserting Bookmarks Dynamically
description: "Insert bookmarks into your document dynamically when building a report in Java."
type: docs
weight: 70
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/inserting-bookmarks-dynamically/
timestamp: 2024-01-27-14-07-04
---

You can insert bookmarks to your reports dynamically using `bookmark` tags. Syntax of a `bookmark` tag is defined as follows.

{{< highlight csharp >}}
<<bookmark [bookmark_expression]>>
bookmarked_content
<</bookmark>>
{{< /highlight >}}

Here, `bookmark_expression` defines the name of a bookmark to be inserted during runtime. This expression is mandatory and must return a non‑empty value. While building a report, `bookmark_expression` is evaluated and its result is used to construct a bookmark start and end that replace corresponding opening and closing `bookmark` tags respectively.

**Note** – A `bookmark` tag cannot be used within a chart.

------ 

## FAQ

1. **Q:** How can I generate the bookmark name at runtime?  
   **A:** Use any valid expression that returns a string, such as a field from your data source or a concatenation of values. For example: `<<bookmark ["Section_" + item.getId()]>>`.

2. **Q:** Can a `bookmark` tag be placed inside a table cell?  
   **A:** Yes, the `bookmark` tag works inside tables, paragraphs, and most other document elements. The only restriction is that it cannot be used inside a chart.

3. **Q:** How do I reference a dynamically created bookmark later in the document?  
   **A:** After the report is generated, you can retrieve the bookmark by its runtime name using `doc.getRange().getBookmarks().get("BookmarkName")`. Ensure the name you generated is stored or predictable so you can access it later.

4. **Q:** What happens if the bookmark expression evaluates to an empty string?  
   **A:** The engine will throw an error because a bookmark name is required and cannot be empty. Always validate that the expression returns a non‑empty value before the tag is processed.

5. **Q:** Is it possible to create multiple bookmarks with the same name?  
   **A:** No. Bookmark names must be unique within a document. If you attempt to insert a duplicate name, Aspose.Words will replace the existing bookmark, potentially causing loss of the original bookmark's range. Use distinct names for each bookmark.