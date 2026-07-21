---
id: refl
title: Reflexivity
statement: x = x
hints:
- text: 'Every point equals itself, and the proof is a single constructor.'
- text: 'The proof is reflexivity, the one constructor of the identity type.'
---

The identity type `x = x` is the type of proofs that `x` equals itself. It has one constructor. Use it.

Build it.

```rzk prelude
#lang rzk-1
```

```rzk template
#def refl-at (A : U) (x : A)
  : x = x
  := ?
```

```rzk solution
#def refl-at (A : U) (x : A)
  : x = x
  := refl
```

## Conclusion

`refl` is the proof that anything equals itself. Every path is built, in the end, from `refl`.
