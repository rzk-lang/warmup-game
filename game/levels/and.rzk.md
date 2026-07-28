---
id: and
title: Conjunction
statement: Bool
checks:
- and true true = true
- and true false = false
- and false true = false
- and false false = false
hints:
- text: 'Case-analyse the first argument `a` with `match`. If `a` is `false`, the answer is `false`; if `a` is `true`, the answer is `b`.'
- text: 'Assemble the two cases as a single `match a (false ⇒ … | true ⇒ …)`, filling each branch from the first hint.'
---

Conjunction: `and a b` is `true` exactly when both are. Case-analyse the first argument.

Build it.

```rzk prelude
#lang rzk-1
#data Bool := false | true
```

```rzk template
#def and (a b : Bool)
  : Bool
  := ?
```

```rzk solution
#def and (a b : Bool)
  : Bool
  := match a
       ( false ⇒ false
       | true ⇒ b)
```

## Conclusion

Splitting on `a` with `match`: a `false` short-circuits to `false`, a `true` defers to `b`. The same pattern defines every boolean operation.
