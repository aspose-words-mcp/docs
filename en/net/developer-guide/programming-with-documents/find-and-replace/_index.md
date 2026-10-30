---
title: Find and Replace in C#
second_title: Aspose.Words for .NET
articleTitle: Find and Replace
linktitle: Find and Replace
type: docs
description: "Find a string or regular expression pattern in your document and replace it with the text you want using C#."
weight: 100
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/find-and-replace/
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

Aspose.Words presents the find and replace functionality with the [Aspose.Words.Replacing](https://reference.aspose.com/words/net/aspose.words.replacing/) namespace. You can work with many options during the find and replace process using [FindReplaceOptions](https://reference.aspose.com/words/net/aspose.words.replacing/findreplaceoptions/) class.

### Find and Replace Text Using Simple String Replacement {#find-and-replace-text-using-simple-string-replacement}

You can use one of the [Replace](https://reference.aspose.com/words/net/aspose.words/range/replace/#replace/) methods to find or replace a particular string and return the number of replacements that were made. In this case, you can specify a string to be replaced, a string that will replace all its occurrences, whether the replacement is case-sensitive, and whether only stand-alone words will be affected.

The following code example shows how to find the string “_CustomerName_” and replace it with the string *“James Bond”*:

{{< gist "aspose-words-gists" "27c3408b2c7fbee8d6dc6a1c8b61c105" "replace-with-string.cs" >}}

You can notice the difference between the document before applying simple string replacement:

<img src="before-simple-string-replacement.png" alt="before-simple-string-replacement" style="width:600px"/>

And after applying simple string replacement:

<img src="after-simple-string-replacement.png" alt="after-simple-string-replacement" style="width:600px"/>

### Find and Replace Text Using Regular Expressions {#find-and-replace-text-using-regular-expressions}

A regular expression (regex) is a pattern that describes a certain sequence of text. Suppose you want to replace all double occurrences of a word with a single word occurrence. Then you can apply the following regular expression to specify the double-word pattern: `([a-zA-Z]+) \1`.

Use the other [Replace](https://reference.aspose.com/words/net/aspose.words/range/replace/) method to search and replace particular character combinations by setting the `Regex` parameter as the regular expression pattern to find matches.

The following code example shows how to replace strings that match a regular expression pattern with a specified replacement string:

{{< gist "aspose-words-gists" "27c3408b2c7fbee8d6dc6a1c8b61c105" "replace-with-regex.cs" >}}

You can notice the difference between the document before applying string replacement with regular expressions:

<img src="before-replacement-with-regular-expressions.png" alt="before-replacement-with-regular-expressions" style="width:600px"/>

And after applying string replacement with regular expressions:

<img src="after-replacement-with-regular-expressions.png" alt="after-replacement-with-regular-expressions" style="width:600px"/>

### Find and Replace String Using Metacharacters {#find-and-replace-text-using-metacharacters}

You can use metacharacters in the search string or the replacement string if a particular text or phrase is composed of multiple paragraphs, sections, or pages. Some of the metacharacters include **&p** for a paragraph break, **&b** for a section break, **&m** for a page break, and **&l** for a line break.

{{% alert color="primary" %}}

Note that the metacharacter **&&** equals to **&**. For example, if you need to find text for **&p** that is not a paragraph break, then you can use **&&p**.

{{% /alert %}}

The following code example shows how to replace text with paragraph and page break:

{{< gist "aspose-words-gists" "27c3408b2c7fbee8d6dc6a1c8b61c105" "replace-text-containing-meta-characters.cs" >}}

## Find and Replace String in Header/Footer of a Document {#find-and-replace-string-in-header-or-footer-of-a-document}

You can find and replace text in the header/footer section of a Word document using the [HeaderFooter](https://reference.aspose.com/words/net/aspose.words/headerfooter/) class.

The following code example shows how to replace the text of the footer section in your document:

{{< gist "aspose-words-gists" "27c3408b2c7fbee8d6dc6a1c8b61c105" "replace-text-in-footer.cs" >}}

You can notice the difference between the document before applying footer string replacement:

<img src="before-applying-footer-string-replacement.png" alt="before-applying-footer-string-replacement" style="width:600px"/>

And after applying footer string replacement:

<img src="after-applying-footer-string-replacement.png" alt="after-applying-footer-string-replacement" style="width:600px"/>

## Ignore Text During Find and Replace {#ignore-text-during-find-and-replace}

While applying the find and replace operation, you can ignore certain segments of the text. So, certain parts of the text can be excluded from the search, and the find and replace can be applied only to the remaining parts.

Aspose.Words provides many find and replace properties for ignoring text such as [IgnoreDeleted](https://reference.aspose.com/words/net/aspose.words.replacing/findreplaceoptions/ignoredeleted/), [IgnoreFieldCodes](https://reference.aspose.com/words/net/aspose.words.replacing/findreplaceoptions/ignorefieldcodes/), [IgnoreFields](https://reference.aspose.com/words/net/aspose.words.replacing/findreplaceoptions/ignorefields/), [IgnoreFootnotes](https://reference.aspose.com/words/net/aspose.words.replacing/findreplaceoptions/ignorefootnotes/), and [IgnoreInserted](https://reference.aspose.com/words/net/aspose.words.replacing/findreplaceoptions/ignoreinserted/).

The following code example shows how to ignore text inside delete revisions:

{{< gist "aspose-words-gists" "27c3408b2c7fbee8d6dc6a1c8b61c105" "ignore-text-inside-delete-revisions.cs" >}}

## Customize Find and Replace Operation {#customize-find-and-replace-operation}

Aspose.Words provides many different [properties](https://reference.aspose.com/words/net/aspose.words.replacing/findreplaceoptions/) to find and replace text such as applying specific format with [ApplyFont](https://reference.aspose.com/words/net/aspose.words.replacing/findreplaceoptions/applyfont/) and [ApplyParagraphFormats](https://reference.aspose.com/words/net/aspose.words.replacing/findreplaceoptions/applyparagraphformat/) properties, using substitutions in replacement patterns with [UseSubstitutions](https://reference.aspose.com/words/net/aspose.words.replacing/findreplaceoptions/usesubstitutions/) property, and others.

The following code example shows how to highlight a specific word in your document:

{{< gist "aspose-words-gists" "27c3408b2c7fbee8d6dc6a1c8b61c105" "highlight-color.cs" >}}

Aspose.Words allows you to use the [IReplacingCallback](https://reference.aspose.com/words/net/aspose.words.replacing/ireplacingcallback/) interface to create and call a custom method during a replace operation. You may have some use cases where you need to customize the find and replace operation such as replacing text specified with a regular expression with HTML tags, so basically you will apply replace with inserting HTML.

If you need to replace a string with an HTML tag, apply the **IReplacingCallback** interface to customize the find and replace operation so the match starts at the beginning of a run with the match node of your document. Let us provide several examples of using **IReplacingCallback**.

The following code example shows how to replace text specified with HTML:

{{< gist "aspose-words-gists" "27c3408b2c7fbee8d6dc6a1c8b61c105" "replace-with-html.cs" >}}

The following code example shows how to prepend a line number to each line:

{{< gist "aspose-words-gists" "27c3408b2c7fbee8d6dc6a1c8b61c105" "line-counter.cs" >}}

------

## FAQ

1. **Q:** How can I perform a case‑insensitive find and replace?  
   **A:** Set the `FindReplaceOptions.MatchCase` property to `false` when calling `Range.Replace`. This tells Aspose.Words to ignore case while searching, so “Customer” and “customer” are treated as the same word.

2. **Q:** How do I replace text using a regular expression?  
   **A:** Use the overload of `Range.Replace` that accepts a `Regex` object. Pass the pattern to the `Regex` parameter and provide the replacement string. The method will replace every match that satisfies the regular expression.

3. **Q:** How can I replace text only in the main body and ignore headers, footers, or footnotes?  
   **A:** Call `Replace` on the body of each section instead of `doc.Range`: `foreach (Section section in doc.Sections) section.Body.Range.Replace("old", "new", options);`. Headers and footers are not part of the body. To skip footnotes and endnotes as well, set `FindReplaceOptions.IgnoreFootnotes` to `true`.

4. **Q:** How do I replace a match with HTML markup?  
   **A:** Pass the HTML as the replacement string and implement the `IReplacingCallback` interface. In the `Replacing` method, move a `DocumentBuilder` to `args.MatchNode`, call `builder.InsertHtml(args.Replacement)`, remove `args.MatchNode`, and return `ReplaceAction.Skip`. Register the callback with `FindReplaceOptions.ReplacingCallback` before calling `Range.Replace`. This works when the placeholder (for example `{PLACEHOLDER}`) is a run of its own.

5. **Q:** How can I highlight all occurrences of a word instead of replacing it?  
   **A:** Set `ApplyFont.HighlightColor` of `FindReplaceOptions` to the desired color and call `Range.Replace` with the word as both the search string and the replacement, for example `doc.Range.Replace("Customer", "Customer", options)`. The text stays the same and each occurrence gets the highlight. Do not pass an empty replacement: it deletes every match. For a regular expression, use `"$0"` as the replacement and set `UseSubstitutions` to `true` to keep each match's own text.