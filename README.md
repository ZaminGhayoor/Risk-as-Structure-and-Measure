# Risk as Structure and Measure

## Abstract
This repository develops an algebraic and analytical framework for actuarial pricing. The central idea is that expected present value (EPV) should be viewed not only as a probability-based calculation, but also as a linear map on a space of cashflows. This allows actuarial models to be studied using vector spaces, kernels, quotient spaces, group actions, and continuity arguments.

The project begins with the classical actuarial formulas for discrete and continuous insurance models, then reframes them in a more structural way:
- **cashflows** are elements of a vector space,
- **pricing** is a linear functional,
- **financial equivalence** is captured by cosets of the kernel,
- **portfolio rearrangements** are modeled by group actions,
- **reinsurance** is interpreted through quotient structures,
- and **stability** is handled through convergence theorems.

The result is a mathematically richer perspective on risk that connects abstract algebra, real analysis, and actuarial science.

## Core Thesis
Expected present value can be treated as a map

\[
f(c) = \mathbb{E}\left[\sum_{t \ge 0} v^t c_t\right]
\]

from a cashflow space into the real numbers. Once that perspective is adopted, the following questions become natural:

1. What algebraic structure does the cashflow space carry?
2. What is the kernel of the pricing map?
3. When do two risks become equivalent under pricing?
4. How does reinsurance factor through quotient spaces?
5. Which limits preserve actuarial valuation?

## Main Mathematical Ideas

### 1. Cashflow space
A cashflow is a sequence
\[
c = (c_0, c_1, c_2, \dots)
\]
with addition and scalar multiplication defined pointwise. This gives a vector space (or module, depending on scalar field / ring).

### 2. EPV as a linear functional
If absolute convergence holds, then
\[
f(c+d)=f(c)+f(d), \quad f(\alpha c)=\alpha f(c),
\]
so pricing becomes a linear functional.

### 3. Kernel and financial equivalence
The kernel
\[
\ker(f)=\{c : f(c)=0\}
\]
represents cashflows with zero expected present value. Two cashflows are financially equivalent when they differ by an element of the kernel.

### 4. Quotient interpretation
If a family of reinsurance legs lies in a subspace \(R \subseteq \ker(f)\), then pricing factors through the quotient space:
\[
C \to C/R \to \mathbb{R}.
\]
This is the structural version of saying that valuation depends only on the equivalence class of the claim.

### 5. Symmetry
A permutation of policy labels acts on the portfolio. The total EPV is invariant under reordering:
\[
f\left(\sum_j c_j\right)=\sum_j f(c_j).
\]
This separates expected value from dispersion effects such as variance.

### 6. Analytical stability
Term insurance can converge to whole life under monotone convergence. More general perturbations can be handled by dominated convergence. This provides a rigorous stability argument for actuarial approximations.

## Discrete Insurance Model
For benefit amount \(B\), annual premium \(P\), discount factor \(v\), and life-contingent probabilities,
\[
\text{Benefit EPV} = \sum_{k=0}^{n-1} B v^{k+1} {}_k p_x q_{x+k},
\]
\[
\text{Premium EPV} = \sum_{k=0}^{n-1} P v^k {}_k p_x.
\]

By the equivalence principle,
\[
P =
B
\frac{\sum_{k=0}^{n-1} v^{k+1} {}_k p_x q_{x+k}}
{\sum_{k=0}^{n-1} v^k {}_k p_x}.
\]

### Simplified constant-hazard model
If \(q_{x+k}=q\) is constant and \({}_k p_x = p^k\), then
\[
P = B q v.
\]
In this case, the pricing map \(\Phi(B)=\alpha B\) with \(\alpha=qv\) is a linear isomorphism onto its image, and in the scalar one-dimensional case can be viewed as a bijection on \(\mathbb{R}\).

## Continuous-Time Model
With discount function
\[
v(t)=\exp\left(-\int_0^t \delta(s) ds\right),
\]
survival function \(S_x(t)\), and force of mortality \(\mu_x(t)\),

\[
\text{Benefit EPV}
=
\int_0^\infty B \; v(t) \mu_x(t) S_x(t) \, dt,
\]

\[
\text{Premium EPV}
=
\int_0^\infty p(t) v(t) S_x(t) \, dt.
\]

Under the equivalence principle,
\[
p =
B
\frac{\int_0^\infty v(t)\mu_x(t)S_x(t) \, dt}
{\int_0^\infty v(t)S_x(t) \, dt}.
\]

## What makes this project PhD-level
This repository does not stop at calculation. It reframes actuarial valuation as a structural mathematical object and pushes toward research-style questions:

- classify kernels for richer cashflow spaces,
- characterize quotient structures induced by reinsurance contracts,
- study invariance under group actions on portfolios,
- determine when pricing functionals extend continuously to larger function spaces,
- connect actuarial valuation to functional analysis and representation theory.

## Repository Contents
- `README.md` — project overview and mathematical framing
- `paper_style_notes.md` — expanded research notes
- `presentation_expansion.md` — slide-to-paper style expansion
- `figures/epv_linearity.png` — premium vs benefit linearity figure
- `figures/kernel_cosets.png` — structural diagram for kernel / quotient interpretation

## Suggested GitHub Description
Abstract algebra and analysis view of actuarial pricing through linear functionals, kernels, quotient spaces, and EPV structure.
