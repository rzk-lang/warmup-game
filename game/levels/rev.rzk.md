---
id: rev
title: Reversing a path
statement: y = x
inventory:
- name: ind-path
  synopsis: 'path induction: reduces a goal about a path to the refl case'
hints:
- text: 'Induct on `p` with `ind-path`. In the base case `y` becomes `x` and `p` becomes `refl`, so you need only a proof of `x = x`.'
- text: 'The motive is `\ w _ → w = x` and the base case is `refl`: write `ind-path A x (\ w _ → w = x) refl y p`.'
---

If `x` equals `y`, then `y` equals `x`: equality is symmetric. Prove it by path induction, handling the case where the path is `refl`.

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
#def rev (A : U) (x y : A) (p : x = y)
  : y = x
  := ?
```

```rzk solution
#def rev (A : U) (x y : A) (p : x = y)
  : y = x
  := ind-path A x (\ w _ → w = x) refl y p
```

## Conclusion

Reversal is symmetry of equality. Path induction reduces it to the one case that is obvious: `refl` reversed is `refl`.
