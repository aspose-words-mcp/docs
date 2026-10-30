---
title: Inserting Bookmarks Dynamically in C#
second_title: Aspose.Words for .NET
articleTitle: Inserting Bookmarks Dynamically
linktitle: Inserting Bookmarks Dynamically
description: "Insert bookmarks into your document dynamically when building a report using C#."
type: docs
weight: 70
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/inserting-bookmarks-dynamically/
aliases: [/net/template-syntax/#inserting-bookmarks-dynamically]
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to insert bookmarks dynamically in reporting templates.

{{% /alert %}}

You can insert bookmarks to your reports dynamically using `bookmark` tags. Syntax of a `bookmark` tag is defined as follows.

{{< highlight csharp >}}
<<bookmark [bookmark_expression]>>
bookmarked_content
<</bookmark>>
{{< /highlight >}}

Here, `bookmark_expression` defines the name of a bookmark to be inserted during runtime. This expression is mandatory and must return a non‑empty value. While building a report, `bookmark_expression` is evaluated and its result is used to construct a bookmark start and end that replace corresponding opening and closing `bookmark` tags respectively.

**Note** – A `bookmark` tag cannot be used within a chart.

## Limitations and Considerations

- A `bookmark` tag cannot be used within a chart.

## Related APIs

- [Bookmark](https://reference.aspose.com/words/net/aspose.words/bookmark/)
- [BookmarkCollection](https://reference.aspose.com/words/net/aspose.words/bookmarkcollection/)
- [Range.Bookmarks](https://reference.aspose.com/words/net/aspose.words/range/bookmarks/)

------

## FAQ

1. **Q:** How do I define the name of a bookmark dynamically?  
   **A:** Place an expression that evaluates to the desired bookmark name inside the `bookmark` tag, e.g., `<<bookmark [Customer.Id]>>`. At runtime the expression is evaluated and the resulting string becomes the bookmark name.

2. **Q:** Can I use the `bookmark` tag inside a table, list, or other container elements?  
   **A:** Yes. The `bookmark` tag works inside tables, lists, paragraphs, and most other document elements. The only restriction is that it cannot be placed inside a chart.

3. **Q:** What happens if the bookmark expression returns an empty string or null?  
   **A:** The tag is ignored and no bookmark is created. Because the expression must return a non‑empty value, an empty result will cause the engine to skip the bookmark insertion without raising an error.

4. **Q:** How can I reference a bookmark that was created dynamically later in the same report?  
   **A:** Use a `link` tag with the same expression that named the bookmark, e.g., `<<link ["Section_" + Id] ["Go to section"]>>`. The engine inserts a hyperlink to the dynamically created bookmark. For a bookmark with a fixed name, a regular `REF` field in the template works as well.