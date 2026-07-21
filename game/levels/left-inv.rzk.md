---
id: left-inv
title: A reversal undoes its path
statement: 'concat A y x y (rev A x y p) p = refl'
hints:
- text: 'Induct on `p`. The base case is `refl`.'
- text: 'The motive is `\ w r → concat A w x w (rev A x w r) r = refl` and the base case is `refl`. Assemble these with `ind-path`, inducting on `p`.'
---

The other way round is trivial too: `concat (rev p) p = refl`. Together with the previous level, this makes reversal a genuine inverse for concatenation. Prove it by inducting on `p`.

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
#def rev (A : U) (x y : A) (p : x = y)
  : y = x
  := ind-path A x (\ w _ → w = x) refl y p
#def concat (A : U) (x y z : A) (p : x = y) (q : y = z)
  : x = z
  := ind-path A y (\ w _ → x = w) p z q
```

```rzk template
#def left-inv (A : U) (x y : A) (p : x = y)
  : concat A y x y (rev A x y p) p = refl
  := ?
```

```rzk solution
#def left-inv (A : U) (x y : A) (p : x = y)
  : concat A y x y (rev A x y p) p = refl
  := ind-path A x (\ w r → concat A w x w (rev A x w r) r = refl) refl y p
```

## Conclusion

Both `p · rev p` and `rev p · p` reduce to `refl`: every path has a two-sided inverse. These are the unit and inverse laws that make paths into a groupoid.
