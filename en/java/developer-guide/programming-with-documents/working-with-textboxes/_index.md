---
title: Working with Linked TextBoxes in Java
second_title: Aspose.Words for Java
articleTitle: Working with Linked TextBoxes
linktitle: Working with Linked TextBoxes
description: "Introduction to linked textboxes feature in Aspose.Words for Java."
type: docs
aliases:
 - /java/working-with-linked-textboxes/
weight: 250
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-linked-textboxes/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with textboxes in documents.

{{% /alert %}}

In Aspose.Words, the [TextBox](https://reference.aspose.com/words/java/com.aspose.words/textbox/) class is used to specify how text is displayed inside a shape. It exposes a public property named **Parent** to get the parent shape for the text box so that the customer can find the linked [Shape](https://reference.aspose.com/words/java/com.aspose.words/shape/) from the associated **TextBox**.

## Creating a Link

The **TextBox** class provides [isValidLinkTarget()](https://reference.aspose.com/words/java/com.aspose.words/textbox/#isValidLinkTarget-com.aspose.words.TextBox) method in order to check whether the **TextBox** can be linked to the target **Textbox**.

The following code example shows how to check if the `TextBox` can be linked to the target Textbox:

{{< gist "aspose-words-gists" "8efa479dedfc5a2f45b37e8c900d50a2" "create-link.java" >}}

## Check TextBox Sequence

There are several ways to display text in a shape. The [getTextBox()](https://reference.aspose.com/words/java/com.aspose.words/shape/#getTextBox) can be the Head, Middle, or Tail of a sequence.

The following code example shows how to check if **TextBox** is a Head, Tail, or Middle of the sequence:

{{< gist "aspose-words-gists" "8efa479dedfc5a2f45b37e8c900d50a2" "check-sequence.java" >}}

## Breaking a Link

Using the [breakForwardLink()](https://reference.aspose.com/words/java/com.aspose.words/textbox/#breakForwardLink) method you can break the link to the next **TextBox**.

The following code example shows how to break a link for a **TextBox**:

{{< gist "aspose-words-gists" "8efa479dedfc5a2f45b37e8c900d50a2" "break-link.java" >}}

## FAQ

1. **Q:** How can I check if a `TextBox` can be linked to another `TextBox`?  
   **A:** Call `textBox.isValidLinkTarget(targetTextBox)`. The method returns `true` when the two text boxes belong to the same document and satisfy the linking rules; otherwise it returns `false`.

2. **Q:** How do I obtain the shape that contains a linked `TextBox`?  
   **A:** Use the `textBox.getParent()` property. It returns the parent `Shape` object, allowing you to access shape‑level properties or navigate to the linked shape.

3. **Q:** How can I determine whether a `TextBox` is the head, middle, or tail of a linked sequence?  
   **A:** Use `getNext()` and `getPrevious()`: the head has a next text box but no previous one, a middle text box has both, and the tail has a previous text box but no next one. The code example above shows these checks.

4. **Q:** How do I break a forward link from a `TextBox`?  
   **A:** Invoke `textBox.breakForwardLink()`. This removes the link to the next text box in the sequence, leaving the current box isolated.

5. **Q:** Can I link a `TextBox` to a shape that is not a `TextBox`?  
   **A:** No. Linking is only supported between `TextBox` objects. Attempting to link to other shape types will cause `isValidLinkTarget` to return `false` and the link operation will be ignored.