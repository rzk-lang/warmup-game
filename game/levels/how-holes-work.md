---
id: how-holes-work
title: How holes work
role: bridge-in
---

Welcome to the Rzk warm-up. This game teaches Rzk one small step at a time, and assumes you have never seen it before.

Every puzzle hands you an unfinished piece of Rzk code with a gap in it, written `?`. That gap is a **hole**. Your job is to fill every hole so the code is complete.

Click a hole and the panel beside the editor shows two things:

- its **goal**: what your answer has to be (its type), and
- its **context**: everything you already have to work with right there, the values and assumptions in scope.

The engine also suggests **moves**: ready-made steps you can tap to make progress, each one worked out from the goal. Some build an answer from the goal's shape; others reuse something from the context. You can always type into the editor by hand instead.

Press **Check** to see how you did. A puzzle is solved once the code checks with no holes left. If you get stuck, ask for a **hint** with the hint button; some hints appear only once the goal has a certain shape.

This page is always one tap away: the header keeps a "❓ Holes" link that jumps back here from anywhere in the game.

## Glossary

A quick reference for the words this game uses. Skip it for now, and come back whenever a term is unfamiliar.

Playing:

- **hole** (`?`): a gap in the code you have to fill.
- **goal**: the type your answer must have, shown for the focused hole.
- **context**: the values and assumptions in scope at that hole.
- **move**: a suggested step you can tap. An *introduction* builds a value from the goal's shape (a `\` for a function, a pair for a product); a *give* reuses something from the context.
- **Check**: type-checks the code; you win when no holes remain.

Language:

- **type**: a classification of values; `A : U` reads "`A` is a type".
- **universe** (`U`): the type whose values are themselves types.
- **value**: an expression, such as the one that fills a hole.
- **function** (`A → B`): sends an `A` to a `B`; written `\ x → …` and applied by juxtaposition, `f x`.
- **λ-abstraction** (`\ x → …`): a function written inline; `\` stands for the Greek λ.
- **dependent function** (`(x : A) → B x`): a function whose result type depends on the argument.
- **product** (`prod A B`): the type of pairs of an `A` and a `B`; here a shorthand for `Σ (a : A) , B`.
- **pair** (`(a , b)`) and **projections** (`first`, `second`): build a pair and take it apart.
- **Σ-type** (`Σ (x : A) , B x`): a dependent pair, where the second type may depend on the first value.
- **type family** (`B : A → U`): a type `B x` for each point `x`.
- **proposition as type** (Curry–Howard): a proposition is a type, and a proof is a value of that type.
- **Unit** / **unit**: truth (`⊤`), the proposition that always holds, with proof `unit`.
- **identity type** (`x = y`): the type of proofs that `x` equals `y`; its one constructor is `refl`.
- **path induction** (`ind-path`): to prove a statement about a path `p : x = y`, it is enough to prove the case where `p` is `refl`. The **motive** is that statement, as it depends on the endpoint and the path.
