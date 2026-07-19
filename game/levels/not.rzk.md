---
id: not
title: Negation
statement: Bool → Bool
hints:
- text: '`rec-Bool` takes the result type, then the value for `false`, then the value for `true`.'
- text: 'Negation sends `false` to `true` and `true` to `false`: write `rec-Bool Bool true false`.'
---

Negation swaps `true` and `false`. Build it with the generated `rec-Bool`.

Build it.

```rzk prelude
#lang rzk-1
#data Bool := false | true
```

```rzk template
#def not
  : Bool → Bool
  := ?
```

```rzk solution
#def not
  : Bool → Bool
  := rec-Bool Bool true false
```

## Conclusion

Negation returns the *other* value in each case. Because the computation rules of an inductive type are definitional, `not (not true)` already computes to `true`; proving `not (not b) = b` for every `b` follows by induction, once you have identity types.
