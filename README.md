# Vortex Blinking Simulation in Hamiltonian Chaos

### Formulation

1. **Stream Function (Ψ):** 
   In potential flow theory, the stream function is a scalar function whose contours represent the flow lines of the fluid. For a vortex, the stream function Ψ at a point (x, y) in the plane is given by:
   $$
   Ψ(x, y) = \frac{Γ}{2π} \ln\sqrt{(x - x_0)^2 + (y - y_0)^2}
   $$
   Here, $Γ$ is the circulation of the vortex, and $(x_0, y_0)$ is the position of the vortex center. The circulation $Γ$ determines the strength and the rotational direction of the vortex.

2. **Velocity Field:** 
   The velocity components (u, v) at any point (x, y) in the flow field can be derived from the stream function. They are given by the partial derivatives of Ψ:
   $$
   u(x, y) = \frac{\partial Ψ}{\partial y}, \quad v(x, y) = -\frac{\partial Ψ}{\partial x}
   $$
   Substituting the expression for Ψ and simplifying, we get:
   $$
   u(x, y) = -\frac{Γ}{2π} \frac{y - y_0}{(x - x_0)^2 + (y - y_0)^2}, \quad v(x, y) = \frac{Γ}{2π} \frac{x - x_0}{(x - x_0)^2 + (y - y_0)^2}
   $$
   These expressions describe the velocity field around the vortex.

3. **Regularization with Delta (δ):**
   In numerical simulations, a small parameter δ is often added to the denominator to avoid the singularity at the vortex center:
   $$
   u(x, y) = -\frac{Γ}{2π} \frac{y - y_0}{(x - x_0)^2 + (y - y_0)^2 + δ^2}, \quad v(x, y) = \frac{Γ}{2π} \frac{x - x_0}{(x - x_0)^2 + (y - y_0)^2 + δ^2}
   $$
   This δ term helps to avoid numerical issues when the point (x, y) is very close to the vortex center (x_0, y_0).


## Parameter Overview

- **delta**: A small numerical value to avoid singularities 
- **vortex_frequency**: Controls how frequently the active vortex switches
- **orientation**: Sets the initial orientation of vortex interaction
