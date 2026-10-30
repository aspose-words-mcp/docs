---
title: Installation
second_title: Aspose.Words for JasperReports
articleTitle: Installation
linktitle: Installation
description: "Aspose.Words for JasperReports works with JasperReports and JasperServer. This article explains how to integrate the exporter."
type: docs
weight: 60
url: /jasperreports/installation/
timestamp: 2026-04-28-10-15-55
---

{{% alert color="primary" %}}

Aspose.Words for JasperReports works with JasperReports and JasperServer. This article explains how to integrate the exporter.

{{% /alert %}}

## Integration with JasperReports

To use Aspose.Words for JasperReports from your application, you should copy a single appropriate **.jar** file from the \lib folder of **Aspose.Words.JasperReports-xx.x.zip** to the JasperReports\lib directory or to a library folder of your application. After that, you can access the exporters programmatically.

**Note:** Starting from release **1.9.0** there are several versions of JAR library (necessary for better support of older versions of JasperReports). Please select the correct JAR file according to your JasperReports and JasperServer versions using the table below:

| For<br>JasperServer | For<br>JasperReports | Use the following JAR library |
| :- | :- | :- |
| 8.0.0 ... 8.2.0 | 7.0.0 ... 7.0.4 | **aspose.words.jasperreports-xx.x.x-8.0.0-8.2.0.jar** |
| 7.8.0 ... 8.0.0 | 6.12.0... 6.20.0 | **aspose.words.jasperreports-xx.x.x-7.8.0-8.0.0.jar** |
| 7.1.0 ... 7.5.0 | 6.5.0 ... 6.11.0 | **aspose.words.jasperreports-xx.x.x-7.1.0-7.5.0.jar** |
| 6.4.2 ... 6.4.3 | 6.4.2 ... 6.4.21 | **aspose.words.jasperreports-xx.x.x-6.4.2-6.4.3.jar** |
| 6.3.0 ... 6.4.0 | 6.3.0 ... 6.4.1 | **aspose.words.jasperreports-xx.x.x-6.3.0-6.4.0.jar** |

Please copy **ONLY ONE** jar library according to the version of installed JasperReports.

The following example shows typical code needed to export a report to a DOC file using Aspose.Words for JasperReports. More examples can be found in the demo reports included in the product download.

**Java**
{{< highlight java >}}
   import com.aspose.words.jasperreports.*;
   AWDocExporter exporter = new AWDocExporter();
   File sourceFile = new File(fileName);
   JasperPrint jasperPrint = (JasperPrint)JRLoader.loadObject(sourceFile);
   exporter.setParameter(JRExporterParameter.JASPER_PRINT, jasperPrint);
   File destFile = new File(sourceFile.getParent(), jasperPrint.getName() + ".doc");
   exporter.setParameter(JRExporterParameter.OUTPUT_FILE_NAME, destFile.toString());
   exporter.exportReport();
{{< /highlight >}}

## Integration with JasperServer

To add DOC, DOCX, RTF, ODT, HTML and TXT export formats to JasperServer, perform the following steps. In all of the following steps **<InstallDir>** stands for the `JasperServer` installation directory.

**Step 0: Stop JasperServer**

Stop JasperReports Server. It is recommended also to clean **<InstallDir>\apache-tomcat\logs** directory after stopping.

**Step 1: Add Exporter Configuration**

Edit the **<InstallDir>\apache-tomcat\webapps\jasperserver\WEB-INF\flows\viewReportBeans.xml** file.

Add the following bean definitions **before** the `<util:map id="exporterConfigMap">` element:

**XML**
{{< highlight xml >}}
<!-- Aspose.Words for JasperReports Exporters -->
<bean id="aw_reportDocExporter" class="com.aspose.words.jasperreports.AWReportDocExporter" parent="baseReportExporter">
   <property name="exportParameters" ref="aw_exportParameters"/>
   <property name="setResponseContentLength" value="true"/>
