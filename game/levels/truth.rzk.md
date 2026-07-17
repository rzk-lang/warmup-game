---
id: truth
title: Truth
statement: A → Unit
hints:
- text: 'Introduce the argument, then ignore it: the goal `Unit` has just one proof.'
- text: 'That proof is `unit`. Write `\ _ → unit`.'
---

Truth, written `⊤`, is the proposition that always holds. In Rzk it is `Unit`, and its single proof is `unit`. Show that truth follows from anything: given any `A`, produce a proof of `Unit`.

Build it.

```rzk prelude
#lang rzk-1
```

```rzk template
#def truth (A : U)
  : A → Unit
  := ?
```

```rzk solution
#def truth (A : U)
  : A → Unit
  := \ _ → unit
```

## Conclusion

`Unit` is truth: always inhabited by `unit`, whatever else is in play. A proof of `A → ⊤` simply discards its input.
