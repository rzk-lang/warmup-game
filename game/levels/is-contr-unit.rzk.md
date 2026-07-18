---
id: is-contr-unit
title: Unit is contractible
statement: is-contr Unit
hints:
- text: 'A value of `is-contr Unit` is a pair `(center , proof)`: the center point, and a proof that every element equals it.'
- text: 'The center is `unit`, and every element equals it by `refl`: write `(unit , \ x → refl)`.'
---

A **contractible** type has a center point to which everything is equal. Show `Unit` is contractible: give the center, and the proof that every element equals it.

Build it.

```rzk prelude
#lang rzk-1
#def is-contr (A : U)
  : U
  := Σ (c : A) , (x : A) → c = x
```

```rzk template
#def is-contr-Unit
  : is-contr Unit
  := ?
```

```rzk solution
#def is-contr-Unit
  : is-contr Unit
  := (unit , \ x → refl)
```

## Conclusion

`unit` is the center, and every element equals it by `refl`. `Unit` is contractible, the strongest of the three properties.
