---
id: contr-is-prop
title: Contractible types are propositions
statement: is-prop A
inventory:
- name: rev
  synopsis: reverses a path, from `x = y` to `y = x`
- name: concat
  synopsis: concatenates two paths, from `x = y` and `y = z` to `x = z`
hints:
- text: 'Introduce `x` and `y`. The contraction `second c` gives, for each point, an equality from the center: `second c x : first c = x`.'
- text: 'Route `x` to `y` through the centre: reverse the centre-to-`x` path `second c x` with `rev`, then `concat` it with the centre-to-`y` path `second c y`.'
---

The first step of the hierarchy: every contractible type is a proposition. Given a center `c` and its contraction, show that any two points `x` and `y` are equal, by routing both through the center.

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
#def is-contr (A : U)
  : U
  := Σ (c : A) , (x : A) → c = x
#def is-prop (A : U)
  : U
  := (x y : A) → x = y
```

```rzk template
#def contr-is-prop (A : U) (c : is-contr A)
  : is-prop A
  := ?
```

```rzk solution
#def contr-is-prop (A : U) (c : is-contr A)
  : is-prop A
  := \ x y → concat A x (first c) y (rev A (first c) x (second c x)) (second c y)
```

## Conclusion

Any two points meet at the center: reverse the path from the center to `x`, then follow the path from the center to `y`. So a contractible type is a proposition.
