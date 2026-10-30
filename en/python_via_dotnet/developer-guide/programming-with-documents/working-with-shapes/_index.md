---
title: Working with Shapes in Python
second_title: Aspose.Words for Python via .NET
articleTitle: Working with Shapes
linktitle: Working with Shapes
description: "Create and manage shapes, ole objects in a document using Python."
type: docs
weight: 280
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/working-with-shapes/
aliases:
- /python/working-with-shapes/
- /python/working-with-graphic-elements/
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page demonstrates how to create, modify, and query various shape types in Word documents using Aspose.Words for Python via .NET, providing code examples for inserting shapes, setting properties such as aspect ratio and layout, handling special shapes, and working with OLE objects and Office Math conversion.
{{% /alert %}}

This topic discusses how to work programmatically with shapes using Aspose.Words.

The shapes in Aspose.Words represent an object in the drawing layer, such as an AutoShape, textbox, freeform, OLE object, ActiveX control, or picture. A Word document can contain one or more different shapes. Shapes in Aspose.Words are represented by the [Shape](https://reference.aspose.com/words/python-net/aspose.words.drawing/shape/) class.

## Inserting Shapes Using Document Builder

You can insert inline shape with specified type and size and free-floating shape with the specified position, size and text wrap type into a document using the [insert_shape](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_shape/) method. The **insert_shape** method allows inserting DML shape into the document model. The document must be saved in the format, which supports DML shapes, otherwise, such nodes will be converted to VML shape, while document saving.

The following code example shows how to insert these types of shapes into the document:

{{< gist "aspose-words-gists" "664d989412b46c6a03619182c5a4b9cd" "insert-shape.py" >}}

## Set Aspect Ratio Locked

Using Aspose.Words, you can specify whether the shape’s aspect ratio is locked through the [aspect_ratio_locked](https://reference.aspose.com/words/python-net/aspose.words.drawing/shapebase/aspect_ratio_locked/) property.

The following code example shows how to work with the **aspect_ratio_locked** property:

{{< gist "aspose-words-gists" "664d989412b46c6a03619182c5a4b9cd" "aspect-ratio-locked.py" >}}

## Set Shape Layout In Cell

You can also specify whether the shape is displayed inside a table or outside of it using the [is_layout_in_cell](https://reference.aspose.com/words/python-net/aspose.words.drawing/shapebase/is_layout_in_cell/) property.

The following code example shows how to work with the **is_layout_in_cell** property:

{{< gist "aspose-words-gists" "664d989412b46c6a03619182c5a4b9cd" "layout-in-cell.py" >}}

## Create Snip Corner Rectangle

You can create a snip corner rectangle using Aspose.Words. The shape types are *SingleCornerSnipped, TopCornersSnipped, DiagonalCornersSnipped,  TopCornersOneRoundedOneSnipped,  SingleCornerRounded,  TopCornersRounded,* and *DiagonalCornersRounded.*

The DML shape is created using **insert_shape** method with these shape types. These types cannot be used to create VML shapes. Attempt to create shape by using the public constructor of the "Shape" class raises the "NotSupportedException" exception.

The following code example shows how to insert these type of shapes into the document:

{{< gist "aspose-words-gists" "664d989412b46c6a03619182c5a4b9cd" "add-corners-snipped.py" >}}

## Get Actual Shape Bounds Points

Using Aspose.Words API, you can get the location and size of the shape containing block in points, relative to the anchor of the topmost shape. To do this, use the [bounds_in_points](https://reference.aspose.com/words/python-net/aspose.words.drawing/shapebase/bounds_in_points/) property.

The following code example shows how to work with the **bounds_in_points** property:

{{< gist "aspose-words-gists" "664d989412b46c6a03619182c5a4b9cd" "get-actual-shape-bounds-points.py" >}}

## Specify Vertical Anchor

You can specify the text vertical alignment within a shape using the [vertical_anchor](https://reference.aspose.com/words/python-net/aspose.words.drawing/textbox/vertical_anchor/) property.

The following code example shows how to work with the **vertical_anchor** property:

{{< gist "aspose-words-gists" "664d989412b46c6a03619182c5a4b9cd" "vertical-anchor.py" >}}

## Detect SmartArt Shape

Aspose.Words also allows to detect if the Shape has a `SmartArt` object. To do this, use the [has_smart_art property](https://reference.aspose.com/words/python-net/aspose.words.drawing/shape/has_smart_art/) property.

The following code example shows how to work with the **has_smart_art** property:

{{< gist "aspose-words-gists" "664d989412b46c6a03619182c5a4b9cd" "detect-smart-art-shape.py" >}}

## Insert Horizontal Rule into Document

You can insert horizontal rule shape into a document using the [insert_horizontal_rule](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_horizontal_rule/) method.

The following code example shows how to do this:

{{< gist "aspose-words-gists" "664d989412b46c6a03619182c5a4b9cd" "insert-horizontal-rule.py" >}}

Aspose.Words API provides the [horizontal_rule_format](https://reference.aspose.com/words/python-net/aspose.words.drawing/shape/horizontal_rule_format/) property to access the properties of the horizontal rule shape. The [HorizontalRuleFormat](https://reference.aspose.com/words/python-net/aspose.words.drawing/horizontalruleformat/) class exposes basic properties like Height, Color, NoShade etc. for the formatting of a horizontal rule.

The following code example shows how to set **HorizontalRuleFormat**:

{{< gist "aspose-words-gists" "664d989412b46c6a03619182c5a4b9cd" "horizontal-rule-format.py" >}}

## Import Shapes with Math XML as Shapes into DOM

You can use the [convert_shape_to_office_math](https://reference.aspose.com/words/python-net/aspose.words.loading/loadoptions/convert_shape_to_office_math/) property to convert the shapes with EquationXML to Office Math objects. The default value of this property corresponds to Microsoft Word behavior, i.e. shapes with equation XML are not converted to Office math objects.

The following code example shows how to convert shapes to Office Math objects:

{{< gist "aspose-words-gists" "664d989412b46c6a03619182c5a4b9cd" "convert-shape-to-office-math.py" >}} 

## FAQ

1. **Q:** How do I insert a shape with a specific size and position?  
   **A:** Use `DocumentBuilder.insert_shape(shape_type, width, height)` for inline shapes or `DocumentBuilder.insert_shape(shape_type, horz_pos, left, vert_pos, top, width, height, wrap_type)` for floating shapes. The method creates a DML shape that retains its properties when saved in a format that supports DML.

2. **Q:** How can I lock the aspect ratio of a shape?  
   **A:** Set the `aspect_ratio_locked` property of the shape (or `ShapeBase` object) to `True`. This prevents the shape from being distorted when its size is changed.

3. **Q:** What property controls whether a shape is placed inside a table cell?  
   **A:** Use the `is_layout_in_cell` property. Setting it to `True` forces the shape to be rendered inside the cell boundaries; `False` places it outside the cell.

4. **Q:** How do I detect if a shape contains a SmartArt diagram?  
   **A:** Check the `has_smart_art` property of the `Shape` object. It returns `True` when the shape encapsulates a SmartArt object.

5. **Q:** How can I insert an OLE object as an icon with a custom caption?  
   **A:** Call `DocumentBuilder.insert_ole_object_as_icon(file_name, is_linked, icon_file, icon_caption)`. Ensure the icon image is 32 × 32 pixels for correct display.