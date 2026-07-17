---
id: negation-aside
title: Negation and disjunction
role: note
---

So far every connective was native. **Negation** and **disjunction** are not.

Negation `¬ A` means "`A` leads to a contradiction". It is written `A → ⊥`, where `⊥` is falsity: the proposition with no proof at all. Disjunction `A ∨ B` is a proof of one side or the other.

Both need types Rzk does not build in. Falsity is the empty type `Void`, and disjunction is the coproduct `coprod A B`. Rzk will gain these once it supports user-defined inductive types; until then a game has to postulate them. The next level does exactly that, postulating `Void` in its prelude, so treat it as a preview rather than something Rzk already provides.
