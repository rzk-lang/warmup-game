---
id: dpair
title: A dependent pair
statement: 'Σ (x : A) , B x'
hints:
- text: 'A Σ-value is still a pair `(? , ?)`.'
- text: 'Pair `a` with `b`; the second component has type `B a`.'
---

In a **Σ-type** the type of the second component depends on the first. Here `b` has type `B a`, which mentions the chosen `a`. Even so, the value is built exactly like an ordinary pair.

Build it.

```rzk prelude
#lang rzk-1
```

```rzk template
#def dpair (A : U) (B : A → U) (a : A) (b : B a)
  : Σ (x : A) , B x
  := ?
```

```rzk solution
#def dpair (A : U) (B : A → U) (a : A) (b : B a)
  : Σ (x : A) , B x
  := (a , b)
```

## Conclusion

A dependent pair is built with `( _ , _ )` just like a product. The only new thing is that the second type may look at the first value.
