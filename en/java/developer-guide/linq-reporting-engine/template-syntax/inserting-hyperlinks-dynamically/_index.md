---
title: Inserting Hyperlinks Dynamically in Java
second_title: Aspose.Words for Java
articleTitle: Inserting Hyperlinks Dynamically
linktitle: Inserting Hyperlinks Dynamically
description: "Insert hyperlinks into your document dynamically when building a report in Java."
type: docs
weight: 80
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/inserting-hyperlinks-dynamically/
timestamp: 2024-01-27-14-07-04
---

You can insert hyperlinks to your reports dynamically using `link` tags. Syntax of a `link` tag is defined as follows.

{{< highlight csharp >}}
<<link [uri_or_bookmark_expression] [display_text_expression]>>
{{< /highlight >}}

Here, `uri_or_bookmark_expression` defines URI or the name of a bookmark within the same document for a hyperlink to be inserted dynamically. This expression is mandatory and must return a non‑empty value.

In turn, `display_text_expression` defines text to be displayed for the hyperlink. This expression is optional. If it is omitted or returns an empty value, then during runtime, a value of `uri_or_bookmark_expression` is used as display text as well.

**Note** – Values of both `uri_or_bookmark_expression` and `display_text_expression` can be of any types. During runtime, `Object.toString()` is invoked to get textual representations of these expressions' values, which is useful for expressions of types like [URI](https://docs.oracle.com/javase/7/docs/api/java/net/URI.html), for example. 

While building a report, `uri_or_bookmark_expression` and `display_text_expression` are evaluated and their results are used to construct a hyperlink that replaces the corresponding `link` tag then. If `uri_or_bookmark_expression` returns the name of a bookmark in the same document, then the hyperlink navigates to the bookmark. Otherwise, the hyperlink navigates to a corresponding external resource.

**Note** – A `link` tag cannot be used within a chart.

------ 

## FAQ

1. **Q:** How do I create a hyperlink that points to an external URL?  
   **A:** Use the `link` tag with the URL as the first argument, e.g., `<<link ["https://example.com"] ["Visit Example"]>>`. The URL expression can be a string literal, a variable, or any object whose `toString()` returns a valid URI.

2. **Q:** Can I link to a bookmark inside the same document?  
   **A:** Yes. Provide the bookmark name as the `uri_or_bookmark_expression`, for example `<<link ["MyBookmark"] ["Go to Section"]>>`. At runtime the tag creates a hyperlink that navigates to the bookmark named *MyBookmark*.

3. **Q:** What happens if I omit the display‑text expression?  
   **A:** When the second argument is omitted or evaluates to an empty value, Aspose.Words uses the string representation of the first argument (the URI or bookmark name) as the visible text of the hyperlink.

4. **Q:** Is it possible to use a `link` tag inside a chart?  
   **A:** No. The `link` tag is not supported inside chart elements. Attempting to do so will cause the tag to be ignored or raise an error during report generation. Place the tag in regular paragraphs or tables instead.