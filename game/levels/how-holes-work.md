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

## The road ahead

The game builds Rzk's type theory from nothing, one chapter at a time:

1. **Getting started** — holes, and how to read a definition.
2. **Dependent types** — functions, pairs, and Σ-types, then coproducts, booleans, and numbers.
3. **Propositions as types** — logic read as types: implication, conjunction, negation, and quantifiers.
4. **Identity types** — equality, path induction, and the algebra of paths.
5. **Equivalences and univalence** — what it means for two types to be the same.
6. **Sets and logic** — contractible types, propositions, and sets.
7. **A taste of directed types** — the cubes, topes, and morphisms that Rzk was built for.

Nothing is assumed before chapter 1, and each chapter builds on the ones before it.

## Glossary

A quick reference for the words this game uses. Skip it for now, and come back whenever a term is unfamiliar.

Playing:

- **hole** (`?`): a gap in the code you have to fill.
- **goal**: the type your answer must have, shown for the focused hole.
- **context**: the values and assumptions in scope at that hole.
- **move**: a suggested step you can tap. An *introduction* builds a value from the goal's shape (a `\` for a function, a pair for a product); a *give* reuses something from the context.
- **Check**: type-checks the code; you win when no holes remain.

Language. Each entry notes the common alternative names you may meet elsewhere.

- **type**: a classification of values; `A : U` reads "`A` is a type". Pictured as a *space* in homotopy type theory.
- **universe** (`U`): the type whose values are themselves types.
- **value**: an expression, such as the one that fills a hole. Also called a *term*, an *element*, or (for a type seen as a space) a *point*.
- **function** (`A → B`): sends an `A` to a `B`; written `\ x → …` and applied by juxtaposition, `f x`. Also called a *map*.
- **λ-abstraction** (`\ x → …`): a function written inline; `\` stands for the Greek λ. Also called an *anonymous function*.
- **dependent function** (`(x : A) → B x`): a function whose result type depends on the argument. Also called a *Π-type* (pi-type); one such function is a *section* of the family `B`.
- **product** (`prod A B`): the type of pairs of an `A` and a `B`; here a shorthand for `Σ (a : A) , B`. As a proposition it is *conjunction*.
- **pair** (`(a , b)`) and **projections** (`first`, `second`): build a pair and take it apart.
- **Σ-type** (`Σ (x : A) , B x`): a dependent pair, where the second type may depend on the first value. Also called a *dependent pair type* or *dependent sum*.
- **type family** (`B : A → U`): a type `B x` for each point `x`. Also called a *fibration*; each `B x` is a *fiber*.
- **proposition as type** (Curry–Howard): a proposition is a type, and a proof is a value of that type.
- **Unit** / **unit**: truth, the proposition that always holds, with proof `unit`. Also called the *terminal type*.
- **identity type** (`x = y`): the type of proofs that `x` equals `y`; its one constructor is `refl`. Also called the *path type*; a proof is a *path*.
- **path induction** (`ind-path`): to prove a statement about a path `p : x = y`, it is enough to prove the case where `p` is `refl`. Also called the *J rule*. The **motive** is that statement, as it depends on the endpoint and the path.
- **contractible** (`is-contr A`): `A` has a center point to which every point is equal.
- **proposition** (`is-prop A`): any two points of `A` are equal. Also called a *mere proposition*.
- **set** (`is-set A`): any two proofs of one equality in `A` are equal.
- **homotopy** (`homotopy A B f g`): a pointwise equality of functions, `(x : A) → f x = g x`.
- **equivalence** (`is-equiv`, `Equiv A B`): a function with a two-sided inverse, and two types related by one.
- **univalence**: the axiom that equality of types is the same as equivalence of types.
- **morphism** (`hom A x y`): a *directed* path from `x` to `y`, a map out of the interval `Δ¹`. Also called an *arrow*.
- **directed interval** (`2`): the basic cube of directed type theory, with endpoints `0₂` and `1₂`; the whole interval as a shape is `Δ¹`.
