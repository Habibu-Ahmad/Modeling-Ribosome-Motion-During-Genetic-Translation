# **TASEP Simulation in Python**

## **📜 Model Description**
The **Totally Asymmetric Simple Exclusion Process (TASEP)** is a stochastic model describing particles moving on a **one-dimensional lattice** under exclusion constraints. Each site can hold at most one particle.

- A particle enters the **first site** with rate \(\alpha\) if the site is empty.
- At site \( x \), the particle **hops to \( x+1 \) with rate \( p \)** if the next site is empty.
- A particle exits the **last site** (\( L \)) with rate \( \beta \).

### **🔹 Lattice Representation**
![Icon Pack - mRNA (2)](https://github.com/user-attachments/assets/73ad909f-289e-4ffd-bbce-102677d6f07d)

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




