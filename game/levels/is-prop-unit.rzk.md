---
id: is-prop-unit
title: Unit is a proposition
statement: is-prop Unit
hints:
- text: 'Introduce the two elements `x` and `y`. You need a proof of `x = y`.'
- text: 'Introduce `x` and `y`; both are definitionally `unit`, so `refl` proves `x = y`.'
---

A **proposition** is a type in which any two elements are equal. `Unit` is the simplest example: it has essentially one element. Show it is a proposition.

Build it.

```rzk prelude
#lang rzk-1
#def is-prop (A : U)
  : U
  := (x y : A) → x = y
```

```rzk template
#def is-prop-Unit
  : is-prop Unit
  := ?
```

```rzk solution
#def is-prop-Unit
  : is-prop Unit
  := \ x y → refl
```

## Conclusion

Every element of `Unit` is definitionally `unit`, so any two are equal by `refl`. `Unit` is a proposition.
