Finite-Horizon PMF DAG Growth Simulations

This repository contains simulation code supporting the study “Finite-Horizon Freedom Maximization in Constrained Directed Acyclic Graph Growth” by Georgios Kouvidis. The code implements Monte Carlo simulations and diagnostic tools used to analyze the structural consequences of the Principle of Maximal Freedom (PMF) in constrained directed acyclic graph growth systems.

Directed acyclic growth processes arise in many combinatorial and stochastic systems where structural constraints limit admissible extensions. In such systems, admissibility alone does not determine which extension occurs; a selection rule is required. The simulations in this repository explore a growth rule based on the finite-horizon Principle of Maximal Freedom, under which admissible extensions are evaluated according to the number of admissible future growth trajectories they preserve over a fixed horizon.

The repository includes two main computational components. The first is a PMF DAG Growth Simulator that performs Monte Carlo simulations of constrained DAG growth under the finite-horizon PMF rule. The second is a Continuation Landscape Analyzer that estimates continuation multiplicities for admissible extensions and allows visualization of the ranked continuation landscape across admissible branches. These tools were used to generate the simulation results and diagnostics described in the accompanying research paper.

In the model, the growth process proceeds by sequentially adding vertices and precedence relations while preserving acyclicity and satisfying structural constraints. The constraint family used in the experiments is characterized by a memory depth parameter d, a maximum out-degree Δ, a parent cap k_max, and an antichain restriction on admissible parent sets. These constraints determine the set of admissible extensions Adm(G) available from a given state G.

For a fixed evaluation horizon H, the continuation multiplicity Φ_H(G) represents the number of admissible continuation sequences of length H starting from state G. For each admissible extension e, the one-step freedom score Ψ_H(G,e) is defined as the continuation multiplicity of the successor state G ⊕ e over horizon H−1. The deterministic PMF rule selects the admissible extension that maximizes this continuation multiplicity, while probabilistic variants select extensions according to a softmax distribution over the same scores.

Typical simulation experiments involve 30–40 independent runs of DAG growth over approximately 20 steps, using a finite evaluation horizon (commonly H = 3) and Monte Carlo sampling to estimate continuation multiplicities when exact enumeration becomes computationally expensive. A key observable used in the experiments is the admissible branching proxy b(G) = |Adm(G)|, which measures the size of the admissible extension set at a given state. Comparisons between PMF-driven growth and random admissible growth reveal systematic structural differences, including larger admissible frontiers and reduced longest-chain depth under PMF selection.

The continuation landscape analyzer estimates continuation multiplicities for all admissible first-step extensions from representative states and ranks them to visualize the continuation landscape. These diagnostics reveal that admissible branches often possess significantly different continuation capacities, forming a heterogeneous spectrum rather than a binary classification of viable versus non-viable extensions. PMF selections consistently occur near the upper portion of this spectrum, illustrating how freedom-maximizing growth tends to preserve larger sets of admissible future trajectories.

The code is written in Python and requires standard scientific computing libraries such as NumPy, NetworkX, and Matplotlib. Experiments included in the repository reproduce the parameter sweeps and continuation landscape diagnostics described in the accompanying paper.

If you use this code in academic work, please cite the associated paper and the archived software release. The software is intended as a research tool for exploring constrained growth processes, continuation multiplicity analysis, and freedom-maximizing selection dynamics in directed acyclic systems.

Author: Georgios Kouvidis
Independent Researcher
Year: 2026
