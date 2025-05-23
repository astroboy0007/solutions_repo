# Calculus

## Functions

### Task 1

Functions:  

1. \( f(x) = x^2 \)  
2. \( g(x) = \sqrt{x} \)  
3. \( h(x) = \frac{1}{x} \)  
4. \( j(x) = \sin(x) \)

Calculation:  

For \( f(x) = x^2 \):  

\[
f(2) = 2^2 = 4
\]  


For \( g(x) = \sqrt{x} \):  

\[
g(2) = \sqrt{2} \approx 1.414
\]  


For \( h(x) = \frac{1}{x} \):  

\[
h(2) = \frac{1}{2} = 0.5
\]  


For \( j(x) = \sin(x) \):  

   Assuming \( x = 2 \) is in radians,  

\[
j(2) = \sin(2) \approx 0.909
\]  


Summary: 

- \( f(2) = 4 \)  
- \( g(2) \approx 1.414 \)  
- \( h(2) = 0.5 \)  
- \( j(2) \approx 0.909 \)

---

### Task 2

Step 1: Definitions of the Functions
Given:  

- \( f(x) = 3x - 1 \)
- \( g(x) = \sqrt{x} \)

---

Step 2: Compositions of Functions  
\( f(g(x)) \):  

   Substitute \( g(x) = \sqrt{x} \) into \( f(x) \):  

\[
f(g(x)) = f(\sqrt{x}) = 3\sqrt{x} - 1
\]  

\( g(f(x)) \):  

   Substitute \( f(x) = 3x - 1 \) into \( g(x) \):  

\[
g(f(x)) = g(3x - 1) = \sqrt{3x - 1}
\]  

\( f(f(x)) \):  

   Substitute \( f(x) = 3x - 1 \) into \( f(x) \) again:  

\[
f(f(x)) = f(3x - 1) = 3(3x - 1) - 1 = 9x - 3 - 1 = 9x - 4
\]  

\( g(g(x)) \):  

   Substitute \( g(x) = \sqrt{x} \) into \( g(x) \) again:  

\[
g(g(x)) = g(\sqrt{x}) = \sqrt{\sqrt{x}} = x^{1/4}
\]  

---

Step 3: Instructions for Visualizing in GeoGebra
To plot the functions \( f(g(x)) \), \( g(f(x)) \), \( f(f(x)) \), and \( g(g(x)) \) in GeoGebra:  

