---
title: Working with Shapes in Node.js
second_title: Aspose.Words for Node.js via .NET
articleTitle: Working with Shapes
linktitle: Working with Shapes
description: "Create and manage shapes, ole objects in a document using Node.js."
type: docs
weight: 280
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/working-with-shapes/
timestamp: 2025-07-09-10-05-05
---

This topic discusses how to work programmatically with shapes using Aspose.Words.

The shapes in Aspose.Words represent an object in the drawing layer, such as an AutoShape, textbox, freeform, OLE object, ActiveX control, or picture. A Word document can contain one or more different shapes. Shapes of the document are represented by the [Shape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/) class.

## Inserting Shapes Using Document Builder

You can insert inline shape with specified type and size and free-floating shape with the specified position, size and text wrap type into a document using [insertShape](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertshape/) method. The [insertShape](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertshape/) method allows inserting DML shape into the document model. The document must be saved in the format, which supports DML shapes, otherwise, such nodes will be converted to VML shape, while document saving.

The following code example shows how to insert these types of shapes into the document:

{{< gist "aspose-words-gists" "3a90c8783e87c53371d103d9350f1d31" "insert-shape.js" >}}

## Set Aspect Ratio Locked

Using Aspose.Words, you can specify whether the shape's aspect ratio is locked through the [aspectRatioLocked](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapebase/aspectratiolocked/) property.

The following code example shows how to work with the **aspectRatioLocked** property:

{{< gist "aspose-words-gists" "3a90c8783e87c53371d103d9350f1d31" "aspect-ratio-locked.js" >}}

## Set Shape Layout In Cell

You can also specify whether the shape is displayed inside a table or outside of it using the [isLayoutInCell property](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapebase/islayoutincell/) property.

The following code example shows how to work with the **isLayoutInCell** property:

{{< gist "aspose-words-gists" "3a90c8783e87c53371d103d9350f1d31" "layout-in-cell.js" >}}

## Create Snip Corner Rectangle

You can create a snip corner rectangle using Aspose.Words. The shape types are [SingleCornerSnipped](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapetype/), [TopCornersSnipped](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapetype/), [DiagonalCornersSnipped](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapetype/), [TopCornersOneRoundedOneSnipped](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapetype/), [SingleCornerRounded](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapetype/), [TopCornersRounded](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapetype/), and [DiagonalCornersRounded](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapetype/).

The DML shape is created using [insertShape](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/insertshape/) method with these shape types. These types cannot be used to create VML shapes. Attempt to create shape by using the public constructor of the [Shape](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/) class raises the "NotSupportedException" exception.

The following code example shows how to insert these type of shapes into the document:

{{< gist "aspose-words-gists" "3a90c8783e87c53371d103d9350f1d31" "add-corners-snipped.js" >}}

## Get Actual Shape Bounds Points

Using Aspose.Words API, you can get the location and size of the shape containing block in points, relative to the anchor of the topmost shape. To do this, use the [boundsInPoints2](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shapebase/boundsinpoints2/) property.

The following code example shows how to work with the **BoundsInPoints** property:

{{< gist "aspose-words-gists" "3a90c8783e87c53371d103d9350f1d31" "get-actual-shape-bounds-points.js" >}}

## Specify Vertical Anchor

You can specify the text vertical alignment within a shape using the [verticalAnchor](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/textbox/verticalanchor/) property.

The following code example shows how to work with the **verticalAnchor** property:

{{< gist "aspose-words-gists" "3a90c8783e87c53371d103d9350f1d31" "vertical-anchor.js" >}}

## Detect SmartArt Shape

Aspose.Words also allows to detect if the Shape has a `SmartArt` object. To do this, use the [hasSmartArt](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/hassmartart/) property.

The following code example shows how to work with the **hasSmartArt** property:

{{< gist "aspose-words-gists" "3a90c8783e87c53371d103d9350f1d31" "detect-smart-art-shape.js" >}}

