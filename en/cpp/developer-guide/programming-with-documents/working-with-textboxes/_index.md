---
title: Working with TextBoxes in C++
second_title: Aspose.Words for C++
articleTitle: Working with TextBoxes
linktitle: Working with TextBoxes
description: "Introduction to linked textboxes feature in Aspose.Words for C++."
type: docs
aliases:
 - /cpp/working-with-linked-textboxes/
weight: 250
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/working-with-textboxes/
timestamp: 2024-01-27-14-07-04
---

In Aspose.Words, the [TextBox](https://reference.aspose.com/words/cpp/aspose.words.drawing/textbox/) class is used to specify how text is displayed inside a shape. It exposes a public property named **Parent** to get the parent shape for the text box so that the customer can find the linked [Shape](https://reference.aspose.com/words/cpp/aspose.words.drawing/shape/) from the associated **TextBox**.

## Create A Link

The **TextBox** class provides [IsValidLinkTarget](https://reference.aspose.com/words/cpp/aspose.words.drawing/textbox/isvalidlinktarget/) method in order to check whether the **TextBox** can be linked to the target **Textbox**.

The following code example shows how to check if the `TextBox` can be linked to the target Textbox:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Linked-Textboxes-WorkingWithLinkedTextboxes-CreateALink.cpp" >}}

## Check TextBox Sequence

There are several ways to display text in a shape. The [get_TextBox()](https://reference.aspose.com/words/cpp/aspose.words.drawing/shape/get_textbox/) can be the Head, Middle, or Tail of a sequence.

The following code example shows how to check if **TextBox** is a Head, Tail, or Middle of the sequence:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Linked-Textboxes-WorkingWithLinkedTextboxes-CheckSequence.cpp" >}}

## Break a Link

Using the [BreakForwardLink](https://reference.aspose.com/words/cpp/aspose.words.drawing/textbox/breakforwardlink/) method you can break the link to the next **TextBox**.

The following code example shows how to break a link for a **TextBox**:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-Linked-Textboxes-WorkingWithLinkedTextboxes-BreakALink.cpp" >}}

------ 

## FAQ

1. **Q:** How can I verify that one TextBox can be linked to another TextBox?  
   **A:** Use the `TextBox::IsValidLinkTarget` method. Pass the target `TextBox` instance to this method; it returns `true` if the link is allowed, otherwise `false`. This check prevents linking incompatible text boxes.

2. **Q:** How do I determine whether a TextBox is the head, middle, or tail of a linked sequence?  
   **A:** Use `TextBox::get_Previous()` and `TextBox::get_Next()`. The head of a chain has no previous TextBox, the tail has no next one, and a middle TextBox has both.

3. **Q:** What is the correct way to break an existing forward link from a TextBox?  
   **A:** Call the `BreakForwardLink()` method on the `TextBox` you want to detach. This removes the link to the next TextBox while leaving the rest of the chain intact.

4. **Q:** How can I obtain the Shape that contains a given TextBox?  
   **A:** Use the `Parent` property of the `TextBox`. It returns a pointer to the owning `Shape` object, allowing you to access shape‑level properties such as position, size, or fill.

5. **Q:** How do I link two TextBoxes together programmatically?  
   **A:** After confirming the link is valid with `IsValidLinkTarget`, assign the target TextBox to the source using `TextBox::set_Next`. Example:  

   ```cpp
   System::SharedPtr<Aspose::Words::Drawing::TextBox> sourceBox = sourceShape->get_TextBox();
   System::SharedPtr<Aspose::Words::Drawing::TextBox> targetBox = targetShape->get_TextBox();

   if (sourceBox->IsValidLinkTarget(targetBox))
   {
       sourceBox->set_Next(targetBox);
   }
   ```  

   This creates a forward link from `sourceBox` to `targetBox`.