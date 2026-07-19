---
id: univalence-intro
title: Univalence
role: bridge-in
---

Equal types are equivalent: from a path `A = B` you can build an equivalence, by path induction (at `refl` the equivalence is the identity). You will build this map, `idtoequiv`.

**Univalence** is the axiom that this map is itself an equivalence: equality of types is *the same as* equivalence of types.

```
ua : (A B : U) → Equiv (A = B) (Equiv A B)
```

Univalence is not provable in the theory so far, so it is assumed as a postulate. With it, an equivalence between types yields a genuine equality of types.

*By the end of this section you will be able to:* turn a path into an equivalence, and, using univalence, turn an equivalence into a path.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §2.10.
