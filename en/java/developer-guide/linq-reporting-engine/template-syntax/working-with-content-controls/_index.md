---
title: Working with Content Controls in Java
second_title: Aspose.Words for Java
articleTitle: Working with Content Controls
linktitle: Working with Content Controls
description: "Perform certain operations on content controls dynamically while building a report in Java."
type: docs
weight: 83
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-content-controls/
timestamp: 2024-01-27-14-07-04
---

LINQ Reporting Engine enables you to perform certain operations on content controls dynamically while building a report.

**Note** – To work with content controls in template documents using Microsoft Word®, you may need to [show the Developer tab on its ribbon](https://docs.microsoft.com/en-us/visualstudio/vsto/how-to-show-the-developer-tab-on-the-ribbon?view=vs-2022).

## Setting Checkbox Value Dynamically

You can set checkbox values to either checked or unchecked in your reports dynamically by taking the following steps:

1. Add a checkbox content control to your template at a place where you want it to appear in a result document.
1. By editing content control properties, add a check tag to the title of the checkbox content control using the following syntax.

{{< highlight csharp >}}
<<check [conditional_expression]>>
{{< /highlight >}}

Here, `conditional_expression` defines a condition upon which the value of the checkbox content control is to be set to checked (or unchecked, if the condition is not met). The conditional expression must return a `Boolean` value.

While building a report, a conditional expression declared within a `check` tag is evaluated and the value of its containing checkbox content control is set accordingly. The `check` tag itself is removed then.

## Adding Combobox and Dropdown List Items Dynamically

You can dynamically add items to comboboxes and dropdown lists defined in your template by taking the following steps:

1. Add a combobox or dropdown list content control to your template at a place where you want it to appear in a result document.
2. By editing content control properties, add an `item` tag to the title of this content control using the following syntax.

{{< highlight csharp >}}
<<item [value_expression] [display_name_expression]>>
{{< /highlight >}}

Here, `value_expression` defines a value of a combobox or dropdown list item to be added dynamically. This expression is mandatory and must return a non‑empty value.

In turn, `display_name_expression` defines a display name of the combobox or dropdown list item to be added. This expression is optional. If it is omitted, then during runtime, a value of `value_expression` is used as a display name as well.

**Note** – Values of both `value_expression` and `display_name_expression` can be of any types. During runtime, `Object.toString()` is invoked to get textual representations of these expressions' values.

While building a report, `value_expression` and `display_name_expression` are evaluated and a corresponding combobox or dropdown list item is added. A declaring `item` tag is removed then.

A single `item` tag causes addition of a single combobox or dropdown list item during runtime. You can add multiple combobox or dropdown list items using multiple `item` tags as shown in the following snippet.

{{< highlight csharp >}}
<<item ...>><<item ...>>
{{< /highlight >}}

Also, you can normally use `item` tags within data bands to add a combobox or dropdown list item per item of a data collection. For example, given that `clients` is a `DataTable` instance having a field named “Name”, you can use the following template to cover such a scenario.

{{< highlight csharp >}}
<<foreach [client in clients]>><<item [client.Name]>><</foreach>>
{{< /highlight >}}

An `item` tag can also be combined with an `if` tag to add a combobox or dropdown list item depending on a condition as shown in the following snippet.

{{< highlight csharp >}}
<<if ...>><<item ...>><</if>>
{{< /highlight >}}

Existing combobox and dropdown list items are not affected by `item` tags. Thus, you can combine both ways of adding combobox and dropdown list items using a template: static and dynamic.

**Note** – While inserting a combobox or dropdown list, Microsoft Word adds a default item that has to be removed manually, if the item is unwanted.

## Setting Content Control Titles Dynamically

You can normally use common expression tags in content control titles, thus forming their contents dynamically. For example, given that `s` is a string value, you can set a content control title from this value dynamically by putting the following expression tag into the title.

{{< highlight csharp >}}
<<[s]>>
{{< /highlight >}}

------ 

## FAQ

1. **Q:** How do I set a checkbox content control to checked or unchecked based on data?  
   **A:** Add a `check` tag to the checkbox title, e.g., `<<check [order.IsPaid]>>`. The expression must return a Boolean; if true, the checkbox is checked, otherwise it remains unchecked. The tag is removed after evaluation.

2. **Q:** How can I add items to a combobox or dropdown list at runtime?  
   **A:** Use the `item` tag inside the content control title: `<<item [value] [displayName]>>`. Place multiple `item` tags or put them inside a `foreach` loop to add many items dynamically.

3. **Q:** Is it possible to set the title of a content control dynamically?  
   **A:** Yes. Insert an expression tag directly in the title, such as `<<[customer.Name]>>`. The expression is evaluated and the resulting string becomes the control's title.

4. **Q:** Can I conditionally add a combobox item?  
   **A:** Combine `if` and `item` tags: `<<if [product.InStock]>> <<item [product.Id] [product.Name]>> <</if>>`. The item is added only when the condition evaluates to true.

5. **Q:** Word adds a default item to a new combobox; how do I remove it?  
   **A:** The default item must be removed manually in the template before processing, or you can delete it after the report is built: get the combobox `StructuredDocumentTag` and call `sdt.getListItems().removeAt(0)`.