## Project Overview

Ribosome motion during genetic translation is modeled using the **Totally Asymmetric Simple Exclusion Process (TASEP)**, with validation via Monte Carlo simulations. It is then extended to a **ballistic model**, an approximation of TASEP in the low-density regime, characterized by deterministic ribosome movement without excluded volume interactions and incorporating finite mRNA lifetime. The model includes the partitioning of mRNAs into **k-somes** (monosomes, disomes, trisomes, and tetrasomes) and estimation of kinetic parameters such as the initiation rate `α` and elongation rates `p`. Predictions are compared against **Ribo-seq experimental data**.

## 🧬 Model Description

The **Totally Asymmetric Simple Exclusion Process (TASEP)** is a stochastic model describing particles moving unidirectionally on a one-dimensional lattice under an exclusion constraint, where each site can be occupied by at most one particle. This framework models ribosome translation on mRNA.

In this model:
- Ribosomes **initiate** at the first site with rate `α`,
- **Elongate** through the lattice with rate `p`, only if the next site is empty,
- **Terminate** at the final site with rate `β`,
- And the mRNA **degrades** with rate `ω`, limiting its lifetime.


<img width="2986" height="936" alt="mRNA_translation" src="https://github.com/user-attachments/assets/c4e2e0f4-0b73-42af-8767-7b5610716897" />



## **📈 Simulation Method**
The **random sequential update rule** is used:
- At each time step, a site is randomly selected.
- If the site is occupied and the next site is empty, the particle moves with probability \( p \).
- Particles enter and exit based on the boundary conditions \( \alpha \) and \( \beta \).

## **🚀 Running the Simulation**
Run different regimes with:
```bash
python src/high_density.py
python src/low_density.py
python src/maximal_current.py
```

## **📄 References**
- Derrida, B., Domany, E., & Mukamel, D. (1992). *Exact solution of a one-dimensional asymmetric exclusion model with open boundaries*. Journal of Statistical Physics.
- MacDonald, C. T., Gibbs, J. H., & Pipkin, A. C. (1968). *Kinetics of biopolymerization on nucleic acid templates*. Biopolymers.




