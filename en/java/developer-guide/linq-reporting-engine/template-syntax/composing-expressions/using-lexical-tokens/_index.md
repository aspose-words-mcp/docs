---
title: Using Lexical Tokens in Java
second_title: Aspose.Words for Java
articleTitle: Using Lexical Tokens
linktitle: Using Lexical Tokens
description: "Use lexical tokens in template expressions when building a report in Java."
type: docs
weight: 10
ai_search_scope: words_java
ai_search_endpoint: "https://docsearch.api.aspose.cloud/ask"
ai_search_fast_endpoint: "https://docsearch.api.aspose.cloud/search"
url: /java/using-lexical-tokens/
timestamp: 2024-10-21-11-17-44
---

The following table describes lexical tokens that you can use in template expressions and restrictions on these tokens' usage comparing with C# Language Specification 5.0.

| Token | Restrictions |
| :- | :- |
| **Keyword** | Only the following tokens are reserved as keywords: `true`, `false`, `null`, `new`, and `in`. |
| **Identifier** | - The feature of keyword escaping through the “@” character is not supported.<br>- Unicode character escapes are not permitted in identifiers. |
| **Literal** | - 32-bit Unicode character escapes are not supported.<br>- Unsigned integer and decimal literals are not permitted. |
| **Operator** | See “Using Operators.” |

You can use the following identifiers that are not preceded by a member access operator in template expressions:

- The name of a passed data source object
- The name of an iteration variable within its scope (see “Outputting Sequential Data” for more information)
- The name of a common variable after it is declared (see “Using Variables” for more information)
- The name of a lambda function parameter within the scope of the lambda function
- A fully or partially qualified name of a type that is known by the engine (see “Setting up Known External Types” for more information)
- The name of a member of an object that is determined as follows:
  - Inside a data band body, the object is resolved to the innermost iteration variable.
  - Outside a data band body, the object is resolved to a passed data source.

The feature of the omitting of an object identifier while accessing the object's members is also known as the contextual object member access. See “Using Contextual Object Member Access” for more information.

------ 

## FAQ

1. **Q:** Which words are treated as reserved keywords in template expressions?  
   **A:** Only `true`, `false`, `null`, `new`, and `in` are reserved. All other identifiers can be used freely.

2. **Q:** Can I escape a keyword by prefixing it with `@` like in C#?  
   **A:** No. The `@` escape syntax is not supported in Aspose.Words template expressions, so a keyword cannot be used as an identifier.

3. **Q:** Are Unicode escape sequences allowed in identifiers or literals?  
   **A:** Not in identifiers: Unicode character escapes are not permitted there. In literals, `\uXXXX` escapes work, but 32‑bit Unicode character escapes are not supported.

4. **Q:** May I use unsigned integer or decimal literals (e.g., `123u`, `3.14m`) in expressions?  
   **A:** No. The engine only supports signed integer and double literals. Unsigned or decimal suffixes are rejected.

5. **Q:** How can I refer to a type that the engine knows about?  
   **A:** Use the fully or partially qualified type name (e.g., `java.util.Date` or `Date`). The type must be registered as a known external type in the reporting engine configuration.