</bean>
<bean id="aw_reportDocxExporter" class="com.aspose.words.jasperreports.AWReportDocxExporter" parent="baseReportExporter">
   <property name="exportParameters" ref="aw_exportParameters"/>
   <property name="setResponseContentLength" value="true"/>
</bean>
<bean id="aw_reportRtfExporter" class="com.aspose.words.jasperreports.AWReportRtfExporter" parent="baseReportExporter">
   <property name="exportParameters" ref="aw_exportParameters"/>
   <property name="setResponseContentLength" value="true"/>
</bean>
<bean id="aw_reportOdtExporter" class="com.aspose.words.jasperreports.AWReportOdtExporter" parent="baseReportExporter">
   <property name="exportParameters" ref="aw_exportParameters"/>
   <property name="setResponseContentLength" value="true"/>
</bean>
<bean id="aw_reportHtmlExporter" class="com.aspose.words.jasperreports.AWReportHtmlExporter" parent="baseReportExporter">
   <property name="exportParameters" ref="aw_exportParameters"/>
   <property name="setResponseContentLength" value="true"/>
</bean>
<bean id="aw_reportTxtExporter" class="com.aspose.words.jasperreports.AWReportTxtExporter" parent="baseReportExporter">
   <property name="exportParameters" ref="aw_exportParameters"/>
   <property name="setResponseContentLength" value="true"/>
</bean>

<!-- Exporter Configuration Beans -->
<bean id="aw_docExporterConfiguration" class="com.jaspersoft.jasperserver.war.action.ExporterConfigurationBean">
   <property name="descriptionKey" value="DOC - Word Document via Aspose.Words"/>
   <property name="exportParameters" ref="aw_exportParameters"/>
   <property name="currentExporter" ref="aw_reportDocExporter"/>
</bean>
<bean id="aw_docxExporterConfiguration" class="com.jaspersoft.jasperserver.war.action.ExporterConfigurationBean">
   <property name="descriptionKey" value="DOCX - Word Document via Aspose.Words"/>
   <property name="exportParameters" ref="aw_exportParameters"/>
   <property name="currentExporter" ref="aw_reportDocxExporter"/>
</bean>
<bean id="aw_rtfExporterConfiguration" class="com.jaspersoft.jasperserver.war.action.ExporterConfigurationBean">
   <property name="descriptionKey" value="RTF - Rich Text Format via Aspose.Words"/>
   <property name="exportParameters" ref="aw_exportParameters"/>
   <property name="currentExporter" ref="aw_reportRtfExporter"/>
</bean>
<bean id="aw_odtExporterConfiguration" class="com.jaspersoft.jasperserver.war.action.ExporterConfigurationBean">
   <property name="descriptionKey" value="ODT - OpenDocument Text via Aspose.Words"/>
   <property name="exportParameters" ref="aw_exportParameters"/>
   <property name="currentExporter" ref="aw_reportOdtExporter"/>
</bean>
<bean id="aw_htmlExporterConfiguration" class="com.jaspersoft.jasperserver.war.action.ExporterConfigurationBean">
   <property name="descriptionKey" value="HTML - Web Page via Aspose.Words"/>
   <property name="exportParameters" ref="aw_exportParameters"/>
   <property name="currentExporter" ref="aw_reportHtmlExporter"/>
</bean>
<bean id="aw_txtExporterConfiguration" class="com.jaspersoft.jasperserver.war.action.ExporterConfigurationBean">
   <property name="descriptionKey" value="TXT - Plain Text via Aspose.Words"/>
   <property name="exportParameters" ref="aw_exportParameters"/>
   <property name="currentExporter" ref="aw_reportTxtExporter"/>
</bean>
{{< /highlight >}}


**Note for JasperServer 3.x and 4.x:**
Add the following properties to each configuration bean (not required for 5.x, 6.x, 7.x, 8.x):
{{< highlight xml >}}
<property name="iconSrc" value="/images/aw_docx.gif"/>
<property name="parameterDialogName" value=""/>
{{< /highlight >}}

**Step 2: Register Exporters in the Map**

