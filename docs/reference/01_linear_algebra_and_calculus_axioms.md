---
epistemic_grade: E3
---

# Formal Mathematical Axioms, Spectral Theory, PDEs & Convex Optimality (`sci-maths` — `E3`)

> **Epistemic Credibility Grade: `E3` (Formal Deductive Axioms & Proven Theorems — Non-Overridable Primary Truth)**
>
> This reference corpus establishes the primary axioms, theorems, and exact `N` vs. `N ± 1` boundary cut-points of Linear Algebra, Differential Forms, Partial Differential Equations, Probability, and Convex Optimization consumed via `make consult LAYER=sci-maths` ([01_formal_mathematics_taxonomy_and_branch_map.md](../architecture/01_formal_mathematics_taxonomy_and_branch_map.md)).

---

## 1. Hilbert Spaces, Spectral Decomposition & Matrix Cut-Points (`MATH-01`) [E3]

> **Summary [E3]:** *Every compact self-adjoint operator on a Hilbert space admits a real orthogonal spectral decomposition, while finite-dimensional linear maps $A \in \mathbb{F}^{m \times n}$ are completely classified by their rank $r$, singular values $\sigma_1 \ge \dots \ge \sigma_r > 0$, and positive-definiteness eigenvalues ([01_formal_mathematics_taxonomy_and_branch_map.md](../architecture/01_formal_mathematics_taxonomy_and_branch_map.md)).*

Every finite-dimensional or separable Hilbert space $\mathcal{H}$ over $\mathbb{F} \in \{\mathbb{R}, \mathbb{C}\}$ satisfies the inner-product, singular-value, and spectral invariants below:

- **Cauchy-Schwarz & Triangle Inequalities (`E3`)**: For all $u, v \in \mathcal{H}$, $|\langle u, v \rangle| \le \|u\|\,\|v\|$ and $\|u + v\| \le \|u\| + \|v\|$, with Cauchy-Schwarz equality if and only if $u$ and $v$ are linearly dependent.
- **Spectral Theorem for Self-Adjoint Operators (`E3`)**: Every Hermitian matrix $A = A^* \in \mathbb{C}^{N \times N}$ admits a unitary diagonalization $A = U \Lambda U^*$ ($U^*U = I_N$) with purely real eigenvalues $\lambda_1 \le \lambda_2 \le \dots \le \lambda_N \in \mathbb{R}$:
  $$A = \sum_{k=1}^{N} \lambda_k \, u_k u_k^*$$
- **Singular Value Decomposition (`SVD`, `E3`)**: Every matrix $A \in \mathbb{C}^{m \times n}$ of rank $r \le \min(m, n)$ factors as $A = U \Sigma V^*$ with $\sigma_1 \ge \sigma_2 \ge \dots \ge \sigma_r > 0$ and $\sigma_{r+1} = \dots = 0$.

The table below defines exact algebraic and spectral cut-points (`N` vs. `N ± 1`):

| Algebraic Property | Nominal Nonsingular / Strict Regime | Exact Cut-Point Boundary | Degenerate / Singular Regime |
| :--- | :--- | :--- | :--- |
| **Rank-Nullity (`A` on $\mathbb{F}^{N \times N}$)** | $\operatorname{rank}(A) = N$, $\dim(\ker A) = 0$, $\det(A) \ne 0$ (bijective) | $\operatorname{rank}(A) = N \to N - 1$ ($\sigma_N = 0$) | $\operatorname{rank}(A) \le N - 1$, $\dim(\ker A) \ge 1$ (non-unique / inconsistent $Ax = b$). |
| **Symmetric Definiteness ($A = A^\top$)** | $\lambda_{\min}(A) > 0$ (Strictly Positive Definite; Cholesky $A = LL^\top$ exists) | $\lambda_{\min}(A) = 0$ (Positive Semidefinite ridge) | $\lambda_{\min}(A) < 0 < \lambda_{\max}(A)$ (Indefinite saddle) or $\lambda_{\max}(A) < 0$ (Negative Definite). |
| **Banach Contraction Mapping ($T: X \to X$)** | Lipschitz constant $L \in [0, 1)$: unique fixed point $x^* = T(x^*)$, geometric error $\|x_k - x^*\| \le \frac{L^k}{1-L}\|x_1 - x_0\|$ | $L = 1$ (Non-expansive; uniqueness/convergence not guaranteed) | $L > 1$ (Expansive; iterative divergence possible). |

