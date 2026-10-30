---
title: Convert Between Measurement Units in C++
second_title: Aspose.Words for C++
articleTitle: Convert Between Measurement Units
linktitle: Convert Between Measurement Units
description: "Aspose.Words for C++ can help you with how to convert between measurement units, for example, inches to points and points to inches, pixels to points, points to pixels."
type: docs
weight: 20
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/convert-between-measurement-units/
timestamp: 2024-01-27-14-07-04
---

Most of the object properties provided in the Aspose.Words API that represent some measurement, such as width or height, margins, and various distances, accept values in points, where 1 inch equals 72 points. Sometimes this is not convenient and points need to be converted to other units.

Aspose.Words provides the [ConvertUtil](https://reference.aspose.com/words/cpp/aspose.words/convertutil/) class that provides helper functions to convert between various measurement units. It enables converting inches, pixels and millimeters to points, points to inches and pixels, and converting pixels from one resolution to another. Converting pixels to points and vice versa can be performed at 96 dpi (dots per inch) resolutions or specified dpi resolution.

The **ConvertUtil** class is especially useful when setting various page properties because, for instance, inches are more common measurement units than points.

The following code example shows how to specify page properties in inches:

{{< gist "aspose-words-gists" "d55d8631947d283b1f0da99afa06c492" "cpp-Programming-Documents-ConvertUtil-UtilityClasses-ConvertBetweenMeasurementUnits.cpp" >}}

------ 

## FAQ

1. **Q:** How do I convert inches to points using Aspose.Words for C++?  
   **A:** Call `Aspose::Words::ConvertUtil::InchToPoint(double inches)`. For example:  
   ```cpp
   double points = Aspose::Words::ConvertUtil::InchToPoint(2.5); // 2.5 inches = 180 points
   ```

2. **Q:** How can I convert points to pixels at a specific DPI?  
   **A:** Use `Aspose::Words::ConvertUtil::PointToPixel(double points, double resolution)`. Example:  
   ```cpp
   double pixels = Aspose::Words::ConvertUtil::PointToPixel(72, 96); // 72 points = 96 pixels at 96 dpi
   ```

3. **Q:** Is there a method to convert millimeters to points?  
   **A:** Yes, `Aspose::Words::ConvertUtil::MillimeterToPoint(double millimeters)`. Example:  
   ```cpp
   double points = Aspose::Words::ConvertUtil::MillimeterToPoint(25.4); // 25.4 mm = 72 points
   ```

4. **Q:** How do I convert pixels from one resolution to another?  
   **A:** Use `Aspose::Words::ConvertUtil::PixelToNewDpi(double pixels, double oldDpi, double newDpi)`. Example:  
   ```cpp
   double newPixels = Aspose::Words::ConvertUtil::PixelToNewDpi(200, 96, 300); // 200 px at 96 dpi → equivalent at 300 dpi
   ```

5. **Q:** Can ConvertUtil convert points back to inches?  
   **A:** Yes, call `Aspose::Words::ConvertUtil::PointToInch(double points)`. Example:  
   ```cpp
   double inches = Aspose::Words::ConvertUtil::PointToInch(144); // 144 points = 2 inches
   ```