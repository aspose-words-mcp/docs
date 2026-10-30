---
title: How to Add Group Shape into Word File
second_title: Aspose.Words for Node.js via .NET
articleTitle: Working with Group Shape in Word Documents
linktitle: Working with Group Shape in Word Documents
description: "Add group shape into a document using Node.js."
type: docs
weight: 290
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/how-to-add-group-shape-into-a-word-document/
timestamp: 2025-07-09-10-05-05
---

Sometimes you need to add a group shape into a Word document. Such a group shape consists of multiple shapes.

In Microsoft Word, you can quickly add a group shape using the Group command/button. An individual shape in a group can be moved separately.

In Aspose.Words it is very easy to add a group shape using [GroupShape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/groupshape/) class. Shape is created separately using [Shape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/) class and then added in [GroupShape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/groupshape/) object using [appendChild](https://reference.aspose.com/words/nodejs-net/aspose.words/compositenode/appendChild/) method.

The following code example shows how to add a group shape into a Word document:

{{< gist "aspose-words-gists" "91a118ddf96c535d343b275d397fce3d" "add-group-shape.js" >}}

{{% alert color="primary" %}}

Below are some of the `Shape` types supported in Aspose.Words. For complete list, please see [Aspose.Words.Drawing.ShapeType](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapetype/) enumeration

- [Rectangle](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapetype/)
- [RoundRectangle](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapetype/)
- [Ellipse](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapetype/)
- [Diamond](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapetype/)
- [Triangle](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapetype/)
- [RightTriangle](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapetype/)
- [Parallelogram](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapetype/)
- [Trapezoid](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapetype/)
- [Hexagon](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapetype/)
- [Octagon](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapetype/)

{{% /alert %}}

------ 

## FAQ

1. **Q:** How do I create a `GroupShape` and add individual shapes to it in Aspose.Words for Node.js?  
   **A:** First create a `Document` and a `DocumentBuilder`. Insert each `Shape` (e.g., rectangle, ellipse) with `builder.insertShape`, then group them with `builder.insertGroupShape([shape1, shape2])`. Alternatively, create a `new aw.Drawing.GroupShape(doc)` and add the shapes to it with `groupShape.appendChild(shape)`. Finally save the document.

2. **Q:** Which shape types can be added to a `GroupShape`?  
   **A:** Any shape type defined in the `ShapeType` enumeration can be added, such as Rectangle, RoundRectangle, Ellipse, Diamond, Triangle, RightTriangle, Parallelogram, Trapezoid, Hexagon, Octagon, etc. The full list is available in the Aspose.Words documentation.

3. **Q:** Can I set the position and size of shapes inside a `GroupShape`?  
   **A:** Yes. After creating a `Shape`, set its `left`, `top`, `width`, and `height` properties before appending it to the group. These coordinates are relative to the group's coordinate system.

4. **Q:** How do I apply fill color or line style to a shape within a `GroupShape`?  
   **A:** Use the shape's `fill` and `stroke` objects. For example, `shape.fill.foreColor = "#FF0000";` sets a red fill, and `shape.stroke.color = "#000000";` sets a black outline.

5. **Q:** How can I save the document after adding a `GroupShape`?  
   **A:** Call the `save` method on the `Document` instance, specifying the desired format, e.g., `document.save("GroupShape.docx");`. The document will contain the group shape with all its child shapes.