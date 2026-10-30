---
title: Repeat Table Header Rows on Pages
second_title: Aspose.Words for Java
articleTitle: Repeat Table Header Rows on Pages
linktitle: Repeat Table Header Rows on Pages
description: "Repeat a header row of a table on every page. Docx4j does not provide an opportunity to work with a header row."
type: docs
weight: 10
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/repeat-table-header-rows-on-pages/
timestamp: 2024-01-31-14-23-37
---

{{% alert color="primary" %}}

See more details in the [Working with Columns and Rows](/words/java/working-with-columns-and-rows/) article of the [Working with Tables](/words/java/working-with-tables/) documentation section.

{{% /alert %}}

A table can specify certain starting table rows to be used as header rows. This means that if the table spans over many pages, these rows will be repeated at the top of the table for each page. In Aspose.Words, you can apply this setting by using the [getHeadingFormat()](https://reference.aspose.com/words/java/com.aspose.words/rowformat/#getHeadingFormat) property.

The following code example shows how to build a table with rows that repeat on every page:

{{< highlight csharp >}}
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
builder.getRowFormat().setHeadingFormat(true);
builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
builder.getCellFormat().setWidth(100);
builder.insertCell();
builder.writeln("Heading row 1");
builder.endRow();
builder.insertCell();
builder.writeln("Heading row 2");
builder.endRow();
builder.getCellFormat().setWidth(50);
builder.getParagraphFormat().clearFormatting();

// Insert some content so the table is long enough to continue onto the next page.
for (int i = 0; i < 50; i++)
{
    builder.insertCell();
    builder.getRowFormat().setHeadingFormat(false);
    builder.write("Column 1 Text");
    builder.insertCell();
    builder.write("Column 2 Text");
    builder.endRow();
}
doc.save(dataDir + "RepearHeaderRows.doc");
{{< /highlight >}}

See also:

- [GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/releases/tag/Aspose.Words_Java_for_Docx4j-v1.0.0) for running code

- [GitHub](https://github.com/aspose-words/Aspose.Words-for-Java/blob/master/Plugins/Aspose_Words_Java_for_Docx4j/src/main/java/com/aspose/words/examples/asposefeatures/tables/repeatheaderrow/AsposeRepeatHeaderRow.java) for code example
