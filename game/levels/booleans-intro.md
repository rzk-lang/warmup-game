---
id: booleans-intro
title: Booleans
role: bridge-in
---

The type of **booleans** `Bool` has exactly two values, `false` and `true`. It is the inductive type with two constructors and no fields:

```
#data Bool := false | true
```

This generates `ind-Bool` and `rec-Bool`. To define something for every boolean, give its value on `false` and on `true`.

*By the end of this section you will be able to:* define negation and conjunction on booleans.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §1.8.
