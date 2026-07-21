---
id: swap
title: Swapping a pair
statement: prod B A
hints:
- text: 'Build a new pair `(? , ?)`, this time with the `B` first.'
- text: 'Build the new pair with `second p` first and `first p` second.'
---

Turn a pair of an `A` and a `B` into a pair of a `B` and an `A`. Project out both components, then put them back in the other order.

Build it.

```rzk prelude
#lang rzk-1
#def prod (A B : U)
  : U
  := Σ (a : A) , B
```

```rzk template
#def swap (A B : U) (p : prod A B)
  : prod B A
  := ?
```

```rzk solution
#def swap (A B : U) (p : prod A B)
  : prod B A
  := (second p , first p)
```

## Conclusion

Swapping is projecting both ways and re-pairing. `second p`, a `B`, leads; `first p`, an `A`, follows.
