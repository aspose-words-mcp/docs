---
title: OLE Objects and Online Video
second_title: Aspose.Words for Python via .NET
articleTitle: Working with OLE Objects and Online Video
linktitle: Working with OLE Objects and Online Video
description: "Insert ole objects or onlin vodeo into a document using Python."
type: docs
weight: 360
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/working-with-ole-objects/
aliases:
- /python/working-with-ole-objects-and-online-video/
- /python-net/working-with-ole-objects-and-online-video/
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page demonstrates how to insert OLE objects—including setting package properties, accessing raw data, and inserting as icons—and how to embed online videos (via URL or HTML embed code) into Word documents using Aspose.Words for Python via .NET.  
{{% /alert %}}

OLE (Object Linking and Embedding) is a technology by which users can work with documents containing "objects" created or edited by third-party applications. That is, OLE allows an editing application to export these "objects" to another editing application and then import them with additional content.

In this article, we will talk about inserting an OLE object and setting its properties, as well as inserting an online video into a document.

## Insert OLE Object

If you want OLE Object, call the [insert_ole_object](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_ole_object/) method and pass it the **prog_id** explicitly with other parameters.

The following code example shows how to insert OLE Object into a document:

{{< gist "aspose-words-gists" "2c7d2bb472db1a698568d980c01b0735" "insert-ole-object.py" >}}

### Set File Name and Extension when Inserting OLE Object

OLE package is a legacy and "undocumented" way to store embedded objects if an OLE handler is unknown.

Early Windows versions such as Windows 3.1, 95, and 98 had a Packager.exe application that could be used to embed any type of data into the document. This application is now excluded from Windows, but Microsoft Word and other applications still use it to embed data if the OLE handler is missing or unknown. The `OlePackage` class allows users to access the OLE Package properties.

The following code example shows how to set the file name, extension, and display name for OLE Package:

{{< gist "aspose-words-gists" "2c7d2bb472db1a698568d980c01b0735" "insert-ole-objectwith-ole-package.py" >}}

### Get Access to OLE Object Raw Data

Users can access OLE object data using various properties and methods of the `OleFormat` class. For example, it is possible to get the `OLE` object raw data or the path and name of a source file for the linked OLE object.

The following code example shows how to get OLE Object raw data using the [get_raw_data](https://reference.aspose.com/words/python-net/aspose.words.drawing/oleformat/get_raw_data/) method:

{{< gist "aspose-words-gists" "2c7d2bb472db1a698568d980c01b0735" "get-access-to-ole-object-raw-data.py" >}}

### Insert OLE Object as an Icon

OLE objects can also be inserted into documents as images.

The following code example shows how to insert OLE Object as an icon. For this purpose, the [DocumentBuilder](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/) class exposes the [insert_ole_object_as_icon](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_ole_object_as_icon/) method:

{{< gist "aspose-words-gists" "2c7d2bb472db1a698568d980c01b0735" "insert-ole-object-as-icon.py" >}}

The following code example shows how to inserts an embedded OLE object as an icon from a stream into the document:

{{< gist "aspose-words-gists" "2c7d2bb472db1a698568d980c01b0735" "insert-ole-object-as-icon-using-stream.py" >}}

{{% alert color="primary" %}}

Maximum size of the icon must be 32x32 for the correct display.

{{% /alert %}}

## Insert Online Video

Online video can be inserted into Word document from the *"Insert" > "Online Video"* tab. You can insert an online video into a document at the current location by calling the [insert_online_video](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/insert_online_video/) method.

The [DocumentBuilder](https://reference.aspose.com/words/python-net/aspose.words/documentbuilder/) class introduces four overloads of this method. The first one works with the most popular video resources and takes the `URL` of the video as a parameter. For example, the first overload supports simple insertion of online videos from [YouTube](https://www.youtube.com/) and [Vimeo](https://vimeo.com/) resources.

The following code example shows how to insert an online video from *Vimeo* into a document:

{{< gist "aspose-words-gists" "2c7d2bb472db1a698568d980c01b0735" "insert-online-video.py" >}}

The second overload works with all other video resources and takes embedded HTML code as a parameter. The HTML code for embedding a video may vary depending on the provider, so contact the respective provider for details.

{{% alert color="primary" %}}

Please note that the document will be automatically optimized for MS Word 2013 to show video.

{{% /alert %}}

The following code example shows how to insert an online video into a document using such HTML code:

{{< gist "aspose-words-gists" "2c7d2bb472db1a698568d980c01b0735" "insert-online-video-with-embed-html.py" >}} 

## FAQ

1. **Q:** How can I insert an OLE object as an icon instead of displaying its full content?  
   **A:** Use `DocumentBuilder.insert_ole_object_as_icon`. Pass the file name (or a stream and its ProgId), the icon file, and the icon caption, e.g., `insert_ole_object_as_icon(file_name, is_linked, icon_file, icon_caption)`. The method creates a `Shape` that represents the icon in the document.

2. **Q:** I need to set a custom file name and extension for an OLE package that has no native handler. How is this done?  
   **A:** Insert the data with `DocumentBuilder.insert_ole_object(stream, "Package", False, None)`, then set `file_name` (including the extension) and `display_name` on the `ole_format.ole_package` of the returned shape. This embeds the data with the specified file name, allowing Word to recognize the file type.

3. **Q:** How can I retrieve the raw binary data of an embedded OLE object?  
   **A:** Access the `OleFormat` of the shape that contains the OLE object and call `OleFormat.get_raw_data()`. The method returns a `bytes` array containing the original embedded file data.

4. **Q:** Which video platforms are supported by the simple `insert_online_video(url, width, height)` overload?  
   **A:** The overload works directly with YouTube and Vimeo URLs. For other platforms you must use the overload that accepts embedded HTML code, providing the HTML snippet and an optional poster image.

5. **Q:** My inserted online video does not display in Word 2013. What should I check?  
   **A:** If the video is not displayed correctly, insert it with the overload that takes the embed HTML code and a thumbnail image: `insert_online_video(video_url, video_embed_code, thumbnail_image_bytes, width, height)`. Also verify that the video URL is reachable and that the width/height parameters are set to reasonable values (e.g., 360 × 270).