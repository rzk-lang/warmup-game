---
id: right-unit
title: Paths can compute
statement: 'concat A x y y p refl = p'
hints:
- text: 'What is `concat A x y y p refl`? Concatenation was defined by inducting on its second path, and here that path is already `refl`.'
- text: 'So `concat A x y y p refl` reduces to `p` on the nose. The two sides are literally the same, so the proof is `refl`.'
---

Some equations between paths hold *definitionally*, with no work at all. Because `concat` was defined by inducting on its second argument, feeding `refl` there makes it compute. Show that `concat A x y y p refl` equals `p`.

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
#def right-unit (A : U) (x y : A) (p : x = y)
  : concat A x y y p refl = p
  := ?
```

```rzk solution
#def right-unit (A : U) (x y : A) (p : x = y)
  : concat A x y y p refl = p
  := refl
```

## Conclusion

`concat A x y y p refl` and `p` are definitionally equal, so `refl` proves it. The mirror law `concat A x x y refl p = p` does not compute this way; it needs its own path induction.
