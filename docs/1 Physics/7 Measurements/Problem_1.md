# Problem 1

# Measuring Earth's Gravitational Acceleration with a Pendulum

## Motivation  

The acceleration $g \, \mathrm{}$ due to gravity is a fundamental constant that influences a wide range of physical phenomena. Measuring $g \, \mathrm{}$ accurately is crucial for understanding gravitational interactions, designing structures, and conducting experiments in various fields. One classic method for determining $g \, \mathrm{}$  is through the oscillations of a simple pendulum, where the period of oscillation depends on the local gravitational field.

This is an excellent plan for measuring Earth's gravitational acceleration using a pendulum while emphasizing the importance of uncertainties in experimental physics! Here's how you can format and implement the markdown elements, calculations, and deliverables you've outlined:

---


**1. Tabulated Data:**

| Measurement | Length \(L\) (m) | Time for 10 Oscillations \(T_{10}\) (s) | Mean Time \(T_{\text{mean}}\) (s) | Std. Dev. \(\sigma\) (s) | Uncertainty in Mean \(\Delta T\) (s) |
|-------------|------------------|---------------------------------------|-----------------------------------|--------------------------|------------------------------------|
| Trial 1     | 1.00             | 22.3                                 |                                   |                          |                                    |
| Trial 2     | 1.00             | 22.5                                 |                                   |                          |                                    |
| ...         |                  |                                       |                                   |                          |                                    |


**2. Calculation Results:**

You can add a section to display derived values like:


#### Calculations:

1. **Pendulum Period**:
   The period \(T\) is calculated as:
   $$
   T = \frac{T_{10}}{10}
   $$

2. **Acceleration due to Gravity**:
   Using the formula:
   $$
   g = \frac{4\pi^2L}{T^2}
   $$

3. **Propagation of Uncertainties**:
   Total uncertainty in \(g\) is calculated as:
   $$
   \Delta g = g \cdot \sqrt{\left(\frac{\Delta L}{L}\right)^2 + \left(2 \cdot \frac{\Delta T}{T}\right)^2}
   $$


---

### Python Code Snippets
Here’s an example for analyzing uncertainties and calculating \(g\):

```python
import numpy as np

# Parameters
length = 1.0  # Pendulum length (meters)
time_measurements = [22.3, 22.5, 22.4, 22.6, 22.3, 22.5, 22.4, 22.7, 22.3, 22.6]  # Time for 10 oscillations

# Calculate mean and standard deviation
mean_time = np.mean(time_measurements)
std_dev = np.std(time_measurements)
uncertainty_in_mean = std_dev / np.sqrt(len(time_measurements))

# Calculate period
period = mean_time / 10

# Calculate acceleration due to gravity
g = (4 * np.pi**2 * length) / period**2

# Propagate uncertainty
delta_length = 0.001  # Example uncertainty in length (meters)
delta_period = uncertainty_in_mean / 10
delta_g = g * np.sqrt((delta_length / length)**2 + (2 * delta_period / period)**2)

print(f"Mean time for 10 oscillations: {mean_time:.2f} s")
print(f"Period: {period:.2f} s")
print(f"Acceleration due to gravity: {g:.2f} m/s^2 ± {delta_g:.2f} m/s^2")
```
```
Output:
Mean time for 10 oscillations: 22.46 s
Period: 2.25 s
Acceleration due to gravity: 7.83 m/s^2 ± 0.03 m/s^2
```

---

### Discussion Points
1. **Impact of Measurement Resolution**:  

     - Higher resolution tools reduce uncertainties, leading to more precise values of \(g\).  

     - Discuss how the resolution of the ruler and stopwatch influences results.

2. **Effect of Timing Variability**:  

     - Variability in repeated measurements contributes to standard deviation.  

     - Highlight the importance of consistent measurement practices.

3. **Experimental Limitations**:  

     - Assumptions: Neglecting air resistance, ensuring small displacement (<15°).  

     - Limitations: Human reaction time affecting stopwatch readings.

