---
id: is-set-void
title: The empty type is a set
statement: is-set Void
hints:
- text: 'Among the arguments you are handed `x : Void`. From it, conclude anything.'
- text: 'After introducing all four arguments, eliminate the `Void` element `x` with `rec-Void` at the goal `p = q`.'
---

The empty type is a set for a trivial reason: it has no elements to compare, so any two proofs of any equality in it are equal, by ex falso. Prove it.

Build it.

```rzk prelude
#lang rzk-1
#data Void
#def is-prop (A : U)
  : U
  := (x y : A) → x = y
#def is-set (A : U)
  : U
  := (x y : A) → is-prop (x = y)
```

```rzk template
#def is-set-Void
  : is-set Void
  := ?
```

```rzk solution
#def is-set-Void
  : is-set Void
  := \ x y p q → rec-Void (p = q) x
```

## Conclusion

With no elements to compare, `Void` is a set for free: the very first argument is an impossible `x : Void`, and `rec-Void` closes the goal.
