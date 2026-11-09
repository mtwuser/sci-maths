---
description: "Formal mathematical rigor, deductive proof structure, and Spectral/Calculus invariants (sci-maths)"
---

# Formal Mathematics Corpus Rules (`sci-maths`)

## 1. Deductive Proof Integrity & Epistemic Precedence (`MATH-01..03`)

1. **`MATH-01` (Explicit Domain, Codomain & Regularity Hypotheses)**: Every theorem, operator, or equation must state its space ($\mathbb{R}^n$, $\mathcal{H}$, $C^k(\Omega)$) and regularity hypotheses before invoking linearity, invertibility, or integration by parts.
2. **`MATH-02` (Singularity & Cut-Point Verification `N vs N±1`)**: Always verify degenerate boundaries ($\det(A) = 0$, $\lambda = 0$, boundary $\partial \Omega = \emptyset$, non-commuting operators $[A, B] \ne 0$).
3. **`MATH-03` (`citation_receipt` Provenance)**: Cite primary theorems from `sci-maths::docs/reference/01_linear_algebra_and_calculus_axioms.md` (`E3`) when deriving applied or physical results.
