---
title: Work with Document Properties
second_title: Aspose.Words for Python via .NET
articleTitle: Work with Document Properties
linktitle: Work with Document Properties
description: "Aspose.Words for Python allows storing some useful information about your document, such as API and Version Number or Authorized Date, in built-in or custom document properties."
type: docs
weight: 10
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/work-with-document-properties/
aliases: [/python/work-with-document-properties/]
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}

*Purpose Summary. What is this page about?*

This page describes how to use Aspose.Words for Python via .NET to access, enumerate, add, remove, and update built‑in and custom document properties, link custom properties to content, work with document variables, and remove personal information from Word documents.

{{% /alert %}}

Document properties allow storing some useful information about your document. These properties can be divided into two groups:

* System or built-in that contain values such as document title, author name, document statistics, and others.
* User-defined or custom, provided as name-value pairs where the user can define both the name and value.

It is useful to know that information about API and Version Number is directly written to output documents. For example, upon converting a document to PDF, Aspose.Words fills in the "Application" field with "Aspose.Words", and the "PDF Producer" field with "Aspose.Words for Python via .NET YY.M.N", where *YY.M.N* is the version of Aspose.Words used for conversion. For more details, see [Generator or Producer Name Included in Output Documents](/words/python-net/generator-or-producer-name-included-in-output-documents/).

{{% alert color="primary" %}}

Note that you **cannot direct** Aspose.Words to change or remove this information from output documents.

{{% /alert %}}

## Access Document Properties

To access document properties in Aspose.Words use:

* [built_in_document_properties](https://reference.aspose.com/words/python-net/aspose.words/document/built_in_document_properties/) to obtain built-in properties.

* [custom_document_properties](https://reference.aspose.com/words/python-net/aspose.words/document/custom_document_properties/) to obtain custom properties.

**BuiltInDocumentProperties** and **CustomDocumentProperties** are collections of [DocumentProperty](https://reference.aspose.com/words/python-net/aspose.words.properties/documentproperty/) objects. These objects can be obtained through the indexer property by name or by index.

**BuiltInDocumentProperties** additionally provides access to document properties through a set of entered properties that return values of the appropriate type. **CustomDocumentProperties** enable you to add or remove document properties from a document.

The [DocumentProperty](https://reference.aspose.com/words/python-net/aspose.words.properties/documentproperty/) class allows you to get the name, value, and type of a document property. [value](https://reference.aspose.com/words/python-net/aspose.words.properties/documentproperty/value/) returns an object, but there is a set of methods allowing you to get the property value converted to a specific type. After you get to know what type the property is, you can use one of the **DocumentProperty.to_xxx** methods, such as **DocumentProperty.**[DocumentProperty.to_int](https://reference.aspose.com/words/python-net/aspose.words.properties/documentproperty/to_int/) and **DocumentProperty.**[to_int](https://reference.aspose.com/words/python-net/aspose.words.properties/documentproperty/to_int/), to obtain the value of the appropriate type.

The following code example shows how to enumerate all built-in and custom properties in a document:

{{< gist "aspose-words-gists" "f594b976dcd6cfbe363ad317ca32a3a0" "enumerate-properties.py" >}}

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Python-via-.NET/blob/master/Examples/Data/Properties.docx).

{{% /alert %}}

In Microsoft Word, you can access document properties using the “File → Properties” menu.

<img src="work-with-document-properties-1.png" alt="work-with-document-properties-1.png" style="width:400px"/>

## Add or Remove Document Properties

You cannot add or remove built-in document properties using Aspose.Words. You can only change or update their values.

To add custom document properties with Aspose.Words, use the [add](https://reference.aspose.com/words/python-net/aspose.words.properties/customdocumentproperties/add/) method, passing the new property name and the value of the appropriate type. The method returns the newly created **DocumentProperty** object.

To remove custom properties, use the [remove](https://reference.aspose.com/words/python-net/aspose.words.properties/documentpropertycollection/remove/) method, passing it the property name to remove, or the [remove_at](https://reference.aspose.com/words/python-net/aspose.words.properties/documentpropertycollection/remove_at/) method to remove the property by index. You can also remove all properties using the [clear](https://reference.aspose.com/words/python-net/aspose.words.properties/documentpropertycollection/clear/) method.

The following code example checks whether a custom property with a given name exists in a document and adds a few more custom document properties:

{{< gist "aspose-words-gists" "f594b976dcd6cfbe363ad317ca32a3a0" "add-custom-properties.py" >}}

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Python-via-.NET/blob/master/Examples/Data/Properties.docx).

{{% /alert %}}

The following code example shows how to remove a custom document property:

{{< gist "aspose-words-gists" "f594b976dcd6cfbe363ad317ca32a3a0" "remove-custom-properties.py" >}}

## Update Built-In Document Properties

Aspose.Words does not automatically update document properties, as Microsoft Word does with some properties, but provides a method to update some statistical built-in document properties. Call the [update_word_count](https://reference.aspose.com/words/python-net/aspose.words/document/update_word_count/) method to recalculate and update the following properties:

* [characters](https://reference.aspose.com/words/python-net/aspose.words.properties/builtindocumentproperties/characters/)
* [characters_with_spaces](https://reference.aspose.com/words/python-net/aspose.words.properties/builtindocumentproperties/characters_with_spaces/)
* [words](https://reference.aspose.com/words/python-net/aspose.words.properties/builtindocumentproperties/words/)
* [paragraphs](https://reference.aspose.com/words/python-net/aspose.words.properties/builtindocumentproperties/paragraphs/)
* [lines](https://reference.aspose.com/words/python-net/aspose.words.properties/builtindocumentproperties/lines/)

## Create a New Custom Property Linked to Content

Aspose.Words provides the [add_link_to_content](https://reference.aspose.com/words/python-net/aspose.words.properties/customdocumentproperties/add_link_to_content/) method to create a new custom document property linked to content. This property returns the newly created property object or None if the [link_source](https://reference.aspose.com/words/python-net/aspose.words.properties/documentproperty/link_source/) is invalid.

The following code example shows how to configure a link to a custom property:

{{< gist "aspose-words-gists" "f594b976dcd6cfbe363ad317ca32a3a0" "configuring-link-to-content.py" >}}

## Get Document Variables

You can get a collection of document variables using the [variables](https://reference.aspose.com/words/python-net/aspose.words/document/variables/) property. Variable names and values are strings.

The following code example shows how to enumerate document variables:

{{< gist "aspose-words-gists" "f594b976dcd6cfbe363ad317ca32a3a0" "get-variables.py" >}}

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Python-via-.NET/blob/master/Examples/Data/Properties.docx).

{{% /alert %}}

## Remove Personal Information from Document

If you want to share a Word document with other people, you may want to remove personal information such as author name and company. To do this use the [remove_personal_information](https://reference.aspose.com/words/python-net/aspose.words/document/remove_personal_information/) property to set the flag indicating that Microsoft Word will remove all user information from comments, revisions, and document properties upon saving the document.

The following code example shows how to remove personal information:

{{< gist "aspose-words-gists" "f594b976dcd6cfbe363ad317ca32a3a0" "remove-personal-information.py" >}}

{{% alert color="primary" %}}

Setting this option does not actually remove personal information while processing a document in Aspose.Words and affects only the Microsoft Word behavior.

{{% /alert %}}  

## FAQ

1. **Q:** *Can I modify built‑in document properties such as Title or Author?*  
   **A:** Yes, you can change the values of built‑in properties, but you cannot add new built‑in properties or remove existing ones. Use the `built_in_document_properties` collection to set the desired values.

2. **Q:** *How can I list all custom document properties in a document?*  
   **A:** Iterate over the `custom_document_properties` collection. Each item is a `DocumentProperty` object, and you can read its `name`, `value`, and type‑specific getters (e.g., `to_string()`, `to_int()`).

3. **Q:** *Is it possible to prevent Aspose.Words from writing the Application and PDF Producer fields in generated PDFs?*  
   **A:** Partly. Set `export_generator_name = False` on `PdfSaveOptions` to omit the PDF Producer field (product name and version). The Application field still contains "Aspose.Words".

4. **Q:** *Can I create a custom property that automatically reflects the content of a bookmark or field?*  
   **A:** Yes. Use the `add_link_to_content` method of `custom_document_properties` and provide the bookmark or field name as the link source. The property will update whenever the linked content changes.