---

## 2. Differential Forms & Generalized Stokes-Cartan Theorem (`MATH-02`) [E3]

> **Summary [E3]:** *On any compact oriented smooth $n$-manifold $\Omega$ with piecewise-smooth boundary $\partial \Omega$, the exterior derivative $d$ and boundary operator $\partial$ are dual ($\int_\Omega d\omega = \int_{\partial\Omega} \omega$ and $d^2 \omega = 0$), unifying all classical integral theorems of vector calculus ([01_socratic_math_foundations.md](../guides/01_socratic_math_foundations.md)).*

For any smooth $(n-1)$-form $\omega \in \Omega^{n-1}(\Omega)$ on a compact oriented $n$-manifold $\Omega$:
$$\int_{\Omega} d\omega = \int_{\partial \Omega} \omega, \qquad d(d\omega) = 0$$

The table below instantiates Stokes-Cartan across Euclidean dimensions `1D`, `2D`, and `3D`:

| Classical Theorem | Manifold Dimension & Boundary | Differential Form $\omega$ | Vector Calculus Identity |
| :--- | :--- | :--- | :--- |
| **Fundamental Theorem of Calculus** | $n = 1$: Interval $[a, b]$, $\partial[a,b] = \{b\} - \{a\}$ | $0$-form $f(x)$ | $\int_a^b f'(x)\,dx = f(b) - f(a)$ |
| **Green's Theorem in the Plane** | $n = 2$: Planar region $D \subset \mathbb{R}^2$, $\partial D = C$ | $1$-form $P\,dx + Q\,dy$ | $\iint_D \left(\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y}\right)dA = \oint_{\partial D} (P\,dx + Q\,dy)$ |
| **Kelvin-Stokes Curl Theorem** | $n = 2$: Oriented surface $S \subset \mathbb{R}^3$, $\partial S = \Gamma$ | $1$-form $\mathbf{F} \cdot d\mathbf{r}$ | $\iint_S (\nabla \times \mathbf{F}) \cdot d\mathbf{S} = \oint_{\partial S} \mathbf{F} \cdot d\mathbf{r}$ |
| **Gauss-Ostrogradsky Divergence Theorem** | $n = 3$: Volume $V \subset \mathbb{R}^3$, $\partial V = \Sigma$ | $2$-form $\mathbf{F} \cdot d\mathbf{S}$ | $\iiint_V (\nabla \cdot \mathbf{F})\,dV = \oiint_{\partial V} \mathbf{F} \cdot \hat{\mathbf{n}}\,dS$ |

---

## 3. Sturm-Liouville Operators, PDE Classification & `CFL` Stability (`MATH-03`) [E3]

> **Summary [E3]:** *Second-order linear PDEs $A u_{xx} + B u_{xy} + C u_{yy} + \dots = 0$ split sharply across the discriminant cut-point $\Delta = B^2 - 4AC$ (`< 0` elliptic, `= 0` parabolic, `> 0` hyperbolic), while explicit finite-difference solvers require strict `CFL` time-step bounds ([01_formal_mathematics_taxonomy_and_branch_map.md](../architecture/01_formal_mathematics_taxonomy_and_branch_map.md)).*

- **Regular Sturm-Liouville Eigenvalue Problem (`E3`)**: On $[a, b]$ with $p(x) > 0$, $w(x) > 0$:
  $$\mathcal{L}[y](x) = -\frac{d}{dx}\!\left[p(x)\frac{dy}{dx}\right] + q(x)y(x) = \lambda w(x) y(x)$$
  yields a countable real spectrum $\lambda_1 < \lambda_2 < \dots \to +\infty$ whose eigenfunctions $\{y_n\}$ form a complete orthogonal basis in $L^2_w([a,b])$, with inhomogeneities solved via Green's kernel $\mathcal{L}[G(x,\xi)] = \delta(x - \xi)$.

