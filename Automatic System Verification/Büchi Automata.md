
#### **1. Definition**

A **Büchi automaton** is a type of **ω-automaton** (automaton over infinite words) that accepts infinite strings based on the **infinitely occurring accepting states**. Formally, it is a tuple:

$A=(Q,Σ,δ,q0,F)$

where:
- Q: Finite set of **states**.
- Σ: Input **alphabet** (symbols representing system actions or propositions).
    
- δ: **Transition relation** $δ⊆Q×Σ×Q$ (nondeterministic) or $δ:Q×Σ→Q$ (deterministic).
    
- $q_0$​: **Initial state**.
    
- $F⊆Q$: Set of **accepting (final) states**.