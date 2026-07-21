---
id: apply
title: Dependent functions
statement: B a
hints:
- text: 'The goal `B a` is closed by a single application.'
- text: 'The goal `B a` is `f` applied to `a`.'
---

So far every function returned a fixed type. A dependent function is more general: its result type may depend on the input, as in `f : (x : A) → B x`. Given such an `f` and an input `a`, produce the output. Application is all you need.

Build it.

```rzk prelude
#lang rzk-1
```

```rzk template
#def apply (A : U) (B : A → U) (f : (x : A) → B x) (a : A)
  : B a
  := ?
```

```rzk solution
#def apply (A : U) (B : A → U) (f : (x : A) → B x) (a : A)
  : B a
  := f a
```

## Conclusion

Applying `f : (x : A) → B x` to `a` specializes the result type to `B a`. Ordinary function types `A → B` are the special case where `B` does not depend on the input.
