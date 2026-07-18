---
id: rec-coprod
title: The recursion principle for coproducts
statement: coprod A B → C
inventory:
- name: ind-coprod
  synopsis: case analysis on a coproduct (its induction principle)
hints:
- text: 'Use `ind-coprod` with a constant motive `\ _ → C`, then the two handlers.'
- text: 'Write `ind-coprod A B (\ _ → C) l r`.'
---

To define a function out of a coproduct, handle each side. Given `l : A → C` and `r : B → C`, derive recursion from `ind-coprod`.

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
#def rec-coprod (A B C : U) (l : A → C) (r : B → C)
  : coprod A B → C
  := ?
```

```rzk solution
#def rec-coprod (A B C : U) (l : A → C) (r : B → C)
  : coprod A B → C
  := ind-coprod A B (\ _ → C) l r
```

## Conclusion

Case analysis: one handler per constructor. Recursion is again induction with a constant motive.
