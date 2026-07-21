---
id: transport
title: Transport
statement: B y
inventory:
- name: ind-path
  synopsis: 'path induction: reduces a goal about a path to the refl case'
hints:
- text: 'A path `x = y` lets you carry a value from `B x` to `B y`. Induct on `p`; the base case asks for a `B x`, which is exactly `b`.'
- text: 'The motive is `\ w _ → B w` and the base case is `b`. Assemble these with `ind-path`, inducting on `p`.'
---

A **type family** `B : A → U` assigns a type `B x` to each point `x` of `A`. When `x = y`, a value of `B x` can be carried over to a value of `B y`. Given `p : x = y` and `b : B x`, do the carrying. Induct on `p`.

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

Transport moves a value along a path, from the type `B x` at one end to `B y` at the other. It is how you substitute equals for equals.
