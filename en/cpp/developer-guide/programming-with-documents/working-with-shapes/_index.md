---
title: Working with Shapes in C++
second_title: Aspose.Words for C++
articleTitle: Working with Shapes
linktitle: Working with Shapes
description: "Introduction to shape markup language, creating shapes of different types using C++."
type: docs
weight: 280
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/working-with-shapes/
aliases:
- /cpp/working-with-graphic-elements/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with shapes such as images, text boxes, and drawing objects.

{{% /alert %}}

This topic discusses how to work programmatically with shapes using Aspose.Words.

The shapes in Aspose.Words represent an object in the drawing layer, such as an AutoShape, textbox, freeform, OLE object, ActiveX control, or picture. A Word document can contain one or more different shapes. Shapes in Aspose.Words are represented by the [Shape](https://reference.aspose.com/words/cpp/aspose.words.drawing/shape/) class.

## Inserting Shapes Using Document Builder

You can insert inline shape with specified type and size and free-floating shape with the specified position, size and text wrap type into a document using the [InsertShape](https://reference.aspose.com/words/cpp/aspose.words/documentbuilder/insertshape/) method. The **InsertShape** method allows inserting DML shape into the document model. The document must be saved in the format, which supports DML shapes, otherwise, such nodes will be converted to VML shape, while document saving.

The following code example shows how to insert these types of shapes into the document:

{{< gist "aspose-words-gists" "954ada9988be69b7c0cc29f3280a0bb1" "insert-shape.h" >}}

## Set Aspect Ratio Locked

Using Aspose.Words, you can specify whether the shape's aspect ratio is locked through the [get_AspectRatioLocked()](https://reference.aspose.com/words/cpp/aspose.words.drawing/shapebase/get_aspectratiolocked/) property.

The following code example shows how to work with the **get_AspectRatioLocked()** property:

{{< gist "aspose-words-gists" "954ada9988be69b7c0cc29f3280a0bb1" "aspect-ratio-locked.h" >}}

## Set Shape Layout In Cell

You can also specify whether the shape is displayed inside a table or outside of it using the [get_IsLayoutInCell()](https://reference.aspose.com/words/cpp/aspose.words.drawing/shapebase/get_islayoutincell/) property.

The following code example shows how to work with the **get_IsLayoutInCell()** property:

{{< gist "aspose-words-gists" "954ada9988be69b7c0cc29f3280a0bb1" "layout-in-cell.h" >}}

## Create Snip Corner Rectangle

You can create a snip corner rectangle using Aspose.Words. The shape types are *SingleCornerSnipped, TopCornersSnipped, DiagonalCornersSnipped, TopCornersOneRoundedOneSnipped, SingleCornerRounded, TopCornersRounded,* and *DiagonalCornersRounded.*

The DML shape is created using **InsertShape** method with these shape types. These types cannot be used to create VML shapes. Attempt to create shape by using the public constructor of the "Shape" class raises the "NotSupportedException" exception.

The following code example shows how to insert these type of shapes into the document:

{{< gist "aspose-words-gists" "954ada9988be69b7c0cc29f3280a0bb1" "add-corners-snipped.h" >}}

## Get Actual Shape Bounds Points

Using Aspose.Words API, you can get the location and size of the shape containing block in points, relative to the anchor of the topmost shape. To do this, use the [get_BoundsInPoints()](https://reference.aspose.com/words/cpp/aspose.words.drawing/shapebase/get_boundsinpoints/) property.

The following code example shows how to work with the **get_BoundsInPoints()** property:

{{< gist "aspose-words-gists" "954ada9988be69b7c0cc29f3280a0bb1" "get-actual-shape-bounds-points.h" >}}

## Specify Vertical Anchor

You can specify the text vertical alignment within a shape using the [get_VerticalAnchor()](https://reference.aspose.com/words/cpp/aspose.words.drawing/textbox/get_verticalanchor/) property.

The following code example shows how to work with the **get_VerticalAnchor()** property:

{{< gist "aspose-words-gists" "954ada9988be69b7c0cc29f3280a0bb1" "vertical-anchor.h" >}}

## Detect SmartArt Shape

Aspose.Words also allows to detect if the Shape has a `SmartArt` object. To do this, use the [get_HasSmartArt()](https://reference.aspose.com/words/cpp/aspose.words.drawing/shape/get_hassmartart/) property.

The following code example shows how to work with the **get_HasSmartArt()** property:

{{< gist "aspose-words-gists" "954ada9988be69b7c0cc29f3280a0bb1" "detect-smart-art-shape.h" >}}

## Insert Horizontal Rule into Document

You can insert horizontal rule shape into a document using the [InsertHorizontalRule](https://reference.aspose.com/words/cpp/aspose.words/documentbuilder/inserthorizontalrule/) method.

The following code example shows how to do this:

{{< gist "aspose-words-gists" "954ada9988be69b7c0cc29f3280a0bb1" "insert-horizontal-rule.h" >}}

Aspose.Words API provides the [get_HorizontalRuleFormat()](https://reference.aspose.com/words/cpp/aspose.words.drawing/shape/get_horizontalruleformat/) property to access the properties of the horizontal rule shape. The [HorizontalRuleFormat](https://reference.aspose.com/words/cpp/aspose.words.drawing/horizontalruleformat/) class exposes basic properties like Height, Color, NoShade etc. for the formatting of a horizontal rule.

The following code example shows how to set **HorizontalRuleFormat**:

{{< gist "aspose-words-gists" "954ada9988be69b7c0cc29f3280a0bb1" "horizontal-rule-format.h" >}}

## Import Shapes with Math XML as Shapes into DOM

You can use the [get_ConvertShapeToOfficeMath()](https://reference.aspose.com/words/cpp/aspose.words.loading/loadoptions/get_convertshapetoofficemath/) property to convert the shapes with EquationXML to Office Math objects. The default value of this property corresponds to Microsoft Word behavior, i.e. shapes with equation XML are not converted to Office math objects.

The following code example shows how to convert shapes to Office Math objects:

{{< gist "aspose-words-gists" "954ada9988be69b7c0cc29f3280a0bb1" "convert-shape-to-office-math.h" >}}
