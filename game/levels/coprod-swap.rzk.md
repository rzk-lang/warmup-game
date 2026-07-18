---
id: coprod-swap
title: Swapping a coproduct
statement: coprod A B → coprod B A
inventory:
- name: ind-coprod
  synopsis: case analysis on a coproduct
- name: inl
  synopsis: the left injection
- name: inr
  synopsis: the right injection
- name: coprod
  synopsis: the coproduct type former
hints:
- text: 'Analyse the input with `ind-coprod`, targeting `coprod B A`.'
- text: 'Send a left `a` to the right and a right `b` to the left: `ind-coprod A B (\ _ → coprod B A) (\ a → inr B A a) (\ b → inl B A b)`.'
---

A disjoint union does not care about the order of its two sides. Turn a `coprod A B` into a `coprod B A` by swapping the tags.

Build it.

```rzk prelude
#lang rzk-1
#postulate coprod (A B : U) : U
#postulate inl (A B : U) : A → coprod A B
#postulate inr (A B : U) : B → coprod A B
#postulate ind-coprod
  ( A B : U)
  ( C : coprod A B → U)
  ( l : (a : A) → C (inl A B a))
  ( r : (b : B) → C (inr A B b))
  : (z : coprod A B) → C z
```

```rzk template
#def coprod-swap (A B : U)
  : coprod A B → coprod B A
  := ?
```

```rzk solution
#def coprod-swap (A B : U)
  : coprod A B → coprod B A
  := ind-coprod A B (\ _ → coprod B A) (\ a → inr B A a) (\ b → inl B A b)
```

## Conclusion

Each case is re-tagged: `inl` becomes `inr` and `inr` becomes `inl`. Case analysis plus the two injections is all it takes.
