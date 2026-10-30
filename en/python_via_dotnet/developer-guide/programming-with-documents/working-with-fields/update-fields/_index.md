---
title: Updating Fields Python
second_title: Aspose.Words for Python via .NET
articleTitle: Update Fields
linktitle: Update Fields
description: "Update fields in a document in different ways and using different option in Python."
type: docs
weight: 30
ai_search_scope: words_python
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /python-net/update-fields/
aliases:
- /python/updating-and-removing-a-field/
- /python-net/updating-and-removing-a-field/
timestamp: 2026-02-03-11-08-55
---

{{% alert color="grey" %}}
*Purpose Summary. What is this page about?*

This page explains how to update fields in documents using Aspose.Words for Python via .NET, covering programmatic updates, automatic updates during rendering and mail merge, handling dirty fields, and updating the `last_saved_time` property, with code examples.
{{% /alert %}}

Typically, a field inserted into Microsoft Word already contains an up to date value. For example, if the field is a formula or a page number, it will contain the correct calculated value for the given version of the document. But if you have an application that generates or modifies a document with fields like merging two documents or populating it with data, then ideally all fields must be updated for the document to be useful.

## How to Update Fields

When a document is loaded, Aspose.Words mimics the behavior of Microsoft Word with the option to automatically update fields is switched off. The behavior can be summarized as follows:

- when you open/save a document the fields remain intact
- you can explicitly update all fields in a document, for example, rebuild `TOC`, when you need to
- when you print/render to PDF or XPS the fields related to page-numbering in headers/footers are updated
- when you execute Mail Merge all fields are updated automatically

### Update Fields Programmatically

To explicitly update fields in the whole document, simply call the [update_fields](https://reference.aspose.com/words/python-net/aspose.words/document/update_fields/) method. To update fields contained in part of a document, obtain a [Range](https://reference.aspose.com/words/python-net/aspose.words/range/) object and call the [update_fields](https://reference.aspose.com/words/python-net/aspose.words/range/update_fields/) method. In Aspose.Words, you can obtain a **Range** for any node in the document tree, such as [Section](https://reference.aspose.com/words/python-net/aspose.words/section/), [HeaderFooter](https://reference.aspose.com/words/python-net/aspose.words/headerfooter/) , [Paragraph](https://reference.aspose.com/words/python-net/aspose.words/paragraph/), etc. using the [Node.range](https://reference.aspose.com/words/python-net/aspose.words/node/range/) property. You can update the result of a single field by calling the [update](https://reference.aspose.com/words/python-net/aspose.words.fields/field/update/) method.

### Automatic Update of Page-Related Fields During Rendering

When you execute conversion of a document to a fixed-page format e.g. to PDF or XPS, then Aspose.Words will automatically update page layout-related fields `PAGE`, `PAGEREF` found in headers/footers of the document. This behavior mimics the behavior of Microsoft Word when printing a document.

If you want to update all other fields in the document, then you need to call [update_fields](https://reference.aspose.com/words/python-net/aspose.words/document/update_fields/) before rendering the document.

The following code example shows how to update all fields before rendering a document:

{{< gist "aspose-words-gists" "365214c8b2e8c065166447871a1499aa" "update-doc-fields.py" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-Python-via-.NET/blob/master/Examples/Data/Rendering.docx).

{{% /alert %}}

### Automatic Field Update During Mail Merge

When you execute a mail merge, all fields in the document will be automatically updated. This is because the Mail Merge is a case of a field update. The program encounters a Mail Merge field and needs to update its result, which involves grabbing the value from the data source and inserting it into the field. The logic is of course more complicated, for example, when the end of the document/mail merge region is reached but there is still further data to be merged, then the region needs to be duplicated and the new set of fields updated.

## Update Fields Having Dirty Attribute

The w:dirty is a field-level attribute that will refresh only the field you specify when the document is opened. It tells MS Word to only refresh this field the next time the document is opened. You can use the [update_dirty_fields](https://reference.aspose.com/words/python-net/aspose.words.loading/loadoptions/update_dirty_fields/) property to specify whether to update the fields with the dirty attribute. When the value of **update_dirty_fields** is set to *true*, all fields having *true* value for [Field.is_dirty](https://reference.aspose.com/words/python-net/aspose.words.fields/field/is_dirty/) or [FieldChar.is_dirty](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldchar/is_dirty/) property are updated on document load.

The following code example shows how to update fields having the dirty attribute:

{{< gist "aspose-words-gists" "365214c8b2e8c065166447871a1499aa" "update-dirty-fields.py" >}}

## Update LastSavedTime Property Before Saving

You can use the [SaveOptions.update_last_saved_time_property](https://reference.aspose.com/words/python-net/aspose.words.saving/saveoptions/update_last_saved_time_property/) property whether to update the corresponding built-in document property [last_saved_time](https://reference.aspose.com/words/python-net/aspose.words.properties/builtindocumentproperties/last_saved_time/) when saving the document.

The following code example shows how to update this property:

{{< gist "aspose-words-gists" "b05f6fe5e272263ce37254e9e36a5ae0" "update-last-saved-time.py" >}}

## Related APIs

- [Document.update_fields()](https://reference.aspose.com/words/python-net/aspose.words/document/update_fields/) - Updates all fields in the document.
- [Range.update_fields()](https://reference.aspose.com/words/python-net/aspose.words/range/update_fields/) - Updates fields within a specific range (e.g., section, header, paragraph).
- [Field.update()](https://reference.aspose.com/words/python-net/aspose.words.fields/field/update/) - Updates a single field.
- [LoadOptions.update_dirty_fields](https://reference.aspose.com/words/python-net/aspose.words.loading/loadoptions/update_dirty_fields/) - Gets or sets a value indicating whether to update fields marked as dirty when loading a document.
- [Field.is_dirty](https://reference.aspose.com/words/python-net/aspose.words.fields/field/is_dirty/) - Gets or sets a value indicating whether the field result is out of date.
- [FieldChar.is_dirty](https://reference.aspose.com/words/python-net/aspose.words.fields/fieldchar/is_dirty/) - Gets or sets a value indicating whether the field result is out of date.
- [SaveOptions.update_last_saved_time_property](https://reference.aspose.com/words/python-net/aspose.words.saving/saveoptions/update_last_saved_time_property/) - Gets or sets a value indicating whether to update the `last_saved_time` built-in document property when saving.
- [BuiltInDocumentProperties.last_saved_time](https://reference.aspose.com/words/python-net/aspose.words.properties/builtindocumentproperties/last_saved_time/) - Gets or sets the date and time the document was last saved.