Edit the **<InstallDir>\apache-tomcat\webapps\jasperserver\WEB-INF\flows\viewReportBeans.xml** file.

Locate the `<util:map id="exporterConfigMap">` element and add the Aspose.Words exporters:

**XML**
{{< highlight xml >}}
<util:map id="exporterConfigMap">
   <entry key="pdf" value-ref="pdfExporterConfiguration"/>
   <entry key="xls" value-ref="xlsExporterConfiguration"/>
   <entry key="rtf" value-ref="rtfExporterConfiguration"/>
   <entry key="csv" value-ref="csvExporterConfiguration"/>
   <entry key="swf" value-ref="swfExporterConfiguration"/>
   <!-- Aspose.Words for JasperReports START -->
   <entry key="aw_doc" value-ref="aw_docExporterConfiguration"/>
   <entry key="aw_docx" value-ref="aw_docxExporterConfiguration"/>
   <entry key="aw_rtf" value-ref="aw_rtfExporterConfiguration"/>
   <entry key="aw_odt" value-ref="aw_odtExporterConfiguration"/>
   <entry key="aw_html" value-ref="aw_htmlExporterConfiguration"/>
   <entry key="aw_txt" value-ref="aw_txtExporterConfiguration"/>
   <!-- Aspose.Words for JasperReports END -->
</util:map>
{{< /highlight >}}

**Step 3: Copy Image Icons (JasperServer 3.x and 4.x only)**

Copy all GIF images from the \lib_ folder in **Aspose.Words.JasperReports-xx.x.zip** to **<InstallDir>**\apache-tomcat\webapps\jasperserver\images\.

**Note:** This step is only applied to JasperReports Server 3.x and 4.x, not required for JasperReports Server 5.x, 6.x, 7.x, and 8.x versions.

**Step 4: Copy the JAR File**

Copy the appropriate JAR file from the \lib folder of **Aspose.Words.JasperReports-xx.x.x.zip** to **<InstallDir>**\apache-tomcat\webapps\jasperserver\WEB-INF\lib.

If you are using JasperServer v8.0.0 ... v8.2.0 (with JasperReports 7.0.0 - 7.0.4), copy **aspose.words.jasperreports-xx.x.x-8.0.0-8.2.0.jar** file.

If you are using JasperServer v7.8.0 ... v8.0.0 (with JasperReports 6.12.0 - 6.20.5), copy **aspose.words.jasperreports-xx.x.x-7.8.0-8.0.0.jar** file.

If you are using JasperServer v7.1.0 ... v7.5.0 (with JasperReports 6.5.0 - 6.11.0), copy **aspose.words.jasperreports-xx.x.x-7.1.0-7.5.0.jar** file.

If you are using JasperServer v6.4.2 ... v6.4.3 (with JasperReports 6.4.2 - 6.4.21), copy **aspose.words.jasperreports-xx.x.x-6.4.2-6.4.3.jar** file.

If you are using JasperServer v6.3.0 ... v6.4.0 (with JasperReports 6.3.0 - 6.4.1), copy **aspose.words.jasperreports-xx.x.x-6.3.0-6.4.0.jar** file.

NOTE: You need to copy **ONLY ONE** jar file.

**Step 5a: Configure Export Parameters (Optional)**

Edit the **<InstallDir>\apache-tomcat\webapps\jasperserver\WEB-INF\applicationContext.xml** file.

This bean may contain various configuration settings intended to configure the export. For example, you can use the `JasperReports` font mapping feature or specify the location of the Aspose.Words for JasperReports license file.

**XML**
{{< highlight xml >}}
<bean id="aw_exportParameters" class="com.aspose.words.jasperreports.AWExportParametersBean">
  <property name="fontMap">
    <util:map id="fontMap">
      <entry key="sansserif" value="Arial"/>
      <entry key="serif" value="Times New Roman"/>
      <entry key="monospaced" value="Courier"/>
    </util:map>
  </property>
  <!-- Uncomment to apply a license
  <property name="licenseFile" value="/path/to/Aspose.Words.JasperReports.lic"/>
  -->
