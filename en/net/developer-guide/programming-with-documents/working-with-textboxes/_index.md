---
title: Working with TextBoxes in C#
second_title: Aspose.Words for .NET
articleTitle: Working with TextBoxes
linktitle: Working with TextBoxes
description: "Introduction to linked textboxes feature in Aspose.Words for .NET."
type: docs
weight: 250
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/working-with-textboxes/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with textboxes in documents.

{{% /alert %}}

In Aspose.Words, the [TextBox](https://reference.aspose.com/words/net/aspose.words.drawing/textbox/) class is used to specify how text is displayed inside a shape. It exposes a public property named **Parent** to get the parent shape for the text box so that the customer can find the linked [Shape](https://reference.aspose.com/words/net/aspose.words.drawing/shape/) from the associated **TextBox**.

## Creating a Link

The **TextBox** class provides [IsValidLinkTarget](https://reference.aspose.com/words/net/aspose.words.drawing/textbox/isvalidlinktarget/) method in order to check whether the **TextBox** can be linked to the target **Textbox**.

The following code example shows how to check if the `TextBox` can be linked to the target Textbox:

{{< gist "aspose-words-gists" "68b6041746b3d6bf5137cff8e6385b5f" "create-link.cs" >}}

## Check TextBox Sequence

There are several ways to display text in a shape. The [TextBox](https://reference.aspose.com/words/net/aspose.words.drawing/shape/textbox/) can be the Head, Middle, or Tail of a sequence.

The following code example shows how to check if **TextBox** is a Head, Tail, or Middle of the sequence:

{{< gist "aspose-words-gists" "68b6041746b3d6bf5137cff8e6385b5f" "check-sequence.cs" >}}

## Breaking a Link

Using the [BreakForwardLink](https://reference.aspose.com/words/net/aspose.words.drawing/textbox/breakforwardlink/) method you can break the link to the next **TextBox**.

The following code example shows how to break a link for a **TextBox**:

{{< gist "aspose-words-gists" "68b6041746b3d6bf5137cff8e6385b5f" "break-link.cs" >}}

------

## FAQ

1. **Q:** How can I verify whether one TextBox can be linked to another?  
   **A:** Use the `TextBox.IsValidLinkTarget(TextBox target)` method. It returns `true` if the current TextBox can be linked to the specified target TextBox, otherwise `false`.

2. **Q:** How do I determine the position of a TextBox within a linked sequence?  
   **A:** Check the `TextBox.Previous` and `TextBox.Next` properties. The first TextBox in the linked chain has no `Previous`, the last one has no `Next`, and a middle one has both.

3. **Q:** What method should I use to break a forward link from a TextBox?  
   **A:** Invoke `TextBox.BreakForwardLink()`. This removes the link from the current TextBox to the next one in the sequence, leaving the remaining chain intact.

4. **Q:** How can I obtain the Shape that contains a TextBox?  
   **A:** Access the `TextBox.Parent` property, which returns the `Shape` object that hosts the TextBox. This allows you to manipulate shape-level properties such as size, position, or formatting.