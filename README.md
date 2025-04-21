# Quantum Wavefunction Evolution Simulation

## Overview
This project aims to simulate the time evolution of a quantum particle in a one-dimensional quantum system governed by the Hamiltonian:

$$\hat H = \frac{\hat p^2}{2m} + V(x)$$

In this system:
- `x` denotes the position of the particle.
- `p` denotes the momentum of the particle.
- `m` represents the mass of the particle.
- `V(x)` is the potential energy function, which will define the behavior of the wavefunction in the system.

The primary goal is to visualize the quantum wavefunction's time evolution for different energy eigenstates $\psi_n(x, t)$ using the **time-dependent Schrödinger equation**.

## Mathematical Background

### Schrödinger Equation
The time-dependent Schrödinger equation for a particle can be written as:
    
$$ i\hbar \frac{\partial \psi}{\partial t} = H \psi(x, t) $$


Substituting $\hat H = \frac{\hat{p}^2}{2m} + V(x)$ and using the canonical momentum operator $\hat{p} = -i\hbar \frac{\partial}{\partial x}$, we obtain:

$$
i\hbar \frac{\partial \psi(x, t)}{\partial t} = \left[-\frac{\hbar^2}{2m} \frac{\partial^2}{\partial x^2} + V(x)\right] \psi(x, t).
$$



For a stationary potential $V(x)$, the time evolution of the wavefunction is determined by the eigenstates of the Hamiltonian. Solving the **time-independent Schrödinger equation**,

$$
\hat H | \psi_n(x) \rangle = E_n | \psi_n(x) \rangle
$$


provides the energy eigenvalues $E_n$ and eigenfunctions $ \psi_n(x) $. Using these, a general wavefunction is expressed as:
    
$$
\psi(x, t) = \sum_n c_n \psi_n(x) e^{-iE_n t / \hbar}
$$


where $c_n$ are the coefficients for the eigenstate decomposition.

### Time Evolution
By selecting specific energy eigenstates or superpositions of eigenstates $\psi(x, t) = \sum_n c_n \psi_n(x) $, we can utilize their time-dependent factor $ e^{-iE_n t / \hbar} $ to study how the wavefunction evolves over time.

### Visualization Goals
- Visualize $ |\psi(x, t)|^2 $, the probability density of the particle, for different energy levels $n$.
- Analyze the behavior of $ \psi(x, t) $ for various potential functions $V(x)$.

## Project Structure

### Features
1. **Hamiltonian Simulation**:
    - Solve the time-independent Schrödinger equation to compute $\psi_n(x)$ and $E_n$.
2. **Wavefunction Time Evolution**:
    - Visualize the evolution of the probability density $|\psi(x, t)|^2 $.
3. **Potential Use Cases**:
    - Simple potentials $V(x)$: e.g. free particle, infinite square well, harmonic oscillator.
    - Customizable user-defined potentials.

### Visualizations
The simulation will generate dynamic visualizations showcasing:
1. The initial wavefunction.
2. The system's evolution over time.
3. Comparisons between different energy eigenstates.

## Dependencies
The simulation will use the following Python libraries:
- **numpy**: Efficient numerical routines (e.g., solving differential equations).
- **scipy**: For solving eigenvalue problems in the Hamiltonian.
- **matplotlib**: Visualization of the wavefunction and probability density.
- **ffmpeg**: To create animations for wavefunction evolution.
- **seaborn**: Additional aesthetic visualizations.

Ensure you have Python 3.9+ installed.

## Usage Instructions
1. Clone this repository into your working directory.
2. Install required dependencies using:
   ```bash
   pip install -r requirements.txt
   ```
3. Define the Hamiltonian parameters and potential $ V(x) $ using configuration scripts.
4. Run the simulation script to generate eigenvalues, eigenfunctions, and visualizations.
5. Explore or modify predefined examples in the `/notebooks` folder.

## Example Test Cases
### Infinite Square Well
A particle trapped in an infinite square potential well:

$$
\cases{V(x) = 0 \quad & $\text{for } 0 \leq x \leq L$ \\
       \infty \quad & \text{elsewhere}}
$$

Wavefunctions $ \psi_n(x) $ and energy levels $E_n $ are well-known, making it an ideal test case.

### Quadratic Potential (Harmonic Oscillator)
The classic example of $ V(x) = 0.5kx^2 $, representing a harmonic oscillator.

## Future Extensions
- Extend to higher-dimensional systems (e.g., 2D or 3D quantum wells).
- Incorporate non-stationary potentials $ V(x, t) $ for time-varying phenomena.
