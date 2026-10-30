---
title: Apply Custom Formatting to Fields
second_title: Aspose.Words for Java
articleTitle: Apply Custom Formatting to Fields
linktitle: Apply Custom Formatting to Fields
description: "Format and evaluate fields result using Java."
type: docs
weight: 40
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/applying-custom-formatting-to-fields/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page outlines how to apply custom formatting to fields (like merge fields or document variables) in Aspose.Words.

{{% /alert %}}

Sometimes users need to apply custom formatting to fields. In this article, we will look at a couple of examples of how this can be done.

To learn more options, see the full list of properties for each field type in the corresponding class in the [com.aspose.words](https://reference.aspose.com/words/java/com.aspose.words/) package.

## How to Apply Custom Formatting to Field Result

Aspose.Words provides API for custom formatting of field's result. You can implement [IFieldResultFormatter](https://reference.aspose.com/words/java/com.aspose.words/ifieldresultformatter/) interface to control how the field result is formatted. You can apply numeric format switch, i.e. \# "#.##", date/time format switch, i.e. \@ "dd.MM.yyyy", and number format switch, i.e. \* Ordinal.

The following code example shows how to apply custom formatting for the field result:

{{< gist "aspose-words-gists" "de2643d9d0ea757bcbb6934f66f9f841" "field-result-formatting.java" >}}

{{< gist "aspose-words-gists" "de2643d9d0ea757bcbb6934f66f9f841" "field-result-formatter.java" >}}

## How to evaluate `IF` condition

If you want to evaluate `IF` condition after mail merge, you can use the [evaluateCondition()](https://reference.aspose.com/words/java/com.aspose.words/fieldif/#evaluateCondition) method that immediately returns the result of the expression evaluation.

The following code example shows how to use this method:

{{< gist "aspose-words-gists" "de2643d9d0ea757bcbb6934f66f9f841" "evaluate-if-condition.java" >}}

## How to Apply Custom Formatting to Time Field

By default Aspose.Words updates `TIME` field with current culture short time format. If you want to format the `TIME` field according to your requirement, you can achieve this by implementing [IFieldUpdateCultureProvider](https://reference.aspose.com/words/java/com.aspose.words/ifieldupdatecultureprovider/) interface.

The following code examples shows how to apply custom formatting to the `TIME` field:

{{< gist "aspose-words-gists" "de2643d9d0ea757bcbb6934f66f9f841" "field-update-culture.java" >}}

{{< gist "aspose-words-gists" "de2643d9d0ea757bcbb6934f66f9f841" "field-update-culture-provider.java" >}}

## Related APIs

- [IFieldResultFormatter](https://reference.aspose.com/words/java/com.aspose.words/ifieldresultformatter/)
- [FieldIf.evaluateCondition](https://reference.aspose.com/words/java/com.aspose.words/fieldif/#evaluateCondition)
- [IFieldUpdateCultureProvider](https://reference.aspose.com/words/java/com.aspose.words/ifieldupdatecultureprovider/)
- [Field](https://reference.aspose.com/words/java/com.aspose.words/field/)

## FAQ

1. **Q:** How can I format a date field with a custom pattern?  
   **A:** Implement `IFieldResultFormatter` and, in its `formatDateTime(Date value, String format, int calendarType)` method, return the string formatted with `SimpleDateFormat` and the desired pattern, such as `"dd.MM.yyyy"`. Assign the formatter with `doc.getFieldOptions().setResultFormatter(...)`.

2. **Q:** What switch should I use to apply a numeric format to a field result?  
   **A:** Use the numeric format switch `\# "#.##"` (or any valid .NET/Java numeric format string) inside the field code. The custom formatter can also apply this switch programmatically.

3. **Q:** How do I evaluate an `IF` field after performing a mail merge?  
   **A:** Call `FieldIf.evaluateCondition()` on the `FieldIf` object. This method returns a `FieldIfComparisonResult` value (`TRUE`, `FALSE`, or `ERROR`) indicating the result of the expression without needing to update the whole document.

4. **Q:** How can I change the culture used by the `TIME` field?  
   **A:** Implement `IFieldUpdateCultureProvider` and return a `CultureInfo` that matches your required time format. Register it with `doc.getFieldOptions().setFieldUpdateCultureProvider(provider)` and set `doc.getFieldOptions().setFieldUpdateCultureSource(FieldUpdateCultureSource.FIELD_CODE)`; the provider is used when the fields are updated.

5. **Q:** Is it possible to apply an ordinal number format (e.g., 1st, 2nd) to a field?  
   **A:** Yes. Use the number format switch `\* Ordinal` in the field code, or return the ordinal string from your `IFieldResultFormatter` implementation for the field's result.