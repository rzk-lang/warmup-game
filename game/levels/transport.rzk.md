---
id: transport
title: Transport
statement: B y
inventory:
- name: ind-path
  synopsis: 'path induction: reduces a goal about a path to the refl case'
hints:
- text: 'A path `x = y` lets you carry a value from `B x` to `B y`. Induct on `p`; the base case asks for a `B x`, which is exactly `b`.'
- text: 'The motive is `\ w _ → B w` and the base case is `b`: write `ind-path A x (\ w _ → B w) b y p`.'
---

Equal points have interchangeable fibers. Given `p : x = y` and a value `b : B x`, produce a value of `B y`. Induct on `p`.

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
#def transport (A : U) (B : A → U) (x y : A) (p : x = y) (b : B x)
  : B y
  := ?
```

```rzk solution
#def transport (A : U) (B : A → U) (x y : A) (p : x = y) (b : B x)
  : B y
  := ind-path A x (\ w _ → B w) b y p
```

## Conclusion

Transport carries a value along a path between its indices. It is the machinery behind substituting equals for equals.
