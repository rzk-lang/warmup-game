---
id: fst
title: Taking a pair apart
statement: A
hints:
- text: 'The `first` projection reads off the first component of a pair.'
- text: 'Apply it to `p`: write `first p`.'
---

A pair can be taken apart. The `first` projection reads off the first component, and `second` reads off the second. Use one of them to recover the `A` inside `p`.

Build it.

```rzk prelude
#lang rzk-1
#def prod (A B : U)
  : U
  := Σ (a : A) , B
```

```rzk template
#def fst (A B : U) (p : prod A B)
  : A
  := ?
```

```rzk solution
#def fst (A B : U) (p : prod A B)
  : A
  := first p
```

## Conclusion

`first` and `second` are the two projections out of a pair. Here `first p` recovers the `A`; `second p` would give the `B`.