</bean>
{{< /highlight >}}

**Step 5b: Enable Web Services Exporters (Optional)**

**Note:** Starting from JasperReports Server 5.6, SOAP Web Services are **NOT** supported. Use REST API instead (see Step 5c).

Edit the **<InstallDir>\apache-tomcat\webapps\jasperserver\WEB-INF\applicationContext-web-services.xml** file.

Add the following beans inside the `<beans>` section:

**XML**
{{< highlight xml >}}
    ...
    <!-- Aspose.Words for JasperReports Web Services START -->
    <bean id="awDocExporter" class="com.aspose.words.jasperreports.ws.AWDocWSExporter" scope="prototype">
        <property name="exportParams" ref="aw_exportParameters"/>
    </bean>
    <bean id="awDocxExporter" class="com.aspose.words.jasperreports.ws.AWDocxWSExporter" scope="prototype">
        <property name="exportParams" ref="aw_exportParameters"/>
    </bean>
    <bean id="awHtmlExporter" class="com.aspose.words.jasperreports.ws.AWHtmlWSExporter" scope="prototype">
        <property name="exportParams" ref="aw_exportParameters"/>
    </bean>
    <bean id="awOdtExporter" class="com.aspose.words.jasperreports.ws.AWOdtWSExporter" scope="prototype">
        <property name="exportParams" ref="aw_exportParameters"/>
    </bean>
    <bean id="awRtfExporter" class="com.aspose.words.jasperreports.ws.AWRtfWSExporter" scope="prototype">
        <property name="exportParams" ref="aw_exportParameters"/>
    </bean>
    <bean id="awTxtExporter" class="com.aspose.words.jasperreports.ws.AWTxtWSExporter" scope="prototype">
        <property name="exportParams" ref="aw_exportParameters"/>
    </bean>
    <!-- Aspose.Words for JasperReports END -->
    ...
{{< /highlight >}}

Add entries to the `exportersMap`:

**XML**
{{< highlight xml >}}
    <util:map id="exportersMap">
        ...
        <!-- Aspose.Words for JasperReports START -->
        <entry key="aw_doc" value-ref="awDocExporter"/>
        <entry key="aw_docx" value-ref="awDocxExporter"/>
        <entry key="aw_html" value-ref="awHtmlExporter"/>
        <entry key="aw_odt" value-ref="awOdtExporter"/>
        <entry key="aw_rtf" value-ref="awRtfExporter"/>
        <entry key="aw_txt" value-ref="awTxtExporter"/>
        <!-- Aspose.Words for JasperReports END -->
    </util:map>
{{< /highlight >}}

Add entries to the `exportParametersMap`:

**XML**
{{< highlight xml >}}
<util:map id="exportParametersMap">
    ...
    <!-- Aspose.Words for JasperReports START -->
    <entry key="aw_doc" value-ref="aw_exportParameters"/>
    <entry key="aw_docx" value-ref="aw_exportParameters"/>
    <entry key="aw_html" value-ref="aw_exportParameters"/>
    <entry key="aw_odt" value-ref="aw_exportParameters"/>
    <entry key="aw_rtf" value-ref="aw_exportParameters"/>
    <entry key="aw_txt" value-ref="aw_exportParameters"/>
    <!-- Aspose.Words for JasperReports END -->
</util:map>
{{< /highlight >}}

**Note:** Starting from JasperReports Server 8.2 'exportParametersMap' could be not in 'applicationContext-web-services.xml' you can add this util:map section manually.

**Step 5c: Enable REST API Exporters (Required for JasperServer 5.6+)**

Edit the **<InstallDir>\apache-tomcat\webapps\jasperserver\WEB-INF\applicationContext-remote-services.xml** file.

Add the following beans inside the `<beans>` section:

