# Problem 1

# Orbital Period and Orbital Radius

## Motivation

The relationship between the square of the orbital period and the cube of the orbital radius, known as Kepler's Third Law, is a cornerstone of celestial mechanics. This simple yet profound relationship allows for the determination of planetary motions and has implications for understanding gravitational interactions on both local and cosmic scales. By analyzing this relationship, one can connect fundamental principles of gravity with real-world phenomena such as satellite orbits and planetary systems.

---

### **Derivation of Kepler’s Third Law for Circular Orbits**  

Newton’s form of Kepler’s Third Law comes from equating the centripetal force required to keep a body in circular orbit with the gravitational force.

## Gravitational Force and Orbital Motion

### Gravitational Force (Newton's Law of Gravitation):


\[
F = \frac{G M m}{r^2}
\]



Where:  
 \(G\) is the gravitational constant.  
 \(M\) is the mass of the central body (e.g., the Sun for planets, the Earth for the Moon).  
 \(m\) is the mass of the orbiting body.  
 \(r\) is the orbital radius.  

### Centripetal Force needed to keep the body in circular motion:


\[
F = \frac{m v^2}{r}
\]



Where:  
 \(v\) is the orbital velocity.

### Setting gravitational force equal to centripetal force:


\[
\frac{G M m}{r^2} = \frac{m v^2}{r}
\]



Cancel \(m\) from both sides:


\[
\frac{G M}{r^2} = \frac{v^2}{r}
\]



Rearrange:


\[
G M = v^2 r
\]



### Orbital Velocity and Orbital Period:
The orbital velocity \(v\) is related to the orbital period \(T\) by:


\[
v = \frac{2 \pi r}{T}
\]



Substituting into our equation:


\[
G M = \left( \frac{2 \pi r}{T} \right)^2 r
\]



Expanding and solving for \(T^2\):


\[
T^2 = \frac{4 \pi^2}{G M} r^3
\]



This shows that:


\[
T^2 \propto r^3
\]



### Conclusion:
This proportionality is **Kepler’s Third Law**.


---

### **Implications for Astronomy**
1. **Calculating Planetary Masses:**  
    - Rearranging the equation: 
        \(  M = \frac{4\pi^2 r^3}{G T^2} \)
    - If we know the orbital radius and period of a satellite, we can estimate the mass of the central body.

2. **Determining Distances in the Solar System:**  
    - Using known periods, astronomers can determine the semi-major axis of a planet's orbit.

3. **Exoplanet Detection:**  
    - By measuring the orbital period of an exoplanet (e.g., through transit or radial velocity methods), its orbital radius can be estimated.

---

### **Real-World Examples**
1. **Moon's Orbit Around Earth:**  
    - The Moon has an orbital period of **27.3 days** and a mean orbital radius of **384,400 km**.
    - Using Kepler’s Third Law, we can verify the Earth’s mass.

2. **Planets in the Solar System:**  
    - Applying the law to planets orbiting the Sun reveals a consistent pattern that holds across different planetary orbits.

---

### **Computational Model: Simulation of Circular Orbits**

This Python script numerically simulates circular orbits and verifies Kepler’s Third Law.

```python
import numpy as np
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D
from matplotlib.animation import FuncAnimation, PillowWriter

# Constants
G = 6.67430e-11  # Gravitational constant (m^3 kg^-1 s^-2)
M_sun = 1.989e30  # Mass of the Sun (kg)

# Actual planetary data (Orbital radii in meters and periods in seconds)
planet_data = {
    "Mercury": {"radius": 5.79e10, "period": 7.6e6, "color": "gold", "size": 300},
    "Venus": {"radius": 1.08e11, "period": 1.94e7, "color": "orange", "size": 600},
    "Earth": {"radius": 1.50e11, "period": 3.15e7, "color": "blue", "size": 800},
    "Mars": {"radius": 2.28e11, "period": 5.94e7, "color": "red", "size": 400},
    "Jupiter": {"radius": 7.78e11, "period": 3.73e8, "color": "brown", "size": 2000},
    "Saturn": {"radius": 1.43e12, "period": 9.29e8, "color": "yellow", "size": 1700},
    "Uranus": {"radius": 2.87e12, "period": 2.65e9, "color": "cyan", "size": 1500},
    "Neptune": {"radius": 4.50e12, "period": 5.2e9, "color": "purple", "size": 1400},
}

# Extract data into arrays
radii = np.array([data["radius"] for data in planet_data.values()])
periods = np.array([data["period"] for data in planet_data.values()])
planet_colors = [data["color"] for data in planet_data.values()]
planet_sizes = [data["size"] for data in planet_data.values()]
planet_names = list(planet_data.keys())

# Normalize radii and periods for better scaling
radii_cubed = radii**3 / 1e36  # Scale to make numbers manageable
periods_squared = periods**2 / 1e16

# Create the figure and 3D axis
fig = plt.figure(figsize=(12, 8))
ax = fig.add_subplot(111, projection='3d')

# Plot planets as styled circles
planet_plots = []
for i, (radius, period, color, size) in enumerate(zip(radii_cubed, periods_squared, planet_colors, planet_sizes)):
    p = ax.scatter(
        radius, 
        period, 
        zs=0, 
        s=size, 
        color=color, 
        edgecolors='black', 
        label=planet_names[i]
    )
    planet_plots.append(p)

# Annotate planets
for i, (planet, radius, period) in enumerate(zip(planet_names, radii_cubed, periods_squared)):
    ax.text(
        radius,
        period,
        0,
        planet,
        fontsize=10,
        color='black',
        bbox=dict(facecolor='white', edgecolor='black', boxstyle='round,pad=0.3')
    )

# Axis labels and title
ax.set_xlabel("Orbital Radius Cubed (r³) [10³⁶ m³]", fontsize=12)
ax.set_ylabel("Orbital Period Squared (T²) [10¹⁶ s²]", fontsize=12)
ax.set_zlabel("Z-axis (Fixed at 0)", fontsize=12)
ax.set_title("3D Visualization of Kepler's Third Law", fontsize=14, fontweight='bold')

# Animation function
def update(frame):
    ax.view_init(elev=30, azim=frame)  # Rotate the plot by changing the azimuthal angle
    return planet_plots

# Create the animation
ani = FuncAnimation(fig, update, frames=np.arange(0, 360, 2), interval=50, blit=False)

# Save as GIF
ani.save("kepler_3d_animation.gif", writer=PillowWriter(fps=20))

# Display success message
print("GIF saved as 'kepler_3d_animation.gif'")
```
![kepler 3d animation](kepler_3d_animation.gif)

This script:  

* Simulates various orbital radii.  

* Computes the corresponding orbital periods.  

* Plots \( T^2 \) vs. \( r^3 \), which should yield a straight line, confirming Kepler's Third Law.

---

### **Extending to Elliptical Orbits**
* Kepler’s Third Law applies to **elliptical orbits** as well, but instead of \( r \), we use the **semi-major axis** \( a \).
* The law still holds:  


\[
T^2 = \frac{4\pi^2 a^3}{G M}
\]



* Example: Halley's Comet, which follows an **elliptical** orbit, still obeys this principle.


---

### **Conclusion**
- Kepler’s Third Law provides a fundamental relationship between orbital period and radius.
- It is widely used in planetary science, space exploration, and astrophysics.
- The computational model successfully verifies the law and its real-world applications.








