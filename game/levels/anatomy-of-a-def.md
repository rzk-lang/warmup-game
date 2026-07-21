---
id: anatomy-of-a-def
title: Anatomy of a definition
---

Rzk code is a list of **definitions**. Each one is introduced by `#def` and gives a name to something you build. A puzzle asks you to finish one definition by filling its hole.

A definition has four parts:

```
#def  name  (parameters)  : result-type  := body
```

- **`#def name`** starts the definition and gives it a name.
- **parameters** are the inputs, each written `(x : A)`, read "`x` of type `A`", and listed in parentheses. A parameter `(A : U)` introduces a *type*: `U` is the universe, the type whose values are themselves types. A later parameter can then mention it, as in `(x : A)`, "`x` is some value of the type `A`".
- **`: result-type`** is what the definition produces. This is the **goal**.
- **`:= body`** is how it is built. In a puzzle the body starts as a hole, `?`, and finishing the puzzle means replacing that `?`.

Above the part you edit sits a read-only **prelude**: the definitions you are given to work with. Its first line is always `#lang rzk-1`, which selects the language and can be ignored.

The parameters become the **context** the engine shows you, and the result type becomes the **goal**. Time to fill one.