The table below defines exact PDE classification and explicit discretization cut-points:

| PDE Regime / Scheme | Canonical Operator | Exact Cut-Point (`N` vs. `N ± 1`) | Physical & Numerical Behavior |
| :--- | :--- | :--- | :--- |
| **Elliptic PDE** | Poisson / Laplace ($-\nabla^2 u = f$) | $\Delta = B^2 - 4AC < 0$ | Infinite propagation speed; smooth interior solutions; boundary-value problem (`Dirichlet`/`Neumann`). |
| **Parabolic PDE (`FTCS` Diffusion)** | Heat / Fick ($u_t = \alpha \nabla^2 u$) | $\Delta = B^2 - 4AC = 0$; 1D explicit Fourier number $r = \frac{\alpha \Delta t}{\Delta x^2} \le \frac{1}{2}$ (`1D`) or $\le \frac{1}{2d}$ (`d`-D) | Forward-time centered-space (`FTCS`) is stable for $r \le 0.5$ and **oscillatory/divergent for $r > 0.5$**; Crank-Nicolson / Backward Euler are unconditionally $A$-stable. |
| **Hyperbolic PDE (`CFL` Wave/Advection)** | Advection ($u_t + c u_x = 0$) / Wave ($u_{tt} = c^2 \nabla^2 u$) | $\Delta = B^2 - 4AC > 0$; Courant number $C = \frac{|c|\Delta t}{\Delta x} \le 1.0$ | Domain of dependence must lie inside numerical stencil: **stable for $C \le 1.0$, unconditionally unstable for $C > 1.0$**. |

---

## 4. Kolmogorov Probability, Bayes' Theorem & `KKT` Convex Optimality (`MATH-04`) [E3]

> **Summary [E3]:** *On a measure space $(\Omega, \mathcal{F}, \mathbb{P})$ with $\mathbb{P}(\Omega) = 1$, conditional beliefs update via Bayes' rule, while constrained smooth convex programs achieve global optimality if and only if the four Karush-Kuhn-Tucker (`KKT`) conditions hold under Slater's regularity condition ([01_socratic_math_foundations.md](../guides/01_socratic_math_foundations.md)).*

1. **Kolmogorov Axioms & Bayes' Theorem (`E3`)**: Non-negativity $\mathbb{P}(E) \ge 0$, normalization $\mathbb{P}(\Omega) = 1$, countable additivity $\mathbb{P}(\bigsqcup_{i=1}^\infty E_i) = \sum_{i=1}^\infty \mathbb{P}(E_i)$, and for $\mathbb{P}(B) > 0$:
   $$\mathbb{P}(A \mid B) = \frac{\mathbb{P}(B \mid A)\,\mathbb{P}(A)}{\mathbb{P}(B)}$$
2. **Karush-Kuhn-Tucker (`KKT`) Global Optimality Cut-Points (`E3`)**: For minimizing convex differentiable $f_0(x)$ subject to convex $g_i(x) \le 0$ ($i=1\dots m$) and affine $h_j(x) = 0$ ($j=1\dots p$) satisfying Slater's strict interior condition ($\exists \tilde{x}: g_i(\tilde{x}) < 0$), $x^*$ is globally optimal if and only if multipliers $(\mu^*, \nu^*)$ satisfy:
   - **Primal Feasibility**: $g_i(x^*) \le 0$ and $h_j(x^*) = 0$.
   - **Dual Feasibility**: $\mu_i^* \ge 0$ for all $i = 1, \dots, m$ ($\mu_i^* < 0$ violates optimality).
   - **Complementary Slackness (`Active vs. Inactive Constraint Cut-Point`)**: $\mu_i^* g_i(x^*) = 0$ ($g_i(x^*) < 0 \implies \mu_i^* = 0$; $\mu_i^* > 0 \implies g_i(x^*) = 0$).
   - **Lagrangian Stationarity**: $\nabla f_0(x^*) + \sum_{i=1}^m \mu_i^* \nabla g_i(x^*) + \sum_{j=1}^p \nu_j^* \nabla h_j(x^*) = \mathbf{0}$.
