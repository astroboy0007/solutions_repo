# Analytic geometry

## Vectors


### Problem 1
**Question:** By what number should vector **a** = [3, 4] be multiplied so that its length is equal to 1?

**Solution:**  
1. The length of a vector **v** = [x, y] is calculated as:  

\[
\|v\| = \sqrt{x^2 + y^2}
\]  

For vector **a** = [3, 4]:  

\[
\|a\| = \sqrt{3^2 + 4^2} = \sqrt{9 + 16} = 5
\]  


2. To make the length of the vector equal to 1, divide each component of the vector by its length:  

\[
\text{Multiplier} = \frac{1}{\|a\|} = \frac{1}{5}
\]  


**Answer:** Vector **a** should be multiplied by  \( \frac{1}{5} \).

---

### Problem 2
**Question:** Calculate the length of vector **b** = [1, 1] and find the unit vector of this vector.

**Solution:**
1. The length of vector **b** is:  

\[
\|b\| = \sqrt{1^2 + 1^2} = \sqrt{1 + 1} = \sqrt{2}
\]

2. The unit vector of **b** is obtained by dividing each component of the vector by its length:  

\[
\text{Unit vector of } \mathbf{b} = \frac{\mathbf{b}}{\|b\|} = \frac{1}{\sqrt{2}}[1, 1] = \left[\frac{1}{\sqrt{2}}, \frac{1}{\sqrt{2}}\right]
\]

**Answer:** Length of **b** = \( \sqrt{2} \), Unit vector of **b** = \([ \frac{1}{\sqrt{2}}, \frac{1}{\sqrt{2}} ]\).

---

### Problem 3
**Question:** Plot the vector and the unit vector from the previous exercise.

**Solution:** 
To visualize, plot the vector **b** = [1, 1] and its unit vector \([ \frac{1}{\sqrt{2}}, \frac{1}{\sqrt{2}} ]\) on a Cartesian plane. The unit vector will have the same direction as **b**, but its length will be 1.


```python
import matplotlib.pyplot as plt
import numpy as np

# Define the vector and its unit vector
vector_b = np.array([1, 1])
unit_vector_b = vector_b / np.linalg.norm(vector_b)

# Create a figure and axis
plt.figure(figsize=(6, 6))
plt.axhline(0, color='gray', linewidth=0.5, linestyle='--')
plt.axvline(0, color='gray', linewidth=0.5, linestyle='--')

# Plot the vector b
plt.quiver(0, 0, vector_b[0], vector_b[1], angles='xy', scale_units='xy', scale=1, color='blue', label='Vector b')

# Plot the unit vector of b
plt.quiver(0, 0, unit_vector_b[0], unit_vector_b[1], angles='xy', scale_units='xy', scale=1, color='green', label='Unit Vector of b')

# Set plot limits
plt.xlim(-1.5, 1.5)
plt.ylim(-1.5, 1.5)

# Add labels, legend, and title
plt.legend()
plt.grid()
plt.title("Vector and Unit Vector")
plt.xlabel("X")
plt.ylabel("Y")

# Show the plot
plt.show()
```

![alt text](image-1.png)

---

### Problem 4
**Question:** Calculate the length of vector **c** = [1, 2, 3] and find the unit vector of this vector.

**Solution:**
1. The length of vector **c** is:  

\[
\|c\| = \sqrt{1^2 + 2^2 + 3^2} = \sqrt{1 + 4 + 9} = \sqrt{14}
\]  


2. The unit vector of **c** is:  

\[
\text{Unit vector of } \mathbf{c} = \frac{\mathbf{c}}{\|c\|} = \frac{1}{\sqrt{14}}[1, 2, 3] = \left[\frac{1}{\sqrt{14}}, \frac{2}{\sqrt{14}}, \frac{3}{\sqrt{14}}\right]
\]  


**Answer:** Length of **c** = \( \sqrt{14} \), Unit vector of **c** = \([ \frac{1}{\sqrt{14}}, \frac{2}{\sqrt{14}}, \frac{3}{\sqrt{14}} ]\).

---

### Problem 5
**Question:** Find the Cartesian coordinates of vector **v** = [2, 3, 4] in the basis:  

\[
\{\mathbf{b_1} = [1, 0, 1], \mathbf{b_2} = [0, 1, 0], \mathbf{b_3} = [1, 0, -1]\}.
\]

**Solution:**
Let vector **v** = [2, 3, 4] be represented in the given basis as:  

\[
\mathbf{v} = c_1 \mathbf{b_1} + c_2 \mathbf{b_2} + c_3 \mathbf{b_3},
\]  

where \( \mathbf{b_1} = [1, 0, 1] \), \( \mathbf{b_2} = [0, 1, 0] \), and \( \mathbf{b_3} = [1, 0, -1] \).

Set up the system of equations:  

\[
\begin{cases} 
c_1(1) + c_2(0) + c_3(1) = 2, \\
c_1(0) + c_2(1) + c_3(0) = 3, \\
c_1(1) + c_2(0) - c_3(1) = 4.
\end{cases}
\]

Simplify:  
1. From the first equation: \( c_1 + c_3 = 2 \).
2. From the second equation: \( c_2 = 3 \).
3. From the third equation: \( c_1 - c_3 = 4 \).

Solve for \( c_1 \) and \( c_3 \):  

1. Add \( c_1 + c_3 = 2 \) and \( c_1 - c_3 = 4 \):  

\[
2c_1 = 6 \quad \Rightarrow \quad c_1 = 3.
\]  

2. Substitute \( c_1 = 3 \) into \( c_1 + c_3 = 2 \):  

\[
3 + c_3 = 2 \quad \Rightarrow \quad c_3 = -1.
\]  


**Answer:** Cartesian coordinates in the given basis: \( c_1 = 3, c_2 = 3, c_3 = -1 \).

---

