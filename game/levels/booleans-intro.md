---
id: booleans-intro
title: Booleans
role: bridge-in
---

The type of **booleans** `Bool` has exactly two values, `false` and `true`. It is the inductive type with two constructors and no fields:

```
#data Bool := false | true
```

To define something for every boolean, `match` on it and give its value on `false` and on `true`.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §1.8.
