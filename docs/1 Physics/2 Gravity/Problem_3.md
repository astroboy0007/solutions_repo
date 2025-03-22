# Problem 3

# Trajectories of a Freely Released Payload Near Earth

## Motivation

When a payload is released from a moving rocket near Earth, its trajectory depends on its initial conditions (position, velocity, and altitude) as well as Earth's gravitational pull. Depending on the initial speed and direction, the payload can follow one of several possible paths:  
- **Elliptical Orbit:** When the payload's speed is less than the circular orbital speed, it will remain bound to Earth on an elliptical orbit.  
- **Parabolic Trajectory:** When the payload's speed is exactly the escape velocity, it follows a parabolic path, representing the threshold between bound and unbound orbits.  
- **Hyperbolic Trajectory:** If the payload's speed exceeds the escape velocity, it follows a hyperbolic path and escapes Earth’s gravitational pull.  

Understanding these trajectories is crucial for:  
- **Orbital Insertion:** Placing satellites and payloads into stable orbits.  
- **Reentry:** Safely returning objects to Earth.  
- **Escape Scenarios:** Planning missions that leave Earth’s gravitational field for interplanetary or even interstellar travel.


## Theoretical Background

When an object moves under the influence of Earth's gravity, its acceleration is given by Newton's law of universal gravitation:



\[
\vec{a} = -\frac{\mu}{r^3}\vec{r} \quad \text{with} \quad \mu = G M_{\text{earth}}
\]



Where:
- \( G \) is the gravitational constant.
- \( M_{\text{earth}} \) is Earth's mass.
- \( r \) is the distance from Earth's center.

If the payload is released at an altitude \( h \) above Earth's surface, the initial distance is:



\[
r_0 = R_{\text{earth}} + h
\]



Depending on the payload's speed \( v_0 \):
- For **elliptical orbits**: \( v_0 < v_{\text{circular}} \) where \( v_{\text{circular}} = \sqrt{\mu / r_0} \)
- For a **parabolic trajectory**: \( v_0 = v_{\text{escape}} = \sqrt{2\mu / r_0} \)
- For **hyperbolic trajectories**: \( v_0 > v_{\text{escape}} \)

## Numerical Simulation and Visualization

The following Python script uses a numerical integrator to solve the two-dimensional equations of motion for a payload released near Earth. It simulates three cases:
- **Elliptical Orbit:** \( v_0 = 0.95 \times v_{\text{circular}} \)
- **Parabolic Trajectory:** \( v_0 = v_{\text{escape}} \)
- **Hyperbolic Trajectory:** \( v_0 = 1.1 \times v_{\text{escape}} \)

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.integrate import solve_ivp

# Constants
G = 6.67430e-11           # Gravitational constant (m^3 kg^-1 s^-2)
M_earth = 5.972e24        # Mass of Earth (kg)
mu = G * M_earth          # Earth's gravitational parameter (m^3/s^2)
R_earth = 6371e3          # Earth's radius (m)

# Initial Conditions
altitude = 300e3          # Altitude above Earth's surface (m)
r0 = R_earth + altitude   # Initial distance from Earth's center (m)
v_circular = np.sqrt(mu / r0)        # Circular orbital velocity (m/s)
v_escape = np.sqrt(2 * mu / r0)        # Escape velocity (m/s)

# Define different cases with corresponding initial tangential speeds
cases = {
    "Elliptical Orbit (v0 = 0.95 * v_circular)": 0.95 * v_circular,
    "Parabolic Trajectory (v0 = v_escape)": v_escape,
    "Hyperbolic Trajectory (v0 = 1.1 * v_escape)": 1.1 * v_escape,
}

# Differential equations for 2D motion under gravity
def equations(t, state):
    x, y, vx, vy = state
    r = np.sqrt(x**2 + y**2)
    ax = -mu * x / r**3
    ay = -mu * y / r**3
    return [vx, vy, ax, ay]

# Store trajectories for each scenario
trajectories = {}

# Perform the numerical integration for each case
for description, v0 in cases.items():
    # Initial state: payload at (r0, 0) with velocity perpendicular to the radius (0, v0)
    state0 = [r0, 0, 0, v0]
    
    # Time span: shorter for elliptical orbits, longer for escaping trajectories
    if "Elliptical" in description:
        t_span = (0, 6000)  # seconds
    else:
        t_span = (0, 20000) # seconds
    
    t_eval = np.linspace(t_span[0], t_span[1], 1000)
    sol = solve_ivp(equations, t_span, state0, t_eval=t_eval, rtol=1e-8)
    trajectories[description] = sol

# Plot the results
plt.figure(figsize=(10, 8))

# Draw Earth as a circle
theta = np.linspace(0, 2 * np.pi, 300)
earth_x = R_earth * np.cos(theta)
earth_y = R_earth * np.sin(theta)
plt.fill(earth_x, earth_y, color='lightblue', label='Earth')

# Colors for different trajectories
colors = ['r', 'g', 'b']
for (desc, sol), color in zip(trajectories.items(), colors):
    plt.plot(sol.y[0], sol.y[1], color, label=desc)

plt.xlabel('x (m)')
plt.ylabel('y (m)')
plt.title('Trajectories of a Freely Released Payload Near Earth')
plt.axis('equal')
plt.grid(True)
plt.legend()
plt.show()
```
![alt text](image-3.png)

## Discussion
### Trajectory Analysis
- Elliptical Orbits: With an initial speed less than the circular orbital velocity, the payload enters a bound, elliptical trajectory. Such orbits are common for satellites.

- Parabolic Trajectories: A payload released with exactly the escape velocity follows a parabolic path—this is the critical condition between remaining bound and escaping Earth's gravity.

- Hyperbolic Trajectories: With an initial speed exceeding the escape velocity, the payload follows a hyperbolic trajectory. This extra speed allows the payload to permanently escape Earth’s gravitational influence, which is essential in certain interplanetary or deep-space missions.

### Applications in Space Missions
- Orbital Insertion: Precise adjustments of speed and direction are necessary to insert payloads into stable orbits (typically elliptical).

- Reentry: Understanding these trajectories helps in planning safe reentry paths for returning spacecraft.

- Escape Trajectories: Hyperbolic trajectories are crucial for missions targeting journeys beyond Earth’s gravitational well.

## Conclusion
By varying the initial velocity and direction of a payload released near Earth, we can observe different trajectories—elliptical, parabolic, or hyperbolic—each corresponding to distinct mission profiles such as satellite insertion, reentry, or escape. The accompanying Python simulation serves as a computational tool for visualizing these scenarios, offering insights vital for space mission planning and execution.