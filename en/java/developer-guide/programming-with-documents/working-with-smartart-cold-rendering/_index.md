---
title: Working with SmartArt Cold Rendering in Java
second_title: Aspose.Words for Java
articleTitle: Working with SmartArt Cold Rendering
linktitle: Working with SmartArt Cold Rendering
description: "Introduction to SmartArt shapes using Java."
type: docs
weight: 330
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-smartart-cold-rendering/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how SmartArt cold rendering works when converting documents.

{{% /alert %}}

SmartArt graphics are used to quickly and easily create a visual representation of information. You simply choose from a large number of layouts that best suits your situation. This ease of use makes SmartArt graphics quite popular for some purposes.

Microsoft Word generates and saves the pre-rendered drawing along with the `SmartArt` object. In most cases, the pre-rendered drawing is rendered well by Aspose.Words and no additional actions are required. However, if the document is saved by other applications, the pre-rendered SmartArt drawing may be missing or incorrect. In this case, the `SmartArt` object itself should be laid-out and rendered using Aspose.Words. We call this process the `SmartArt` Cold Rendering.

## Using SmartArt Cold Rendering

Aspose.Words allows you to use a pre-rendered drawing or perform cold rendering:

* If a pre-rendered drawing is available, Aspose.Words uses it to render the `SmartArt` object.
* If pre-rendered drawing is missing, Aspose.Words implicitly performs cold rendering to render the `SmartArt` object.
* If a pre-rendered drawing is present but is incorrect, it is required to perform SmartArt cold rendering explicitly by calling [updateSmartArtDrawing()](https://reference.aspose.com/words/java/com.aspose.words/shape/#updateSmartArtDrawing) method.

The following code example shows how to update drawings for all diagrams in the document:

{{< gist "aspose-words-gists" "69fffe75454d325c814eefbe9a99e8d7" "update-smart-art-drawing.java" >}}

## Support for Standard SmartArt Layouts

Currently, only a limited number of standard Microsoft Word SmartArt layouts are supported. Also, some of these layouts are supported partially, meaning that significant nodes and shapes of the diagram are rendered, but there may be differences between the Microsoft Word and Aspose.Words diagram layout.

The table below lists the fully and partially supported layouts:

| SmartArt Layouts Group | Fully supported layouts                                      | Partially supported layouts                                  |
| ---------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `List` | <ul><li>Basic Block List</li><li>Alternating Hexagons</li><li>Vertical Bullet List</li><li>Vertical Box List</li><li>Varying Width List</li><li>Horizontal Bullet List</li><li>Grouped List</li><li>Vertical Block List</li><li>Vertical Chevron List</li><li>Vertical Arrow List</li><li>Trapezoid List</li><li>Table List</li><li>Pyramid List</li><li>Target List</li></ul> | <ul><li>Lined List</li><li>Vertical Bracket List</li><li>Tab List</li><li>Stacked List</li><li>Vertical Accent List</li><li>Vertical Circle List</li></ul> |
| `Process` | <ul><li>Basic Process</li><li>Accent Process</li><li>Continuous Block Process</li><li>Increasing Arrow Process</li><li>Converging Text</li><li>Basic Timeline</li><li>Basic Chevron Process</li><li>Chevron Accent Process</li><li>Closed Chevron Process</li><li>Chevron List</li><li>Vertical Process</li><li>Staggered Process</li><li>Process List</li><li>Basic Bending Process</li><li>Repeating Bending Process</li><li>Detailed Process</li><li>Upward Arrow</li><li>Descending Process</li><li>Circular Bending Process</li></ul> | <ul><li>Step Up Process</li><li>Step Down Process</li><li>Alternating Flow</li><li>Increasing Circle Process</li><li>Pie Process</li><li>Interconnected Block Process</li><li>Process Arrows</li><li>Circle Accent Timeline</li><li>Circle Process</li><li>Sub Step Process</li><li>Phased Process</li><li>Random to Result Process</li><li>Circle Arrow Process</li></ul> |
| `Cycle` | –                                                            | <ul><li>Segmented Cycle</li><li>Hexagon Radial</li></ul>     |
| `Hierarchy` | –                                                            | <ul><li>Table Hierarchy</li><li>Architecture Layout</li></ul> |
| `Relationship` | <ul><li>Balance</li><li>Funnel</li><li>Gear</li><li>Plus And Minus</li><li>Arrow Ribbon</li><li>Counterbalance Arrows</li><li>Opposing Arrows</li><li>Nested Target</li><li>Basic Target</li><li>Basic Pie</li><li>Basic Venn</li><li>Stacked Venn</li><li>Interconnected Ring</li></ul> | <ul><li>Circle Relationship</li><li>Opposing Ideas</li><li>Equation</li><li>Vertical Equation</li><li>Linear Venn</li></ul> |
| `Matrix` | <ul><li>Basic Matrix</li><li>Titled Matrix</li><li>Grid Matrix</li><li>Cycle Matrix</li></ul> | –                                                            |
| `Pyramid` | –                                                            | <ul><li>Segmented Pyramid</li></ul>                          |

## Comparison of SmartArt Rendering in Aspose.Words and Microsoft

The table below shows example pictures of Aspose.Words Cold Rendering of some standard layouts compared to Microsoft Word output:

|                               | **Aspose.Words**                                             | **Microsoft Word**                                           |
| ----------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **Basic Process**             | <img src="basic-process-aspose.png" alt="basic_process_aspose-java"/> | <img src="basic-process-word.png" alt="basic_process_word-java"/> |
| **Circular Bending Process**  | <img src="circular-bending-process-aspose.png" alt="circular_bending_process_aspose-java"/> | <img src="circular-bending-process-word.png" alt="circular_bending_process_word-java"/> |
| **Repeating Bending Process** | <img src="repearing-bending-process-aspose.png" alt="repearing_bending_process_aspose-java"/> | <img src="repearing-bending-process-word.png" alt="repearing_bending_process_word-java"/> |
| **Trapezoid List**            | <img src="trapezoid-list-aspose.png" alt="trapezoid_list_aspose-java"/> | <img src="trapezoid-list-word.png" alt="trapezoid_list_word-java"/> |  

## FAQ

1. **Q:** How can I force Aspose.Words to perform cold rendering when the pre‑rendered SmartArt drawing is incorrect?  
   **A:** Call the `Shape.updateSmartArtDrawing()` method on each `Shape` that contains a SmartArt object. This forces Aspose.Words to discard the existing drawing and lay out the SmartArt anew.

2. **Q:** Is cold rendering performed automatically if the pre‑rendered drawing is missing?  
   **A:** Yes. When Aspose.Words loads a document and detects that a SmartArt object has no associated drawing, it automatically performs cold rendering without any additional code.

3. **Q:** Which SmartArt layout groups are fully supported by Aspose.Words for Java?  
   **A:** The fully supported groups are **List**, **Process**, **Relationship**, and **Matrix**. The documentation table lists the exact layouts within each group.

4. **Q:** How do I update the drawings for all SmartArt objects in a document with a single call?  
   **A:** Iterate through all `Shape` nodes, check `shape.hasSmartArt()`, and invoke `shape.updateSmartArtDrawing()`. The sample code in the article demonstrates this pattern.

5. **Q:** Can I determine programmatically whether a SmartArt object already has a pre‑rendered drawing?  
   **A:** No. The API has no property that shows whether a pre‑rendered drawing exists. If you are not sure the drawing is correct, call `shape.updateSmartArtDrawing()` to rebuild it with cold rendering.