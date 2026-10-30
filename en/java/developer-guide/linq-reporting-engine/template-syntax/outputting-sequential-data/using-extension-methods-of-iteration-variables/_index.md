---
title: Using Extension Methods of Iteration Variables
second_title: Aspose.Words for Java
articleTitle: Using Extension Methods of Iteration Variables
linktitle: Using Extension Methods of Iteration Variables
description: "Use extension methods for iteration variables of any type when building a report in Java."
type: docs
weight: 40
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/using-extension-methods-of-iteration-variables/
timestamp: 2024-10-21-11-17-44
---

LINQ Reporting Engine provides special extension methods for iteration variables of any type. You can normally use these extension methods in template expressions. The following list describes the extension methods.

- indexOf()

Returns the zero-based index of a sequence item that is represented by the corresponding iteration variable. You can use this extension method to distinguish sequence items with different indexes and then handle them in different ways. For example, given that `items` is an enumeration of the strings “item1”, “item2”, and “item3”, you can use the following template to enumerate them prefixing all of them but the first one with commas.

{{< highlight csharp >}}
The items are: <<foreach [
    item in items]>><<[item.indexOf() != 0
        ? ", "
        : ""]>><<[item]>><</foreach>>.
{{< /highlight >}}

In this case, the engine produces a report as follows.

{{< highlight csharp >}}
The items are: item1, item2, item3.
{{< /highlight >}}

- numberOf()

Returns the one-based index of a sequence item that is represented by the corresponding iteration variable. You can use this extension method to number sequence items without involving Microsoft Word® lists. For example, given the previous declaration of items, you can enumerate and number them in a document table using the following template.

| No. | Item |
| :- | :- |
| {{< highlight csharp >}}
<<foreach [item in items]>><<[item.numberOf()]>>{{< /highlight >}} | {{< highlight csharp >}}
<<[item]>><</foreach>>{{< /highlight >}} |

In this case, the engine produces a report as follows.

| No. | Item |
| :- | :- |
| 1 | item1 |
| 2 | item2 |
| 3 | item3 |
  

------  

## FAQ

1. **Q:** How can I obtain the zero‑based position of the current item inside a `foreach` loop?  
   **A:** Use the `indexOf()` extension method on the iteration variable, e.g., `<<[item.indexOf()]>>`. It returns `0` for the first element, `1` for the second, and so on.

2. **Q:** What method should I use to get a one‑based (human‑friendly) index for numbering items?  
   **A:** Call `numberOf()` on the iteration variable, e.g., `<<[item.numberOf()]>>`. This returns `1` for the first element, `2` for the second, etc., which is useful for creating numbered lists without Word list formatting.

3. **Q:** Can I use these extension methods inside conditional expressions to treat the first or last element differently?  
   **A:** Yes. For example, `<<[item.indexOf() == 0 ? "First:" : ""]>>` adds a prefix only to the first item, and `<<[item.numberOf() == items.count() ? " (last)" : ""]>>` can identify the last element.

4. **Q:** How do I add a separator (such as a comma) before every item except the first one?  
   **A:** Combine `indexOf()` with a conditional expression: `<<[item.indexOf() != 0 ? ", " : ""]>>`. This inserts the separator only when the current index is not zero.

5. **Q:** Are `indexOf()` and `numberOf()` limited to string collections, or can they be used with any enumerable type?  
   **A:** They work with iteration variables of any type—lists of objects, custom classes, or primitive types—because the methods operate on the position of the item in the sequence, not on the item's value.