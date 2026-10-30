---
title: Forcing Movement to Next Item within Data Band
second_title: Aspose.Words for Java
articleTitle: Forcing Movement to Next Item within Data Band
linktitle: Forcing Movement to Next Item within Data Band
description: "Force movement to the next item within a data band when building a report in Java."
type: docs
weight: 50
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/forcing-movement-to-next-item-within-data-band/
timestamp: 2024-10-21-11-17-44
---

You can instruct the engine to force movement to the next item within a data band using a `next` tag. This feature is useful in label‑print‑like scenarios when you need to output data about a fixed number of items in a single table row like in the following example. Given that `Clients` is a `DataTable` instance having a field named "Name", you can use the following template to output three client names per table row while outputting names of all clients in a single table.

| &lt;&lt;foreach [c in Clients]&gt;&gt;&lt;&lt;[c.Name]&gt;&gt; | &lt;&lt;next&gt;&gt;&lt;&lt;[c.Name]&gt;&gt; | &lt;&lt;next&gt;&gt;&lt;&lt;[c.Name]&gt;&gt; &lt;&lt;/foreach&gt;&gt; |
| :- | :- | :- |


In this case, the engine produces a report as follows.

| A Company | B Ltd. | C & D |
| :- | :- | :- |
| **E Corp.** | **F & Partners** | **G & Co.** |
| **H Group** | **I & Sons** | **J Ent.** |


------ 

## FAQ

1. **Q:** How does the `next` tag affect the position of data within a data band?  
   **A:** The `next` tag moves the engine to the next item of the data band's sequence; the content after the tag is filled with the data of that item. It is typically used inside a `foreach` loop to place consecutive items side‑by‑side in the same row.

2. **Q:** Can the `next` tag be combined with other tags such as `if` or `else`?  
   **A:** Yes. The `next` tag works together with other tags. For example, you can place an `if` block after a `next` tag to output data of the next item only when a condition is met.

3. **Q:** What happens if the data source contains fewer items than the number of `next` positions defined in the template?  
   **A:** The engine stops iterating when the data source is exhausted, leaving any remaining cells in the row empty. No error is thrown; the output simply contains blank cells for the missing items.

4. **Q:** Is the `next` tag available in other language APIs (e.g., .NET, C++)?  
   **A:** The `next` tag is part of the Aspose.Words Reporting Engine syntax and works the same across all supported languages, including Java, .NET, and C++. The only difference is the surrounding code used to load the template and data.

5. **Q:** Can I change the number of items per row dynamically (e.g., based on a configuration value)?  
   **A:** Yes. You can generate the template programmatically or use conditional logic to insert the appropriate number of `next` tags based on a variable that holds the desired column count. The engine will respect the generated template at runtime.