---
id: and
title: Conjunction
statement: Bool
hints:
- text: 'Case-analyse the first argument `a` with `rec-Bool`. If `a` is `false`, the answer is `false`; if `a` is `true`, the answer is `b`.'
- text: 'The false-case is `false`, the true-case is `b`: write `rec-Bool Bool false b a`.'
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
  := rec-Bool Bool false b a
```

## Conclusion

Splitting on `a`: a `false` short-circuits to `false`, a `true` defers to `b`. The same pattern defines every boolean operation.
