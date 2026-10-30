---
title: Working with DataTable Row Objects in Java
second_title: Aspose.Words for Java
articleTitle: Working with DataTable Row Objects
linktitle: Working with DataTable Row Objects
description: "Use simplified syntax in template expressions to work with DataTable row objects when building a report in Java."
type: docs
weight: 30
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/working-with-datatable-row-objects/
timestamp: 2024-10-21-11-17-44
---

LINQ Reporting Engine enables you to access a data associated with a particular `DataTable` row instance in template expressions using the “.” operator. The following table describes, which identifiers you can use to access different kinds of the data.

| Data Kind | Identifier | Examples of Template Expressions |
| :- | :- | :- |
| **Field Value** | Field name | Given that `r` is a row that has a field named “Name”, you can access the field's value using the following syntax.<br />{{< highlight csharp >}}r.Name{{< /highlight >}} |
| **Single Parent or Child Row** | Parent (child) table name | Given that r is a row of a `DataTable` that has a parent (child) `DataTable` named “City”, you can access the single parent (child) row of r using the following syntax.<br />{{< highlight csharp >}}r.City{{< /highlight >}}<br />Given that the “City” `DataTable` has a field named “Name”, you can access the field's value for the single parent (child) row using the following syntax.<br />{{< highlight csharp >}}r.City.Name{{< /highlight >}} |
| **Enumeration of Child or Parent Rows** | Child (parent) table name | Given that r is a row of a `DataTable` that has a child (parent) `DataTable` named “Persons”, you can access the enumeration of the child (parent) rows of `r` using the following syntax.<br />{{< highlight csharp >}}r.Persons{{< /highlight >}}<br />Given that the “Persons” `DataTable` has a field named “Age”, you can count the child (parent) rows that correspond to persons over thirty years old using the following syntax.<br />{{< highlight csharp >}}r.Persons.count(p => p.Age > 30){{< /highlight >}} |

**Note** – Field and table names are case‑insensitive.

To determine parent‑child relationships for a particular `DataTable` instance, the engine uses `DataRelation` objects contained within the corresponding `DataSet` instance. Thus, you can manage these relationships in a common way.

**Note** – Instead of using of table names to access data of child or parent rows, you can also use relation names, which is useful when you deal with multiple relations to the same table.

------ 

## FAQ

1. **Q:** How do I read a field value from the current DataTable row in a template?  
   **A:** Use the row identifier followed by a dot and the field name, e.g., `r.Name`. The identifier (`r`) represents the current row object, and the expression returns the value of the *Name* column for that row.

2. **Q:** How can I obtain a related parent row from the current row?  
   **A:** Reference the parent table name as a property of the row, for example `r.City`. This returns the single parent row. You can then chain another field name, such as `r.City.Name`, to read a column from the parent row.

3. **Q:** What is the syntax for iterating over child rows of the current row?  
   **A:** Use the child table name, e.g., `r.Persons`. This yields a collection of child rows that you can apply LINQ methods to, such as `r.Persons.count(p => p.Age > 30)` or `r.Persons.sum(p => p.Salary)`.

4. **Q:** Are table and field identifiers case‑sensitive in template expressions?  
   **A:** No. Identifiers are case‑insensitive, so `r.Name`, `r.name`, or `r.NaMe` all refer to the same column.

5. **Q:** When a DataSet contains multiple relations to the same table, how can I specify which relation to use?  
   **A:** Use the relation name defined in the DataSet instead of the table name, e.g., `r.RelationName`. This disambiguates the relationship when several exist between the same pair of tables.