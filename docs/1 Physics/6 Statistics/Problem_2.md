# Problem 2

# Estimating Pi using Monte Carlo Methods

## Motivation

Monte Carlo simulations are a powerful class of computational techniques that use randomness to solve problems or estimate values. One of the most elegant applications of Monte Carlo methods is estimating the value $\pi$ of through geometric probability. By randomly generating points and analyzing their positions relative to a geometric shape, we can approximate $\pi$ in an intuitive and visually engaging way.

This problem connects fundamental concepts of probability, geometry, and numerical computation. It also provides a gateway to understanding how randomness can be harnessed to solve complex problems in physics, finance, and computer science. The Monte Carlo approach to $\pi$ estimation highlights the versatility and simplicity of this method while offering practical insights into convergence rates and computational efficiency.

The Monte Carlo method to estimate π is indeed fascinating! Here's an overview and guidance to help you accomplish each part of this task.

## Task 1

### **Theoretical Foundation**
The technique leverages the geometric probability of points in a square and circle:
1. Consider a unit circle with radius \( r = 1 \) inscribed in a square of side length \( 2r = 2 \).
2. The area of the circle is \( \pi r^2 = \pi \), and the area of the square is \( 4r^2 = 4 \).
3. If we randomly distribute points within the square, the proportion of points falling inside the circle compared to the total points in the square approximates the ratio of the areas:
   \[
   \text{Ratio} = \frac{\text{Points inside the circle}}{\text{Total points in the square}} \approx \frac{\text{Area of the circle}}{\text{Area of the square}} = \frac{\pi}{4}
   \]
4. Therefore, we can estimate \( \pi \) as:
   \[
   \pi \approx 4 \times \frac{\text{Points inside the circle}}{\text{Total points}}
   \]

### **Simulation**
Here's a step-by-step guide:
1. **Random Point Generation:**
   - Generate random (x, y) coordinates within the square \( [-1, 1] \times [-1, 1] \).
   - Ensure randomness by using functions like `random.uniform(-1, 1)` in Python.
2. **Circle Membership Check:**
   - Use the equation \( x^2 + y^2 \leq 1 \) to determine if a point lies inside the circle.
   - Count the number of points satisfying this condition.
3. **π Estimation:**
   - Apply the formula \( \pi \approx 4 \times \frac{\text{Points inside the circle}}{\text{Total points}} \).

### **Visualization**
1. Plot the square and unit circle for reference.
2. Mark points inside the circle with one color (e.g., green) and points outside with another (e.g., red).
3. Tools like `matplotlib` in Python work great for this purpose.

Example Python snippet:
```python
import matplotlib.pyplot as plt
import random

N = 10000  # Number of random points
points_inside = 0
x_inside, y_inside, x_outside, y_outside = [], [], [], []

for _ in range(N):
    x, y = random.uniform(-1, 1), random.uniform(-1, 1)
    if x**2 + y**2 <= 1:
        points_inside += 1
        x_inside.append(x)
        y_inside.append(y)
    else:
        x_outside.append(x)
        y_outside.append(y)

# Estimation of π
pi_estimate = 4 * points_inside / N
print(f"Estimated π: {pi_estimate}")

# Visualization
plt.figure(figsize=(6, 6))
plt.scatter(x_inside, y_inside, color="green", s=1)
plt.scatter(x_outside, y_outside, color="red", s=1)
plt.gca().set_aspect("equal", adjustable="box")
plt.title(f"Monte Carlo π Estimation (N={N})")
plt.show()
```

### **Analysis**
1. **Accuracy Improvement:** 
   - The accuracy of the π estimate increases with more points due to the law of large numbers.
2. **Convergence Rate:**
   - Convergence is proportional to \( \frac{1}{\sqrt{N}} \), where \( N \) is the number of points.
   - For higher precision, use a larger \( N \), but note that computational time also increases.
3. **Considerations:**
   - Randomness quality affects the accuracy; use high-quality pseudorandom number generators.
   - Parallelization can speed up computations for large \( N \).

