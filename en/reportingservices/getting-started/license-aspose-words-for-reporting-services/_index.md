---
title: License
second_title: Aspose.Words for Reporting Services
articleTitle: License Aspose.Words for Reporting Services
linktitle: License Aspose.Words for Reporting Services
description: "Licensing details of the Aspose.Words for Reporting Services."
type: docs
weight: 50
url: /reportingservices/license-aspose-words-for-reporting-services/
timestamp: 2024-10-24-11-44-28
---

{{% alert color="primary" %}}

Once you are happy with the evaluation, [buy a license](https://purchase.aspose.com/pricing/words/family/). Before purchasing make sure you understand and agree to the license subscription terms.

The license is emailed to you when the order has been paid. The license is a clear text, digitally signed XML file and contains information such as the client name, the purchased product and the type of the license. Do not modify the content of the license file as it will invalidate the license.

{{% /alert %}}

## Licensing a Server

Download the license file and copy it to the `C:\Program Files\Microsoft SQL Server&#92;&lt;Instance&gt;\Reporting Services\ReportServer\bin` folder on the server.
Where &lt;Instance&gt; is the subdirectory name that corresponds to the Microsoft SQL Server instance you want to license:

- The default instance directory for Microsoft SQL Server 2012 is MSRS11.MSSQLSERVER.
- The default instance directory for Microsoft SQL Server 2014 is MSRS12.MSSQLSERVER.
- The default instance directory for Microsoft SQL Server 2016 is MSRS13.MSSQLSERVER.

For Microsoft SQL Server 2017, 2019 and 2022, copy the license file to the `C:\Program Files\Microsoft SQL Server Reporting Services\SSRS\ReportServer\bin` folder. For Power BI Report Server, copy it to the `C:\Program Files\Microsoft Power BI Report Server\PBIRS\ReportServer\bin` folder.

## Licensing Application Development

Add a reference to Aspose.Words for Reporting Services to your project and `Aspose.Words.ReportingServices.dll` will be automatically copied to the Bin (binary output) folder of your application.

The license can be loaded from a file, stream or an embedded resource. Aspose.Words for Reporting Services will try to find the license in the following locations:

- Explicit path.
- The folder that contains `Aspose.Words.ReportingServices.dll`.
- The folder that contains the assembly that called `Aspose.Words.ReportingServices.dll`.
- The folder that contains the entry assembly (your .exe).
- An embedded resource in the assembly that called `Aspose.Words.ReportingServices.dll`.

Use the License.SetLicense method to license the component. The easiest way to set a license is to put the license file in the same folder as the `Aspose.Words.ReportingServices.dll` and specify just the file name without a path as shown in the following example:

**C#**

{{< highlight csharp >}}
Aspose.Words.ReportingServices.License license = new Aspose.Words.ReportingServices.License();
license.SetLicense("Aspose.Words.Reporting.Services.lic");
{{< /highlight >}}

**Visual Basic**

{{< highlight vb >}}
Dim license As Aspose.Words.ReportingServices.License = New Aspose.Words.ReportingServices.License()
license.SetLicense("Aspose.Words.Reporting.Services.lic")
{{< /highlight >}}

The following example shows how to set a license from a stream:

**C#**

{{< highlight csharp >}}
Aspose.Words.ReportingServices.License license = new Aspose.Words.ReportingServices.License();
license.SetLicense(myStream);
{{< /highlight >}}

**Visual Basic**

{{< highlight vb >}}
Dim license As Aspose.Words.ReportingServices.License = New Aspose.Words.ReportingServices.License()
license.SetLicense(myStream)
{{< /highlight >}}

### Deploying a License with Your Application

Distribute the license file in the same folder as `Aspose.Words.ReportingServices.dll`.

### Licensing Generation of Reports at Design Time

Download the license file and copy it to the folder that contains the `Aspose.Words.ReportingServices.dll` used by the Report Designer (for a manual installation, see [Integrating Manually with Visual Studio Report Designer](/words/reportingservices/integrating-manually-with-visual-studio-report-designer/)).

### Testing a License

To test that a license has been installed correctly, export any report as a Microsoft Word document. If the document contains no watermark at the top, the license was activated successfully.

**When a valid Aspose.Words.ReportingServices.lic is present in the `ReportServer\bin` folder, no evaluation watermark is added to the file**

![todo:image_alt_text](license-aspose-words-for-reporting-services-1.png)

**If there is a problem with the license, the error message will be output into the report**

![todo:image_alt_text](license-aspose-words-for-reporting-services-2.png)
