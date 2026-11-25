---
title: How to Add Group Shape into Word Document
second_title: Aspose.Words for C++
articleTitle: How to Add Group Shape into a Word Document
linktitle: Working with Group Shapes in Word Documents
description: "Grouping and ungrouping shapes using C++."
type: docs
weight: 290
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/how-to-add-group-shape-into-a-word-document/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page describes how to insert a group shape programmatically.

{{% /alert %}}

Sometimes you need to add a group shape into a Word document. Such a group shape consists of multiple shapes.

In Microsoft Word, you can quickly add a group shape using the Group command/button. An individual shape in a group can be moved separately.

In Aspose.Words it is very easy to add a group shape using the [GroupShape](https://reference.aspose.com/words/cpp/aspose.words.drawing/groupshape/) class. **Shape** is created separately using the [Shape](https://reference.aspose.com/words/cpp/aspose.words.drawing/shape/) class and then added to the [GroupShape](https://reference.aspose.com/words/cpp/aspose.words.drawing/groupshape/) object using the [AppendChild](https://reference.aspose.com/words/cpp/aspose.words/compositenode/appendchild/) method.

The following code example shows how to add a group shape into a Word document:

{{< gist "aspose-words-gists" "80429079be65ac0af21e5c7a38fe9a7c" "add-group-shape.h" >}}

{{% alert color="primary" %}}

Below are some of the `Shape` types supported in Aspose.Words:

- Rectangle
- RoundRectangle
- RoundRectangle
- Ellipse
- Diamond
- Triangle
- RightTriangle
- Parallelogram
- Trapezoid
- Hexagon
- Octagon

For complete list, please check the [ShapeType](https://reference.aspose.com/words/cpp/aspose.words.drawing/shapetype/) class.

{{% /alert %}}

------ 

## FAQ

1. **Q:** How do I create a `GroupShape` in Aspose.Words for C++?  
   **A:** First create the individual `Shape` objects you want to group, set their size and position, then instantiate a `GroupShape` object. Add each `Shape` to the `GroupShape` using `groupShape->AppendChild(shape)`. Finally, insert the `GroupShape` into the document (e.g., `builder->get_CurrentParagraph()->AppendChild(groupShape)`).

2. **Q:** Which shape types can be added to a `GroupShape`?  
   **A:** Any shape type supported by Aspose.Words can be part of a group, such as `ShapeType::Rectangle`, `ShapeType::Ellipse`, `ShapeType::Diamond`, `ShapeType::Triangle`, `ShapeType::Parallelogram`, `ShapeType::Hexagon`, etc. Refer to the `ShapeType` enumeration for the full list.

3. **Q:** How can I control the position and size of shapes inside the group?  
   **A:** Set the `Width`, `Height`, `Left`, and `Top` properties of each `Shape` before appending it to the `GroupShape`. The coordinates are relative to the group's origin, so the shapes retain the specified layout when the group is rendered.

4. **Q:** Can a `GroupShape` be added to a header, footer, or other specific part of the document?  
   **A:** Yes. Retrieve the desired `HeaderFooter` node (e.g., `builder->get_CurrentSection()->get_HeadersFooters()->idx_get(HeaderFooterType::HeaderPrimary)`) and call `AppendChild` on its paragraph or directly on the `HeaderFooter` to insert the `GroupShape`.

5. **Q:** Do I need to call any additional method to finalize the group after adding shapes?  
   **A:** No extra method is required. Once all shapes are appended, the `GroupShape` becomes part of the document tree and will be saved and displayed as a grouped object automatically.