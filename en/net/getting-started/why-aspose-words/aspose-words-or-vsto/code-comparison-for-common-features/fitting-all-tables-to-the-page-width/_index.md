---
title: Fitting all Tables to the Page Width
second_title: Aspose.Words for .NET
articleTitle: Fitting all Tables to the Page Width
linktitle: Fitting all Tables to the Page Width
description: "Fit a table into a document by page width easily and fast instead of using VSTO in C#."
type: docs
weight: 30
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/fitting-all-tables-to-the-page-width/
timestamp: 2024-01-27-14-07-04
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to adjust all tables so they fit within the page width.

{{% /alert %}}

## VSTO

{{< highlight csharp >}}
string mypath = "Document.docx";
Word.Application wordApp = Application;
wordApp.Documents.Open(mypath);
foreach (Table table in this.Application.ActiveDocument.Tables)
{
  table.PreferredWidthType = WdPreferredWidthType.wdPreferredWidthPercent;
  table.PreferredWidth = 100;
}
{{< /highlight >}}

## Aspose.Words

{{< highlight csharp >}}
Document doc = new Document( "doc.docx");
foreach (Table table in doc.GetChildNodes(NodeType.Table, true))
{
	table.PreferredWidth = PreferredWidth.FromPercent(100);
}
{{< /highlight >}}

## Download Sample Code

- [Github](https://github.com/asposemarketplace/Aspose_for_VSTO/releases/download/Aspose.Words1.0/Fitting.all.Tables.to.the.Page.Width.Aspose.Words.zip)
- [Sourceforge](https://sourceforge.net/projects/asposevsto/files/)
