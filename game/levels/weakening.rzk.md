---
id: weakening
title: Weakening
statement: 'A → B → A'
hints:
- text: 'Introduce the two arguments; call them `a` and `b`. The goal becomes `A`.'
- text: 'After introducing both arguments, return the first and ignore the second.'
---

If `A` holds, it still holds no matter what else you assume. Given a proof of `A`, produce, for any `B`, a proof of `B → A`.

Build it.

```rzk prelude
#lang rzk-1
```

```rzk template
#def weakening (A B : U)
  : A → B → A
  := ?
```

```rzk solution
#def weakening (A B : U)
  : A → B → A
  := \ a b → a
```

## Conclusion

This is weakening: an extra assumption never hurts. As a term it is exactly the constant function.
