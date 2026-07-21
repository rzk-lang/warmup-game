---
id: pair
title: Building a pair
statement: prod A B
hints:
- text: 'A pair is written `(? , ?)`. Tap the introduction move, or type the two components yourself.'
- text: 'Pair `a` with `b`, in that order.'
---

The product `prod A B` holds an `A` together with a `B`. You are given one of each. Put them together.

Build it.

```rzk prelude
#lang rzk-1
#def prod (A B : U)
  : U
  := Σ (a : A) , B
```

```rzk template
#def pair (A B : U) (a : A) (b : B)
  : prod A B
  := ?
```

```rzk solution
#def pair (A B : U) (a : A) (b : B)
  : prod A B
  := (a , b)
```

## Conclusion

A pair is built from its two components with `( _ , _ )`. Nothing more is needed.
