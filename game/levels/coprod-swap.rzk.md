---
id: coprod-swap
title: Swapping a coproduct
statement: coprod A B → coprod B A
hints:
- text: 'Take the input apart with `match`: one branch per constructor, `inl a ⇒ …` and `inr b ⇒ …`, each landing in `coprod B A`.'
- text: 'Send `inl a` to the right with `inr B A`, and `inr b` to the left with `inl B A`. Fill these into `match w (…)` under a `\ w →`.'
---

A disjoint union does not care about the order of its two sides. Turn a `coprod A B` into a `coprod B A` by swapping the tags.

Build it.

```rzk prelude
#lang rzk-1
#data coprod (A B : U)
  := inl (a : A)
  |  inr (b : B)
```

```rzk template
#def coprod-swap (A B : U)
  : coprod A B → coprod B A
  := ?
```

```rzk solution
#def coprod-swap (A B : U)
  : coprod A B → coprod B A
  := \ w → match w
       ( inl a ⇒ inr B A a
       | inr b ⇒ inl B A b)
```

## Conclusion

Each case is re-tagged: `inl` becomes `inr` and `inr` becomes `inl`. Case analysis with `match`, plus the two injections, is all it takes. A `match` gives one branch per constructor and binds that constructor's fields — here the value `a` under `inl`, and `b` under `inr`.
