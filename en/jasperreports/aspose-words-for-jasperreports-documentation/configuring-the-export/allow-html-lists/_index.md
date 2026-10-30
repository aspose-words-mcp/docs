---
title: Converting HTML Lists to Word Lists
second_title: Aspose.Words for JasperReports
articleTitle: Converting HTML Lists to Word Lists
linktitle: Converting HTML Lists to Word Lists
description: "Aspose Words for JasperReports can convert Html lists into Words lists with bullets and numbers."
type: docs
weight: 230
url: /jasperreports/converting-html-lists-to-word-lists/
aliases: [/jasperreports/allow-html-lists/]
timestamp: 2025-10-27-17-45-04
---

Aspose.Words for JasperReports allows to convert HTML lists with bullets and numbers into Words lists using the **ALLOW_HTML_LISTS** option.

By default, value of the **ALLOW_HTML_LISTS** parameter is **false**. This means that Aspose.Words for JasperReports will replace HTML bulleted and numbered lists with plain text. However, you can enable this option by setting it to **true** if you want to convert an HTML list to a Word list.

{{% alert color="primary" %}}

**Note**: This option only affects export to DOCX, DOC, and RTF output formats.

{{% /alert %}}

**In JasperReports:**

{{< highlight java >}}
import com.aspose.words.jasperreports.*;
AWDocExporter exporter = new AWDocExporter();
exporter.setParameter(AWExporterParameter.ALLOW_HTML_LISTS, true);
exporter.exportReport();
{{< /highlight >}}

**In JasperServer:**

{{< highlight xml >}}
<bean id="aw_exportParameters" class="com.aspose.words.jasperreports.AWExportParametersBean">
    <property name="allowHtmlLists" value="true"/>
</bean>
{{< /highlight >}}
