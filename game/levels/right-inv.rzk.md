---
forbidden:
- idJ
inventory:
- name: ind-path
  synopsis: 'path induction: reduces a goal about a path to the refl case'
id: right-inv
title: A path undoes its reversal
statement: 'concat A x y x p (rev A x y p) = refl'
hints:
- text: 'Induct on `p`. In the base case `p` is `refl`, `rev refl` is `refl`, and `concat refl refl` computes to `refl`.'
- text: 'The motive is `\ w r → concat A x w x r (rev A x w r) = refl` and the base case is `refl`. Assemble these with `ind-path`, inducting on `p`.'
---

A path followed by its reversal returns to the start: `concat p (rev p) = refl`. Prove it by inducting on `p`.

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
#def right-inv (A : U) (x y : A) (p : x = y)
  : concat A x y x p (rev A x y p) = refl
  := ?
```

```rzk solution
#def right-inv (A : U) (x y : A) (p : x = y)
  : concat A x y x p (rev A x y p) = refl
  := ind-path A x (\ w r → concat A x w x r (rev A x w r) = refl) refl y p
```

## Conclusion

Going out along `p` and back along `rev p` is trivial, and path induction reduces it to the `refl` case.
