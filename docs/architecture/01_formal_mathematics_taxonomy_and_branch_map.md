---
epistemic_grade: E3
---

# Formal & Applied Mathematics Taxonomy, Deductive Hierarchy & Numerical Conditioning (`sci-maths` — `E3`)

> **Epistemic Credibility Grade: `E3` (Canonical UNESCO / MSC 2020 Formal Sciences Architecture)**
>
> This architecture specification defines the five foundational branches of **`sci-maths`** (`canonical_trunk: "formal"`), the deductive proof precedence hierarchy, numerical conditioning bridges, and outward interfaces to `sci-physics`, `sci-biology`, `sci-engineering`, `geo-es`, and `software-engineering` ([01_linear_algebra_and_calculus_axioms.md](../reference/01_linear_algebra_and_calculus_axioms.md)).

---

## 1. The 5 Canonical Branches of `sci-maths` (`MSC 2020`) [E3]

> **Summary [E3]:** *Every deductive proof, variational formulation, or numerical algorithm in the network maps to one of five orthogonal `MSC 2020` mathematical branches (`BRANCH-01..05`), linking pure axiomatic structures to physical conservation laws, biological stoichiometry, and software verification ([01_linear_algebra_and_calculus_axioms.md](../reference/01_linear_algebra_and_calculus_axioms.md)).*

The table below maps each canonical mathematical branch to its `MSC 2020` classification codes, primary `E3` invariants, and cross-corpus consumers:

| Branch ID & Domain | `MSC 2020` Scope | Primary `E3` Objects & Invariants | Cross-Corpus Consumers |
| :--- | :--- | :--- | :--- |
| **`BRANCH-01`: Foundations, Logic & Discrete Structures** | `03`, `05`, `06`, `68` | First-Order Logic soundness/completeness, `ZFC` set axioms, DAG acyclicity, Pigeonhole & discrete cut-points (`N` vs. `N ± 1`). | AST/type verification, Merkle DAG topology, cryptographic hash chains (`software-engineering`). |
| **`BRANCH-02`: Algebra, Linear Algebra & Spectral Theory** | `15`, `16`, `20`, `47` | Vector/Hilbert spaces, Rank-Nullity (`rank A + null A = N`), `SVD`, Spectral Theorem ($T = T^*$), Lie groups/algebras. | Quantum observables (`sci-physics`), metabolic stoichiometry (`sci-biology`), modal dynamics (`sci-engineering`). |
| **`BRANCH-03`: Mathematical Analysis, Measure & PDEs** | `26`, `28`, `34`, `35`, `42`, `46` | Cauchy completeness, Lebesgue integration, Generalized Stokes' Theorem ($\int_\Omega d\omega = \int_{\partial\Omega}\omega$), Sturm-Liouville & Fourier transforms. | Maxwell electrodynamics, Navier-Stokes, Fourier/Fick transport (`sci-physics`), reaction-diffusion (`sci-biology`). |
| **`BRANCH-04`: Differential, Riemannian & Symplectic Geometry** | `51`, `53`, `57`, `58` | Metric tensor ($ds^2 = g_{\mu\nu}dx^\mu dx^\nu$), Gauss-Bonnet curvature, symplectic $2$-forms ($\omega = \sum dp_i \wedge dq_i$), Liouville volume invariance. | Hamiltonian mechanics & General Relativity (`sci-physics`), `ETRS89`/`UTM` geodetic projections (`geo-es`). |
| **`BRANCH-05`: Probability, Statistics, Optimization & Numerical Analysis** | `60`, `62`, `65`, `90` | Kolmogorov probability space $(\Omega, \mathcal{F}, \mathbb{P})$, Bayes' Theorem, `KKT` convex optimality, `CFL` discretization stability. | Statistical mechanics (`sci-physics`), population genetics (`sci-biology`), `SIL` reliability & sensor filtering (`sci-engineering`). |

---

## 2. Deductive Structure & Epistemic Precedence Hierarchy [E3]

