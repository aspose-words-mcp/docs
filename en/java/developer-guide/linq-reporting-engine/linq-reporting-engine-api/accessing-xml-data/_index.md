---
title: Accessing XML Data in Java
second_title: Aspose.Words for Java
articleTitle: Accessing XML Data
linktitle: Accessing XML Data
description: "Learn how to access XML data while building a report using LINQ in Java."
type: docs
weight: 20
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/accessing-xml-data/
timestamp: 2024-01-27-14-07-04
---

To access XML data while building a report, you can use facilities of `DataSet` to read XML into it and then pass it to the engine as a data source. However, if your scenario does not permit to specify XML schema while loading XML into `DataSet`, all attributes and text values of XML elements are loaded as strings then. Thus, it becomes impossible, for example, to use arithmetic operations on numbers or to specify custom date-time and numeric formats to output corresponding values, because all of them are treated as strings.

To overcome this limitation, you can pass an `XmlDataSource` instance to the engine as a data source instead. Even when XML schema is not provided, `XmlDataSource` is capable to recognize values of the following types by their string representations:

- Long
- Double
- Boolean
- Date

**Note** – For recognition of data types to work, string representations of corresponding attributes and text values of XML elements must be formed using invariant culture settings.

While loading data to `XmlDataSource`, the engine performs actions typical for XML deserialization behind the scenes: It maps complex-type XML elements to internal objects and simple-type XML elements to fields of containing objects. So, in template documents, an `XmlDataSource` instance should be treated as an object having corresponding fields and nested objects as shown in the following example.

XML

{{< highlight xml >}}
<Person>
	<Name>John Doe</Name>
	<Age>30</Age>
	<Birth>1989-04-01 4:00:00 pm</Birth>
	<Child>Ann Doe</Child>
	<Child>Charles Doe</Child>
</Person>
{{< /highlight >}}

Template document

{{< highlight xml >}}
Name: <<[Name]>>, Age: <<[Age]>>, Date of Birth: <<[Birth]:"dd.MM.yyyy">>
Children:
<<foreach [in Child]>><<[Child_Text]>>
<</foreach>>
{{< /highlight >}}

Source code

{{< highlight java >}}
Document doc = ...;             // Loading a template document.
XmlDataSource dataSource = ...; // Loading XML.

ReportingEngine engine = new ReportingEngine();
engine.buildReport(doc, dataSource);
{{< /highlight >}}

Result document

{{< highlight text >}}
Name: John Doe, Age: 30, Date of Birth: 01.04.1989
Children:
Ann Doe
Charles Doe
{{< /highlight >}}

**Note** – To reference a sequence of repeated simple-type XML elements with the same name, the elements' name itself (for example, “Child”) should be used in a template document, whereas the same name with the “_Text” suffix (for example, “Child_Text”) should be used to reference the text value of one of these elements.

By default, if a root XML element contains only a sequence of elements of one type, the engine does not generate an internal root object while loading XML data. So, in template documents, such an `XmlDataSource` instance should be treated as a sequence of corresponding nested objects as shown in the following example.

XML

{{< highlight xml >}}
<Persons>
	<Person>
		<Name>John Doe</Name>
		<Age>30</Age>
		<Birth>1989-04-01 4:00:00 pm</Birth>
	</Person>
	<Person>
		<Name>Jane Doe</Name>
		<Age>27</Age>
		<Birth>1992-01-31 07:00:00 am</Birth>
	</Person>
	<Person>
		<Name>John Smith</Name>
		<Age>51</Age>
		<Birth>1968-03-08 1:00:00 pm</Birth>
	</Person>
</Persons>
{{< /highlight >}}

Template document

{{< highlight xml >}}
<<foreach [in persons]>>Name: <<[Name]>>, Age: <<[Age]>>, Date of Birth: <<[Birth]:"dd.MM.yyyy">>
<</foreach>>

Average age: <<[persons.average(p => p.Age)]>>
{{< /highlight >}}

Source code

{{< highlight java >}}
Document doc = ...             // Loading a template document.
XmlDataSource dataSource = ... // Loading XML (without schema).

ReportingEngine engine = new ReportingEngine();
engine.buildReport(doc, dataSource, "persons");
{{< /highlight >}}

Result document

{{< highlight text >}}
Name: John Doe, Age: 30, Date of Birth: 01.04.1989
Name: Jane Doe, Age: 27, Date of Birth: 31.01.1992
Name: John Smith, Age: 51, Date of Birth: 08.03.1968

Average age: 36
{{< /highlight >}}

However, if your scenario requires an internal object for a root XML element to be always generated while loading data to `XmlDataSource`, you can force this as shown in the following code snippet.

