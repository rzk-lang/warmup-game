---
id: concat-assoc
title: Concatenation is associative
statement: 'concat A x z w (concat A x y z p q) r = concat A x y w p (concat A y z w q r)'
hints:
- text: 'Induct on the last path `r`. In the base case `r` is `refl`, and both sides compute to `concat A x y z p q`.'
- text: 'The motive repeats the goal with the endpoint `e` and path `s` varying — `\ e s → concat A x z e (concat A x y z p q) s = concat A x y e p (concat A y z e q s)` — and the base case is `refl`. Assemble these with `ind-path`, inducting on `r`.'
---

Three paths in a row compose to one, and it does not matter how you group them. Prove that concatenation is associative, by inducting on the last path.

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
#def concat-assoc (A : U) (x y z w : A) (p : x = y) (q : y = z) (r : z = w)
  : concat A x z w (concat A x y z p q) r = concat A x y w p (concat A y z w q r)
  := ?
```

```rzk solution
#def concat-assoc (A : U) (x y z w : A) (p : x = y) (q : y = z) (r : z = w)
  : concat A x z w (concat A x y z p q) r = concat A x y w p (concat A y z w q r)
  := ind-path A z (\ e s → concat A x z e (concat A x y z p q) s = concat A x y e p (concat A y z e q s)) refl w r
```

## Conclusion

Inducting on `r` reduces to `r = refl`, where both groupings compute to `concat A x y z p q`. Associativity holds up to a path, and here that path is `refl`.
