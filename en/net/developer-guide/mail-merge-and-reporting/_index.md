---
title: Mail Merge and Reporting in C#
second_title: Aspose.Words for .NET
articleTitle: Mail Merge and Reporting
linktitle: Mail Merge and Reporting
aliases:
  - /net/about-mail-merge/
type: docs
description: "Mail Merge is a popular feature for quickly creating documents using C#. Aspose.Words for .NET takes the standard Mail Merge functionality and advances it many steps ahead, turning it into a full-fledged reporting solution that allows you to create even more complex documents such as reports, catalogs, inventories, and invoices."
keywords: "how to use Mail Merge c#"
weight: 30
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/mail-merge-and-reporting/
timestamp: 2024-07-11-08-07-06
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how Mail Merge and reporting features work in Aspose.Words and shows how to generate documents from data sources.

{{% /alert %}}

Mail Merge is a popular feature for quickly and easily creating documents such as letters, labels, and envelopes. Aspose.Words enables you to generate documents from templates with Mail Merge fields.

A Mail Merge field is a field that you can insert into a mail merge template to include specific values from a data source record in output documents. For example, you can insert a merge field in an email template so that the greeting will have the recipient's first name rather than a generic “Hello!”. Aspose.Words places data from an external source, such as a database or file, into these fields and formats them. The resulting document is saved in the specified folder.

Aspose.Words takes the standard Mail Merge functionality and advances it many steps ahead, turning it into a full-fledged reporting solution that allows you to create even more complex documents such as reports, catalogs, inventories, and invoices. Here are a few advantages of the Aspose.Words reporting solution:

- Design reports in Microsoft Word using standard Mail Merge fields
- Define regions in the document that are growing, such as detailed order rows
- Insert images during a mail merge
- Execute any custom logic, control formatting, or insert complex content using Mail Merge event handlers
- Fill in documents with data from any type of data source

{{% alert color="primary" %}}

