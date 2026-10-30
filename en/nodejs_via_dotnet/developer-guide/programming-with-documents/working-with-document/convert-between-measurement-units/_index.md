---
title: Convert Between Measurement Units
second_title: Aspose.Words for Node.js via .NET
articleTitle: Convert Between Measurement Units
linktitle: Convert Between Measurement Units
description: "Aspose.Words for Node.js via .NET can help you with how to convert between measurement units, for example, inches to points and points to inches, pixels to points, points to pixels."
type: docs
weight: 20
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/convert-between-measurement-units/
timestamp: 2025-07-09-10-05-05
---

Most of the object properties provided in the Aspose.Words API that represent some measurement, such as width or height, margins, and various distances, accept values in points, where 1 inch equals 72 points. Sometimes this is not convenient and points need to be converted to other units.

Aspose.Words provides the [ConvertUtil](https://reference.aspose.com/words/nodejs-net/aspose.words/convertutil/) class that provides helper functions to convert between various measurement units. It enables converting inches, pixels and millimeters to points, points to inches and pixels, and converting pixels from one resolution to another. Converting pixels to points and vice versa can be performed at 96 dpi (dots per inch) resolutions or specified dpi resolution.

The [ConvertUtil](https://reference.aspose.com/words/nodejs-net/aspose.words/convertutil/) class is especially useful when setting various page properties because, for instance, inches are more common measurement units than points.

The following code example shows how to specify page properties in inches:

{{< gist "aspose-words-gists" "0fd389e71a7e1ef74e6e48e94d37be5d" "convert-between-measurement-units.js" >}}

------ 

## FAQ

1. **Q:** How do I convert inches to points using `ConvertUtil`?  
   **A:** Use the static method `ConvertUtil.inchToPoint`. Pass the number of inches and the method returns the equivalent points (1 inch = 72 points).  
   ```javascript
   const aw = require('@aspose/words');
   const ConvertUtil = aw.ConvertUtil;

   const inches = 2.5;
   const points = ConvertUtil.inchToPoint(inches); // 180 points
   ```

2. **Q:** Can I convert pixels to points at a custom DPI?  
   **A:** Yes. Call `ConvertUtil.pixelToPoint` with the pixel value and the DPI you want to use. This lets you adapt the conversion to the resolution of your source image.  
   ```javascript
   const pixels = 300;
   const dpi = 150; // custom DPI
   const points = ConvertUtil.pixelToPoint(pixels, dpi);
   ```

3. **Q:** Is there a method to convert millimeters to points?  
   **A:** `ConvertUtil` provides `millimeterToPoint`. Supply the millimeter value and it returns the corresponding points (1 mm ≈ 2.83465 points).  
   ```javascript
   const millimeters = 50;
   const points = ConvertUtil.millimeterToPoint(millimeters);
   ```

4. **Q:** What DPI does `ConvertUtil` use by default when converting pixels?  
   **A:** When you call `ConvertUtil.pixelToPoint` without specifying a DPI, the method assumes a default of 96 dpi, which is the standard screen resolution. If you need a different DPI, pass it as the second argument.

5. **Q:** How can I convert points back to inches?  
   **A:** Use the static method `ConvertUtil.pointToInch`. It takes a point value and returns the measurement in inches.  
   ```javascript
   const points = 144;
   const inches = ConvertUtil.pointToInch(points); // 2 inches
   ```