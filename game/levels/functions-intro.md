---
id: functions-intro
title: Functions
role: bridge-in
---

Functions are the core of type theory. A function type is written `A → B`. A function is built with a λ-abstraction, written `\ x → body`: the backslash `\` stands for the Greek λ, a λ with one leg missing, the same shorthand Haskell uses. A function is applied to an argument by juxtaposition, `f x`.

Three shorthands appear throughout, and all of them nest to the right:

- `\ x y z → …` is short for `\ x → \ y → \ z → …` — bind one argument at a time.
- `f x y z` is short for `((f x) y) z` — apply to one argument at a time.
- `A → B → C → D` is short for `A → (B → (C → D))` — the arrow groups to the right.

Together these are *currying*: a function of several arguments is really a function that returns a function, so it can be applied to its arguments one at a time (*partial application*).

Meeting a function goal always starts the same way: introduce the argument. Tapping the introduction move (or typing `\ x → ?` by hand) turns a goal `A → B` into a goal `B`, with a new `x : A` added to the context. Using a function you already have is the reverse: apply it to an argument.

*By the end of this chapter you will be able to:* build the identity and constant functions, compose functions, reorder arguments, and apply a dependent function. The `S` combinator is marked ★ and may be skipped.
