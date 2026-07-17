---
id: modus-ponens
title: Modus ponens
statement: '(p : prod A (A → B)) → B'
hints:
- text: 'Introduce the pair `p`. Its first component proves `A`, its second proves `A → B`.'
- text: 'Apply the implication to the proof of `A`: write `second p (first p)`.'
---

**Modus ponens** is the fundamental rule of logic: from `A` and `A → B`, conclude `B`. Here both premises are packed into one pair `p`. Take them apart and apply.

Build it.

```rzk prelude
#lang rzk-1
#def prod (A B : U)
  : U
  := Σ (a : A) , B
```

```rzk template
#def modus-ponens (A B : U)
  : (p : prod A (A → B)) → B
  := ?
```

```rzk solution
#def modus-ponens (A B : U)
  : (p : prod A (A → B)) → B
  := \ p → second p (first p)
```

## Conclusion

Modus ponens is just application: `second p`, the implication, applied to `first p`, the hypothesis, yields `B`.
