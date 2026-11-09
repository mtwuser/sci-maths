# Formal Mathematical Axioms, Spectral Theory & Differential Calculus (`sci-maths` — `E3`)

> **Epistemic Credibility Grade: `E3` (Formal Deductive Axioms & Proven Theorems — Non-Overridable Primary Truth)**
>
> This reference corpus establishes the primary deductive axioms and theorems of Linear Algebra, Multivariable & Vector Calculus, and Differential Equations consumed via `make consult LAYER=sci-maths` (`citation_receipt` `E3`).

---

## 1. Vector Spaces, Inner Products & the Spectral Theorem (`MATH-01` — `E3`)

Every finite-dimensional or separable Hilbert space $\mathcal{H}$ over $\mathbb{F} \in \{\mathbb{R}, \mathbb{C}\}$ satisfies the inner-product and spectral decomposition invariants below:

- **Inner-Product Space & Cauchy-Schwarz Inequality (`E3`)**: For all $u, v \in \mathcal{H}$, $|\langle u, v \rangle|^2 \le \langle u, u \rangle \langle v, v \rangle$, with equality if and only if $u$ and $v$ are linearly dependent.
- **Spectral Theorem for Self-Adjoint Operators (`E3`)**: Every compact self-adjoint (Hermitian) linear operator $T: \mathcal{H} \to \mathcal{H}$ ($T^* = T$) admits an orthonormal eigenbasis $\{e_k\}_{k=1}^n$ with purely real eigenvalues $\lambda_k \in \mathbb{R}$ such that:
  $$T = \sum_{k=1}^{n} \lambda_k \, |e_k\rangle\langle e_k|$$
- **Boundary Cut-Point (`N` vs. `N ± 1` Rank-Nullity Invariant)**: For any linear map $A: V \to W$ on $\dim(V) = N$, $\operatorname{rank}(A) + \dim(\ker A) = N$. A rank drop from $N$ to $N - 1$ marks the exact singularity boundary ($\det(A) = 0$).

---

## 2. Multivariable Calculus & Generalized Stokes' Theorem (`MATH-02` — `E3`)

Differential forms on an oriented smooth $n$-manifold $\Omega$ unify the Fundamental Theorem of Calculus, Green's Theorem, the Divergence Theorem (Gauss), and Classical Stokes' Theorem into a single boundary identity:

- **Generalized Stokes-Cartan Theorem (`E3`)**: For any compact oriented $n$-dimensional manifold $\Omega$ with boundary $\partial \Omega$ and smooth $(n-1)$-form $\omega$:
  $$\int_{\Omega} d\omega = \int_{\partial \Omega} \omega$$
- **Exterior Derivative Nilpotency (`Poincaré Lemma`, `E3`)**: $d(d\omega) = 0$ ($\nabla \times (\nabla \phi) = \mathbf{0}$ and $\nabla \cdot (\nabla \times \mathbf{A}) = 0$ in $\mathbb{R}^3$).

---

## 3. Linear Differential Operators, Green's Functions & Sturm-Liouville Theory (`MATH-03` — `E3`)

Second-order linear differential equations governing dynamical systems, wave propagation, and quantum eigenstates follow the Sturm-Liouville operator structure:

- **Sturm-Liouville Eigenvalue Problem (`E3`)**:
  $$\mathcal{L}[y](x) = -\frac{d}{dx}\left[p(x)\frac{dy}{dx}\right] + q(x)y(x) = \lambda w(x) y(x)$$
  where $p(x) > 0$ and weight $w(x) > 0$ on $[a, b]$ guarantee real eigenvalues $\lambda_1 < \lambda_2 < \dots \to +\infty$ and $w$-orthogonal eigenfunctions $\langle y_m, y_n \rangle_w = \int_a^b y_m(x) y_n(x) w(x)\,dx = 0$ for $m \ne n$.
- **Green's Function Superposition (`E2/E3`)**: If $\mathcal{L}[G(x, \xi)] = \delta(x - \xi)$ subject to homogeneous boundary conditions, then the unique solution to $\mathcal{L}[y] = f(x)$ is $y(x) = \int_a^b G(x, \xi) f(\xi)\,d\xi$.
