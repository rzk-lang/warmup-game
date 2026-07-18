---
id: s-axiom
title: The S axiom
statement: '(f : A → B → C) → (g : A → B) → (a : A) → C'
hints:
- text: 'Introduce `f`, `g`, and `a`. The goal becomes `C`.'
- text: 'Feed `a` to both `f` and `g`, then combine: write `f a (g a)`.'
---

One of the two axioms of intuitionistic implication (weakening was the other). You built this already as the `S` combinator; here it is again, read as a logical law: if `A` implies `B → C`, and `A` implies `B`, then `A` implies `C`.

Build it.

```rzk prelude
#lang rzk-1
```

```rzk template
#def s-axiom (A B C : U)
  : (f : A → B → C) → (g : A → B) → (a : A) → C
  := ?
```

```rzk solution
#def s-axiom (A B C : U)
  : (f : A → B → C) → (g : A → B) → (a : A) → C
  := \ f g a → f a (g a)
```

## Conclusion

Weakening and this S law together prove every tautology of pure implication. Curry–Howard turns each such proof into a program.
