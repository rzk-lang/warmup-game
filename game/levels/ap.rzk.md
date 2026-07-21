---
id: ap
title: A function acts on a path
statement: f x = f y
inventory:
- name: ind-path
  synopsis: 'path induction: reduces a goal about a path to the refl case'
hints:
- text: 'A function respects equality. Induct on `p` with `ind-path`; the base case needs a proof of `f x = f x`.'
- text: 'The motive is `\ w _ → f x = f w` and the base case is `refl`. Assemble these with `ind-path`, inducting on `p`.'
---

A function respects equality. Given a path `p : x = y`, produce a path `f x = f y`. Induct on `p`.

Build it.

```rzk prelude
#lang rzk-1
#def ind-path
  ( A : U) (a : A)
  ( C : (x : A) → (a = x) → U)
  ( d : C a refl)
  ( x : A) (p : a = x)
  : C x p
  := idJ (A , a , C , d , x , p)
```

```rzk template
#def ap (A B : U) (f : A → B) (x y : A) (p : x = y)
  : f x = f y
  := ?
```

```rzk solution
#def ap (A B : U) (f : A → B) (x y : A) (p : x = y)
  : f x = f y
  := ind-path A x (\ w _ → f x = f w) refl y p
```

## Conclusion

`ap`, the action of a function on paths, carries a path in `A` to a path in `B`. Functions send equal inputs to equal outputs.
