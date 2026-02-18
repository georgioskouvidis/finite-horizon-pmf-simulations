# Finite-Horizon Freedom Maximization in Directed Acyclic Growth

This repository contains simulation code supporting the paper:

**“Finite-Horizon Freedom Maximization in Directed Acyclic Growth.”**

The code implements Monte Carlo approximations of finite-horizon structural freedom
and compares freedom-maximizing growth (PMF) with random admissible growth
under bounded memory and bounded branching constraints.

---

## Overview

The simulations investigate structural consequences of the finite-horizon
Principle of Maximal Freedom (PMF) defined on directed acyclic graphs (DAGs)
under explicit finite branching assumptions.

The computational study examines:

- Baseline PMF vs random admissible growth
- Horizon sensitivity (H-sweep)
- Branching capacity scaling (Δ-sweep)
- Memory depth scaling (d-sweep)

Structural metrics include:

- Admissible extension set size |Adm(G)|
- Longest chain length (causal depth)
- Boundary size
- Out-degree statistics

The purpose of the simulations is structural comparison, not numerical optimization.

---

## Constraint Environment

Growth is performed under the parameterized constraint family:

K(d, Δ, k_max)

where:

- d: memory depth (attachment window)
- Δ: maximum out-degree per node
- k_max: maximum number of parents per new event
- Parent sets must form an antichain

All simulations use finite states and bounded branching.

---

## Methodology

Finite-horizon structural freedom Φ_H(G) is estimated using Monte Carlo rollouts
for computational tractability.

For each admissible move e, the one-step score

Ψ_H(G, e) = Φ_{H-1}(G ⊕ e)

is approximated via bounded-depth sampling.

Multiple independent runs are averaged to obtain structural statistics.

Random seeds are fixed where indicated to ensure reproducibility.

---

## Requirements

- Python 3.x
- numpy
- matplotlib

No additional external dependencies are required.

---

## Reproducibility

All experiments reported in the associated paper can be reproduced
by running the notebook in sequence.

Simulation parameters (number of runs, horizon H, branching Δ, memory depth d)
are explicitly specified in the notebook cells.

---

## Disclaimer

This repository provides computational support for a formal investigation of
finite-horizon growth operators under bounded constraints.  
It does not claim universality beyond the explored constraint families
and finite-state settings.

---

## License

This code is provided for academic and research use.

