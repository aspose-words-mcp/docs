---
title: Find and Replace in Java
second_title: Aspose.Words for Java
articleTitle: Find and Replace
linktitle: Find and Replace
type: docs
description: "Find a string or regular expression pattern in your document and replace it with the text you want using Java."
weight: 100
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/find-and-replace/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains additional find-and-replace features including regex, wildcards, and custom callbacks.

{{% /alert %}}

You can easily navigate within your document using a keyboard and mouse, but if you have many pages to scroll through, it will take quite a while to find specific text in a long document. It will be more time consuming when you want to replace certain characters or words that you have used in your document. The “Find and replace” functionality enables you to find a sequence of characters in a document and replace it with another sequence of characters.

Aspose.Words allows you to find a specific string or regular expression pattern in your document and replace it with an alternative without installing and using additional applications such as Microsoft Word. This will speed up many typing and formatting tasks, potentially saving you hours of work.

This article explains how to apply string replacement and regular expressions with the support of metacharacters.

## Ways to Find and Replace {#ways-to-find-and-replace}

Aspose.Words provides two ways to apply the find and replace operation by using the following:

1. *Simple string replacement* – to find and replace a specific string with another, you need to specify a search string (alphanumeric characters) that is going to be replaced according to all occurrences with another specified replacement string. Both strings must not contain symbols. Take into account that string comparison can be case-sensitive, or you may be unsure of spelling or have several similar spellings.
2. *Regular expressions* – to specify a regular expression to find the exact string matches and replace them according to your regular expression. Note that a word is defined as being made up of only alphanumeric characters. If replacement is executed with only whole words being matched and the input string happens to contain symbols, then no phrases will be found.

In addition, you can use special metacharacters with simple string replacement and regular expressions to specify breaks within the find and replace operation.

