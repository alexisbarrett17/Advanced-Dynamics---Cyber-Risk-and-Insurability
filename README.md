Advanced Dynamics Project
Nonlinear Cyber Insurability Dynamics

Overview
This project models cyber risk and insurability dynamics using a three-dimensional nonlinear dynamical system inspired by predator–prey interactions and feedback control mechanisms. The objective is not prediction, but qualitative analysis of stability, sensitivity, and long-term behavior in complex risk systems.

The model captures interactions between organizational vulnerabilities, attack pressure, and insurer confidence, and explores how nonlinear feedback can generate threshold effects, oscillatory behavior, and sensitivity to initial conditions.

Mathematical Model
The system evolves according to the ordinary differential equations

dx/dt = αx − βxy − γxz
dy/dt = δxy − εy
dz/dt = θxz − ψz

where:

x(t) represents vulnerability level
y(t) represents attack pressure
z(t) represents insurability or underwriter confidence

Parameter Interpretation

α : intrinsic vulnerability growth
β : attack–vulnerability interaction
γ : mitigation pressure induced by insurance
δ : attack amplification
ε : natural attack decay
θ : insurer responsiveness
ψ : information decay or underwriting uncertainty

All parameters are taken to be positive, and state variables are constrained to remain nonnegative.

Numerical Method
The system is solved numerically using a fourth-order Runge–Kutta (RK4) method implemented explicitly in the code. The time step is dt = 0.01, and simulations are run for time horizons up to T = 150. Nonnegativity is enforced after each integration step.

The numerical solutions are intended for qualitative exploration rather than high-precision prediction.

Simulations and Visualizations
The script produces the following outputs:

1. Time-series plots of x(t), y(t), and z(t), illustrating coupled nonlinear evolution and feedback effects.

2. A two-dimensional phase portrait in the (x, z) plane, highlighting the relationship between vulnerability and insurability over time.

3. A three-dimensional phase-space trajectory (x, y, z), revealing global structure of the system’s flow.

4. A sensitivity-to-initial-conditions experiment, in which two nearly identical initial states are evolved forward and their separation is plotted on a logarithmic scale, demonstrating exponential divergence consistent with chaotic or near-chaotic dynamics.

File Structure
All components are contained within a single Python file:

cyber_insurability_dynamics.py

This file includes the model definition, RK4 integrator, simulation routines, visualization code, and sensitivity analysis.

Dependencies
Python 3.x
NumPy
Matplotlib

Execution
Running the script will automatically generate all figures. No additional configuration is required.

Key Observations
The system exhibits strong nonlinear coupling across all three state variables. Small perturbations in initial conditions lead to rapid divergence of trajectories. Insurability acts as a feedback control variable that significantly influences long-term system behavior. The model naturally produces threshold effects and path dependence.

These characteristics align with known features of complex risk systems subject to delayed response and incomplete information.

Scope and Limitations
This model is theoretical and illustrative. It is not calibrated to empirical data and should not be interpreted as a predictive cyber risk or insurance tool. Its purpose is to demonstrate how nonlinear dynamics and sensitivity emerge in applied risk contexts.

Academic Context
This project was completed for an Advanced Dynamics / Nonlinear Systems course and emphasizes continuous-time ODE modeling, phase-space analysis, numerical integration, and sensitivity to initial conditions. No prior background in cybersecurity is required to understand the mathematical results.
