# Kuramoto Model: Phase Transitions & Synchronization

**Course:** IDC621 Modelling Complex Systems (Term Paper 2)  
**Author:** [Your Name]  

This repository contains a high-performance Python simulation of the **Kuramoto model**, a foundational mathematical framework used to study synchronization in complex systems. The code models a large population of coupled limit-cycle oscillators and visualizes their macroscopic phase transitions.

## 📌 Project Overview

The Kuramoto model describes phenomena ranging from the synchronous flashing of fireflies to the firing of pacemaker neurons and the stability of power grids. This project numerically integrates the governing differential equations of the model to explore:
* How varying the global coupling strength (`K`) drives the system from incoherence to full synchronization.
* The dependence of the critical coupling threshold (`Kc`) on the underlying natural frequency distribution (Normal, Uniform, and Lorentzian).
* The bifurcation of the oscillator population into "phase-locked" and "drifting" states.

## ⚙️ Computational Methodology

To ensure physical accuracy and computational efficiency, this simulation employs:
1. **Mean-Field Reduction:** The standard O(N²) calculation for oscillator interactions is reduced to O(N) by calculating the complex order parameter `r`, which acts as the mean field.
2. **Runge-Kutta 4th Order (RK4):** A highly stable RK4 integration scheme is used in place of standard Euler methods to prevent numerical drift over long simulation times.
3. **Vectorization:** Written utilizing `NumPy` array operations to rapidly simulate thousands of oscillators simultaneously.

## 🚀 Installation & Usage

### Prerequisites
The code is written in standard Python (or as a Jupyter Notebook) and requires the following libraries:
* `numpy`
* `matplotlib`

You can install them via pip:
`pip install numpy matplotlib`

### Running the Code
Simply clone the repository and run the Python script or open the Jupyter Notebook:
`python "Kuramoto Model.py"`

## 📊 Results and Visualizations

The simulation generates three primary figures (included in this repository):

* **`fig1_dynamics.png`**: Displays the time evolution of the order parameter `r(t)` alongside polar plots of the final phase distributions, proving the collapse of the phases into a synchronized cluster at high coupling strengths.
* **`fig2_distributions.png`**: Maps the steady-state order parameter against coupling strength `K` for Normal, Uniform, and Lorentzian distributions. The empirical data strongly matches theoretical critical coupling predictions.
* **`fig3_transition.png`**: Plots the effective frequencies against the natural frequencies, visually distinguishing the oscillators entrained by the mean field (locked) from those that are spinning too fast/slow to be caught (drifting).

## 📁 Repository Structure

* `Kuramoto Model.py` (or `.ipynb`): The main simulation code containing the RK4 integrator and visualization logic.
* `fig1_dynamics.png`: Plot of system dynamics and polar phase distributions.
* `fig2_distributions.png`: Plot of continuous phase transitions.
* `fig3_transition.png`: Scatter plot of effective vs. natural frequencies.
* `report.pdf` / `report.tex`: The LaTeX source and compiled PDF for the formal IDC621 term paper.

## 📝 License
This project is open-source and available under the MIT License.
