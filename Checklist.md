# Models of Computation – Revision Checklist

## Finite-State Automata & Regular Languages

- [0] Know the formal definition of a **DFA** (Q, Σ, δ, q₀, F) and what each component means.  
- [0] Be able to explain how a DFA **runs on a word** and decides accept/reject.  
- [0] Understand what a **language recognized by a DFA** is.  

- [0] Know the formal definition of an **NFA** and how it differs from a DFA (set‑valued δ, ε‑moves).  
- [0] Be able to explain how an NFA accepts a word (“there exists an accepting path”).  
- [0] Understand that **NFAs and DFAs recognize exactly the same class** of languages (regular).  

- [0] Understand the **subset construction**:
  - [0] DFA states are subsets of NFA states.  
  - [0] Start state is ε‑closure of NFA start state.  
  - [0] Accept states contain at least one NFA accept state.  

- [0] Be able to define a **regular language** (recognized by some DFA).  

---

## Regular Operations and Regular Expressions

- [0] Recall language operations: union, intersection, complement, concatenation, star.  
- [0] Know that **regular languages are closed** under these operations.  

- [0] Know the **syntax of regular expressions**:
  - [0] Base: `a`, `ε`, `∅`.  
  - [0] Operators: union, concatenation, star.  

- [0] Understand that **REs, DFAs, NFAs** all define the same class of languages (regular).  
- [0] Have the high‑level idea of **FA → RE** via GNFA and state elimination (no need for algorithm details).  

---

## Pumping Lemma and Non-Regularity

- [0] Be able to state the **pumping lemma** correctly (`w = xyz`, `|y| > 0`, `|xy| ≤ p`, `xyⁱz ∈ L` for all `i`).  
- [0] Understand the **intuition** (finite states → repeated state → loop).  

- [0] Practise the **proof pattern** for non‑regular languages:
  - [0] Assume `L` is regular.  
  - [0] Take pumping length `p`.  
  - [0] Choose a suitable `w ∈ L` with `|w| ≥ p`.  
  - [0] For any valid split `w = xyz`, find `i` (often 0 or 2) so `xyⁱz ∉ L`.  
  - [0] Conclude `L` is not regular.  

---

## DFA Minimisation

- [0] Know what it means for two states to be **equivalent** or **distinguishable**.  
- [0] Understand why equivalent states can be **merged**.  

- [0] Remember the **minimisation procedure**:
  - [0] Remove unreachable states.  
  - [0] Initial partition: accept vs non‑accept states.  
  - [0] Repeatedly split blocks where states behave differently on some symbol.  
  - [0] Build new DFA with one state per final block.  

- [0] Know the result: minimised DFA is unique up to renaming (isomorphism).  

---

## Büchi Automata and ω-Regular Languages

- [0] Understand the motivation: **infinite words** / infinite behaviours.  

- [0] Know the definition of a **Büchi automaton** (same structure as NFA but for `Σ^ω`).  
- [0] Understand what a **run** is on an infinite word.  
- [0] Know the Büchi **acceptance condition**:
  - [0] Accept if some accepting state is visited **infinitely often** along the run.  

- [0] Understand the definition of **ω‑regular languages**:
  - [0] Built from regular languages using union, concatenation (finite with infinite), and `A^ω`.  

- [0] Know the theorem: ω‑language is ω‑regular **iff** some non‑deterministic Büchi automaton recognizes it.  
- [0] Be aware that ω‑regular languages are closed under union, intersection, complementation.  

- [0] Understand the notion of **limit of a regular language** `lim(A)` (infinitely many prefixes in `A`).  
- [0] Know that limits correspond to **deterministic** Büchi automata and this is a strict subset of ω‑regular languages.  
- [0] Remember there are ω‑regular languages with **no deterministic Büchi automaton** (e.g. finitely many 1’s).  

---

## Linear Temporal Logic (LTL)

- [0] Understand the time model: infinite sequence of states `A₀A₁A₂…` with AP labels.  

- [0] Know the **syntax** of LTL:
  - [0] Atomic propositions `a ∈ AP`, `true`.  
  - [0] Boolean: `¬`, `∧` (others derived).  
  - [0] Temporal: `⃝φ` (next), `φ₁ U φ₂` (until).  

- [0] Be able to define **derived operators**:
  - [0] `◇φ = true U φ` (eventually).  
  - [0] `□φ = ¬◇¬φ` (always).  

- [0] Know the **semantics**:
  - [0] `σ ⊨ a` iff `a` is in the first state’s label.  
  - [0] `σ ⊨ ⃝φ` iff the tail from position 1 satisfies `φ`.  
  - [0] `σ ⊨ φ₁ U φ₂` with the “some position `i` where `φ₂` holds and `φ₁` holds at all earlier positions” condition.  

- [0] Be able to evaluate simple LTL formulas on small traces.  

---

## Transition Systems and LTL Satisfaction

- [0] Know the definition of a **transition system**:
  - [0] States `S`, transition relation `→`, initial states `I`, `AP`, labeling `L`.  

- [0] Understand what a **run** is (infinite sequence of states, starting in `I`, following `→`).  
- [0] Understand a **trace** (labels along a run).  

- [0] Know definition of **`Traces(TS)`** (all traces of all runs).  
- [0] Know when `TS ⊨ φ`: every trace in `Traces(TS)` satisfies `φ`.  
- [0] Remember `TS` can satisfy neither `φ` nor `¬φ` (some traces satisfy, some don’t).  

---

## Modal Logic (brief, supporting intuition)

- [0] Know the meaning of `□φ` (“necessarily φ”) and `◇φ` (“possibly φ”).  
- [0] Know `◇φ = ¬□¬φ`.  
- [0] Have the basic idea of Kripke semantics:
  - [0] Worlds `W` and accessibility relation `R`.  
  - [0] `□a` true at `u` if `a` is true at every `R`‑successor of `u`.  
  - [0] `◇a` true at `u` if `a` is true at some `R`‑successor of `u`.  
