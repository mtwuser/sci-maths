---
epistemic_grade: E1
---

# Socratic Mathematics Curriculum & Proof Verification Guide (`M1 -> M4` — `sci-maths` `E1`)

> **Epistemic Credibility Grade: `E1` (Pedagogical Synthesis, Socratic Progression & Proof Verification Protocol)**
>
> This guide adapts the formal axioms and theorems of `sci-maths` across the four cognitive mastery levels (`domain-maths:M1..M4`) for school students, university specialty tracks, software engineers, and scientific researchers ([01_linear_algebra_and_calculus_axioms.md](../reference/01_linear_algebra_and_calculus_axioms.md)).

---

## 1. Progressive `M1 -> M4` Mathematical Mastery Ladder [E1]

> **Summary [E1]:** *Mathematical instruction progresses from geometric visualization (`M1`) to formal $\varepsilon$-$\delta$ and spectral proof construction (`M2`), numerical conditioning and PDE stability (`M3`), and cross-discipline operator synthesis (`M4`) ([01_formal_mathematics_taxonomy_and_branch_map.md](../architecture/01_formal_mathematics_taxonomy_and_branch_map.md)).*

The table below defines cognitive goals, core topics, and `verify-mastery` gates across `M1..M4`:

| Mastery Stage | Target Persona & Cognitive Focus | Core Mathematical Pillars | Verification Gate (`verify-mastery`) |
| :--- | :--- | :--- | :--- |
| **`M1` (School & Foundations)** | Secondary / High School (`tutor-iso-lab`): geometric intuition before symbolic abstraction; visualize transformations and slopes. | Linear systems ($2 \times 2$, $3 \times 3$), Euclidean vectors, single-variable limits, derivatives, definite integrals, basic probability. | Test degenerate boundary cases (`0`, `1`, parallel lines $\det A = 0$) and explain *why* each algebraic step holds without rote memorization. |
| **`M2` (Undergraduate Rigor)** | University STEM (`specialty/maths`, `specialty/maths-physics`): formal quantifier logic and axiomatic proof construction. | Inner-product spaces, `SVD` & Spectral Theorem (`MATH-01`), Stokes/Divergence (`MATH-02`), Sturm-Liouville ODEs/PDEs (`MATH-03`). | Author complete proofs (`Hypotheses -> Deductive Chain -> Q.E.D.`) and exhibit an explicit counterexample whenever a hypothesis is dropped. |
| **`M3` (Applied & Computational)** | Senior Engineers & Computational Scientists: floating-point conditioning (`IEEE 754`), PDE discretization, and convex optimization. | Condition number $\kappa_2(A)$, `CFL` ($C \le 1$) and `FTCS` ($r \le 0.5$) stability cut-points, `KKT` multipliers (`MATH-04`). | Prove solver stability bounds and verify `AAA` unit tests on both sides of `N` vs. `N ± 1` numerical cut-points. |
| **`M4` (Frontier Research)** | Principal Investigators & Theory Architects: functional analysis, Riemannian/symplectic manifolds, and measure-theoretic probability. | Unbounded self-adjoint operators, Lie algebras, differential $k$-forms on manifolds, stochastic calculus. | Seal multi-corpus derivations with `citation_receipt` provenance (`sci-maths` `E3` $\rightarrow$ `sci-physics` / `sci-engineering`). |

---

## 2. 4-Step Deductive Proof & `N vs. N ± 1` Counterexample Protocol [E1]

> **Summary [E1]:** *Before accepting any mathematical derivation or numerical implementation, verify domain hypotheses, probe the exact `N` vs. `N ± 1` singularity boundary, check dimensional/norm invariance, and anchor the primary `E3` theorem ([01_linear_algebra_and_calculus_axioms.md](../reference/01_linear_algebra_and_calculus_axioms.md)).*

1. **Step 1 — Domain, Regularity & Quantifier Audit**: Write down the ambient space ($\mathbb{R}^N$, $C^k(\Omega)$, $L^2([a,b])$) and verify every hypothesis (compactness, symmetry $A = A^*$, Slater strict feasibility).
2. **Step 2 — `N vs. N ± 1` Boundary & Counterexample Probe**: Evaluate the statement at the critical threshold ($\operatorname{rank}(A) = N - 1$, Lipschitz $L = 1$, Courant $C = 1.01$, discriminant $\Delta = 0$) to confirm sharpness.
3. **Step 3 — Stepwise Deductive or Numerical Bound**: Justify each equality/inequality by an explicit `E3` axiom (`Cauchy-Schwarz`, `Stokes-Cartan`, `Rank-Nullity`, `KKT`) or `E2` `IEEE 754` rounding bound.
4. **Step 4 — Epistemic Provenance Seal**: Attach `sci-maths::docs/reference/01_linear_algebra_and_calculus_axioms.md#<slug>@<digest16>:E3` in downstream specifications or `WORKVALI.md`.

---

## 3. Multi-Perspective Consultation Examples (`M1..M4`) [E1]

> **Summary [E1]:** *A single authoritative `sci-maths` repository serves Socratic school drills (`M1`), university vector-calculus proofs (`M2`), and industrial PDE/SHM solver verification (`M3..M4`) without duplicating axioms.*

- **School Student (`M1`, `specialty/maths`)**: Investigating when two planar lines fail to intersect uniquely reduces to the `N = 2` Rank-Nullity cut-point ($\operatorname{rank}(A) = 2$ unique point vs. $\operatorname{rank}(A) = 1$ parallel or coincident lines).
- **University Physics/Maths Student (`M2`, `specialty/maths-physics`)**: Deriving differential Gauss's law $\nabla \cdot \mathbf{E} = \rho / \varepsilon_0$ from integral flux $\oiint_{\partial V} \mathbf{E}\cdot d\mathbf{S} = Q_{\text{enc}}/\varepsilon_0$ invokes the $n = 3$ Stokes-Cartan Divergence identity (`MATH-02`).
- **Process & SHM Engineer (`M3..M4`, `dept-iso-eng`)**: Ensuring natural frequencies $f_n = \omega_n / (2\pi)$ of a mechanical frame are real and positive invokes symmetry and positive-definiteness of stiffness $\mathbf{K} = \mathbf{K}^\top \succ 0$ and mass $\mathbf{M} = \mathbf{M}^\top \succ 0$ (`MATH-01`).
