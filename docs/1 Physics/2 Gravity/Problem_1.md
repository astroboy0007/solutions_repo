# Problem 1

# Orbital Period and Orbital Radius

## Motivation

The relationship between the square of the orbital period and the cube of the orbital radius, known as Kepler's Third Law, is a cornerstone of celestial mechanics. This simple yet profound relationship allows for the determination of planetary motions and has implications for understanding gravitational interactions on both local and cosmic scales. By analyzing this relationship, one can connect fundamental principles of gravity with real-world phenomena such as satellite orbits and planetary systems.





import numpy as np
import matplotlib.pyplot as plt
from scipy.constants import G, pi

# Constants
M_sun = 1.989e30  # Mass of the Sun in kg
AU = 1.496e11  # 1 Astronomical Unit in meters

# Kepler's Third Law: T^2 = (4 * pi^2 * r^3) / (G * M)
def orbital_period(radius, mass=M_sun):
    return 2 * pi * np.sqrt(radius**3 / (G * mass))

# Generate data points for different orbital radii
radii = np.linspace(0.1, 5, 100) * AU  # From 0.1 AU to 5 AU
periods = orbital_period(radii) / (60 * 60 * 24)  # Convert to days

# Plotting T^2 vs R^3
plt.figure(figsize=(8,6))
plt.plot(radii**3, periods**2, label="Kepler's Third Law", color='b')
plt.xlabel("Orbital Radius Cubed (m^3)")
plt.ylabel("Orbital Period Squared (days^2)")
plt.title("Kepler's Third Law: T^2 vs R^3")
plt.legend()
plt.grid()
plt.show()

# Discussion:
Kepler's Third Law states that the square of the orbital period is proportional to the cube of the orbital radius.
This script computes the orbital period for a range of radii assuming circular orbits.
The resulting graph should show a linear relationship between T^2 and R^3, confirming Kepler's Third Law.
Applications include estimating planetary distances and masses in exoplanet studies.

# Real-world examples:
The Moon's orbit around Earth follows Kepler's Law, enabling precise distance measurements.
The orbits of planets in the Solar System obey this law, allowing for calculations of planetary masses.
Exoplanet detection methods, such as transit and radial velocity, rely on Kepler's laws to estimate planetary properties.
