---
title: How to Add Group Shape into Word Document
second_title: Aspose.Words for Java
articleTitle: How to Add Group Shape into a Word Document
linktitle: Working with Group Shapes in Word Documents
description: "Grouping and ungrouping shapes using Java."
type: docs
weight: 290
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/how-to-add-group-shape-into-a-word-document/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page describes how to insert a group shape programmatically.

{{% /alert %}}

Sometimes you need to add a group shape into a Word document. Such a group shape consists of multiple shapes.

In Microsoft Word, you can quickly add a group shape using the Group command/button. An individual shape in a group can be moved separately.

In Aspose.Words it is very easy to add a group shape using the [GroupShape](https://reference.aspose.com/words/java/com.aspose.words/groupshape/) class. **Shape** is created separately using the [Shape](https://reference.aspose.com/words/java/com.aspose.words/shape/) class and then added to the [GroupShape](https://reference.aspose.com/words/java/com.aspose.words/groupshape/) object using the [appendChild()](https://reference.aspose.com/words/java/com.aspose.words/compositenode/#appendChild-com.aspose.words.Node) method.

The following code example shows how to add a group shape into a Word document:

{{< gist "aspose-words-gists" "810aad86a7a440f9a364db09322bce53" "add-group-shape.java" >}}

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

For complete list, please check the [ShapeType](https://reference.aspose.com/words/java/com.aspose.words/shapetype/) class.

{{% /alert %}}
