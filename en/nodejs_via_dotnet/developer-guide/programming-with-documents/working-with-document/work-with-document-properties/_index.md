---
title: Work with Document Properties
second_title: Aspose.Words for Node.js via .NET
articleTitle: Work with Document Properties
linktitle: Work with Document Properties
description: "Aspose.Words for Node.js allows storing some useful information about your document, such as API and Version Number or Authorized Date, in built-in or custom document properties."
type: docs
weight: 10
ai_search_scope: words_nodejs
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /nodejs-net/work-with-document-properties/
timestamp: 2024-01-31-14-23-37
---

Document properties allow storing some useful information about your document. These properties can be divided into two groups:

* System or built-in that contain values such as document title, author name, document statistics, and others.
* User-defined or custom, provided as name-value pairs where the user can define both the name and value.

It is useful to know that information about API and Version Number is directly written to output documents. For example, upon converting a document to PDF, Aspose.Words fills in the "Application" field with "Aspose.Words", and the "PDF Producer" field with "Aspose.Words for Node.js via .NET YY.M.N", where *YY.M.N* is the version of Aspose.Words used for conversion. For more details, see [Generator or Producer Name Included in Output Documents](/words/nodejs-net/generator-or-producer-name-included-in-output-documents/).

{{% alert color="primary" %}}

Note that you **cannot direct** Aspose.Words to change or remove this information from output documents.

{{% /alert %}}

## Access Document Properties

To access document properties in Aspose.Words use:

* [builtInDocumentProperties](https://reference.aspose.com/words/nodejs-net/aspose.words/document/builtindocumentproperties/) to obtain built-in properties.

* [customDocumentProperties](https://reference.aspose.com/words/nodejs-net/aspose.words/document/customdocumentproperties/) to obtain custom properties.

[builtInDocumentProperties](https://reference.aspose.com/words/nodejs-net/aspose.words/document/builtindocumentproperties/) and [customDocumentProperties](https://reference.aspose.com/words/nodejs-net/aspose.words/document/customdocumentproperties/) are collections of [DocumentProperty](https://reference.aspose.com/words/nodejs-net/aspose.words.properties/documentproperty/) objects. These objects can be obtained through the indexer property by name or by index.

[builtInDocumentProperties](https://reference.aspose.com/words/nodejs-net/aspose.words/document/builtindocumentproperties/) additionally provides access to document properties through a set of entered properties that return values of the appropriate type. [customDocumentProperties](https://reference.aspose.com/words/nodejs-net/aspose.words/document/customdocumentproperties/) enable you to add or remove document properties from a document.

The [DocumentProperty](https://reference.aspose.com/words/nodejs-net/aspose.words.properties/documentproperty/) class allows you to get the name, value, and type of a document property. **value** returns an object, but there is a set of methods allowing you to get the property value converted to a specific type. After you get to know what type the property is, you can use one of the **DocumentProperty.toXXX** methods, such as **DocumentProperty.\_\_str\_\_** and [DocumentProperty.toInt](https://reference.aspose.com/words/nodejs-net/aspose.words.properties/documentproperty/toint/), to obtain the value of the appropriate type.

The following code example shows how to enumerate all built-in and custom properties in a document:

{{< gist "aspose-words-gists" "9bd62e688457850bceba59bc2c0ead99" "enumerate-properties.js" >}}

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Node.js-via-.NET/tree/main/Data/Properties.docx).

{{% /alert %}}

In Microsoft Word, you can access document properties using the "File → Properties" menu.

<img src="work-with-document-properties-1.png" alt="work-with-document-properties-1.png" style="width:400px"/>

## Add or Remove Document Properties

You cannot add or remove built-in document properties using Aspose.Words. You can only change or update their values.

To add custom document properties with Aspose.Words, use the [add](https://reference.aspose.com/words/nodejs-net/aspose.words.properties/customdocumentproperties/add/) method, passing the new property name and the value of the appropriate type. The method returns the newly created [DocumentProperty](https://reference.aspose.com/words/nodejs-net/aspose.words.properties/documentproperty/) object.

To remove custom properties, use the [remove](https://reference.aspose.com/words/nodejs-net/aspose.words.properties/documentpropertycollection/remove/) method, passing it the property name to remove, or the [removeAt](https://reference.aspose.com/words/nodejs-net/aspose.words.properties/documentpropertycollection/removeAt/) method to remove the property by index. You can also remove all properties using the [clear](https://reference.aspose.com/words/nodejs-net/aspose.words.properties/documentpropertycollection/clear/) method.

The following code example checks whether a custom property with a given name exists in a document and adds a few more custom document properties:

{{< gist "aspose-words-gists" "9bd62e688457850bceba59bc2c0ead99" "add-custom-properties.js" >}}

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Node.js-via-.NET/tree/main/Data/Properties.docx).

{{% /alert %}}

The following code example shows how to remove a custom document property:

{{< gist "aspose-words-gists" "9bd62e688457850bceba59bc2c0ead99" "remove-custom-properties.js" >}}

## Update Built-In Document Properties

Aspose.Words does not automatically update document properties, as Microsoft Word does with some properties, but provides a method to update some statistical built-in document properties. Call the [updateWordCount](https://reference.aspose.com/words/nodejs-net/aspose.words/document/updateWordCount/) method to recalculate and update the following properties:

* [characters](https://reference.aspose.com/words/nodejs-net/aspose.words.properties/builtindocumentproperties/characters/)
* [charactersWithSpaces](https://reference.aspose.com/words/nodejs-net/aspose.words.properties/builtindocumentproperties/characterswithspaces/)
* [words](https://reference.aspose.com/words/nodejs-net/aspose.words.properties/builtindocumentproperties/words/)
* [paragraphs](https://reference.aspose.com/words/nodejs-net/aspose.words.properties/builtindocumentproperties/paragraphs/)
* [lines](https://reference.aspose.com/words/nodejs-net/aspose.words.properties/builtindocumentproperties/lines/)

## Create a New Custom Property Linked to Content

Aspose.Words provides the [addLinkToContent](https://reference.aspose.com/words/nodejs-net/aspose.words.properties/customdocumentproperties/addlinktocontent/) method to create a new custom document property linked to content. This property returns the newly created property object or null if the **linkSource** is invalid.

The following code example shows how to configure a link to a custom property:

{{< gist "aspose-words-gists" "9bd62e688457850bceba59bc2c0ead99" "configuring-link-to-content.js" >}}

## Get Document Variables

You can get a collection of document variables using the [variables](https://reference.aspose.com/words/nodejs-net/aspose.words/document/variables/) property. Variable names and values are strings.

The following code example shows how to add and access document variables:

{{< gist "aspose-words-gists" "9bd62e688457850bceba59bc2c0ead99" "get-variables.js" >}}

{{% alert color="primary" %}}

You can download the template file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Node.js-via-.NET/tree/main/Data/Properties.docx).

{{% /alert %}}

## Remove Personal Information from Document

If you want to share a Word document with other people, you may want to remove personal information such as author name and company. To do this use the [removePersonalInformation](https://reference.aspose.com/words/nodejs-net/aspose.words/document/removepersonalinformation/) property to set the flag indicating that Microsoft Word will remove all user information from comments, revisions, and document properties upon saving the document.

The following code example shows how to remove personal information:

{{< gist "aspose-words-gists" "9bd62e688457850bceba59bc2c0ead99" "remove-personal-information.js" >}}

{{% alert color="primary" %}}

Setting this option does not actually remove personal information while processing a document in Aspose.Words and affects only the Microsoft Word behavior.

{{% /alert %}}
