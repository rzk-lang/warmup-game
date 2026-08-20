---
forbidden:
- idJ
inventory:
- name: ind-path
  synopsis: 'path induction: reduces a goal about a path to the refl case'
id: left-unit
title: The left unit law
statement: 'concat A x x y refl p = p'
hints:
- text: 'Induct on `p`. Concatenation was defined by inducting on its *second* path, so `concat p refl` computes but `concat refl p` needs its own induction.'
- text: 'The motive is `\ w r → concat A x x w refl r = r` and, since both sides are `refl` in the base case, the base case is `refl`. Assemble these with `ind-path`, inducting on `p`.'
---

Prepending the trivial path does nothing: `concat refl p = p`. Prove the left unit law by inducting on `p`. (You proved the right unit law earlier, where it held by `refl` alone.)

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
#def concat (A : U) (x y z : A) (p : x = y) (q : y = z)
  : x = z
  := ind-path A y (\ w _ → x = w) p z q
```

```rzk template
#def left-unit (A : U) (x y : A) (p : x = y)
  : concat A x x y refl p = p
  := ?
```

```rzk solution
#def left-unit (A : U) (x y : A) (p : x = y)
  : concat A x x y refl p = p
  := ind-path A x (\ w r → concat A x x w refl r = r) refl y p
```

## Conclusion

Because concatenation recurses on its second path, `concat refl p` does not compute on its own; path induction on `p` reduces it to the trivial case.