{{< highlight csharp >}}
XmlDataLoadOptions options = new XmlDataLoadOptions();
options.setAlwaysGenerateRootObject(true);
XmlDataSource dataSource = new XmlDataSource(..., options);
{{< /highlight >}}

The following example sums up typical scenarios involving nested complex-type XML elements.

XML
{{< highlight csharp >}}
<Managers>
	<Manager>
		<Name>John Smith</Name>
		<Contract>
			<Client>
				<Name>A Company</Name>
			</Client>
			<Price>1200000</Price>
		</Contract>
		<Contract>
			<Client>
				<Name>B Ltd.</Name>
			</Client>
			<Price>750000</Price>
		</Contract>
		<Contract>
			<Client>
				<Name>C &amp; D</Name>
			</Client>
			<Price>350000</Price>
		</Contract>
	</Manager>
	<Manager>
		<Name>Tony Anderson</Name>
		<Contract>
			<Client>
				<Name>E Corp.</Name>
			</Client>
			<Price>650000</Price>
		</Contract>
		<Contract>
			<Client>
				<Name>F &amp; Partners</Name>
			</Client>
			<Price>550000</Price>
		</Contract>
	</Manager>
	<Manager>
		<Name>July James</Name>
		<Contract>
			<Client>
				<Name>G &amp; Co.</Name>
			</Client>
			<Price>350000</Price>
		</Contract>
		<Contract>
			<Client>
				<Name>H Group</Name>
			</Client>
			<Price>250000</Price>
		</Contract>
		<Contract>
			<Client>
				<Name>I &amp; Sons</Name>
			</Client>
			<Price>100000</Price>
		</Contract>
		<Contract>
			<Client>
				<Name>J Ent.</Name>
			</Client>
			<Price>100000</Price>
		</Contract>
	</Manager>
</Managers>
{{< /highlight >}}

Template document

{{< highlight xml >}}
<<foreach [in managers]>>Manager: <<[Name]>>
Contracts:
<<foreach [in Contract]>>- <<[Client.Name]>> ($<<[Price]>>)
<</foreach>>
<</foreach>>
{{< /highlight >}}

Source code

{{< highlight java >}}
Document doc = ...             // Loading a template document.
XmlDataSource dataSource = ... // Loading XML.

ReportingEngine engine = new ReportingEngine();
engine.buildReport(doc, dataSource, "managers");
{{< /highlight >}}

Result document

{{< highlight text >}}
Manager: John Smith
Contracts:
– A Company ($1200000)
– B Ltd. ($750000)
– C & D ($350000)

Manager: Tony Anderson
Contracts:
– E Corp. ($650000)
– F & Partners ($550000)

Manager: July James
Contracts:
– G & Co. ($350000)
– H Group ($250000)
– I & Sons ($100000)
– J Ent. ($100000)
{{< /highlight >}}

------ 

## FAQ

1. **Q:** How does `XmlDataSource` determine the data type of an XML element?  
   **A:** When loading XML, `XmlDataSource` examines the string representation of each element or attribute. If the text matches the invariant‑culture format of a long, double, boolean, or date, the engine converts it to the corresponding Java type (`Long`, `Double`, `Boolean`, or `Date`). This enables arithmetic operations and formatting in templates.

2. **Q:** How can I format dates or numbers in a template that uses `XmlDataSource`?  
   **A:** Use the format specifier after the field name inside the tag. For example, `<<[Birth]:"dd.MM.yyyy">>` formats a date, and `<<[Price]:"#,##0">>` formats a numeric value with thousand separators. Format strings are the same as for Java's `DecimalFormat` and `SimpleDateFormat`.

3. **Q:** What is the purpose of the `_Text` suffix when referencing repeated simple‑type elements?  
   **A:** For a repeated simple element such as `<Child>`, use the element name to iterate over the elements, e.g., `<<foreach [in Child]>>`, and the `_Text` suffix to output the text value of the current element: `<<[Child_Text]>>`.

4. **Q:** How do I force the engine to always generate a root object for the XML data?  
   **A:** Create an `XmlDataLoadOptions` instance, set `getAlwaysGenerateRootObject()` to `true`, and pass the options when constructing the `XmlDataSource`:

   ```java
   XmlDataLoadOptions options = new XmlDataLoadOptions();
   options.setAlwaysGenerateRootObject(true);
   XmlDataSource dataSource = new XmlDataSource(xmlFilePath, options);
   ```

5. **Q:** Can I specify a custom root object name when building the report?  
   **A:** Yes. Pass the desired root name as the third argument to `engine.buildReport`. For example:

   ```java
   engine.buildReport(doc, dataSource, "employees");
   ```

   In the template you would then use `<<foreach [in employees]>>` to iterate over the collection.