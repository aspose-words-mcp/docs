---
title: Mail Merge Template from Mustache Syntax
second_title: Aspose.Words for Java
articleTitle: Mail Merge Template from Mustache Syntax
linktitle: Mail Merge Template from Mustache Syntax
type: docs
description: "Create templates with Mustache syntax. Mustache syntax is the only option to use with templates that do not contain fields (HTML or TXT). With Word templates, you have two options: fields or Mustache syntax using Java."
keywords: "mail merge template mustache syntax java, Mail Merge java, mustache syntax java"
weight: 40
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/mail-merge-template-from-mustache-syntax/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to create mail-merge templates using Mustache syntax and how Aspose.Words interprets template tags.

{{% /alert %}}

Aspose.Words allows you to create templates with mustache syntax in addition to the familiar templates. A Mustache is an alternative variant of template syntax that consists of tag names enclosed by   and is backed by a model object that contains the data for the template.

The Mustache syntax is the only option to use with templates that do not contain fields, such as HTML and TXT templates. With Word templates, you have two options either to use fields or Mustache syntax.

The Mustache syntax supports *foreach* tag, which is an alternative for using Mail Merge with regions. So the benefit is that you can use mustache syntax if for some reason you are not able or simply you do not want to use merge fields and merge regions.

You can also combine Mail Merge fields with some additional fields using the *foreach* tag as shown in the picture below.

<img src="mustache-syntax.png" alt="mustache_syntax_aspose_words_java" style="width:800px"/>

## Create a Mustache Template

The first important point to clarify is that Mustache is not a templating engine. Mustache is another syntax variant which is available for any template in a [load format](https://reference.aspose.com/words/java/com.aspose.words/loadformat/) supported by Aspose.Words. Therefore, you can create such a template both programmatically and through an interface, you just need to include certain syntax and comply with the Mustache specification.

Let's suppose that you need to send the same email to 50 recipients to personalize the greeting with their corresponding first names. You could replace the recipient's first name by some placeholder as the following:

> Dear {{FirstName}}
>
> I hereby...

The question here: how you can create 50 emails from 1 single Mustache template? To answer that, you need to perform a Mail Merge with regions to fill the curly braces for placeholders in the template with actual data and generate an output document.

<img src="mustache-template.png" alt="mustache_template_aspose_words_java" style="width:650px"/>

{{% alert color="primary" %}}

As you notice from the example above, in Mustache you need to use curly braces for placeholders that look like a mustache when you rotate the curly braces 90 degrees clockwise.

{{% /alert %}}

## Work with Mustache Syntax

Mustache is represented as a logic-less order as it lacks any specific control flow statements such as *for* loops and *if* and *else* conditions. But you can use the section tags processing lists and lambdas to achieve conditional evaluation and looping. So to include the Mustache syntax within the Mail Merge operation, you will need to use the [getUseNonMergeFields()](https://reference.aspose.com/words/java/com.aspose.words/mailmerge/#getUseNonMergeFields) property and set its value to *True*.

The following code example shows how to replace the Mustache tags with specific data:

{{< gist "aspose-words-gists" "c0c6109b3d172b64370a9684b6330fe4" "mustache-syntax-using-data-table.java" >}}

You can notice the difference between the document before executing the Mail Merge with regions along with applying the **getUseNonMergeFields()** property:

<img src="mustache-syntax-1.png" alt="mustache_syntax_aspose_words_java" style="width:400px"/>

{{% alert color="primary" %}}

A section begins with a pound and ends with a slash. That is, `{{#foreach list}}` begins a "foreach" section while `{{/foreach list}}` ends it.

{{% /alert %}}

And after applying the Mail Merge with regions:

<img src="mustache-syntax-2.png" alt="mustache_syntax_result_aspose_words_java" style="width:300px"/>

## Use `IF` Fields to Make a Mail Merge Intelligent

Aspose.Words allows you to use Mail Merge fields and Mustache tags with the `IF` statement. The `IF` fields can be used in any Mail Merge document to suppress undesired spaces and commas if a field is blank.

The `IF` field formula is shown below:

**{ IF [Condition] [Display Result 1] [Display Result 2] }**

Here, the Condition can be either a merge field or a Mustache tag.

For example, you can use `IF` fields if you need to insert “his”, “her”, “he” or “she” depending on the gender as the following:

**{ IF { MERGEFIELD Gender } = MALE “true text” “false text” }**

**{ IF “{{ GENDER }}” = MALE “true text” “false text” }**

The following code example shows how to perform a Mail Merge operation with Mustache tags and `IF` fields:

{{< gist "aspose-words-gists" "c0c6109b3d172b64370a9684b6330fe4" "use-if-else-mustache.java" >}}

You can notice the difference between the document before applying the **getUseNonMergeFields()** property:

<img src="mustache-if-field-1.png" alt="mustache_if_field_aspose_words_java" style="width:800px"/>

And after applying the **getUseNonMergeFields()** property:

<img src="mustache-if-field-2.png" alt="mustache_if_field_2_aspose_words_java" style="width:800px"/>

------ 

## FAQ

1. **Q:** How do I enable Mustache syntax processing in a Word template?  
   **A:** Call `MailMerge.setUseNonMergeFields(true)` before calling any mail‑merge methods. This tells Aspose.Words to treat `{{…}}` tags as Mustache placeholders instead of regular merge fields.

2. **Q:** How can I iterate over a collection using Mustache in a mail‑merge operation?  
   **A:** Use the `{{#foreach collection}} … {{/foreach collection}}` section tags. After calling `setUseNonMergeFields(true)`, call `MailMerge.executeWithRegions` (or the equivalent API) and pass a data source that contains the collection.

3. **Q:** Is it possible to mix regular Mail Merge fields with Mustache tags in the same document?  
   **A:** Yes. When `getUseNonMergeFields()` is `true`, Aspose.Words first processes standard merge fields and then replaces Mustache tags. This allows you to combine both approaches in a single template.

4. **Q:** How can I add conditional logic with Mustache tags?  
   **A:** Use Word's built‑in `IF` field and reference a Mustache tag inside the condition, e.g. `{ IF "{{ GENDER }}" = MALE "He" "She" }`. The `IF` field evaluates the value that the Mustache tag resolves to after the merge.

5. **Q:** Why do I get an error about a mail merge region without a matching end when using Mustache syntax?  
   **A:** This error (e.g., “Found start of mail merge region 'list' without matching end”) means a section tag is not closed. Ensure every opening tag like `{{#foreach list}}` has a matching closing tag `{{/foreach list}}` and that there are no stray characters inside the braces.