> **Summary [E3]:** *Formal mathematical truth derives exclusively from explicit axioms and inference rules (`Axiom -> Definition -> Lemma -> Theorem -> Corollary`), outranking empirical regressions (`E2`) and heuristic approximations (`E1`) whenever domain hypotheses are satisfied ([01_socratic_math_foundations.md](../guides/01_socratic_math_foundations.md)).*

Every mathematical claim cited across sovereign nodes obeys four structural invariants:

1. **Explicit Hypothesis & Domain Closure (`MATH-ARCH-01`)**: A theorem applies if and only if every regularity, dimensionality, compactness, or convexity hypothesis holds (`0` silent extrapolation across singular points).
2. **Quantifier Order Precision (`MATH-ARCH-02`)**: Uniform properties ($\forall \varepsilon > 0\,\exists \delta > 0\,\forall x, y$) must never be conflated with pointwise properties ($\forall x\,\forall \varepsilon > 0\,\exists \delta(x) > 0$).
3. **Exact Cut-Point Disambiguation (`N` vs. `N ± 1`, `MATH-ARCH-03`)**: Strict inequalities ($<, >$) and weak inequalities ($\le, \ge$) separate distinct topological regimes (open interior vs. closed boundary, nonsingular vs. degenerate kernel).
4. **Constructive vs. Non-Constructive Provenance (`MATH-ARCH-04`)**: Existence proofs (`Banach Fixed-Point` constructive contraction $\rho < 1$ vs. `Brouwer` non-constructive existence) must declare whether an explicit convergence rate is guaranteed.

---

## 3. Exact Arithmetic vs. `IEEE 754` Floating-Point Conditioning Bridge [E2]

> **Summary [E2]:** *Translating continuous `E3` theorems into finite-precision software (`IEEE 754` Binary64) requires bounding both the problem's relative condition number $\kappa$ and the algorithm's backward stability under machine epsilon $\varepsilon_{\text{mach}} = 2^{-53}$ ([01_linear_algebra_and_calculus_axioms.md](../reference/01_linear_algebra_and_calculus_axioms.md)).*

The table below specifies exact `IEEE 754-2019` floating-point representation parameters and numerical stability cut-points:

| Numerical Parameter / Law | Exact Formula or `IEEE 754` Constant | Stability Cut-Point (`N` vs. `N ± 1`) | Engineering Consequence |
| :--- | :--- | :--- | :--- |
| **`Binary64` (`float64`) Machine Epsilon** | $\varepsilon_{\text{mach}} = 2^{-53} \approx 1.1102230246251565 \times 10^{-16}$ | `53` significand bits (`~15–17` decimal digits) | Relative rounding bound $|\operatorname{fl}(x) - x|/|x| \le \frac{1}{2}\varepsilon_{\text{mach}}$ (`roundTiesToEven`). |
| **`Binary32` (`float32`) Machine Epsilon** | $\varepsilon_{\text{mach},32} = 2^{-24} \approx 5.96046448 \times 10^{-8}$ | `24` significand bits (`~7.2` decimal digits) | Insufficient for ill-conditioned linear solvers or geodetic `UTM` millimeter coordinates. |
| **Matrix Relative Condition Number** | $\kappa_2(A) = \|A\|_2 \|A^{-1}\|_2 = \sigma_{\max}(A)/\sigma_{\min}(A)$ | $\kappa_2(A) = 1$ (orthogonal) vs. $\kappa_2(A) \ge \varepsilon_{\text{mach}}^{-1} \approx 9.0 \times 10^{15}$ | At $\kappa_2(A) \cdot \varepsilon_{\text{mach}} \ge 1$, `0` significant digits remain in `Binary64` direct solve; use `SVD` / `Tikhonov` regularization. |
| **Lax-Richtmyer Equivalence Theorem** | $\text{Consistency} + \text{Stability} \iff \text{Convergence}$ | Amplification factor $|G(k\Delta x)| \le 1 + C\Delta t$ vs. $|G| > 1$ | Consistent linear PDE discretizations converge as $(\Delta x, \Delta t) \to 0$ if and only if Von Neumann / `CFL` stability holds. |
