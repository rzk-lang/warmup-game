---
id: fiber-intro
title: Σ-types with identity
role: bridge-in
---

Pairing a Σ-type with an identity type gives a fundamental construction: the **fiber** (or preimage) of a function. For `f : A → B` and a point `y : B`, the fiber over `y` collects every input that `f` sends to `y`, each paired with a proof:

```
preimage A B f y := Σ (x : A) , (f x = y)
```

A value is a point `x : A` together with a proof that `f x = y`. This is the type-theoretic preimage of `y` under `f`.

*By the end of this section you will be able to:* exhibit a point of a fiber.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §4.2.
