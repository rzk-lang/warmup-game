---
id: ex-falso
title: From falsity, anything
statement: Void → A
hints:
- text: 'The generated `rec-Void` eliminates the empty type into any type.'
- text: 'Apply `rec-Void` at the target type `A`.'
---

The empty type `Void` has no values, so from one you may conclude anything. The `#data Void` declaration generated `rec-Void` for exactly this. Use it.

Build it.

```rzk prelude
#lang rzk-1
#data Void
```

```rzk template
#def ex-falso (A : U)
  : Void → A
  := ?
```

```rzk solution
#def ex-falso (A : U)
  : Void → A
  := rec-Void A
```

## Conclusion

`rec-Void` is *ex falso quodlibet*: with no cases to handle, it produces a value of any type from an impossible input.
