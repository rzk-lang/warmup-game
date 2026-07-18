---
id: inhabited-prop-is-contr
title: An inhabited proposition is contractible
statement: is-contr A
hints:
- text: 'A value of `is-contr A` is a pair of a center and a proof that every point equals it.'
- text: 'Take `a` as the center; the proposition `f` supplies every equality. Write `(a , \ x → f a x)`.'
---

The near-converse of the previous level. A proposition that has at least one point is contractible. Given a proof `f` that `A` is a proposition and a point `a`, build a contraction centered at `a`.

Build it.

```rzk prelude
#lang rzk-1
#def is-prop (A : U)
  : U
  := (x y : A) → x = y
#def is-contr (A : U)
  : U
  := Σ (c : A) , (x : A) → c = x
```

```rzk template
#def inhabited-prop-is-contr (A : U) (f : is-prop A) (a : A)
  : is-contr A
  := ?
```

```rzk solution
#def inhabited-prop-is-contr (A : U) (f : is-prop A) (a : A)
  : is-contr A
  := (a , \ x → f a x)
```

## Conclusion

With a point to serve as the center, a proposition is contractible. So for inhabited types, contractible and proposition coincide.
