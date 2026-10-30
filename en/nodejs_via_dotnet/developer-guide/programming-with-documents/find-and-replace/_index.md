---
title: Find and Replace in Node.js
second_title: Aspose.Words for Node.js via .NET
articleTitle: Find and Replace
linktitle: Find and Replace
type: docs
description: "Find a string or regular expression pattern in your document and replace it with the text you want using Node.js."
weight: 100
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/find-and-replace/
timestamp: 2025-07-09-10-05-05
---

You can easily navigate within your document using a keyboard and mouse, but if you have many pages to scroll through, it will take quite a while to find specific text in a long document. It will be more time consuming when you want to replace certain characters or words that you have used in your document. The “Find and replace” functionality enables you to find a sequence of characters in a document and replace it with another sequence of characters.

Aspose.Words allows you to find a specific string or regular expression pattern in your document and replace it with an alternative without installing and using additional applications such as Microsoft Word. This will speed up many typing and formatting tasks, potentially saving you hours of work.

This article explains how to apply string replacement and regular expressions with the support of metacharacters.

## Ways to Find and Replace {#ways-to-find-and-replace}

Aspose.Words provides two ways to apply the find and replace operation by using the following:

1. *Simple string replacement* – to find and replace a specific string with another, you need to specify a search string (alphanumeric characters) that is going to be replaced according to all occurrences with another specified replacement string. Both strings must not contain symbols. Take into account that string comparison can be case-sensitive, or you may be unsure of spelling or have several similar spellings.
2. *Regular expressions* – to specify a regular expression to find the exact string matches and replace them according to your regular expression. Note that a word is defined as being made up of only alphanumeric characters. If replacement is executed with only whole words being matched and the input string happens to contain symbols, then no phrases will be found.

In addition, you can use special metacharacters with simple string replacement and regular expressions to specify breaks within the find and replace operation.

Aspose.Words presents the find and replace functionality with the [Aspose.Words.Replacing](https://reference.aspose.com/words/nodejs-net/aspose.words.replacing/) module. You can work with many options during the find and replace process using [FindReplaceOptions](https://reference.aspose.com/words/nodejs-net/aspose.words.replacing/findreplaceoptions/) class.

### Find and Replace Text using Simple String Replacement {#find-and-replace-text-using-simple-string-replacement}

You can use one of the [replace](https://reference.aspose.com/words/nodejs-net/aspose.words/range/replace/) and replaceRegex methods to find or replace a particular string and return the number of replacements that were made. In this case, you can specify a string to be replaced, a string that will replace all its occurrences, whether the replacement is case-sensitive, and whether only stand-alone words will be affected.

The following code example shows how to find the string “_CustomerName_” and replace it with the string *“James Bond”*:

{{< gist "aspose-words-gists" "a652819331ab7eff5560cac42bb71ad2" "replace-with-string.js" >}}

You can notice the difference between the document before applying simple string replacement:

<img src="before-simple-string-replacement.png" alt="before-simple-string-replacement" style="width:600px"/>

And after applying simple string replacement:

<img src="after-simple-string-replacement.png" alt="after-simple-string-replacement" style="width:600px"/>

### Find and Replace String using Metacharacters {#find-and-replace-text-using-metacharacters}

You can use metacharacters in the search string or the replacement string if a particular text or phrase is composed of multiple paragraphs, sections, or pages. Some of the metacharacters include **&p** for a paragraph break, **&b** for a section break, **&m** for a page break, and **&l** for a line break.

{{% alert color="primary" %}}

Note that the metacharacter **&&** equals to **&**. For example, if you need to find text for **&p** that is not a paragraph break, then you can use **&&p**.

{{% /alert %}}

The following code example shows how to replace text with paragraph and page break:

{{< gist "aspose-words-gists" "a652819331ab7eff5560cac42bb71ad2" "replace-text-containing-meta-characters.js" >}}

## Find and Replace String in Header/Footer of a Document {#find-and-replace-string-in-header-or-footer-of-a-document}

You can find and replace text in the header/footer section of a Word document using the [HeaderFooter](https://reference.aspose.com/words/nodejs-net/aspose.words/headerfooter/) class.

You can notice the difference between the document before applying header string replacement:

<img src="before-applying-header-string-replacement.png" alt="before-applying-header-string-replacement" style="width:600px"/>

And after applying header string replacement:

<img src="after-applying-header-string-replacement.png" alt="after-applying-header-string-replacement" style="width:600px"/>

The following code example shows how to replace the text of the footer section in your document:

{{< gist "aspose-words-gists" "a652819331ab7eff5560cac42bb71ad2" "replace-text-in-footer.js" >}}

You can notice the difference between the document before applying footer string replacement:

<img src="before-applying-footer-string-replacement.png" alt="before-applying-footer-string-replacement" style="width:600px"/>

And after applying footer string replacement:

<img src="after-applying-footer-string-replacement.png" alt="after-applying-footer-string-replacement" style="width:600px"/>

## Ignore Text During Find and Replace {#ignore-text-during-find-and-replace}

While applying the find and replace operation, you can ignore certain segments of the text. So, certain parts of the text can be excluded from the search, and the find and replace can be applied only to the remaining parts.

Aspose.Words provides many find and replace properties for ignoring text such as [ignoreDeleted](https://reference.aspose.com/words/nodejs-net/aspose.words.replacing/findreplaceoptions/ignoreDeleted/), [ignoreFields](https://reference.aspose.com/words/nodejs-net/aspose.words.replacing/findreplaceoptions/ignoreFields/), and [ignoreInserted](https://reference.aspose.com/words/nodejs-net/aspose.words.replacing/findreplaceoptions/ignoreInserted/).

The following code example shows how to ignore text inside delete revisions:

{{< gist "aspose-words-gists" "a652819331ab7eff5560cac42bb71ad2" "ignore-text-inside-delete-revisions.js" >}}

## Customize Find and Replace Operation {#customize-find-and-replace-operation}

Aspose.Words provides many different properties to find and replace text such as applying specific format with [applyFont](https://reference.aspose.com/words/nodejs-net/aspose.words.replacing/findreplaceoptions/applyFont/) and [applyParagraphFormats](https://reference.aspose.com/words/nodejs-net/aspose.words.replacing/findreplaceoptions/applyParagraphFormat/) properties, using substitutions in replacement patterns with [useSubstitutions](https://reference.aspose.com/words/nodejs-net/aspose.words.replacing/findreplaceoptions/useSubstitutions/) property, and others.

The following code example shows how to highlight a specific word in your document:

{{< gist "aspose-words-gists" "a652819331ab7eff5560cac42bb71ad2" "highlight-color.js" >}}