Aspose.Words presents the find and replace functionality with the [IReplacingCallback](https://reference.aspose.com/words/java/com.aspose.words/ireplacingcallback/) interface. You can work with many options during the find and replace process using [FindReplaceOptions](https://reference.aspose.com/words/java/com.aspose.words/findreplaceoptions/) class.

### Find and Replace Text Using Simple String Replacement {#find-and-replace-text-using-simple-string-replacement}

You can use one of the [replace()](https://reference.aspose.com/words/java/com.aspose.words/range/#replace-java.lang.String-java.lang.String) methods to find or replace a particular string and return the number of replacements that were made. In this case, you can specify a string to be replaced, a string that will replace all its occurrences, whether the replacement is case-sensitive, and whether only stand-alone words will be affected.

The following code example shows how to find the string “_CustomerName_” and replace it with the string *“James Bond”*:

{{< gist "aspose-words-gists" "98f7559b16319b1e49bd27dfbd62d062" "replace-with-string.java" >}}

You can notice the difference between the document before applying simple string replacement:

<img src="before-simple-string-replacement.png" alt="before-simple-string-replacement-java" style="width:600px"/>

And after applying simple string replacement:

<img src="after-simple-string-replacement.png" alt="after-simple-string-replacement-java" style="width:600px"/>

### Find and Replace Text Using Regular Expressions {#find-and-replace-text-using-regular-expressions}

A regular expression (regex) is a pattern that describes a certain sequence of text. Suppose you want to replace all double occurrences of a word with a single word occurrence. Then you can apply the following regular expression to specify the double-word pattern: `([a-zA-Z]+) \1`.

Use the other [replace()](https://reference.aspose.com/words/java/com.aspose.words/range/#replace-java.util.regex.Pattern-java.lang.String) method to search and replace particular character combinations by setting the `Regex` parameter as the regular expression pattern to find matches.

The following code example shows how to replace strings that match a regular expression pattern with a specified replacement string:

{{< gist "aspose-words-gists" "98f7559b16319b1e49bd27dfbd62d062" "replace-with-regex.java" >}}

You can notice the difference between the document before applying string replacement with regular expressions:

<img src="before-replacement-with-regular-expressions.png" alt="before-replacement-with-regular-expressions-java" style="width:600px"/>

And after applying string replacement with regular expressions:

<img src="after-replacement-with-regular-expressions.png" alt="after-replacement-with-regular-expressions-java" style="width:600px"/>

### Find and Replace String Using Metacharacters {#find-and-replace-text-using-metacharacters}

You can use metacharacters in the search string or the replacement string if a particular text or phrase is composed of multiple paragraphs, sections, or pages. Some of the metacharacters include **&p** for a paragraph break, **&b** for a section break, **&m** for a page break, and **&l** for a line break.

{{% alert color="primary" %}}

Note that the metacharacter **&&** equals to **&**. For example, if you need to find text for **&p** that is not a paragraph break, then you can use **&&p**.

{{% /alert %}}

The following code example shows how to replace text with paragraph and page break:

{{< gist "aspose-words-gists" "98f7559b16319b1e49bd27dfbd62d062" "replace-text-containing-meta-characters.java" >}}

## Find and Replace String in Header/Footer of a Document {#find-and-replace-string-in-header-or-footer-of-a-document}

You can find and replace text in the header/footer section of a Word document using the [HeaderFooter](https://reference.aspose.com/words/java/com.aspose.words/headerfooter/) class.

The following code example shows how to replace the text of the footer section in your document:

{{< gist "aspose-words-gists" "98f7559b16319b1e49bd27dfbd62d062" "replace-text-in-footer.java" >}}

You can notice the difference between the document before applying footer string replacement:

<img src="before-applying-footer-string-replacement.png" alt="before-applying-footer-string-replacement-java" style="width:600px"/>

And after applying footer string replacement:

<img src="after-applying-footer-string-replacement.png" alt="after-applying-footer-string-replacement-java" style="width:600px"/>

## Ignore Text During Find and Replace {#ignore-text-during-find-and-replace}

While applying the find and replace operation, you can ignore certain segments of the text. So, certain parts of the text can be excluded from the search, and the find and replace can be applied only to the remaining parts.

Aspose.Words provides many find and replace properties for ignoring text such as [getIgnoreDeleted()](https://reference.aspose.com/words/java/com.aspose.words/findreplaceoptions/#getIgnoreDeleted), [getIgnoreFieldCodes()](https://reference.aspose.com/words/java/com.aspose.words/findreplaceoptions/#getIgnoreFieldCodes), [getIgnoreFields()](https://reference.aspose.com/words/java/com.aspose.words/findreplaceoptions/#getIgnoreFields), [getIgnoreFootnotes()](https://reference.aspose.com/words/java/com.aspose.words/findreplaceoptions/#getIgnoreFootnotes), and [getIgnoreInserted()](https://reference.aspose.com/words/java/com.aspose.words/findreplaceoptions/#getIgnoreInserted).

The following code example shows how to ignore text inside delete revisions:

{{< gist "aspose-words-gists" "98f7559b16319b1e49bd27dfbd62d062" "ignore-text-inside-delete-revisions.java" >}}

## Customize Find and Replace Operation {#customize-find-and-replace-operation}

Aspose.Words provides many different [properties](https://reference.aspose.com/words/java/com.aspose.words/findreplaceoptions/) to find and replace text such as applying specific format with [getApplyFont()](https://reference.aspose.com/words/java/com.aspose.words/findreplaceoptions/#getApplyFont) and [ApplyParagraphFormats](https://reference.aspose.com/words/java/com.aspose.words/findreplaceoptions/#getApplyParagraphFormat) properties, using substitutions in replacement patterns with [getUseSubstitutions()](https://reference.aspose.com/words/java/com.aspose.words/findreplaceoptions/#getUseSubstitutions) property, and others.

The following code example shows how to highlight a specific word in your document:

{{< gist "aspose-words-gists" "98f7559b16319b1e49bd27dfbd62d062" "highlight-color.java" >}}

Aspose.Words allows you to use the [IReplacingCallback](https://reference.aspose.com/words/java/com.aspose.words/ireplacingcallback/) interface to create and call a custom method during a replace operation. You may have some use cases where you need to customize the find and replace operation such as replacing text specified with a regular expression with HTML tags, so basically you will apply replace with inserting HTML.

If you need to replace a string with an HTML tag, apply the **IReplacingCallback** interface to customize the find and replace operation so the match starts at the beginning of a run with the match node of your document. Let us provide several examples of using **IReplacingCallback**.

The following code example shows how to replace text specified with HTML:

{{< gist "aspose-words-gists" "98f7559b16319b1e49bd27dfbd62d062" "replace-with-html.java" >}}

The following code example shows how to prepend a line number to each line:

{{< gist "aspose-words-gists" "98f7559b16319b1e49bd27dfbd62d062" "line-counter.java" >}}

## FAQ

1. **Q:** How can I replace text with HTML markup while preserving the document's formatting?  
   **A:** Implement the `IReplacingCallback` interface and, in the `replacing` method, insert the HTML using `DocumentBuilder.insertHtml`. Set `FindReplaceOptions.setReplacingCallback` to your callback instance, then call `Range.replace` with a regex that matches the placeholder.

2. **Q:** What is the easiest way to replace a merge field without affecting its surrounding runs?  
   **A:** `Range.replace` does not find a merge field by its displayed name such as `«CustomerName»`, because that text is the field result. Run a mail merge, or move a `DocumentBuilder` to the field with `builder.moveToMergeField("CustomerName")` and write the value with `builder.write(...)`. `moveToMergeField` removes the field, so the surrounding runs are not affected.

3. **Q:** How do I ignore text inside deleted revisions or footnotes during a replace operation?  
   **A:** Configure `FindReplaceOptions` by enabling `setIgnoreDeleted(true)` and/or `setIgnoreFootnotes(true)`. Pass the options to `Range.replace` and the engine will skip those nodes.

4. **Q:** Can I use metacharacters to insert line or page breaks in the replacement string?  
   **A:** Yes. Include `&l` for a line break, `&p` for a paragraph break, `&m` for a page break, or `&b` for a section break in the replacement text. Escape an ampersand with `&&` if you need a literal `&`.

5. **Q:** How can I replace text only in headers or footers without affecting the main body?  
   **A:** Iterate through each `HeaderFooter` via `Document.getFirstSection().getHeadersFooters()`, then call `headerFooter.getRange().replace(search, replace, options)` on the header/footer range only. This isolates the operation to those parts.