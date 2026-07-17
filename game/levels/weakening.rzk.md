---
id: weakening
title: Weakening
statement: '(a : A) → (b : B) → A'
hints:
- text: 'Introduce both arguments `a` and `b`. The goal becomes `A`.'
- text: 'Return the proof you already have, ignoring `b`: write `\ a b → a`.'
---

If `A` holds, it still holds no matter what else you assume. Given a proof of `A`, produce, for any `B`, a proof of `B → A`.

Build it.

```rzk prelude
#lang rzk-1
```

```rzk template
#def weakening (A B : U)
  : (a : A) → (b : B) → A
  := ?
```

```rzk solution
#def weakening (A B : U)
  : (a : A) → (b : B) → A
  := \ a b → a
```

## Conclusion

This is weakening: an extra assumption never hurts. As a term it is exactly the constant function.
