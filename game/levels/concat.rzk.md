---
id: concat
title: Concatenating paths
statement: x = z
inventory:
- name: ind-path
  synopsis: 'path induction: reduces a goal about a path to the refl case'
hints:
- text: 'Two paths in a row make one from `x` to `z`. Induct on the second path `q`; in the base case `z` becomes `y` and `q` becomes `refl`, so you already hold `p : x = y`.'
- text: 'The motive is `\ w _ → x = w` and the base case is the path `p` you already hold. Assemble these with `ind-path`, inducting on `q`.'
---

Paths compose. Given `p : x = y` and `q : y = z`, build a path `x = z`. Induct on `q`: when it is `refl`, the answer is just `p`.

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
#def concat (A : U) (x y z : A) (p : x = y) (q : y = z)
  : x = z
  := ?
```

```rzk solution
#def concat (A : U) (x y z : A) (p : x = y) (q : y = z)
  : x = z
  := ind-path A y (\ w _ → x = w) p z q
```

## Conclusion

Concatenation is transitivity of equality. Inducting on `q` reduces to the `refl` case, where the composite is `p` itself.
