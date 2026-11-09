# Formal & Applied Mathematics Taxonomy & Branch Architecture (`sci-maths` — `E3`)

> **Epistemic Credibility Grade: `E3` (Canonical UNESCO/MSC Formal Sciences Branch Architecture)**
>
> This architecture document maps the 5 foundational branches of `sci-maths` (`canonical_trunk: "formal"`) and their outward interfaces to `sci-physics`, `sci-biology`, and `software-engineering`.

---

## 1. The 5 Canonical Branches of `sci-maths` (`MATH-01..03` — `E3`)

Every mathematical derivation, proof, or numerical algorithm in the network belongs to one of five orthogonal branches:

| Branch ID & Domain | Core Sub-Disciplines (`MSC 2020`) | Primary `E3` Objects & Invariants | Cross-Branch Applications (`sci-physics`, `sci-biology`, `software-engineering`) |
| :--- | :--- | :--- | :--- |
| **`BRANCH-01`: Foundations, Logic & Discrete Structures** | Propositional & First-Order Logic, `ZFC` Set Theory, Graph Theory, Combinatorics | Deductive soundness & completeness, DAG acyclicity, Pigeonhole & Cut-Point invariants (`N` vs. `N ± 1`). | Type systems, AST verification, DAG topology resolution (`sync_topology`), cryptographic primitives. |
| **`BRANCH-02`: Algebra, Linear Algebra & Spectral Theory** | Vector/Hilbert Spaces, Matrix Decompositions (`SVD`, Eigenvalues), Group/Lie Algebras | Rank-Nullity (`dim V = rank A + null A`), Spectral Theorem (`T = T*`), condition number $\kappa(A) = \|A\|\|A^{-1}\|$. | Quantum observables (`sci-physics`), stoichiometry matrices (`sci-biology`), ML embeddings. |
| **`BRANCH-03`: Mathematical Analysis, Calculus & PDEs** | Real/Complex Analysis, Vector Calculus, ODEs/PDEs, Sturm-Liouville & Fourier Analysis | Generalized Stokes' Theorem ($\int_\Omega d\omega = \int_{\partial\Omega}\omega$), Lipschitz continuity, Green's functions. | Maxwell's equations, Navier-Stokes, Fourier heat/Fick diffusion (`sci-physics`), Michaelis-Menten & reaction-diffusion (`sci-biology`). |
| **`BRANCH-04`: Geometry, Manifolds & Symplectic Topology** | Differential Geometry, Riemannian Metrics, Tensor Calculus, Symplectic $2$-Forms | Metric invariance ($ds^2 = g_{\mu\nu}dx^\mu dx^\nu$), Liouville phase-space volume conservation ($\omega = \sum dp_i \wedge dq_i$). | Lagrangian/Hamiltonian mechanics & General Relativity (`sci-physics`), geodetic projections (`geo-es`). |
| **`BRANCH-05`: Probability, Statistics & Optimization** | Measure-Theoretic Probability, Bayesian Inference, Convex Optimization, Numerical Analysis | Kolmogorov axioms, Bayes' Theorem, Karush-Kuhn-Tucker (`KKT`) optimality, Courant-Friedrichs-Lewy (`CFL`) stability. | Statistical mechanics (`sci-physics`), population genetics & biostatistics (`sci-biology`), telemetry & FinOps (`dept-iso-finance`). |
