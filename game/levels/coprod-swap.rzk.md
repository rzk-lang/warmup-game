---
id: coprod-swap
title: Swapping a coproduct
statement: coprod A B → coprod B A
hints:
- text: 'Eliminate the input with `rec-coprod`, targeting `coprod B A`, with a handler per side.'
- text: 'Send a left `a` to the right, and a right `b` to the left: write `rec-coprod A B (coprod B A) (\ a → inr B A a) (\ b → inl B A b)`.'
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
  := rec-coprod A B (coprod B A) (\ a → inr B A a) (\ b → inl B A b)
```

## Conclusion

Each case is re-tagged: `inl` becomes `inr` and `inr` becomes `inl`. Case analysis with `rec-coprod`, plus the two injections, is all it takes.
