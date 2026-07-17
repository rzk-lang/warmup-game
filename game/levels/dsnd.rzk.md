---
id: dsnd
title: The dependent projection
statement: B (first p)
hints:
- text: 'The same `second` projection works on a Σ-value.'
- text: 'Apply it to `p`: write `second p`. Its type is `B (first p)`.'
---

Projections work on dependent pairs too. Taking the second component of `p` gives a value whose type mentions the first component. That is the whole point of a Σ-type.

Build it.

```rzk prelude
#lang rzk-1
```

```rzk template
#def dsnd (A : U) (B : A → U) (p : Σ (x : A) , B x)
  : B (first p)
  := ?
```

```rzk solution
#def dsnd (A : U) (B : A → U) (p : Σ (x : A) , B x)
  : B (first p)
  := second p
```

## Conclusion

`second p` has type `B (first p)`: the type of the second projection depends on the first. A product is the special case where `B` ignores its argument.
