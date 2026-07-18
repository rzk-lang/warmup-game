---
id: hott-intro
title: A taste of homotopy type theory
role: bridge-in
---

You now have enough to describe the *shape* of a type by how its equalities behave. This is where homotopy type theory begins. Three properties form a hierarchy:

- a type is **contractible** (`is-contr A`) if it has a center `c` together with a proof that every point equals `c`;
- it is a **proposition** (`is-prop A`), or *mere proposition*, if any two of its points are equal;
- it is a **set** (`is-set A`) if any two proofs of one equality are equal.

Each property is stronger than the next: contractible types are propositions, and propositions are sets. The prelude defines them as

```
is-contr A := Σ (c : A) , (x : A) → c = x
is-prop  A := (x y : A) → x = y
is-set   A := (x y : A) → is-prop (x = y)
```

One fact about `Unit` is used below: in Rzk every element of `Unit` is definitionally `unit`, so an equality between elements of `Unit` holds by `refl`.

*By the end of this chapter you will be able to:* show `Unit` is a proposition and contractible, prove that contractible types are propositions, and prove that an inhabited proposition is contractible.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §§3.1, 3.3, and 3.11.
