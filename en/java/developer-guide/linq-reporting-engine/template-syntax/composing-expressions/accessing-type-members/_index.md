---
title: Accessing Type Members in Java
second_title: Aspose.Words for Java
articleTitle: Accessing Type Members
linktitle: Accessing Type Members
description: "Access public (static and instance) members of accessible types in template expressions when building a report in Java."
type: docs
weight: 30
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/accessing-type-members/
timestamp: 2024-01-27-14-07-04
---

LINQ Reporting Engine enables you to access the following public (static and instance) members of accessible types (see “Working with Types” for more information) in template expressions:

- Fields
- Methods
- Constructors

**Note** – To access a static member of a type in a template expression, the type must be set known for the engine (see “Setting up Known External Types” for more information).

A function type member can be used in a template expression only if the following additional requirements are met:

- The function member returns a value.
- The function member does not take generic type arguments.

The engine supports the following features when dealing with function members:

- Overload resolution according to [C# Language Specification 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=7029)
- Using of parameters taking a variable number of arguments

In addition to C# Language features, the engine provides the following extra features to simplify type member access:

- Accessing members of an object without specifying the object's identifier (see “Using Contextual Object Member Access” for more information)
- Accessing missing members of an object (see “Accessing Missing Members of Data Objects” for more information)

------ 

## FAQ

1. **Q:** How can I access a static field or method of a Java class inside a LINQ Reporting Engine template?  
   **A:** First register the class as a known external type using `engine.getKnownTypes().add(ClassName.class)`. Then you can reference the static member directly in the template, e.g., `<<[ClassName.StaticField]>>` or `<<[ClassName.StaticMethod(arg)]>>`.

2. **Q:** Are instance methods of objects passed to the template callable from the template expression?  
   **A:** Yes. If an object is supplied to the engine as a data source, you can invoke its public instance methods directly, such as `<<[objectInstance.InstanceMethod()]>>`. The method must be public and return a value.

3. **Q:** Can I create a new object inside a template using a constructor?  
   **A:** Constructors are supported as long as they are public, have no generic type arguments, and return a value (the new instance). Use the syntax `<<[new ClassName(arg1, arg2)]>>` after the type has been added to the known types list.

4. **Q:** What restrictions apply to methods used as function members in template expressions?  
   **A:** The method must return a value and cannot have generic type parameters. Overload resolution follows the C# Language Specification 5.0 rules, and methods that accept a variable number of arguments (`params`) are also supported.

5. **Q:** Why does the engine report “type must be known” when I try to use a static member?  
   **A:** The engine only allows static members of types that have been explicitly added to the known external types collection. Add the type with `engine.getKnownTypes().add(YourClass.class)` before processing the template.