## Insert Horizontal Rule into Document

You can insert horizontal rule shape into a document using the [insertHorizontalRule](https://reference.aspose.com/words/nodejs-net/aspose.words/documentbuilder/inserthorizontalrule/) method.

The following code example shows how to do this:

{{< gist "aspose-words-gists" "3a90c8783e87c53371d103d9350f1d31" "insert-horizontal-rule.js" >}}

Aspose.Words API provides the [horizontalRuleFormat](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/shape/horizontalruleformat/) property to access the properties of the horizontal rule shape. The [HorizontalRuleFormat](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/horizontalruleformat/) class exposes basic properties like [height](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/horizontalruleformat/height/), [color](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/horizontalruleformat/color/), [noShade](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/horizontalruleformat/noshade/) etc. for the formatting of a horizontal rule.

The following code example demonstrates how to set [HorizontalRuleFormat](https://reference.aspose.com/words/nodejs-net/aspose.words.drawing/horizontalruleformat/):

{{< gist "aspose-words-gists" "3a90c8783e87c53371d103d9350f1d31" "horizontal-rule-format.js" >}}

## Insert OLE Object as an Icon

Aspose.Words API provides the **DocumentBuilder.insertOleObjectAsIcon** method to insert an embedded or linked OLE object as an icon into the document. This method allows specifying the icon file and the caption. The `OLE` object type shall be detected using the file extension.

The following code example demonstrates how to set insert OLE object as an Icon into the document:

{{< gist "aspose-words-gists" "82ca803e5833cb807b7e1c5111066cb0" "insert-ole-object-as-icon.js" >}}

{{% alert color="primary" %}}

Maximum size of the icon must be 32x32 for the correct display.

{{% /alert %}}

## Import Shapes with Math XML as Shapes into DOM

You can use [convertShapeToOfficeMath](https://reference.aspose.com/words/nodejs-net/aspose.words.loading/loadoptions/convertshapetoofficemath/) property to convert the shapes with EquationXML to Office Math objects. The default value of this property corresponds to MS Word behavior i.e. shapes with equation XML are not converted to Office math objects.

The following code example shows how to convert shapes to Office Math objects:

{{< gist "aspose-words-gists" "3a90c8783e87c53371d103d9350f1d31" "convert-shape-to-office-math.js" >}}

------  

## FAQ

1. **Q:** How do I insert an inline shape versus a floating shape?  
   **A:** Use `DocumentBuilder.insertShape` and set the `wrapType` property. For an inline shape, set `wrapType` to `WrapType.Inline`; for a floating shape, set it to `WrapType.Square` (or another wrap type) and optionally specify the position with `left` and `top`.  

2. **Q:** How can I lock the aspect ratio of a shape so it doesn't get distorted when resized?  
   **A:** Set the `aspectRatioLocked` property of the shape's `ShapeBase` to `true`. This ensures the width‑to‑height ratio remains constant when the shape is resized programmatically or by the user.  

3. **Q:** How can I determine whether a shape contains a SmartArt object?  
   **A:** Check the `hasSmartArt` property of the `Shape` instance. It returns `true` if the shape is a SmartArt diagram, allowing you to handle it differently (e.g., skip processing or apply specific formatting).  

4. **Q:** How do I insert an OLE object as an icon with a custom caption?  
   **A:** Call `DocumentBuilder.insertOleObjectAsIcon(fileName, isLinked, iconFile, iconCaption)`. Provide the file path of the OLE source, whether to link it, the icon file path, and the desired caption string.  

5. **Q:** How can I set the vertical alignment of text inside a textbox shape?  
   **A:** Use the `verticalAnchor` property of the shape's `textBox` object (`shape.textBox.verticalAnchor`). Assign one of the `TextBoxAnchor` enum values such as `Top`, `Middle`, or `Bottom` to control where the text is positioned vertically within the textbox.