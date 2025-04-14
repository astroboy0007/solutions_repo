# Calculus

## Functions

### Task 1

Functions:  

1. \( f(x) = x^2 \)  
2. \( g(x) = \sqrt{x} \)  
3. \( h(x) = \frac{1}{x} \)  
4. \( j(x) = \sin(x) \)

Calculation:  

1. For \( f(x) = x^2 \):  

\[
f(2) = 2^2 = 4
\]  


2. For \( g(x) = \sqrt{x} \):  

\[
g(2) = \sqrt{2} \approx 1.414
\]  


3. For \( h(x) = \frac{1}{x} \):  

\[
h(2) = \frac{1}{2} = 0.5
\]  


4. For \( j(x) = \sin(x) \):  

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

### Step 2: Compositions of Functions  
1. \( f(g(x)) \):  

   Substitute \( g(x) = \sqrt{x} \) into \( f(x) \):  

\[
f(g(x)) = f(\sqrt{x}) = 3\sqrt{x} - 1
\]  

2. \( g(f(x)) \):  

   Substitute \( f(x) = 3x - 1 \) into \( g(x) \):  

\[
g(f(x)) = g(3x - 1) = \sqrt{3x - 1}
\]  

3. \( f(f(x)) \):  

   Substitute \( f(x) = 3x - 1 \) into \( f(x) \) again:  

\[
f(f(x)) = f(3x - 1) = 3(3x - 1) - 1 = 9x - 3 - 1 = 9x - 4
\]  

4. \( g(g(x)) \):  

   Substitute \( g(x) = \sqrt{x} \) into \( g(x) \) again:  

\[
g(g(x)) = g(\sqrt{x}) = \sqrt{\sqrt{x}} = x^{1/4}
\]  

---

Step 3: Instructions for Visualizing in GeoGebra
To plot the functions \( f(g(x)) \), \( g(f(x)) \), \( f(f(x)) \), and \( g(g(x)) \) in GeoGebra:  

1. **Open GeoGebra**:  
   - Access the GeoGebra application or the online version at [GeoGebra.org](https://www.geogebra.org).     

2. **Enter the Functions**:  
   - In the Input field, type the functions as follows:
     - \( f(g(x)) = 3\sqrt{x} - 1 \)
     - \( g(f(x)) = \sqrt{3x - 1} \)
     - \( f(f(x)) = 9x - 4 \)
     - \( g(g(x)) = x^{1/4} \)  

3. **Set the Domain**:  
   - For \( f(g(x)) \), \( g(f(x)) \), and \( g(g(x)) \), restrict the domain to ensure the square root is defined (e.g., \( x \geq 0 \) for \( g(x) \)).
   - Use the syntax in GeoGebra, such as:
     - For \( g(f(x)) \): `If[3x - 1 >= 0, sqrt(3x - 1)]`  

4. **Customize the Graph**:  
   - Assign different colors to each function for better visualization. Right-click on a function and select "Settings" to change its color and style.  

5. **Analyze the Graphs**:  
   - Use GeoGebra’s point tool to evaluate the compositions at specific \( x \)-values.
   - Observe intersections or relationships between the curves.  

---


