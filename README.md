# Risk as Structure and Measure

## Abstract
This repository develops an algebraic and analytical framework for actuarial pricing. The central idea is that expected present value (EPV) should be viewed not only as a probability-based calculation, but also as a linear map on a space of cashflows. This allows actuarial models to be studied using vector spaces, kernels, quotient spaces, group actions, and continuity arguments.

The project begins with classical actuarial formulas for discrete and continuous insurance models, then reframes them in a more structural way:
- cashflows are elements of a vector space,
- pricing is a linear functional,
- financial equivalence is captured by cosets of the kernel,
- portfolio rearrangements are modeled by group actions,
- reinsurance is interpreted through quotient structures,
- and stability is handled through convergence theorems.

The result is a mathematically richer perspective on risk that connects abstract algebra, real analysis, and actuarial science.

## Core Thesis
Expected present value can be treated as a map

`f(c) = E[sum_{t >= 0} v^t c_t]`

from a cashflow space into the real numbers. Once that perspective is adopted, the following questions become natural:

1. What algebraic structure does the cashflow space carry?
2. What is the kernel of the pricing map?
3. When do two risks become equivalent under pricing?
4. How does reinsurance factor through quotient spaces?
5. Which limits preserve actuarial valuation?

## Algebraic and Analytical Framework

### 1. Cashflow space
A cashflow is a sequence

`c = (c_0, c_1, c_2, ...)`

where `c_t` represents the payment at time `t`.

With addition and scalar multiplication defined pointwise, the collection of all such cashflows forms a vector space (or more generally a module, depending on the scalars used).

This provides the algebraic setting for actuarial valuation.

### 2. Expected present value as a pricing map
Define the expected present value map by

`f(c) = E[sum_{t >= 0} v^t c_t]`

If the discounted series is absolutely convergent, then `f` is linear:

`f(c + d) = f(c) + f(d)`

`f(alpha c) = alpha f(c)`

So expected present value is not just a numerical calculation; it is a linear functional on the space of cashflows.

### 3. Kernel and financial equivalence
The kernel of the pricing map is

`ker(f) = {c : f(c) = 0}`

These are exactly the cashflows with zero expected present value.

Two cashflows are financially equivalent if they differ by an element of the kernel, since they receive the same value under `f`.

### 4. Quotient interpretation
If a class of reinsurance adjustments lies in a subspace `R ⊆ ker(f)`, then valuation depends only on the equivalence class of the cashflow. In that case, the pricing map factors through the quotient space:

`C -> C/R -> R`

This is the structural meaning of saying that certain reinsurance modifications do not change value.

### 5. Portfolio symmetry
A permutation of policy labels acts on a portfolio by reordering its individual cashflows. Since expected present value is additive,

`f(sum_j c_j) = sum_j f(c_j)`

the total EPV is unchanged by such reordering.

This shows that valuation is invariant under permutation, even though other quantities such as variance may still change.

### 6. Analytical stability
The algebraic structure explains how risks are organized, but analysis explains why the formulas behave well under limits.

For example:
- term insurance can converge to whole life by the Monotone Convergence Theorem,
- model perturbations can be handled by the Dominated Convergence Theorem.

This gives a rigorous stability argument for actuarial approximations.

## Discrete Insurance Model

For a benefit amount `B`, annual premium `P`, discount factor `v`, and life-contingent probabilities, the expected present values are

`Benefit EPV = sum_{k=0}^{n-1} B v^(k+1) {}_k p_x q_{x+k}`

`Premium EPV = sum_{k=0}^{n-1} P v^k {}_k p_x`

By the equivalence principle, these must be equal, so

`P = B * [sum_{k=0}^{n-1} v^(k+1) {}_k p_x q_{x+k}] / [sum_{k=0}^{n-1} v^k {}_k p_x]`

This is the discrete actuarial pricing formula viewed as a linear valuation rule.

### Simplified constant-hazard model
If mortality is constant so that `q_{x+k} = q` and `{}_k p_x = p^k`, then the premium simplifies to

`P = B q v`

In this case the pricing map becomes

`Phi(B) = alpha B`, where `alpha = qv`

which is linear. In the one-dimensional scalar setting, this can be treated as a bijection from benefit amount to premium.

## Continuous-Time Model

In continuous time, sums are replaced by integrals. Let

`v(t) = exp(-integral_0^t delta(s) ds)`

be the discount function, `S_x(t)` the survival function, and `mu_x(t)` the force of mortality.

Then

`Benefit EPV = integral_0^∞ B v(t) mu_x(t) S_x(t) dt`

and

`Premium EPV = integral_0^∞ p(t) v(t) S_x(t) dt`

Under the equivalence principle,

`p = B * [integral_0^∞ v(t) mu_x(t) S_x(t) dt] / [integral_0^∞ v(t) S_x(t) dt]`

This is the continuous analogue of the discrete formula, now expressed through integration.

## What makes this project research-oriented
This project does not stop at calculation. It reframes actuarial valuation as a structural mathematical object and pushes toward questions such as:
- classifying kernels for richer cashflow spaces,
- characterizing quotient structures induced by reinsurance contracts,
- studying invariance under group actions on portfolios,
- determining when pricing maps extend continuously to larger function spaces,
- and connecting actuarial valuation to functional analysis and algebraic structure.

## Repository Contents
- `README.md` — project overview and mathematical framing
- `paper_style_notes.md` — expanded research notes
- `presentation_expansion.md` — slide-to-paper style expansion
- `figures/epv_linearity.png` — premium vs benefit linearity figure
- `figures/kernel_cosets.png` — structural diagram for kernel / quotient interpretation

## Suggested GitHub Description
Abstract algebra and analysis view of actuarial pricing through linear functionals, kernels, quotient spaces, and expected present value structure.
