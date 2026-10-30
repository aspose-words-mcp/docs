---
title: Removing Paragraphs with Template Syntax Tags in C#
second_title: Aspose.Words for .NET
articleTitle: Removing Paragraphs Containing Only Template Syntax Tags
linktitle: Removing Paragraphs Containing Only Template Syntax Tags
description: "Learn how remove paragraphs containing only template tags using LINQ in C#."
type: docs
weight: 60
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/removing-paragraphs-containing-only-template-syntax-tags/
timestamp: 2024-10-21-11-17-44
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to remove paragraphs that contain only template syntax tags during document generation.

{{% /alert %}}

While building a report, some paragraphs containing only template syntax tags can become empty after the tags are removed or replaced with empty values. To remove such paragraphs from the report, you can apply the `ReportBuildOptions.RemoveEmptyParagraphs` option as shown in the following example.

{{< highlight csharp >}}
ReportingEngine engine = new ReportingEngine();
engine.Options |= ReportBuildOptions.RemoveEmptyParagraphs;
engine.BuildReport(...);
{{< /highlight >}}

The difference in the engine's behavior when the option is applied and not applied is illustrated by the following examples.

**Example 1**

Template document

{{< highlight xml >}}
Prefix
<<[""]>>
Suffix
{{< /highlight >}}

Result document without `ReportBuildOptions.RemoveEmptyParagraphs` applied

{{< highlight xml >}}
Prefix

Suffix
{{< /highlight >}}

Result document with `ReportBuildOptions.RemoveEmptyParagraphs` applied

{{< highlight xml >}}
Prefix
Suffix
{{< /highlight >}}

**Example 2**

Template document

{{< highlight xml >}}
Prefix
<<if [false]>>
Text to be removed
<</if>>
Suffix
{{< /highlight >}}

Result document without `ReportBuildOptions.RemoveEmptyParagraphs` applied
{{< highlight xml >}}
Prefix

Suffix
{{< /highlight >}}

Result document with `ReportBuildOptions.RemoveEmptyParagraphs` applied
{{< highlight xml >}}
Prefix
Suffix
{{< /highlight >}}

**Example 3**

**Note** – In this example, `persons` is assumed to be a data table having a field `Name`.

Template document

{{< highlight xml >}}
Prefix
<<foreach [in persons]>>
<<[Name]>>
<</foreach>>
Suffix
{{< /highlight >}}

Result document without `ReportBuildOptions.RemoveEmptyParagraphs` applied

{{< highlight xml >}}
Prefix

John Doe

Jane Doe

John Smith

Suffix
{{< /highlight >}}

Result document with `ReportBuildOptions.RemoveEmptyParagraphs` applied

{{< highlight xml >}}
Prefix
John Doe
Jane Doe
John Smith
Suffix
{{< /highlight >}}

The same functionality can be applied to selective paragraphs only. To achieve this, you can prepend names of corresponding tags with exclamation marks as shown in the following template snippet instead of applying of the `ReportBuildOptions.RemoveEmptyParagraphs` option.

{{< highlight xml >}}
<<![...]>>
<<!doc [...]>>
<<!foreach [...]>>...<</foreach>>
<<!if [...]>>...<<elseif [...]>>...<<else>>...<</if>>
{{< /highlight >}}

For a tag with its name prepended with an exclamation mark, the engine treats a corresponding paragraph or paragraphs as if `ReportBuildOptions.RemoveEmptyParagraphs` was applied. For the rest of tags, the engine behaves as if `ReportBuildOptions.RemoveEmptyParagraphs` was not applied.

## Limitations and Considerations

- The `ReportBuildOptions.RemoveEmptyParagraphs` option works at the paragraph level and only removes paragraphs that consist solely of a template tag (or tag with an exclamation mark). If a paragraph contains invisible characters such as spaces, tabs, or line breaks besides the tag, it will not be removed. Remove any extra whitespace from the template to allow the paragraph to be deleted.

- The option applies globally to all paragraphs in the document when set on `ReportingEngine.Options`. To apply the removal selectively to specific tags, prepend the tag name with an exclamation mark (`!`). For example, use `<<!foreach [in persons]>>` to remove paragraphs containing only that specific tag.

- The option can be combined with other `ReportBuildOptions` using the bitwise OR operator, e.g., `engine.Options |= ReportBuildOptions.RemoveEmptyParagraphs | ReportBuildOptions.AllowMissingMembers;`.

- When applied to table cells containing only a template tag, the option removes the entire paragraph (and thus the cell content), which may collapse the row if it becomes empty. The option does not delete the table structure itself.

------

## FAQ
1. **Q:** How do I enable automatic removal of empty paragraphs that contain only template tags?  
   **A:** Set the `ReportBuildOptions.RemoveEmptyParagraphs` flag on the `ReportingEngine.Options` property before building the report. Example:  
   ```csharp
   ReportingEngine engine = new ReportingEngine();
   engine.Options |= ReportBuildOptions.RemoveEmptyParagraphs;
   engine.BuildReport(...);
   ```

2. **Q:** Can I apply the empty‑paragraph removal to only specific tags instead of the whole document?  
   **A:** Yes. Prefix the tag name with an exclamation mark (`!`) in the template. The engine will treat paragraphs containing those tags as empty and remove them, while leaving other tags unaffected. Example: `<<!foreach [in persons]>>`.

3. **Q:** Why does a paragraph remain after I enabled `RemoveEmptyParagraphs`?  
   **A:** The paragraph may contain invisible characters such as spaces, tabs, or line‑breaks besides the tag. The option removes a paragraph only when it consists solely of the tag (or tag with an exclamation mark). Remove any extra whitespace from the template to allow the paragraph to be deleted.

4. **Q:** Can `ReportBuildOptions.RemoveEmptyParagraphs` be combined with other `ReportBuildOptions`?  
   **A:** Absolutely. Use the bitwise OR operator to combine multiple options, e.g.,  
   ```csharp
   engine.Options |= ReportBuildOptions.RemoveEmptyParagraphs | ReportBuildOptions.AllowMissingMembers;
   ```

5. **Q:** Does the empty‑paragraph removal affect tables or other container elements?  
   **A:** The option works at the paragraph level. If a table cell contains only a tag that becomes empty, the entire paragraph (and thus the cell content) is removed, which may collapse the row if it becomes empty. It does not delete the table structure itself.