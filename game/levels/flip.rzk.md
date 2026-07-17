---
id: flip
title: Swapping arguments
statement: B → A → C
hints:
- text: 'Introduce both arguments: `\ y x → ?`, with `y : B` and `x : A`.'
- text: 'Call `f` with the arguments in its own order: `f x y`.'
---

A two-argument function can take its arguments in either order. Given `f` that wants an `A` and then a `B`, build the version that wants a `B` and then an `A`.

Build it.

```rzk prelude
#lang rzk-1
```

```rzk template
#def flip (A B C : U) (f : A → B → C)
  : B → A → C
  := ?
```

```rzk solution
#def flip (A B C : U) (f : A → B → C)
  : B → A → C
  := \ y x → f x y
```

## Conclusion

Only the binding order changed. Underneath, `f` is still applied to an `A` and then a `B`.
