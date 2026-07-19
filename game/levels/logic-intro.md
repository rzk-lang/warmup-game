---
id: logic-intro
title: Propositions as types
role: bridge-in
---

Under the **Curry–Howard correspondence**, a proposition is a type and a proof is a value of that type. Proving something is filling a hole, exactly as before. Every logical connective is a type former you have already met:

| English | Logic | Rzk |
| --- | --- | --- |
| A implies B | A → B | `A → B` |
| A and B | A ∧ B | `prod A B` |
| A or B | A ∨ B | `coprod A B` |
| true | ⊤ | `Unit` |
| false | ⊥ | `Void` |
| not A | ¬ A | `A → Void` |
| for all `x`, `P x` | ∀ | `(x : A) → P x` |
| there is an `x` with `P x` | ∃ | `Σ (x : A) , P x` |

So proving a propositional tautology is writing a function of the right type, and the term you write *is* the proof.

*By the end of this chapter you will be able to:* prove truth, weakening, and modus ponens, show that implication distributes over conjunction, and prove a first fact about negation.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §1.11.
