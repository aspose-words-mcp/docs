---
title: Mail Merge with Regions in C++
second_title: Aspose.Words for C++
articleTitle: Mail Merge with Regions
linktitle: Mail Merge with Regions
type: docs
aliases:
 - /cpp/how-to-execute-mail-merge/
description: "Create different regions in your template to have special areas that you can simply fill with your data. Use the Mail Merge with regions if you want to insert tables, rows with repeating data to make your documents dynamically grow."
keywords: "how to execute Mail Merge c++"
weight: 20
ai_search_scope: words_cpp
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /cpp/mail-merge-with-regions/
timestamp: 2024-09-24-14-35-44
---

You can create different regions in your template to have special areas that you can simply fill with your data. Use the Mail Merge with regions if you want to insert tables, rows with repeating data to make your documents dynamically grow by specifying those regions within your template.

You can create nested (child) regions as well as merge regions. The main advantage of using this type is to dynamically increase parts inside a document. See more details in the next article "Nested Mail Merge with Regions".

{{% alert color="primary" %}}

Information about a Mail Merge region can be obtained using the [MailMergeRegionInfo](https://reference.aspose.com/words/cpp/aspose.words.mailmerging/mailmergeregioninfo/) class.

{{% /alert %}}

## How to Execute Mail Merge with Regions

A Mail Merge region is a specific part inside a document that has a start point and an end point. Both points are represented as Mail Merge fields that have specific names *"TableStart:XXX"* and *"TableEnd:XXX"*. All content that is included in a Mail Merge region will automatically be repeated for every record in the data source.

Aspose.Words allows you to execute Mail Merge with regions using one of the [ExecuteWithRegions](https://reference.aspose.com/words/cpp/aspose.words.mailmerging/mailmerge/executewithregions/) methods that accept [IMailMergeDataSource](https://reference.aspose.com/words/cpp/aspose.words.mailmerging/imailmergedatasource/) custom data source.

The following code example shows how to execute Mail Merge with regions from sqlite database with [SQLiteCpp](https://github.com/SRombauts/SQLiteCpp):

{{< gist "aspose-words-gists" "3435df005db9907ec9ba3a6b777ae6fb" "nested-mail-merge.h" >}}

You can notice the difference between the document before executing Mail Merge with regions:

<img src="execute-mail-merge-with-regions-1.png" alt="mail_merge_with_regions_template" style="width:850px"/>

And after executing Mail Merge with regions:

<img src="execute-mail-merge-with-regions-2.png" alt="mail_merge_with_regions_execute" style="width:850px"/>

## Limitations of Mail Merge with Regions

There are some important points that you need to consider when performing a Mail Merge with regions:

* The start point *TableStart:Orders* and the end point *TableEnd:Orders* both need to be in the same row or cell. For example, if you start a merge region in a cell of a table, you must end the merge region in the same row as the first cell.  
  The merge field name must match the column name in your data source. Unless you specify mapped fields, Mail Merge with regions will not succeed for any merge field that has a name other than the column name.
* Aspose.Words for C++ only supports [IMailMergeDataSource](https://reference.aspose.com/words/cpp/aspose.words.mailmerging/imailmergedatasource/) and [IMailMergeDataSourceRoot](https://reference.aspose.com/words/cpp/aspose.words.mailmerging/imailmergedatasourceroot/) based data sources. Unlike .NET and Java, C++ does not have a generally accepted cross‑platform API for working with databases (like ADODB, ODBC, or JDBC). In order to work with a specific data source, you have to implement [IMailMergeDataSource](https://reference.aspose.com/words/cpp/aspose.words.mailmerging/imailmergedatasource/) or [IMailMergeDataSourceRoot](https://reference.aspose.com/words/cpp/aspose.words.mailmerging/imailmergedatasourceroot/) interface.

If one of these rules is broken, you will get unexpected results or an exception may be thrown.

{{% alert color="primary" %}}

If you do not use Mail Merge regions, then it will be similar to Microsoft Word mail merge, and the whole document content will be repeated for each record in the data source.

{{% /alert %}}

------  

## FAQ

1. **Q:** How do I implement a custom `IMailMergeDataSource` in C++?  
   **A:** Create a class that inherits from `Aspose::Words::MailMerging::IMailMergeDataSource` and implement the required members: `get_TableName`, `GetValue`, `MoveNext`, and `GetChildDataSource`. In `GetValue` return the field value for the current record, and in `MoveNext` advance to the next record. Register the data source with `MailMerge::ExecuteWithRegions`.

2. **Q:** Can I use nested mail‑merge regions, and how are they defined?  
   **A:** Yes. Define inner regions with their own `TableStart:ChildRegion` and `TableEnd:ChildRegion` fields inside the outer region. When executing, the outer region's data source must provide a child data source (via `GetChildDataSource`) for each record to populate the inner region.

3. **Q:** What happens if the start and end merge fields of a region are not in the same row or cell?  
   **A:** Aspose.Words throws an `InvalidOperationException`: "Mail merge region '...' is badly formed. TableStart and TableEnd should be in the same section, same table row or same table cell." Ensure both `TableStart` and `TableEnd` tags are placed in the same table row or cell.

4. **Q:** Do the merge field names have to match the column names in my data source?  
   **A:** By default, yes. The field name in the document must exactly match a column name returned by `GetValue`. If you need different names, map them with `MailMerge::get_MappedDataFields()->Add(documentFieldName, dataSourceFieldName)` before calling `ExecuteWithRegions`.

5. **Q:** Is it possible to use a `DataTable` directly with `ExecuteWithRegions` in C++?  
   **A:** No. Unlike .NET, the C++ API does not provide a built‑in `DataTable` implementation. You must wrap your tabular data in a custom class that implements `IMailMergeDataSource` (or use `IMailMergeDataSourceRoot` for hierarchical data).