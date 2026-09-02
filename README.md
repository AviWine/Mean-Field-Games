# Existence of Solutions for a Stationary Mean Field Game System

MSci Mathematics final-year project, University College London (2025–26).

This report studies a **stationary mean field game (MFG)** — a coupled system of a Hamilton–Jacobi–Bellman (HJB) equation and a Kolmogorov–Fokker–Planck (KFP) equation, which together characterise the equilibrium of a game played by a continuum of interacting agents. Under a set of structural assumptions on the Hamiltonian and coupling terms, the report proves existence of a weak solution pair using a two-stage fixed-point argument, then extends the result to a nonlinear, density-dependent source term modelling agent entry/exit.

## Overview

Mean field games (Lasry–Lions, Aumann) model systems with a very large number of interacting, individually-insignificant rational agents by replacing the discrete population with a continuum density. Each agent optimises their own cost given the aggregate behaviour of the population, and the population density in turn evolves according to each agent's optimal control — a self-consistent equilibrium. The framework underlies work in stochastic control and, in applied form, in market microstructure and optimal-execution models.

The system studied here is

```
−Δu + H(x, ∇u) + λu = f(x, m)   in Ω   (HJB)
−Δm − div(m ∂H/∂p(x, ∇u)) + λm = G(x)  in Ω   (KFP)
```

with homogeneous Dirichlet boundary conditions, where `u` is the value function of a representative agent and `m` is the player density.

## Main results

- **Theorem (existence).** Under Lipschitz/growth conditions on the Hamiltonian `H` and the coupling `f(x, m)`, and for `λ` sufficiently large, the coupled system admits a weak solution pair `(u, m) ∈ H¹₀(Ω) × H¹₀(Ω)`.
- **Method.** The two equations are solved independently first — KFP via the Lax–Milgram theorem (linear in `m`), HJB via a fixed-point map (nonlinear), using elliptic regularity to get compactness of the map. The two solution operators are then composed into a single map on `H¹₀(Ω)`, and Schaefer's fixed point theorem is applied to the composition, with an explicit, `μ`-independent bound on the fixed-point set derived via Young's and Cauchy–Schwarz inequalities.
- **Extension (original contribution).** The source term in KFP is generalised from a fixed `G(x)` to a nonlinear, density-dependent `G(x, m)` (e.g. `G(x, m) = a(x) tanh(m)`, modelling saturating entry/exit effects). The existence and uniqueness argument is re-derived under this generalisation — a result not covered explicitly in the cited literature.

## Repository contents

| File | Description |
|---|---|
| `MSciProject.tex` | LaTeX source of the full report |
| `MSciProject.pdf` | Compiled report |
| `presentation.tex` | Slides summarising the project |
| `references.bib` | Bibliography |

## Building

Requires a LaTeX distribution (e.g. TeX Live) with `latexmk`.

```bash
latexmk -pdf MSciProject.tex
latexmk -pdf presentation.tex
```

## References

1. R. J. Aumann, *Markets with a continuum of traders*, Econometrica 32(1-2), 1964.
2. P. Cardaliaguet, *Notes on mean field games*, 2013.
3. L. C. Evans, *Partial Differential Equations*, AMS, 2nd ed., 2010.
4. J.-M. Lasry and P.-L. Lions, *Mean field games*, Japanese Journal of Mathematics, 2007.
5. P. D. Lax and A. N. Milgram, *Parabolic equations*, Contributions to the Theory of Partial Differential Equations, 1954.

## Author

Avi Wine — MSci Mathematics, UCL