1. Access the GeoGebra application or the online version at [GeoGebra.org](https://www.geogebra.org).     

2. In the Input field, type the functions as follows:
     - \( f(g(x)) = 3\sqrt{x} - 1 \)
     - \( g(f(x)) = \sqrt{3x - 1} \)
     - \( f(f(x)) = 9x - 4 \)
     - \( g(g(x)) = x^{1/4} \)  

3. For \( f(g(x)) \), \( g(f(x)) \), and \( g(g(x)) \), restrict the domain to ensure the square root is defined (e.g., \( x \geq 0 \) for \( g(x) \)).
   - Use the syntax in GeoGebra, such as:
     - For \( g(f(x)) \): `If[3x - 1 >= 0, sqrt(3x - 1)]`  

4. Assign different colors to each function for better visualization. Right-click on a function and select "Settings" to change its color and style.  

5.  Use GeoGebra’s point tool to evaluate the compositions at specific \( x \)-values. Observe intersections or relationships between the curves.  

---

### Task 3

**Compositions of Functions**

Given:  

- \( f(x) = e^x \) (exponential function)
- \( g(x) = \ln(x) \) (natural logarithm function)

---

**Composition 1: \( f(g(x)) \)**

Substitute \( g(x) = \ln(x) \) into \( f(x) \):  

\[
f(g(x)) = f(\ln(x)) = e^{\ln(x)}
\]  

From the properties of logarithms and exponentials:  

\[
e^{\ln(x)} = x \quad \text{(for \( x > 0 \))}.
\]  


---

**Composition 2: \( g(f(x)) \)**

Substitute \( f(x) = e^x \) into \( g(x) \):  

\[
g(f(x)) = g(e^x) = \ln(e^x)
\]  

From the properties of logarithms:  

\[
\ln(e^x) = x.
\]  


---

**Conclusion**

For both compositions \( f(g(x)) \) and \( g(f(x)) \), the result is \( x \). This demonstrates that the exponential function \( e^x \) and the natural logarithm function \( \ln(x) \) are **inverse functions** of each other.

**Domain Constraints**:  

- \( g(x) = \ln(x) \) requires \( x > 0 \),
- \( f(x) = e^x \) is valid for all real \( x \).

---

### Task 4

**Problem 1: Inverse Function**
Given the function \( f = \{(1, 7), (2, 9), (3, 11)\} \), we are tasked to find its inverse \( f^{-1} \).

To find the inverse function \( f^{-1} \), we simply swap the elements in each ordered pair.

Solution:  

\[
f = \{(1, 7), (2, 9), (3, 11)\}
\]  

Inverse:  

\[
f^{-1} = \{(7, 1), (9, 2), (11, 3)\}
\]  


---

**Problem 2: Composition of Functions**
The functions \( f(x) = e^x \) and \( g(x) = \ln(x) \) are given. We need to evaluate \( f(g(x)) \) and \( g(f(x)) \), and determine the relationship.

**Evaluate \( f(g(x)) \):**  

\[
f(g(x)) = f(\ln(x)) = e^{\ln(x)}
\]  

From the properties of logarithms and exponentials:  

\[
e^{\ln(x)} = x \quad \text{(for \( x > 0 \))}.
\]  


##### **Evaluate \( g(f(x)) \):**  

\[
g(f(x)) = g(e^x) = \ln(e^x)
\]  

From the properties of logarithms:  

\[
\ln(e^x) = x.
\]  


**Conclusion:**
Both compositions yield:  

\[
f(g(x)) = x \quad \text{and} \quad g(f(x)) = x.
\]  

This shows that \( f(x) = e^x \) and \( g(x) = \ln(x) \) are **inverse functions** of each other.

**Domain Constraints**:  

- \( g(x) = \ln(x) \) requires \( x > 0 \),
- \( f(x) = e^x \) is valid for all real \( x \).

---

### Task 5

**Solution to the Inverse Function**

**Given Function**:  

\[
f = \{(1, 7), (2, 7), (3, 11)\}
\]  


**Finding the Inverse Function**:  

To compute the inverse \( f^{-1} \), we swap the elements in each ordered pair from the given function \( f \). This means:  

- The \( x \)-coordinate becomes the \( y \)-coordinate, and vice versa.

**Inverse Function**:  

\[
f^{-1} = \{(7, 1), (7, 2), (11, 3)\}
\]  

**Note**: In the inverse function \( f^{-1} \), \( 7 \) maps to both \( 1 \) and \( 2 \), which means \( f^{-1} \) is not a function in the strict mathematical sense because a function requires each input to correspond to exactly one output.

---

### Task 6

To address the given task, we need to derive the inverse function of \( f(x) = x - 1 \) and visualize both functions in GeoGebra.

**Step 1: Find the Inverse Function**
The given function is \( f(x) = x - 1 \). To find the inverse function \( f^{-1}(x) \), perform the following steps:  

Replace \( f(x) \) with \( y \):  

\[
y = x - 1
\]

Swap \( x \) and \( y \) to find the inverse:  

\[
x = y - 1
\]

Solve for \( y \):  

\[
y = x + 1
\]  


Thus, the inverse function is:  

\[
f^{-1}(x) = x + 1
\]  


---

**Step 2: Graph Both Functions**
In GeoGebra, you can graph \( f(x) = x - 1 \) and \( f^{-1}(x) = x + 1 \) as follows:

1. Access the GeoGebra application or the online tool at [GeoGebra.org](https://www.geogebra.org).

2. In the Input box, type:  
     - `f(x) = x - 1`  
     - `f_inverse(x) = x + 1`

3. To show the relationship between \( f \) and \( f^{-1} \), graph the identity line \( y = x \). This helps illustrate that the functions are reflections of each other across this line.

4. Use different colors for the graphs of \( f(x) \), \( f^{-1}(x) \), and \( y = x \) to make them visually distinct.

### **Final Notes**
Both functions \( f(x) = x - 1 \) and \( f^{-1}(x) = x + 1 \) are linear. Their graphs will intersect the identity line \( y = x \), demonstrating their inverse relationship.

---
