---
id: homotopy-refl
title: The reflexive homotopy
statement: homotopy A B f f
hints:
- text: 'A homotopy is a function of `x` returning a proof that `f x = f x`.'
- text: 'Introduce `x`; the required proof `f x = f x` is `refl`.'
---

Every function is homotopic to itself. Build the reflexive homotopy: at each point, the value equals itself.

Build it.

```rzk prelude
#lang rzk-1
#def homotopy (A B : U) (f g : A → B)
  : U
  := (x : A) → f x = g x
```

```rzk template
#def homotopy-refl (A B : U) (f : A → B)
  : homotopy A B f f
  := ?
```

```rzk solution
#def homotopy-refl (A B : U) (f : A → B)
  : homotopy A B f f
  := \ x → refl
```

## Conclusion

The reflexive homotopy sends every point to `refl`. Homotopy is a reflexive relation on functions.
