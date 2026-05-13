# Numerical Analysis of the Wheeler–DeWitt Equation in Minisuperspace

## Overview

This repository contains the numerical implementation developed for the Bachelor's Thesis:

**“Quantum Cosmology: Wheeler–DeWitt Equation and Boundary Conditions”**

The project focuses on the study of the Wheeler–DeWitt (WDW) equation in a minisuperspace model, with particular emphasis on the role of boundary conditions in quantum cosmology. Specifically, the Hartle–Hawking no-boundary proposal and the Vilenkin tunneling proposal are implemented and compared.

The numerical framework evaluates semiclassical (WKB) solutions of the WDW equation on a discretized minisuperspace grid.


## Physical Model

The model considers a homogeneous and isotropic universe described by the Friedmann–Robertson–Walker (FRW) metric, coupled to a scalar field $\phi$.

* Minisuperspace variables: $(a, \phi)$
* Compactified variable:
  [
  x = \frac{a}{1+a}, \quad x \in (0,1)
  ]
* Scalar field potential:
  [
  V(\phi) = V_0 + m\left(1 + \cos\left(\frac{\pi \phi}{\Delta}\right)\right)
  ]
* Hubble parameter:
  [
  \mathcal{H}^2(\phi) = \frac{8\pi}{3} V(\phi)
  ]

The Wheeler–DeWitt equation is evaluated in semiclassical approximation.


## Boundary Conditions Implemented

### 1. Hartle–Hawking No-Boundary Proposal

* Regular wave function at $a \to 0$
* Exponential behavior in the quantum region
* Oscillatory behavior in the classical regime

### 2. Vilenkin Tunneling Proposal

* Outgoing modes only in the classical region
* Exponential suppression in the quantum region
* Breaks time-reversal symmetry


## Numerical Methodology

* Discretization of minisuperspace: $(x, \phi)$ grid
* Finite domain: $x \in (0,1)$
* Vectorized implementation using NumPy
* Region separation via boolean masks:

  * Quantum region: $\frac{\mathcal{H}^2 x^2}{(1-x)^2} < 1$
  * Classical region: $\frac{\mathcal{H}^2 x^2}{(1-x)^2} \geq 1$

The wave function is constructed piecewise using semiclassical expressions.


## Output and Visualization

The program generates:

* 3D surface plots of:
  [
  \log |\psi(x,\phi)|
  ]
* 2D slices showing dependence on $\phi$
* Quantitative measures:

  * Maximum amplitude
  * Value at the classical/quantum transition


## Parameter Regimes

Two regimes are explored:

* **Slow-roll regime** ($V_0 > m$):
  Smooth behavior of the wave function

* **Non slow-roll regime** ($V_0 < m$):
  Strong oscillatory dependence on $\phi$



## Requirements

* Python 3.x
* NumPy
* Matplotlib

Install dependencies with:

```bash
pip install numpy matplotlib
```


## Usage

Run the main script:

```bash
python main.py
```

Modify parameters directly in the script:

* Grid resolution
* Potential parameters ($V_0$, $m$, $\Delta$)
* Domain ranges


## Structure

.
├── main.py
└── README.md

##  Reference

This code was developed as part of the Bachelor's Thesis:

> *Quantum Cosmology: Wheeler–DeWitt Equation and Boundary Conditions*

The full theoretical framework and derivations can be found in the accompanying written document.


## Notes

* This implementation evaluates semiclassical approximations and does not solve the full Wheeler–DeWitt equation numerically.
* Results should be interpreted within the validity of the WKB approximation.



## Author

Paula Andrea Monrabal Cutanda,
Bachelor's Degree in Physics,
Universidad Europea de Valencia,
2026
