---
title: Outputting Expression Results in C#
second_title: Aspose.Words for .NET
articleTitle: Outputting Expression Results
linktitle: Outputting Expression Results
description: "Output expression results using placeholder within a template when building a report in C#."
type: docs
weight: 20
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/outputting-expression-results/
aliases: [/net/template-syntax/#outputting-expression-results]
timestamp: 2024-10-21-11-17-44
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to output expression results during template processing with the LINQ Reporting Engine.

{{% /alert %}}

You can output expression results to your reports using expression tags. An expression tag denotes a placeholder for an expression result within a template. While building a report, the corresponding expression is evaluated, and this placeholder is replaced with the formatted result of the expression. 

An expression tag has no name and consists of the following elements:

- An expression enclosed by brackets
- An optional format string enclosed by double quotes and preceded by the ":" character
- An optional `html` switch

{{< highlight xml >}}
<<[expression]:"format" -html>>
{{< /highlight >}}

If `html` switch is not present, the result of the corresponding expression is written to a document as a plain text at runtime. Font attributes are derived from the first character of the corresponding tag in this case.

If `html` switch is present, the expression result is considered to be a HTML block and is written as such. This feature is useful, when you need to format text parts of an expression result in different ways. For example, the following tag is replaced with a content like "**Bold** and *italic* text" at runtime.

{{< highlight xml >}}
<<["<b>Bold</b> and <i>italic</i> text"] -html>>
{{< /highlight >}}

To format a numeric or date-time expression result, you can specify a format string as an element of the corresponding expression tag. Such format strings are the same as the ones that you pass to [IFormattable.ToString](https://docs.microsoft.com/en-us/dotnet/api/system.iformattable.tostring?view=net-6.0) method implementors. That is, for example, given that d is a `DateTime` value, you can use the following template to format the value using the "yyyy.MM.dd" pattern.

{{< highlight xml >}}
<<[d]:"yyyy.MM.dd">>
{{< /highlight >}}

LINQ Reporting Engine provides several additional number formats that can not be specified using format strings because these formats are missing in standard .NET libraries. The following table describes these formats.

| Number Format | Description |
| :- | :- |
| **alphabetic** | Formats an integer number as an upper-case letter (A, B, C, ...) |
| **roman** | Formats an integer number as an upper-case Roman numeral (I, II, III, ...) |
| **ordinal** | Appends an ordinal suffix to an integer number (1st, 2nd, 3rd, ...) |
| **ordinalText** | Converts an integer number to its ordinal text representation (First, Second, Third, ...) |
| **cardinal** | Converts an integer number to its text representation (One, Two, Three, ...) |
| **hex** | Formats an integer number as hexadecimal (8, 9, A, B, C, D, E, F, 10, 11, ...) |
| **arabicDash** | Encloses an integer number with dashes (- 1 -, - 2 -, - 3 -, ...) |
| **dollarText** | Converts a numeric value to its text representation with its fraction as Arabic numerators over 100 (for example, one thousand two hundred thirty-four and 56/100) |

You can specify one of these additional number formats instead of a format string like in the following example. Given that `i` is an integer number, you can format the number as an upper-case letter using the following template.

{{< highlight xml >}}
<<[i]:alphabetic>>
{{< /highlight >}}

LINQ Reporting Engine provides several additional string formats that can not be specified using format strings because these formats are missing in standard .NET libraries. The following table describes these formats.

| String Format | Description |
| :- | :- |
| **lower** | Converts a string to lower case ("the string") |
| **upper** | Converts a string to upper case ("THE STRING") |
| **caps** | Capitalizes a first letter of every word in a string ("The String") |
| **firstCap** | Capitalizes the first letter of the first word in a string ("The string") |

You can specify one of these additional string formats instead of a format string like in the following example. Given that `s` is a string, you can capitalize a first letter of every word in the string using the following template.

{{< highlight xml >}}
<<[s]:caps>>
{{< /highlight >}}

You can also specify one of the additional string formats together with a format string or an additional number format like in the following examples. Given that `d` is a `DateTime` value, you can convert its textual month representation to upper case using the following template.

{{< highlight xml >}}
<<[d]:"MMMM":upper>>
{{< /highlight >}}

Given that `i` is an integer number, you can convert the number to a lower‑case Roman numeral using the following template.

{{< highlight xml >}}
<<[i]:roman:lower>>
{{< /highlight >}}

**Note** – In contrast to format strings, additional number and string formats must not be enclosed with double quotes.

------

## FAQ

1. **Q:** How do I format a numeric value with a custom format string in a template?  
   **A:** Place the numeric expression inside brackets and add the format string after a colon, enclosed in double quotes, e.g., `<<[price]:"C2">>`. The engine evaluates the expression and applies the .NET format specifier when inserting the result.

2. **Q:** What syntax should I use to format a `DateTime` value?  
   **A:** Use the same bracketed expression with a .NET date‑time format string, for example `<<[orderDate]:"yyyy.MM.dd">>`. The date is formatted according to the pattern you provide.

3. **Q:** How can I apply string transformations such as upper‑case or title case?  
   **A:** Append one of the additional string formats after the expression, e.g., `<<[customerName]:upper>>` for upper‑case or `<<[title]:caps>>` to capitalize each word. These formats are not quoted.

4. **Q:** When should I use the `-html` switch in an expression tag?  
   **A:** Add `-html` when the expression result contains HTML markup that must be rendered as formatted content, e.g., `<<["<b>Bold</b>"] -html>>`. Without the switch, the markup is inserted as plain text.

5. **Q:** Can I combine a format string with an additional string or number format?  
   **A:** Yes. Place the format string first, then the additional format, separated by colons, for example `<<[amount]:"N2":upper>>` or `<<[i]:roman:lower>>`. The engine applies the .NET format, then the extra transformation.