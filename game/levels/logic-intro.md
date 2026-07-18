---
id: logic-intro
title: Propositions as types
role: bridge-in
---

Under the **Curry–Howard correspondence**, a proposition is a type and a proof is a value of that type. Proving something is filling a hole, exactly as before. The logical connectives are types you have already met:

- **implication** `A → B` is a function: it turns a proof of `A` into a proof of `B`.
- **conjunction** "`A` and `B`" is the product `prod A B`: a proof is a pair of a proof of `A` and a proof of `B`.
- **truth** is `Unit`: it has the single proof `unit`, so it always holds.

So proving a propositional tautology is writing a function of the right type, and the term you write *is* the proof.

Two connectives are missing. **Disjunction** ("or") and **negation** ("not") need types Rzk does not have built in, so they wait until the optional aside at the end of the chapter.

*By the end of this chapter you will be able to:* prove truth, weakening, and modus ponens, and show that implication distributes over conjunction, all as terms.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §1.11.
