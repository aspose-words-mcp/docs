---
title: Removing Paragraphs Containing Only Template Syntax Tags in Java
second_title: Aspose.Words for Java
articleTitle: Removing Paragraphs Containing Only Template Syntax Tags
linktitle: Removing Paragraphs Containing Only Template Syntax Tags
description: "Learn how remove paragraphs containing only template tags using LINQ in Java."
type: docs
weight: 60
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/removing-paragraphs-containing-only-template-syntax-tags/
timestamp: 2024-07-02-05-47-58
---

While building a report, some paragraphs containing only template syntax tags can become empty after the tags are removed or replaced with empty values. To remove such paragraphs from the report, you can apply the `ReportBuildOptions.REMOVE_EMPTY_PARAGRAPHS` option as shown in the following example.

{{< highlight java >}}
ReportingEngine engine = new ReportingEngine();
engine.setOptions(ReportBuildOptions.REMOVE_EMPTY_PARAGRAPHS);
engine.buildReport(...);
{{< /highlight >}}

The difference in the engine's behavior when the option is applied and not applied is illustrated by the following examples.

**Example 1**

Template document

{{< highlight xml >}}
Prefix
<<[""]>>
Suffix
{{< /highlight >}}

Result document without `ReportBuildOptions.REMOVE_EMPTY_PARAGRAPHS` applied

{{< highlight xml >}}
Prefix

Suffix
{{< /highlight >}}

Result document with `ReportBuildOptions.REMOVE_EMPTY_PARAGRAPHS` applied

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

Result document without `ReportBuildOptions.REMOVE_EMPTY_PARAGRAPHS` applied

{{< highlight xml >}}
Prefix

Suffix
{{< /highlight >}}

Result document with `ReportBuildOptions.REMOVE_EMPTY_PARAGRAPHS` applied

{{< highlight xml >}}
Prefix
Suffix
{{< /highlight >}}

**Example 3**

**Note** – In this example, `persons` is assumed to be a data table having a field Name.

Template document

{{< highlight xml >}}
Prefix
<<foreach [in persons]>>
<<[Name]>>
<</foreach>>
Suffix
{{< /highlight >}}

Result document without `ReportBuildOptions.REMOVE_EMPTY_PARAGRAPHS` applied
{{< highlight xml >}}
Prefix

John Doe

Jane Doe

John Smith

Suffix
{{< /highlight >}}

Result document with `ReportBuildOptions.REMOVE_EMPTY_PARAGRAPHS` applied

{{< highlight xml >}}
Prefix
John Doe
Jane Doe
John Smith
Suffix
{{< /highlight >}}

The same functionality can be applied to selective paragraphs only. To achieve this, you can prepend names of corresponding tags with exclamation marks as shown in the following template snippet instead of applying of the `ReportBuildOptions.REMOVE_EMPTY_PARAGRAPHS` option.

{{< highlight xml >}}
<<![...]>>
<<!doc [...]>>
<<!foreach [...]>>...<</foreach>>
<<!if [...]>>...<<elseif [...]>>...<<else>>...<</if>>
{{< /highlight >}}

For a tag with its name prepended with an exclamation mark, the engine treats a corresponding paragraph or paragraphs as if `ReportBuildOptions.REMOVE_EMPTY_PARAGRAPHS` was applied. For the rest of tags, the engine behaves as if `ReportBuildOptions.REMOVE_EMPTY_PARAGRAPHS` was not applied.

------ 

## FAQ

1. **Q:** How do I enable the removal of empty paragraphs for the whole report?  
   **A:** Set the `ReportBuildOptions.REMOVE_EMPTY_PARAGRAPHS` flag on the `ReportingEngine` before calling `buildReport`. This tells the engine to delete any paragraph that contains only template tags that resolve to empty values.  

2. **Q:** Can I apply the removal behavior only to specific tags instead of the entire document?  
   **A:** Yes. Prefix the tag name with an exclamation mark in the template (e.g., `<<![...]>>`, `<<!foreach [...]>>`). The engine will treat paragraphs containing those tags as empty, while other tags will follow the default behavior.  

3. **Q:** Will a paragraph that contains whitespace or line‑break characters be removed when the option is enabled?  
   **A:** The engine treats a paragraph as empty if, after tag processing, it contains no visible characters. Whitespace and line‑breaks are ignored, so such a paragraph will still be removed.  

4. **Q:** What happens if a paragraph contains both regular text and a tag that resolves to an empty string?  
   **A:** The paragraph is retained because it still contains visible text. The removal option only affects paragraphs that consist solely of tags (or tags that become empty).  