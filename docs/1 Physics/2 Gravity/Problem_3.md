# Problem 3: Trajectories of a Freely Released Payload Near Earth

## Motivation

When an object is released from a moving rocket near Earth, its trajectory depends on its initial conditions as well as Earth’s gravitational force. The payload may follow an elliptical, parabolic, or hyperbolic path. Understanding these trajectories is crucial for:
- **Orbital insertion:** When satellites or spacecraft are inserted into orbit.
- **Reentry:** For returning payloads safely to Earth.
- **Escape scenarios:** For sending spacecraft on interplanetary or interstellar missions.

This problem blends concepts from orbital mechanics with numerical methods and is vital for modern space mission planning.

## Task

1. **Characterize Trajectories:**  
   Define and explain the physical meaning of elliptical, parabolic, and hyperbolic trajectories for a payload released near Earth.

2. **Numerical Analysis:**  
   Compute the path of the payload based on given initial conditions (position, velocity, and altitude) using numerical integration.

3. **Discussion:**  
   Discuss how these trajectories relate to orbital insertion, reentry, or escape scenarios.

4. **Simulation Tool:**  
   Develop a computational tool (using Python) to simulate and visualize the motion of the payload under Earth's gravity with various initial velocities and directions.

## Python Simulation

Below is a Python script that:
- Sets up Earth-related parameters.
- Defines three cases:
  - **Elliptical Orbit:** Initial velocity lower than the circular orbital velocity.
  - **Parabolic Trajectory:** Initial velocity exactly equal to the escape velocity.
  - **Hyperbolic Trajectory:** Initial velocity higher than the escape velocity.
- Uses `scipy.integrate.solve_ivp` to integrate the equations of motion.
- Plots the trajectories along with an outline of Earth.

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.integrate import solve_ivp

# Constants
G = 6.67430e-11       # gravitational constant (m^3 kg^-1 s^-2)
M_earth = 5.972e24    # mass of Earth (kg)
mu = G * M_earth      # Earth's gravitational parameter (m^3/s^2)
R_earth = 6371e3      # Earth's radius (m)

# Initial position: 300 km above Earth's surface
altitude = 300e3                  
r0 = R_earth + altitude  # initial distance from Earth's center (m)

# Circular orbital velocity at r0 (for reference)
v_circular = np.sqrt(mu / r0)

# Escape velocity at r0
v_escape = np.sqrt(2 * mu / r0)

# Define three cases for payload release:
cases = {
    "Elliptical Orbit (v = 0.95*v_circular)": 0.95 * v_circular,
    "Parabolic Trajectory (v = v_escape)": v_escape,
    "Hyperbolic Trajectory (v = 1.1*v_escape)": 1.1 * v_escape,
}

# Differential equations for the two-body problem
def deriv(t, state):
    x, y, vx, vy = state
    r = np.sqrt(x**2 + y**2)
    ax = -mu * x / r**3
    ay = -mu * y / r**3
    return [vx, vy, ax, ay]

# Dictionary to store trajectories of each case
trajectories = {}

# Integrate equations for each case
for label, v0 in cases.items():
    # Initial conditions: positioned at (r0, 0) with velocity vector (0, v0)
    y0 = [r0, 0, 0, v0]
    
    # Set integration time span: 
    # For elliptical orbits, a shorter integration time suffices.
    # For parabolic and hyperbolic trajectories, we extend the time span.
    if "Elliptical" in label:
        t_span = (0, 6000)  # seconds
    else:
        t_span = (0, 20000) # seconds
        
    t_eval = np.linspace(t_span[0], t_span[1], 1000)
    
    sol = solve_ivp(deriv, t_span, y0, t_eval=t_eval, rtol=1e-8)
    trajectories[label] = sol

# Plotting
plt.figure(figsize=(10, 8))

# Plot Earth as a circle
theta = np.linspace(0, 2 * np.pi, 300)
earth_x = R_earth * np.cos(theta)
earth_y = R_earth * np.sin(theta)
plt.fill(earth_x, earth_y, color="lightblue", label="Earth")

# Define colors for trajectories
colors = ["r", "g", "b"]

# Plot each trajectory
for (label, sol), color in zip(trajectories.items(), colors):
    plt.plot(sol.y[0], sol.y[1], color, label=label)

plt.xlabel("x (m)")
plt.ylabel("y (m)")
plt.title("Trajectories of a Freely Released Payload Near Earth")
plt.legend(loc="upper right")
plt.axis("equal")
plt.grid(True)
plt.show()
```
