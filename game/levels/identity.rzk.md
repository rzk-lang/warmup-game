---
id: identity
title: The identity function
statement: A → A
hints:
- text: 'The goal is a function type. Introduce its argument: tap `λ-intro` or type `\ x → ?`.'
- text: 'Now the goal is `A`, with `x : A` in the context. Return `x`.'
---

Every type has an identity function: the one that returns its argument unchanged. Introduce the argument, then hand it straight back.

Build it.

```rzk prelude
#lang rzk-1
```

```rzk template
#def identity (A : U)
  : A → A
  := ?
```

```rzk solution
#def identity (A : U)
  : A → A
  := \ x → x
```

## Conclusion

`λ-intro` turns a goal `A → A` into a goal `A` with the argument in scope. From there the argument itself is the answer.
