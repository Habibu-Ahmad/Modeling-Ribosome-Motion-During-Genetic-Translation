## Project Overview

Ribosome motion during genetic translation is modeled using the **Totally Asymmetric Simple Exclusion Process (TASEP)**, with validation via Monte Carlo simulations. It is then extended to a **ballistic model**, an approximation of TASEP in the low-density regime, characterized by deterministic ribosome movement without excluded volume interactions and incorporating finite mRNA lifetime. The model includes the partitioning of mRNAs into **k-somes** (monosomes, disomes, trisomes, and tetrasomes) and estimation of kinetic parameters such as the initiation rate `α` and elongation rates `p`. Predictions are compared against **Ribo-seq experimental data**.
<img width="2986" height="936" alt="mRNA_translation" src="https://github.com/user-attachments/assets/c4e2e0f4-0b73-42af-8767-7b5610716897" />

## **📜 Model Description**
The **Totally Asymmetric Simple Exclusion Process (TASEP)** is a stochastic model describing particles moving on a **one-dimensional lattice** under exclusion constraints. Each site can hold at most one particle.

- A particle enters the **first site** with rate \(\alpha\) if the site is empty.
- At site \( i \), the particle **hops to \( i+1 \) with rate \( p \)** if the next site is empty.
- A particle exits the **last site** (\( L \)) with rate \( \beta \).

### **🔹 Lattice Representation**
![m<img width="2986" height="936" alt="mRNA_translation" src="https://github.com/user-attachments/assets/40ec932f-7b77-4580-aa67-f68f3fa1dffb" />
](https://github.com/user-attachments/assets/cca1b584-dd40-4bc1-b125-80ab835de9ce)

## **📊 Phases of TASEP**
TASEP exhibits three steady-state phases:

1. **High-Density (HD) Phase**: If \( \alpha > 0.5 \), the density is controlled by the entry rate, \( \rho = 1 - \beta \).
2. **Low-Density (LD) Phase**: If \( \beta > 0.5 \), the density is controlled by the exit rate, \( \rho = \alpha \).
3. **Maximal Current (MC) Phase**: If both \( \alpha, \beta > 0.5 \), the system reaches a maximal flow state with \( \rho = 1/2 \).

The fundamental **current-density relation** is:

$$
J(\rho) = \rho(1 - \rho)
$$

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




