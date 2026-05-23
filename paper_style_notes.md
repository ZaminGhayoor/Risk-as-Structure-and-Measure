# Paper-Style Notes

## 1. Motivation
Actuarial science is usually taught analytically: one computes expected present value by summing or integrating discounted cashflows against probabilities. That perspective is essential, but incomplete. It explains **how to calculate**, not always **how to organize the structure** of risk.

This project studies actuarial pricing through two complementary lenses:

- **Analysis** provides convergence, expectation, integration, and discounting.
- **Algebra** provides linearity, equivalence, kernels, quotient spaces, and symmetry.

The goal is not to replace actuarial formulas, but to reinterpret them in a more structural language.

## 2. Cashflows as algebraic objects
A cashflow stream is modeled as a sequence
\[
c=(c_0,c_1,c_2,\dots).
\]
With pointwise addition and scalar multiplication, these objects form a vector space over \(\mathbb{R}\). This means one can speak about linear maps, subspaces, kernels, and quotient spaces naturally.

In actuarial language:
- adding cashflows corresponds to combining liabilities,
- scaling corresponds to resizing exposures,
- zero corresponds to a null claim.

## 3. Pricing as a linear functional
Define the pricing map by
\[
f(c)=\mathbb{E}\left[\sum_{t \ge 0} v^t c_t\right].
\]
When the discounted series is absolutely summable, this map is linear.

This is a powerful shift in viewpoint: actuarial valuation becomes a functional on a space of risks.

## 4. Kernel and equivalence
The kernel is
\[
\ker(f)=\{c: f(c)=0\}.
\]
Any cashflow in the kernel has zero expected present value. Therefore, if two cashflows differ by an element of the kernel, they have identical price. This motivates the equivalence relation
\[
c_1 \sim c_2 \iff c_1-c_2 \in \ker(f).
\]

This is the structural meaning of financial equivalence.

## 5. Quotient spaces and reinsurance
Suppose a class of reinsurance adjustments lies in a subspace \(R\subseteq\ker(f)\). Then pricing does not depend on the representative cashflow but only on its class in the quotient
\[
C/R.
\]
This is a direct application of the First Isomorphism Theorem:
the pricing map factors through the quotient.

This gives a clean algebraic interpretation of why certain transformations do not alter price.

## 6. Symmetry and portfolios
If a portfolio consists of individual claims \(c_1,\dots,c_n\), then
\[
f\left(\sum_{j=1}^n c_j\right)=\sum_{j=1}^n f(c_j).
\]
Thus reordering the contracts does not affect total EPV. A permutation group acts on the portfolio, and the valuation is invariant under that action.

This separates expected-value structure from higher-order portfolio effects such as variance and tail dependence.

## 7. Stability under limits
Actuarial approximations often rely on passing to limits:
- term insurance approaching whole life,
- stepwise approximations to continuous payments,
- perturbations of mortality or discount assumptions.

These can be justified analytically through monotone convergence or dominated convergence, showing that valuation is stable under suitable approximating sequences.

## 8. Future research directions
The natural next step is to expand beyond finite-dimensional or absolutely summable spaces. Questions include:
- Which Banach or Hilbert spaces of cashflows support continuous pricing maps?
- How should actuarial kernels be classified under richer contract structures?
- Can reinsurance operators be studied as endomorphisms or quotient-inducing maps?
- What symmetries appear in large homogeneous portfolios?

These questions move the project from expository mathematics toward research mathematics.
