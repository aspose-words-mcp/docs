---
title: Working with Shapes in Java
second_title: Aspose.Words for Java
articleTitle: Working with Shapes
linktitle: Working with Shapes
description: "Introduction to shape markup language, creating shapes of different types using Java."
type: docs
weight: 280
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-shapes/
aliases:
- /java/working-with-graphic-elements/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with shapes such as images, text boxes, and drawing objects.

{{% /alert %}}

This topic discusses how to work programmatically with shapes using Aspose.Words.

The shapes in Aspose.Words represent an object in the drawing layer, such as an AutoShape, textbox, freeform, OLE object, ActiveX control, or picture. A Word document can contain one or more different shapes. Shapes in Aspose.Words are represented by the [Shape](https://reference.aspose.com/words/java/com.aspose.words/shape/) class.

## Inserting Shapes Using Document Builder

You can insert inline shape with specified type and size and free-floating shape with the specified position, size and text wrap type into a document using the [insertShape()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertShape-int-double-double) method. The **insertShape()** method allows inserting DML shape into the document model. The document must be saved in the format, which supports DML shapes, otherwise, such nodes will be converted to VML shape, while document saving.

The following code example shows how to insert these types of shapes into the document:

{{< gist "aspose-words-gists" "ae9835338c044aaa3ac54592b7062db8" "insert-shape.java" >}}

## Set Aspect Ratio Locked

Using Aspose.Words, you can specify whether the shape's aspect ratio is locked through the [getAspectRatioLocked()](https://reference.aspose.com/words/java/com.aspose.words/shapebase/#getAspectRatioLocked) property.

The following code example shows how to work with the **getAspectRatioLocked()** property:

{{< gist "aspose-words-gists" "ae9835338c044aaa3ac54592b7062db8" "aspect-ratio-locked.java" >}}

## Set Shape Layout In Cell

You can also specify whether the shape is displayed inside a table or outside of it using the [isLayoutInCell()](https://reference.aspose.com/words/java/com.aspose.words/shapebase/#isLayoutInCell) property.

The following code example shows how to work with the **IsLayoutInCell** property:

{{< gist "aspose-words-gists" "ae9835338c044aaa3ac54592b7062db8" "layout-in-cell.java" >}}

## Create Snip Corner Rectangle

You can create a snip corner rectangle using Aspose.Words. The shape types are *SingleCornerSnipped, TopCornersSnipped, DiagonalCornersSnipped, TopCornersOneRoundedOneSnipped, SingleCornerRounded, TopCornersRounded,* and *DiagonalCornersRounded.*

The DML shape is created using **insertShape()** method with these shape types. These types cannot be used to create VML shapes. Attempt to create shape by using the public constructor of the "Shape" class raises the "UnsupportedOperationException" exception.

The following code example shows how to insert these type of shapes into the document:

{{< gist "aspose-words-gists" "ae9835338c044aaa3ac54592b7062db8" "add-corners-snipped.java" >}}

## Get Actual Shape Bounds Points

Using Aspose.Words API, you can get the location and size of the shape containing block in points, relative to the anchor of the topmost shape. To do this, use the [getBoundsInPoints()](https://reference.aspose.com/words/java/com.aspose.words/shapebase/#getBoundsInPoints) property.

The following code example shows how to work with the **getBoundsInPoints()** property:

{{< gist "aspose-words-gists" "ae9835338c044aaa3ac54592b7062db8" "get-actual-shape-bounds-points.java" >}}

## Specify Vertical Anchor

You can specify the text vertical alignment within a shape using the [getVerticalAnchor()](https://reference.aspose.com/words/java/com.aspose.words/textbox/#getVerticalAnchor) property.

The following code example shows how to work with the **getVerticalAnchor()** property:

{{< gist "aspose-words-gists" "ae9835338c044aaa3ac54592b7062db8" "vertical-anchor.java" >}}

## Detect SmartArt Shape

Aspose.Words also allows to detect if the Shape has a `SmartArt` object. To do this, use the [hasSmartArt()](https://reference.aspose.com/words/java/com.aspose.words/shape/#hasSmartArt) property.

The following code example shows how to work with the **hasSmartArt()** property:

{{< gist "aspose-words-gists" "ae9835338c044aaa3ac54592b7062db8" "detect-smart-art-shape.java" >}}

## Insert Horizontal Rule into Document

You can insert horizontal rule shape into a document using the [insertHorizontalRule()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertHorizontalRule) method.

The following code example shows how to do this:

{{< gist "aspose-words-gists" "ae9835338c044aaa3ac54592b7062db8" "insert-horizontal-rule.java" >}}

Aspose.Words API provides the [getHorizontalRuleFormat()](https://reference.aspose.com/words/java/com.aspose.words/shape/#getHorizontalRuleFormat) property to access the properties of the horizontal rule shape. the [getHorizontalRuleFormat()](https://reference.aspose.com/words/java/com.aspose.words/horizontalruleformat/) class exposes basic properties like Height, Color, NoShade etc. for the formatting of a horizontal rule.

The following code example shows how to set **HorizontalRuleFormat**:

{{< gist "aspose-words-gists" "ae9835338c044aaa3ac54592b7062db8" "horizontal-rule-format.java" >}}

## Import Shapes with Math XML as Shapes into DOM

You can use the [setConvertShapeToOfficeMath()](https://reference.aspose.com/words/java/com.aspose.words/loadoptions/#setConvertShapeToOfficeMath-boolean) property to convert the shapes with EquationXML to Office Math objects. The default value of this property corresponds to Microsoft Word behavior, i.e. shapes with equation XML are not converted to Office math objects.

The following code example shows how to convert shapes to Office Math objects:

{{< gist "aspose-words-gists" "ae9835338c044aaa3ac54592b7062db8" "convert-shape-to-office-math.java" >}}
