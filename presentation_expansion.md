# Slide-to-Paper Expansion

## Original theme
The original presentation argued that actuarial pricing has both an analytical side and an algebraic side. This document expands that theme into a more research-oriented project.

## Slide 1-2: Motivation
Expected present value is usually introduced as a calculation. The deeper claim of this project is that EPV is also a structural map on a space of risks.

## Slide 3: Cashflow space
A cashflow stream is treated as a vector in a space of sequences. This gives immediate access to:
- addition,
- scalar multiplication,
- subspaces,
- linear maps.

## Slide 4-5: Discrete pricing
The discrete insurance premium formula is interpreted as a linear functional in the benefit variable.
Under simplified assumptions, the premium becomes:
P = B q v
which makes the pricing map visibly linear.

## Slide 6: Continuous-time pricing
The continuous model replaces sums with integrals:
benefits and premiums become weighted integrals against mortality and survival terms.
This shows the transition from discrete linear algebra to analysis.

## Slide 7: Kernel and bijection
The pricing map may be injective in simple scalar settings, but the more important general phenomenon is the existence of a nontrivial kernel on richer cashflow spaces.
The kernel defines equivalence classes of financially indistinguishable risks.

## Slide 8: Portfolio symmetry
Permuting policy labels does not change total EPV. This can be treated as a group action preserving valuation.

## Slide 9: Convergence
Actuarial approximations can be justified by convergence theorems, providing analytical stability to the algebraic framework.

## Slide 10: Reinsurance
If a family of reinsurance transformations lies in the kernel, then pricing factors through a quotient space. This is where abstract algebra becomes genuinely explanatory rather than decorative.

## Slide 11-12: Worked example and synthesis
A simple numerical premium formula is included for intuition, but the real significance lies in the structural view:
actuarial pricing can be studied as a linear and quotient-compatible object.
