---
id: not
title: Negation
statement: Bool → Bool
hints:
- text: '`match b` takes one branch per constructor: a value for `false` and a value for `true`.'
- text: 'The `false` branch gives `true`, the `true` branch gives `false`; put them in `match b (false ⇒ … | true ⇒ …)` under a `\ b →`.'
---

Negation swaps `true` and `false`. Take a boolean apart with `match`.

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
  := \ b → match b
       ( false ⇒ true
       | true ⇒ false)
```

## Conclusion

A `match` on a boolean gives one branch per constructor: the value at `false` and the value at `true`. Negation returns the *other* value in each case. Because the computation rules of an inductive type are definitional, `not (not true)` already computes to `true`; proving `not (not b) = b` for every `b` follows once you have identity types.