The [Aspose.Words.MailMerging](https://reference.aspose.com/words/net/aspose.words.mailmerging/) namespace is used to work with mail merging.

{{% /alert %}}

## Mechanism and Main Components of Mail Merge {#mechanism-and-main-components-of-a-mail-merge-operation}

Aspose.Words provides the ability to load documents in various [supported formats](https://reference.aspose.com/words/net/aspose.words/loadformat/) and then allows users to perform a Mail Merge operation.

Usually, a loaded document allows you to store merge fields, for example, a document in DOCX format. But there are formats that do not store such fields, for example, TXT. If Aspose.Words supports loading such file formats, you can add the merge fields directly to the document model, save the document in a convenient [supported format](https://reference.aspose.com/words/net/aspose.words/saveformat/), and perform the Mail Merge operation.

The Mail Merge operation will merge your *mail merge template* and your *data source* to generate individual *merged documents*.

## What is a Mail Merge Template {#what-is-a-mail-merge-template}

The goal of applying a mail merge operation using a merge template is to simplify the process of creating a document.

There are several ways to create and design a merge template. You can use Microsoft Word, and the merge template does not have to be a Microsoft Word template, that is a document in the DOT or DOTX format, it can be a regular document in the DOC or DOCX format. You need to insert some special fields called merge fields into this template in places where you want data from your data source to be later inserted. Or you can programmatically create a merge template using the [DocumentBuilder](https://reference.aspose.com/words/net/aspose.words/documentbuilder/) class.

The merge template contains the main text, which should be the same in all output documents after you perform the Mail Merge operation. You can use any format for your template if there is an ability to add merge fields to it. All merge fields within your template will be filled in from your data source during the Mail Merge operation.

## Data Sources for a Mail Merge Operation {#data-source-types-for-a-mail-merge-operation}

Aspose.Words Mail Merge accepts various data sources. This can be either a DataTable, DataView, DataSet, IDataReader, an array of values supported by ADO .NET, or custom data sources represented by [IMailMergeDataSource](https://reference.aspose.com/words/net/aspose.words.mailmerging/imailmergedatasource/) implementations.

The data source contains all the information that is pulled during the Mail Merge operation in order to personalize individual emails and documents. Data sources can be created manually or generated by reporting from an existing database or application. If you have data in XML format, you can load and merge it with the DataSet. The Mail Merge operation will go through all the data source records and insert them into Mail Merge fields in the document. You can implement some mail merge interfaces such as [IMailMergeDataSourceRoot](https://reference.aspose.com/words/net/aspose.words.mailmerging/imailmergedatasourceroot/) to merge data from any data source, including a LINQ query, an XML file, or business objects.

The following code example shows how to load a data table as the data source for the Mail Merge operation:

{{< gist "aspose-words-gists" "de5e13f5d5bb7d8cb88da900b4f9ed8b" "execute-with-regions-data-table.cs" >}}

{{% alert color="primary" %}}

You can download the sample file of this example from [Aspose.Words GitHub](https://github.com/aspose-words/Aspose.Words-for-.NET/blob/master/Examples/Data/Mail%20merge%20destinations%20-%20Orders.docx).

{{% /alert %}}

## Merged Documents of a Mail Merge Operation {#merged-documents-of-a-mail-merge-operation}

A merged document is the result of the Mail Merge operation when you merge the template with the data source. All merge fields within the merged document are replaced with actual data from your data source.

The following image shows an example of the merge template with merged fields before performing the Mail Merge operation.

![mail-merge-and-reporting-fields-aspose-words-net](mail-merge-and-reporting-1.jpg)

The following image shows an example of the output merged document as a result of performing the Mail Merge operation.

![mail-merge-and-reporting-result-aspose-words-net](mail-merge-and-reporting-2.jpg)

## See Also

- [Work with Mail Merge templates in Word](https://docs.microsoft.com/en-us/power-platform/admin/work-mail-merge-templates)

## Related APIs

- [MailMerge](https://reference.aspose.com/words/net/aspose.words.mailmerging/mailmerge/)
- [IMailMergeDataSource](https://reference.aspose.com/words/net/aspose.words.mailmerging/imailmergedatasource/)
- [IMailMergeDataSourceRoot](https://reference.aspose.com/words/net/aspose.words.mailmerging/imailmergedatasourceroot/)
- [FieldMergingArgs](https://reference.aspose.com/words/net/aspose.words.mailmerging/fieldmergingargs/)
- [DocumentBuilder](https://reference.aspose.com/words/net/aspose.words/documentbuilder/)

## FAQ

1. **Q:** How can I perform a mail merge with repeating rows (regions) in a table?  
   **A:** Use the `ExecuteWithRegions` method. Load the template, call `document.MailMerge.ExecuteWithRegions(dataTable)`, where `dataTable` contains the rows to repeat. The method repeats the region defined by `MERGEFIELD TableStart:RegionName` and `MERGEFIELD TableEnd:RegionName` for each data row.

2. **Q:** How do I insert images into a document during a mail merge?  
   **A:** Include an image merge field (a merge field named `Image:ImagePath`) in the template. Implement `IFieldMergingCallback` and, in its `ImageFieldMerging(ImageFieldMergingArgs args)` method, set `args.ImageFileName` (or `args.ImageStream`) to the image; `args.ImageWidth` and `args.ImageHeight` set its size. Register the callback with `document.MailMerge.FieldMergingCallback = new ImageMergingCallback();`.

3. **Q:** Can I use a custom object collection as the data source for mail merge?  
   **A:** Yes. Implement the `IMailMergeDataSource` (or `IMailMergeDataSourceRoot` for hierarchical data) interface for your collection. Pass the implementation to `document.MailMerge.Execute(customDataSource)`. This allows you to merge from LINQ queries, business objects, or any custom source.

4. **Q:** After a mail merge, I get an empty paragraph left above a merged field. How can I remove it?  
   **A:** Implement `IFieldMergingCallback` and assign it to `document.MailMerge.FieldMergingCallback`. In `FieldMerging`, check if the node before the field's paragraph (`args.Field.Start.ParentParagraph.PreviousSibling`) is an empty `Paragraph`. If so, remove it with `Remove()`. Alternatively, add `MailMergeCleanupOptions.RemoveEmptyParagraphs` to `document.MailMerge.CleanupOptions` before executing the merge to remove paragraphs that become empty during the merge.