**XML**
{{< highlight xml >}}
    ...
    <!-- Aspose.Words for JasperReports REST API START -->
    <bean id="remoteAwDocExporter" class="com.aspose.words.jasperreports.remote.AWDocRemoteExporter" scope="prototype">
        <property name="exportParams" ref="aw_exportParameters"/>
    </bean>
    <bean id="remoteAwDocxExporter" class="com.aspose.words.jasperreports.remote.AWDocxRemoteExporter" scope="prototype">
        <property name="exportParams" ref="aw_exportParameters"/>
    </bean>
    <bean id="remoteAwHtmlExporter" class="com.aspose.words.jasperreports.remote.AWHtmlRemoteExporter" scope="prototype">
        <property name="exportParams" ref="aw_exportParameters"/>
    </bean>
    <bean id="remoteAwOdtExporter" class="com.aspose.words.jasperreports.remote.AWOdtRemoteExporter" scope="prototype">
        <property name="exportParams" ref="aw_exportParameters"/>
    </bean>
    <bean id="remoteAwRtfExporter" class="com.aspose.words.jasperreports.remote.AWRtfRemoteExporter" scope="prototype">
        <property name="exportParams" ref="aw_exportParameters"/>
    </bean>
    <bean id="remoteAwTxtExporter" class="com.aspose.words.jasperreports.remote.AWTxtRemoteExporter" scope="prototype">
        <property name="exportParams" ref="aw_exportParameters"/>
    </bean>
    <!-- Aspose.Words for JasperReports END -->
    ...
{{< /highlight >}}

Add entries to the `remoteExportersMap`:

**XML**
{{< highlight xml >}}
<util:map id="remoteExportersMap">
        ...
        <!-- Aspose.Words for JasperReports START -->
        <entry key="aw_doc" value-ref="remoteAwDocExporter"/>
        <entry key="aw_docx" value-ref="remoteAwDocxExporter"/>
        <entry key="aw_html" value-ref="remoteAwHtmlExporter"/>
        <entry key="aw_odt" value-ref="remoteAwOdtExporter"/>
        <entry key="aw_rtf" value-ref="remoteAwRtfExporter"/>
        <entry key="aw_txt" value-ref="remoteAwTxtExporter"/>
        <!-- Aspose.Words for JasperReports END -->
    </util:map>
{{< /highlight >}}

Add entries to the `exportParametersMap`:

**XML**
{{< highlight xml >}}
<util:map id="exportParametersMap">
    ...
    <!-- Aspose.Words for JasperReports START -->
    <entry key="aw_doc" value-ref="aw_exportParameters"/>
    <entry key="aw_docx" value-ref="aw_exportParameters"/>
    <entry key="aw_html" value-ref="aw_exportParameters"/>
    <entry key="aw_odt" value-ref="aw_exportParameters"/>
    <entry key="aw_rtf" value-ref="aw_exportParameters"/>
    <entry key="aw_txt" value-ref="aw_exportParameters"/>
    <!-- Aspose.Words for JasperReports END -->
</util:map>
{{< /highlight >}}

**Note:** Starting from JasperReports Server 8.2 exportParametersMap could be not in applicationContext-web-services.xml you can add this util:map section manually.

**Step 6: Disable Input Validation (JasperServer 4.7.0+)**

Note: this is applied to JasperServer 4.7.0 and higher. Change the following line in the **<InstallDir>\apache-tomcat\webapps\jasperserver\WEB-INF\classes\esapi\security-config.properties** file:

from
security.validation.input.on=true
to
security.validation.input.on=false

**Step 7: Restart JasperServer**

Restart JasperReports Server and open any report to view. If the previous steps were performed properly, you will see the additional formats icons available (for JasperReports Server 3.x and 4.x) or additional choices in the list of export formats (for JasperReports Server 5.x, 6.x, 7.x and 8.x).

For JasperReports Server 3.x and 4.x -

![todo:image_alt_text](installation-1.png)

For JasperReports Server 5.x -

![todo:image_alt_text](installation-2.png)

For JasperReports Server 6.x, 7.x and 8.x -

![todo:image_alt_text](installation-3.png)

If you do not see additional formats (icons or choices), please check log files in **<InstallDir>**\apache-tomcat\logs directory.
