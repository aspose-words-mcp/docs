---
title: Accessing Type Members in C#
second_title: Aspose.Words for .NET
articleTitle: Accessing Type Members
linktitle: Accessing Type Members
description: "Access public (static and instance) members of accessible types in template expressions when building a report in C#."
type: docs
weight: 30
ai_search_scope: words_net
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /net/accessing-type-members-linq/
timestamp: 2024-02-16-10-54-23
---

{{% alert color="grey" %}}

## Purpose Summary

This page explains how to access type members via LINQ when using Aspose.Words's reporting engine.

{{% /alert %}}

LINQ Reporting Engine enables you to access the following public (static and instance) members of accessible types (see “Working with Types” for more information) in template expressions:

- Fields
- Properties
- Indexer getters
- Methods
- Constructors

**Note** – To access a static member of a type in a template expression, the type must be set known for the engine (see “Setting up Known External Types” for more information).

A function type member can be used in a template expression only if the following additional requirements are met:

- The function member returns a value.
- The function member does not have `ref` or `out` parameters.
- The function member does not take generic type arguments.

The engine supports the following features when dealing with function members:

- Overload resolution according to [C# Language Specification 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=7029)
- Using of default parameter values without support of named parameters
- Using of parameters taking a variable number of arguments

In addition to C# Language features, the engine provides the following extra features to simplify type member access:

- Accessing members of an object without specifying the object's identifier (see “Using Contextual Object Member Access” for more information)
- Accessing missing members of an object (see “Accessing Missing Members of Data Objects” for more information)

------

## FAQ

1. **Q:** How can I call a static method of a type in a template expression?  
   **A:** First register the type as a known external type with the reporting engine, e.g., `engine.KnownTypes.Add(typeof(Math));`. Then you can reference the static member directly in the template, such as `<<[Math.Sqrt(9)]>>`. Static members are accessed with the usual `TypeName.Member` syntax.

2. **Q:** Do I need to specify the object name when accessing its instance properties?  
   **A:** No. The engine supports contextual object member access, allowing you to write just the property name (e.g., `Name`) when the current data object is the context. This simplifies templates and makes them more readable.

3. **Q:** What restrictions apply to methods used as function members in template expressions?  
   **A:** The method must return a value, cannot have `ref` or `out` parameters, and cannot be generic. Overload resolution follows the C# specification, default parameter values are supported, but named parameters are not.

4. **Q:** How can I safely access a member that might not exist on the data object?  
   **A:** Enable the engine's missing‑member handling feature. When a member is not found, the engine returns `null` instead of throwing an exception, allowing you to write expressions like `Customer?.PhoneNumber` without errors.

5. **Q:** Is it possible to instantiate a type using its constructor in a template expression?  
   **A:** Yes. Constructors can be invoked as function members provided they meet the same rules (return value, no `ref`/`out`, no generics). Example: `new DateTime(2023, 1, 1)` creates a `DateTime` object that can be used directly in the expression.