---
id: functions-intro
title: Functions
role: bridge-in
---

Functions are the core of type theory. A function type is written `A → B`. A function is built with a λ-abstraction, `\ x → body`, and applied to an argument by juxtaposition, `f x`.

Meeting a function goal always starts the same way: introduce the argument with `λ-intro`, which turns a goal `A → B` into a goal `B` with a new `x : A` in scope. Using a function you already have is the reverse move, application.

*By the end of this chapter you will be able to:* build the identity and constant functions, compose functions, reorder arguments, and apply a dependent function. The `S` combinator is marked ★ and may be skipped.
