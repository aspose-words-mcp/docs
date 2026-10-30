---
title: Working with Ole Objects
second_title: Aspose.Words for Java
articleTitle: Working with Ole Objects
linktitle: Working with Ole Objects
description: "Create and modify OLE embedding in your document using Java."
type: docs
weight: 360
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-ole-objects/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to work with OLE objects embedded in Word documents.

{{% /alert %}}

OLE (Object Linking and Embedding) is a technology by which users can work with documents containing "objects" created or edited by third-party applications. That is, OLE allows an editing application to export these "objects" to another editing application and then import them with additional content.

In this article, we will talk about inserting an OLE object and setting its properties, as well as inserting an online video into a document.

## Insert OLE Object

If you want OLE Object, call the [insertOleObject()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertOleObject-java.io.InputStream-java.lang.String-boolean-java.io.InputStream) method and pass it the **progId** explicitly with other parameters.

The following code example shows how to insert OLE Object into a document:

{{< gist "aspose-words-gists" "79b218ed58e95a7aea639e04882cbd9b" "insert-ole-object.java" >}}

### Set File Name and Extension when Inserting OLE Object

OLE package is a legacy and "undocumented" way to store embedded objects if an OLE handler is unknown.

Early Windows versions such as Windows 3.1, 95, and 98 had a Packager.exe application that could be used to embed any type of data into the document. This application is now excluded from Windows, but Microsoft Word and other applications still use it to embed data if the OLE handler is missing or unknown. The `OlePackage` class allows users to access the OLE Package properties.

The following code example shows how to set the file name, extension, and display name for OLE Package:

{{< gist "aspose-words-gists" "79b218ed58e95a7aea639e04882cbd9b" "insert-ole-objectwith-ole-package.java" >}}

### Get Access to OLE Object Raw Data

Users can access OLE object data using various properties and methods of the `OleFormat` class. For example, it is possible to get the `OLE` object raw data or the path and name of a source file for the linked OLE object.

The following code example shows how to get OLE Object raw data using the [getRawData()](https://reference.aspose.com/words/java/com.aspose.words/oleformat/#getRawData) method:

{{< gist "aspose-words-gists" "79b218ed58e95a7aea639e04882cbd9b" "get-access-to-ole-object-raw-data.java" >}}

### Insert OLE Object as an Icon

OLE objects can also be inserted into documents as images.

The following code example shows how to insert OLE Object as an icon. For this purpose, the [insertOleObjectAsIcon()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertOleObjectAsIcon-java.io.InputStream-java.lang.String-java.lang.String-java.lang.String) class exposes the [insertOleObjectAsIcon()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertOleObjectAsIcon-java.io.InputStream-java.lang.String-java.lang.String-java.lang.String) method:

{{< gist "aspose-words-gists" "79b218ed58e95a7aea639e04882cbd9b" "insert-ole-object-as-icon.java" >}}

The following code example shows how to inserts an embedded OLE object as an icon from a stream into the document:

{{< gist "aspose-words-gists" "79b218ed58e95a7aea639e04882cbd9b" "insert-ole-object-as-icon-using-stream.java" >}}

{{% alert color="primary" %}}

Maximum size of the icon must be 32x32 for the correct display.

{{% /alert %}}

## Insert Online Video

Online video can be inserted into Word document from the *"Insert" > "Online Video"* tab. You can insert an online video into a document at the current location by calling the [insertOnlineVideo()](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/#insertOnlineVideo-java.lang.String-double-double) method.

The [DocumentBuilder](https://reference.aspose.com/words/java/com.aspose.words/documentbuilder/) class introduces four overloads of this method. The first one works with the most popular video resources and takes the `URL` of the video as a parameter. For example, the first overload supports simple insertion of online videos from [YouTube](https://www.youtube.com/) and [Vimeo](https://vimeo.com/) resources.

The following code example shows how to insert an online video from *Vimeo* into a document:

{{< gist "aspose-words-gists" "79b218ed58e95a7aea639e04882cbd9b" "insert-online-video.java" >}}

The second overload works with all other video resources and takes embedded HTML code as a parameter. The HTML code for embedding a video may vary depending on the provider, so contact the respective provider for details.

{{% alert color="primary" %}}

Please note that the document will be automatically optimized for MS Word 2013 to show video.

{{% /alert %}}

The following code example shows how to insert an online video into a document using such HTML code:

{{< gist "aspose-words-gists" "79b218ed58e95a7aea639e04882cbd9b" "insert-online-video-with-embed-html.java" >}}

## FAQ

1. **Q:** How do I insert an OLE object from a file stream in Java?  
   **A:** Use `DocumentBuilder.insertOleObject(InputStream stream, String progId, boolean asIcon, InputStream presentation)`. Provide the object's ProgID (e.g., `"Word.Document"`), the data stream, `asIcon` to show the object as an icon, and optionally a stream with the image to display.

2. **Q:** How can I set a custom file name, extension, and display name for an OLE package?  
   **A:** Insert the file as an OLE package (`builder.insertOleObject(stream, "Package", false, null)`), then get its `OlePackage` with `shape.getOleFormat().getOlePackage()` and call `setFileName()` and `setDisplayName()`. There is no separate extension setting; the extension is part of the file name.

3. **Q:** What is the way to retrieve the raw binary data of an embedded OLE object?  
   **A:** Get the `OleFormat` object from the OLE `Shape` (`OleFormat ole = shape.getOleFormat();`) and call `ole.getRawData()` to get a byte array containing the original data.

4. **Q:** How can I insert an OLE object as an icon rather than as embedded content?  
   **A:** Use `DocumentBuilder.insertOleObjectAsIcon(InputStream stream, String progId, String iconFileName, String iconDisplayName)`; this inserts the object and displays the specified icon image.

5. **Q:** How can I detect whether a document contains any OLE objects?  
   **A:** OLE objects are `Shape` nodes with OLE data. Iterate through the document's shapes:  
   ```java
   NodeCollection shapes = doc.getChildNodes(NodeType.SHAPE, true);
   for (Shape shape : (Iterable<Shape>) shapes) {
       if (shape.getOleFormat() != null) {
           // OLE object found
       }
   }
   ```  
   If any shape has OLE data, the document includes OLE objects.