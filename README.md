## Project Overview

This project models ribosome motion during genetic translation using the **Totally Asymmetric Simple Exclusion Process (TASEP)** and validates it with simulations. The framework is extended to a **ballistic model**, an approximation of TASEP in the low-density regime, characterized by deterministic ribosome movement without excluded volume interactions and incorporating finite mRNA lifetime. The model partitions mRNAs into **k-somes** (monosomes, disomes, trisomes, and tetrasomes) and estimates kinetic parameters such as the initiation rate `α` and elongation rate `p`. Predictions are compared to **Ribo-seq experimental data**.

##  Model Description

The **Totally Asymmetric Simple Exclusion Process (TASEP)** is a stochastic model describing particles moving unidirectionally along a one-dimensional lattice under an exclusion constraint, where each site can be occupied by at most one particle. This framework is applied to ribosome translation on mRNA.

In this model:
- Ribosomes **initiate** at the first site with rate `α`,
- **Elongate** along the lattice with rate `p`, provided the next site is unoccupied,
- **Terminate** at the final site with rate `β`,
- Taking into account the finite mRNA lifetime, **degradation** occurs with rate `ω`.

<img width="2986" height="636" alt="mRNA_translation" src="https://github.com/user-attachments/assets/c4e2e0f4-0b73-42af-8767-7b5610716897" />


## **Simulation Method**
The **random sequential update rule** is used:
- At each time step, a site is randomly selected.
- If the site is occupied and the next site is empty, the particle moves with probability \( p \).
- Particles enter and exit based on the boundary conditions \( \alpha \) and \( \beta \).



## **References**
- Derrida, B., Domany, E., & Mukamel, D. (1992). *Exact solution of a one-dimensional asymmetric exclusion model with open boundaries*. Journal of Statistical Physics.
- MacDonald, C. T., Gibbs, J. H., & Pipkin, A. C. (1968). *Kinetics of biopolymerization on nucleic acid templates*. Biopolymers.
- Chevalier, C., Dorignac, J., Ibrahim, Y., Choquet, A., David, A., Ripoll, J., Rivals, E., Geniet, F., Walliser, N.-O., Palmeri, J., Parmeggiani, A., & Walter, J.-C. (2022). *Physical modeling of ribosomes along messenger RNA: Estimating kinetic parameters from ribosome profiling experiments using a ballistic model*. arXiv preprint arXiv:2208.12576. https://arxiv.org/abs/2208.12576



