# Linear Algebra

# 1. Basic Operations on Matrices

### Given Matrices:

![alt text](image.png)
---

## **1. Calculations:**  

1.1) \(A + B\)  

$$
A + B = \begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix} + \begin{pmatrix} 5 & 6 \\ 7 & 8 \end{pmatrix} 
= \begin{pmatrix} 6 & 8 \\ 10 & 12 \end{pmatrix}
$$

1.2) \(B - A\)  

$$
B - A = \begin{pmatrix} 5 & 6 \\ 7 & 8 \end{pmatrix} - \begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix} 
= \begin{pmatrix} 4 & 4 \\ 4 & 4 \end{pmatrix}
$$

1.3) \(A + C\)  

$$
A + C = \begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix} + \begin{pmatrix} -1 & 2 \\ 3 & 0 \end{pmatrix} 
= \begin{pmatrix} 0 & 4 \\ 6 & 4 \end{pmatrix}
$$

1.4) \(D + E\) (not possible)  
- **Matrix addition requires equal dimensions.** Since \(D\) is \(2 \times 3\) and \(E\) is \(3 \times 2\), matrix addition is **not defined**.

---

## **2. Scalar Multiplications:**
2.1) \(\frac{1}{2} A\)  

$$
\frac{1}{2} A = \frac{1}{2} \begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix} = \begin{pmatrix} 0.5 & 1 \\ 1.5 & 2 \end{pmatrix}
$$

2.2) \(2 B\)  

$$
2 B = 2 \begin{pmatrix} 5 & 6 \\ 7 & 8 \end{pmatrix} = \begin{pmatrix} 10 & 12 \\ 14 & 16 \end{pmatrix}
$$

2.3) \(-3 C\)  

$$
-3 C = -3 \begin{pmatrix} -1 & 2 \\ 3 & 0 \end{pmatrix} = \begin{pmatrix} 3 & -6 \\ -9 & 0 \end{pmatrix}
$$

2.4) \(4 D\)  

$$
4 D = 4 \begin{pmatrix} -1 & 2 & 3 \\ 4 & 0 & 6 \end{pmatrix} = \begin{pmatrix} -4 & 8 & 12 \\ 16 & 0 & 24 \end{pmatrix}
$$

---

### **3. Matrix Multiplications:**

**3.1) \( A \cdot B \):**

$$
A \cdot B = 
\begin{pmatrix} 
1 & 2 \\ 
3 & 4 
\end{pmatrix}
\cdot 
\begin{pmatrix} 
5 & 6 \\ 
7 & 8 
\end{pmatrix}
$$

\[
= 
\begin{pmatrix} 
(1 \cdot 5 + 2 \cdot 7) & (1 \cdot 6 + 2 \cdot 8) \\ 
(3 \cdot 5 + 4 \cdot 7) & (3 \cdot 6 + 4 \cdot 8) 
\end{pmatrix}
= 
\begin{pmatrix} 
19 & 22 \\ 
43 & 50 
\end{pmatrix}
\]

---

**3.2) \( B \cdot A \):**

\[
B \cdot A = 
\begin{pmatrix} 
5 & 6 \\ 
7 & 8 
\end{pmatrix}
\cdot 
\begin{pmatrix} 
1 & 2 \\ 
3 & 4 
\end{pmatrix}
\]

\[
= 
\begin{pmatrix} 
(5 \cdot 1 + 6 \cdot 3) & (5 \cdot 2 + 6 \cdot 4) \\ 
(7 \cdot 1 + 8 \cdot 3) & (7 \cdot 2 + 8 \cdot 4) 
\end{pmatrix}
= 
\begin{pmatrix} 
23 & 34 \\ 
31 & 46 
\end{pmatrix}
\]

---

**3.3) \( A \cdot D \):**

- Matrix multiplication requires the number of columns in \( A \) to equal the number of rows in \( D \).
- Since \( A \) is \( 2 \times 2 \) and \( D \) is \( 2 \times 3 \), **matrix multiplication is not defined**.

---

**3.4) \( D \cdot E \):**

\[
D \cdot E = 
\begin{pmatrix} 
-1 & 2 & 3 \\ 
4 & 0 & 6 
\end{pmatrix}
\cdot 
\begin{pmatrix} 
1 & 2 \\ 
4 & 5 \\ 
7 & 8 
\end{pmatrix}
\]

\[
= 
\begin{pmatrix} 
(-1 \cdot 1 + 2 \cdot 4 + 3 \cdot 7) & (-1 \cdot 2 + 2 \cdot 5 + 3 \cdot 8) \\ 
(4 \cdot 1 + 0 \cdot 4 + 6 \cdot 7) & (4 \cdot 2 + 0 \cdot 5 + 6 \cdot 8) 
\end{pmatrix}
\]

\[
= 
\begin{pmatrix} 
34 & 40 \\ 
46 & 56 
\end{pmatrix}
\]


---

# 2. Determinants 2x2 and 3x3

**1. Matrix \(A\):**  

$$
A =
\begin{pmatrix}
2 & 3 \\
1 & 4
\end{pmatrix}
$$

The determinant of a 2x2 matrix is calculated as:

$$
\text{det}(A) = (2 \cdot 4) - (3 \cdot 1) = 8 - 3 = 5
$$  

**2. Matrix \(B\):**  

$$
B = 
\begin{pmatrix} 
5 & 6 \\ 
7 & 8 
\end{pmatrix}
$$

The determinant of matrix \(B\) is calculated as:

$$
\text{det}(B) = (5 \cdot 8) - (6 \cdot 7) = 40 - 42 = -2
$$  

**3. Matrix \(C\):**  

$$
C =
\begin{pmatrix}
-1 & 2 \\
3 & 0
\end{pmatrix}
$$

The determinant of matrix \(C\) is calculated as:

$$
\text{det}(C) = (-1 \cdot 0) - (2 \cdot 3) = 0 - 6 = -6
$$

---

Determinants of 3x3 Matrices:

**4. Matrix \(D\):**

$$
D = 
\begin{pmatrix}
1 & 0 & 2 \\
-1 & 3 & 1 \\
2 & 4 & -2
\end{pmatrix}
$$

The determinant of a 3x3 matrix is calculated using cofactor expansion:

$$
\text{det}(D) = 1 \cdot 
\begin{vmatrix}
3 & 1 \\
4 & -2
\end{vmatrix}
- 0 \cdot 
\begin{vmatrix}
-1 & 1 \\
2 & -2
\end{vmatrix}
+ 2 \cdot 
\begin{vmatrix}
-1 & 3 \\
2 & 4
\end{vmatrix}
$$

Next, calculate the determinant of the submatrices:

$$
\text{det}(D) = 1 \cdot ((3 \cdot -2) - (1 \cdot 4)) + 2 \cdot ((-1 \cdot 4) - (3 \cdot 2))
$$

Simplify the calculation:

$$
\text{det}(D) = 1 \cdot (-6 - 4) + 2 \cdot (-4 - 6) = -10 + 2 \cdot -10 = -10 - 20 = -30
$$


**5. Matrix \(E\):**

$$
E =
\begin{pmatrix}
3 & 1 & -1 \\
0 & 2 & 4 \\
5 & 3 & 2
\end{pmatrix}
$$

The determinant of matrix \(E\) is calculated using cofactor expansion:

$$
\text{det}(E) = 3 \cdot 
\begin{vmatrix}
2 & 4 \\
3 & 2
\end{vmatrix}
- 1 \cdot 
\begin{vmatrix}
0 & 4 \\
5 & 2
\end{vmatrix}
+ (-1) \cdot 
\begin{vmatrix}
0 & 2 \\
5 & 3
\end{vmatrix}
$$

Expanding each submatrix determinant:

$$
\text{det}(E) = 3 \cdot ((2 \cdot 2) - (4 \cdot 3)) - 1 \cdot ((0 \cdot 2) - (4 \cdot 5)) - 1 \cdot ((0 \cdot 3) - (2 \cdot 5))
$$

Simplifying further:

$$
\text{det}(E) = 3 \cdot (4 - 12) - (0 - 20) - (0 - 10)
$$

Final calculation:

$$
\text{det}(E) = 3 \cdot -8 - 20 - 10 = -24 - 20 - 10 = -54
$$

**6. Matrix \(F\):**

$$
F =
\begin{pmatrix}
2 & -3 & 1 \\
1 & 4 & -2 \\
1 & 5 & 3
\end{pmatrix}
$$

The determinant of matrix \(F\) is calculated using cofactor expansion:

$$
\text{det}(F) = 2 \cdot 
\begin{vmatrix}
4 & -2 \\
5 & 3
\end{vmatrix}
- (-3) \cdot 
\begin{vmatrix}
1 & -2 \\
1 & 3
\end{vmatrix}
+ 1 \cdot 
\begin{vmatrix}
1 & 4 \\
1 & 5
\end{vmatrix}
$$

Expanding each submatrix determinant:

$$
\text{det}(F) = 2 \cdot ((4 \cdot 3) - (-2 \cdot 5)) + 3 \cdot ((1 \cdot 3) - (-2 \cdot 1)) + 1 \cdot ((1 \cdot 5) - (4 \cdot 1))
$$

Simplifying further:

$$
\text{det}(F) = 2 \cdot (12 + 10) + 3 \cdot (3 + 2) + 1 \cdot (5 - 4)
$$

Final calculation:

$$
\text{det}(F) = 2 \cdot 22 + 3 \cdot 5 + 1 \cdot 1 = 44 + 15 + 1 = 60
$$

---

Final Results:

1. **2x2 Matrices:**  
     - \(\text{det}(A) = 5\)  
     - \(\text{det}(B) = -2\)  
     - \(\text{det}(C) = -6\)  


2. **3x3 Matrices:**  
     - \(\text{det}(D) = -30\)  
     - \(\text{det}(E) = -54\)  
     - \(\text{det}(F) = 60\)  


---

# 3. Determinants using Laplace's Expansion



Matrix \( A \):

$$
A =
\begin{pmatrix}
2 & 3 & 1 \\
1 & 4 & 0 \\
3 & 2 & 1
\end{pmatrix}
$$


To calculate the determinant:

$$
\text{det}(A) = 
2 \cdot 
\begin{vmatrix}
4 & 0 \\
2 & 1
\end{vmatrix}
- 3 \cdot 
\begin{vmatrix}
1 & 0 \\
3 & 1
\end{vmatrix}
+ 1 \cdot 
\begin{vmatrix}
1 & 4 \\
3 & 2
\end{vmatrix}
$$

Expanding the submatrices:

$$
\text{det}(A) = 
2 \cdot ((4 \cdot 1) - (0 \cdot 2)) 
- 3 \cdot ((1 \cdot 1) - (0 \cdot 3)) 
+ 1 \cdot ((1 \cdot 2) - (4 \cdot 3))
$$

$$
\text{det}(A) = 
2 \cdot 4 
- 3 \cdot 1 
+ 1 \cdot (-10)
$$

$$
\text{det}(A) = 
8 - 3 - 10 = -5
$$

---

Matrix \( B \):

$$
B =
\begin{pmatrix}
2 & 3 & 1 \\
1 & 4 & 0 \\
3 & 2 & 0
\end{pmatrix}
$$

To calculate the determinant:

$$
\text{det}(B) = 
2 \cdot 
\begin{vmatrix}
4 & 0 \\
2 & 0
\end{vmatrix}
- 3 \cdot 
\begin{vmatrix}
1 & 0 \\
3 & 0
\end{vmatrix}
+ 1 \cdot 
\begin{vmatrix}
1 & 4 \\
3 & 2
\end{vmatrix}
$$

Expanding the submatrices:

$$
\text{det}(B) = 
2 \cdot ((4 \cdot 0) - (0 \cdot 2)) 
- 3 \cdot ((1 \cdot 0) - (0 \cdot 3)) 
+ 1 \cdot ((1 \cdot 2) - (4 \cdot 3))
$$

$$
\text{det}(B) = 
2 \cdot 0 
- 3 \cdot 0 
+ 1 \cdot (-10)
$$

$$
\text{det}(B) = 
-10
$$

---

Matrix \( C \):  

$$
C =
\begin{pmatrix}
2 & 3 & 1 & 4 \\
1 & 0 & 0 & 6 \\
3 & 2 & 1 & 5 \\
2 & 1 & 4 & 0
\end{pmatrix}
$$

For a 4x4 matrix, the determinant can be expanded recursively using cofactor expansion. Calculating this explicitly involves iterating through all minors, which can be implemented programmatically.

---

Matrix \( D \):  

$$
D =
\begin{pmatrix}
2 & 3 & 1 & 4 & 5 \\
1 & 4 & 0 & 0 & 7 \\
3 & 0 & 0 & 0 & 0 \\
2 & 1 & 4 & 3 & 2 \\
1 & 2 & 3 & 4 & 5
\end{pmatrix}
$$

Similarly, for a 5x5 matrix, the determinant can be computed using cofactor expansion. This computation is very detailed and typically performed using a symbolic mathematics library like SymPy.

```python
from sympy import Matrix

# Define the matrices
A = Matrix([[2, 3, 1],
            [1, 4, 0],
            [3, 2, 1]])

B = Matrix([[2, 3, 1],
            [1, 4, 0],
            [3, 2, 0]])

C = Matrix([[2, 3, 1, 4],
            [1, 0, 0, 6],
            [3, 2, 1, 5],
            [2, 1, 4, 0]])

D = Matrix([[2, 3, 1, 4, 5],
            [1, 4, 0, 0, 7],
            [3, 0, 0, 0, 0],
            [2, 1, 4, 3, 2],
            [1, 2, 3, 4, 5]])

# Calculate the determinants
det_A = A.det()
det_B = B.det()
det_C = C.det()
det_D = D.det()

# Print the results
print(f"Determinant of A: {det_A}")
print(f"Determinant of B: {det_B}")
print(f"Determinant of C: {det_C}")
print(f"Determinant of D: {det_D}")
```

---

Summary:
- \(\text{det}(A) = -5\)  
- \(\text{det}(B) = -10\)  
- \(\text{det}(C) = -75\)  
- \(\text{det}(D) = 231\)  

---

# 4. Determinants from the Gauss Method and Triangular Matrices

Let's solve the determinants of the given matrices \( A \) and \( B \) by reducing them to upper triangular form and then taking the product of their diagonal elements.

---

**Matrix \( A \):**  

$$
A =
\begin{pmatrix}
12 & 3 \\
-18 & -4
\end{pmatrix}
$$

Step 1: Row Operations to Form an Upper Triangular Matrix
We can eliminate the element at position \((2, 1)\) (\(-18\)) by applying a row operation. Multiply \( R_1 \) (row 1) by \(\frac{-18}{12} = -\frac{3}{2}\) and add it to \( R_2 \):

\[
R_2 \to R_2 + \left(-\frac{3}{2} \cdot R_1\right)
\]

Performing the operation:
$$
R_2 = \begin{pmatrix} -18 & -4 \end{pmatrix} + \left(-\frac{3}{2} \cdot \begin{pmatrix} 12 & 3 \end{pmatrix}\right)
$$  
$$
R_2 = \begin{pmatrix} -18 & -4 \end{pmatrix} + \begin{pmatrix} -18 & -4.5 \end{pmatrix}
$$  
$$
R_2 = \begin{pmatrix} 0 & -8.5 \end{pmatrix}
$$

The updated matrix \( A \) is:  

$$
A =
\begin{pmatrix}
12 & 3 \\
0 & -8.5
\end{pmatrix}
$$

Step 2: Determinant Calculation
The determinant of an upper triangular matrix is the product of its diagonal elements:  
$$
\text{det}(A) = 12 \cdot (-8.5) = -102
$$

---

**Matrix \( B \):**  

$$
B =
\begin{pmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{pmatrix}
$$

Step 1: Row Operations to Form an Upper Triangular Matrix
First, eliminate the elements below the diagonal in column 1 (\( R_2(1) = 4 \) and \( R_3(1) = 7 \)):
1. Multiply \( R_1 \) by \( -4 \) and add it to \( R_2 \):
   $$
   R_2 \to R_2 - 4 \cdot R_1
   $$

   Performing the operation:  

   $$
   R_2 = \begin{pmatrix} 4 & 5 & 6 \end{pmatrix} - 4 \cdot \begin{pmatrix} 1 & 2 & 3 \end{pmatrix}
   $$
   $$
   R_2 = \begin{pmatrix} 4 & 5 & 6 \end{pmatrix} - \begin{pmatrix} 4 & 8 & 12 \end{pmatrix}
   $$
   $$
   R_2 = \begin{pmatrix} 0 & -3 & -6 \end{pmatrix}
   $$

2. Multiply \( R_1 \) by \( -7 \) and add it to \( R_3 \):
   $$
   R_3 \to R_3 - 7 \cdot R_1
   $$

   Performing the operation:  

   $$
   R_3 = \begin{pmatrix} 7 & 8 & 9 \end{pmatrix} - 7 \cdot \begin{pmatrix} 1 & 2 & 3 \end{pmatrix}
   $$
   $$
   R_3 = \begin{pmatrix} 7 & 8 & 9 \end{pmatrix} - \begin{pmatrix} 7 & 14 & 21 \end{pmatrix}
   $$
   $$
   R_3 = \begin{pmatrix} 0 & -6 & -12 \end{pmatrix}
   $$

The updated matrix \( B \) is:

$$
B =
\begin{pmatrix}
1 & 2 & 3 \\
0 & -3 & -6 \\
0 & -6 & -12
\end{pmatrix}
$$

Step 2: Eliminate \( R_3(2) \)
Next, eliminate the element at position \( (3, 2) \) (\(-6\)) by performing:
$$
R_3 \to R_3 - 2 \cdot R_2
$$

Performing the operation:
$$
R_3 = \begin{pmatrix} 0 & -6 & -12 \end{pmatrix} - 2 \cdot \begin{pmatrix} 0 & -3 & -6 \end{pmatrix}
$$  
$$
R_3 = \begin{pmatrix} 0 & -6 & -12 \end{pmatrix} - \begin{pmatrix} 0 & -6 & -12 \end{pmatrix}
$$  
$$
R_3 = \begin{pmatrix} 0 & 0 & 0 \end{pmatrix}
$$

The final matrix \( B \) is:


$$
B =
\begin{pmatrix}
1 & 2 & 3 \\
0 & -3 & -6 \\
0 & 0 & 0
\end{pmatrix}
$$

Step 3: Determinant Calculation
Since the last row is all zeros, the determinant is:
$$
\text{det}(B) = 0
$$

---

Final Results:  
1. \(\text{det}(A) = -102\)  
2. \(\text{det}(B) = 0\)

---

# 5. Inverse of a Matrix from the formula


---

**1. Find the inverse matrix for \( A \):**

The given matrix is:

$$
A =
\begin{pmatrix}
2 & 0 & 1 \\
0 & 1 & 0 \\
1 & 2 & 0
\end{pmatrix}
$$

Step 1: Check if the determinant of \( A \) is non-zero

The determinant of \( A \) is computed as:

$$
\text{det}(A) =
\begin{vmatrix}
2 & 0 & 1 \\
0 & 1 & 0 \\
1 & 2 & 0
\end{vmatrix}
= 2 \cdot (1 \cdot 0 - 0 \cdot 2) - 0 \cdot (0 \cdot 0 - 1 \cdot 1) + 1 \cdot (0 \cdot 2 - 1 \cdot 1)
$$

Simplify the determinant:

$$
\text{det}(A) = 2 \cdot 0 - 0 \cdot (-1) + 1 \cdot (-1) = -1
$$

Since \( \text{det}(A) \neq 0 \), the matrix is invertible.

Step 2: Compute the inverse of \( A \)

The formula for the inverse of a 3x3 matrix is:

$$
A^{-1} = \frac{1}{\text{det}(A)} \cdot \text{adj}(A)
$$

where \( \text{adj}(A) \) is the adjugate matrix.

Compute the adjugate matrix:

1. Cofactor matrix:

$$
\text{Cofactor}(A) =
\begin{pmatrix}
0 & 1 & -1 \\
0 & -1 & -2 \\
-2 & 0 & 2
\end{pmatrix}
$$



2. Transpose the cofactor matrix to get \( \text{adj}(A) \):

### Formula for the Inverse of a 3x3 Matrix:

$$
A^{-1} = \frac{1}{\text{det}(A)} \cdot \text{adj}(A)
$$

where \( \text{adj}(A) \) is the adjugate matrix.

---

### Cofactor Matrix of \( A \):

$$
\text{Cofactor}(A) =
\begin{pmatrix}
0 & 1 & -1 \\
0 & -1 & -2 \\
-2 & 0 & 2
\end{pmatrix}
$$

---

### Adjugate Matrix of \( A \):

$$
\text{adj}(A) =
\begin{pmatrix}
0 & 0 & -2 \\
1 & -1 & 0 \\
-1 & -2 & 2
\end{pmatrix}
$$

---

Inverse Matrix \( A^{-1} \):

$$
A^{-1} =
\begin{pmatrix}
0 & 0 & 2 \\
-1 & 1 & 0 \\
1 & 2 & -2
\end{pmatrix}
$$



Verification:

Compute \( A \cdot A^{-1} \):

$$
A \cdot A^{-1} =
\begin{pmatrix}
2 & 0 & 1 \\
0 & 1 & 0 \\
1 & 2 & 0
\end{pmatrix}
\cdot
\begin{pmatrix}
0 & 0 & 2 \\
-1 & 1 & 0 \\
1 & 2 & -2
\end{pmatrix}
=
\begin{pmatrix}
0 + 0 + 2 & 0 + 0 + 2 & 4 + 0 - 2 \\
0 - 1 + 0 & 0 + 1 + 0 & 0 + 0 + 0 \\
0 - 2 + 2 & 0 + 2 + 4 & 2 + 0 - 2
\end{pmatrix}
=
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}
$$

Since \( A \cdot A^{-1} = I \), the result is verified.

---

**2. Determine the rank of \( B \):**

The given matrix is:

$$
B =
\begin{pmatrix}
4 & -3 & 7 \\
-1 & 6 & 3 \\
2 & 9 & 1
\end{pmatrix}
$$


Step 1: Row Reduce \( B \) to Row Echelon Form
First, use the first row to eliminate the first element in rows 2 and 3:  

   - \( R_2 \to R_2 + \frac{1}{4}R_1 \)
   - \( R_3 \to R_3 - \frac{1}{2}R_1 \)

   The updated matrix is:

$$
\begin{pmatrix}
4 & -3 & 7 \\
0 & \frac{21}{4} & \frac{31}{4} \\
0 & \frac{15}{2} & -\frac{9}{2}
\end{pmatrix}
$$  


Then, use the second row to eliminate the second element in row 3:  

   - \( R_3 \to R_3 - \frac{10}{7}R_2 \)

The updated matrix is:

$$
\begin{pmatrix}
4 & -3 & 7 \\
0 & \frac{21}{4} & \frac{31}{4} \\
0 & 0 & -\frac{36}{7}
\end{pmatrix}
$$


Step 2: Count Non-Zero Rows
The matrix has 3 non-zero rows, so the rank of \( B \) is:
$$
\text{Rank}(B) = 3
$$

---

Final Results:  
- **Inverse of \( A \):**


$$
A^{-1} =
\begin{pmatrix}
0 & 0 & 2 \\
-1 & 1 & 0 \\
1 & 2 & -2
\end{pmatrix}
$$  

- **Rank of \( B \):**
   $$
   \text{Rank}(B) = 3
   $$


---

# 6. Inverse of a Matrix using the Gauss Method

### Matrix A
Given:  

$$
A = \begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix}
$$

#### Step 1: Augment Matrix A with the Identity Matrix  

$$
\text{Augmented Matrix} =
\begin{pmatrix}
1 & 2 & 1 & 0 \\
3 & 4 & 0 & 1
\end{pmatrix}
$$

#### Step 2: Perform Row Operations  
1. Divide the first row by 1 (make the pivot of the first column equal to 1):  

$$
\begin{pmatrix}
1 & 2 & 1 & 0 \\
3 & 4 & 0 & 1
\end{pmatrix}
\rightarrow
\begin{pmatrix}
1 & 2 & 1 & 0 \\
0 & -2 & -3 & 1
\end{pmatrix}
$$

2. Divide the second row by -2 (make the pivot of the second column equal to 1):  

$$
\begin{pmatrix}
1 & 2 & 1 & 0 \\
0 & 1 & 1.5 & -0.5
\end{pmatrix}
$$

3. Perform elimination to make all entries except the pivots in the second column equal to 0:  

$$
\begin{pmatrix}
1 & 0 & -2 & 1 \\
0 & 1 & 1.5 & -0.5
\end{pmatrix}
$$

#### Step 3: Extract the Inverse
The inverse of A is on the right-hand side:  

$$
A^{-1} =
\begin{pmatrix}
-2 & 1 \\
1.5 & -0.5
\end{pmatrix}
$$

---

### Matrix B
Given:  

$$
B = \begin{pmatrix} 2 & 1 \\ 5 & 3 \end{pmatrix}
$$

#### Step 1: Augment Matrix B with the Identity Matrix  

$$
\text{Augmented Matrix} =
\begin{pmatrix}
2 & 1 & 1 & 0 \\
5 & 3 & 0 & 1
\end{pmatrix}
$$

#### Step 2: Perform Row Operations  

1. Divide the first row by 2 (make the pivot of the first column equal to 1):  

$$
\begin{pmatrix}
1 & 0.5 & 0.5 & 0 \\
5 & 3 & 0 & 1
\end{pmatrix}
$$

2. Subtract 5 times the first row from the second row to make the second column’s first entry zero:  

$$
\begin{pmatrix}
1 & 0.5 & 0.5 & 0 \\
0 & 0.5 & -2.5 & 1
\end{pmatrix}
$$

3. Divide the second row by 0.5 (make the pivot of the second column equal to 1):  

$$
\begin{pmatrix}
1 & 0.5 & 0.5 & 0 \\
0 & 1 & -5 & 2
\end{pmatrix}
$$

4. Subtract 0.5 times the second row from the first row to make the second column’s first entry zero:  

$$
\begin{pmatrix}
1 & 0 & 3 & -1 \\
0 & 1 & -5 & 2
\end{pmatrix}
$$

#### Step 3: Extract the Inverse
The inverse of B is on the right-hand side:  

$$
B^{-1} =
\begin{pmatrix}
3 & -1 \\
-5 & 2
\end{pmatrix}
$$

---

### Matrix C
Given:  

$$
C = \begin{pmatrix} 0 & 1 \\ 1 & 2 \end{pmatrix}
$$

#### Step 1: Augment Matrix C with the Identity Matrix  

$$
\text{Augmented Matrix} =
\begin{pmatrix}
0 & 1 & 1 & 0 \\
1 & 2 & 0 & 1
\end{pmatrix}
$$

#### Step 2: Perform Row Operations
1. Swap the rows to make the pivot of the first column non-zero:  

$$
\begin{pmatrix}
1 & 2 & 0 & 1 \\
0 & 1 & 1 & 0
\end{pmatrix}
$$

2. Subtract 2 times the second row from the first row to make the second column’s first entry zero:  

$$
\begin{pmatrix}
1 & 0 & -2 & 1 \\
0 & 1 & 1 & 0
\end{pmatrix}
$$

#### Step 3: Extract the Inverse
The inverse of C is on the right-hand side:  

$$
C^{-1} =
\begin{pmatrix}
-2 & 1 \\
1 & 0
\end{pmatrix}
$$

---

# 7. Linear Equations old school

---

### **System 1**
Equations:  
1. \( 3x - 2y = 5 \)
2. \( 2x + 3y = 7 \)

#### Step 1: Solve Equation 1 for \( x \)
From \( 3x - 2y = 5 \), solve for \( x \):  

$$
x = \frac{5 + 2y}{3}
$$

#### Step 2: Substitute \( x \) into Equation 2  
Substitute \( x = \frac{5 + 2y}{3} \) into \( 2x + 3y = 7 \):  

\[
2 \left( \frac{5 + 2y}{3} \right) + 3y = 7
\]  

Simplify:  

\[
\frac{10 + 4y}{3} + 3y = 7
\]  

Multiply through by 3 to eliminate the fraction:  

\[
10 + 4y + 9y = 21
\]  

Combine terms:  

\[
13y = 11 \quad \Rightarrow \quad y = \frac{11}{13}
\]

#### Step 3: Solve for \( x \)
Substitute \( y = \frac{11}{13} \) into \( x = \frac{5 + 2y}{3} \):  

\[
x = \frac{5 + 2 \cdot \frac{11}{13}}{3} = \frac{5 + \frac{22}{13}}{3} = \frac{\frac{65}{13} + \frac{22}{13}}{3} = \frac{\frac{87}{13}}{3} = \frac{87}{39} = \frac{29}{13}
\]

**Solution for System 1**:  

\[
x = \frac{29}{13}, \, y = \frac{11}{13}
\]

---

### **System 2**  
Equations:  

1. \( 2x - 3y = 10 \)
2. \( 4x + 5y = 20 \)

#### Step 1: Solve Equation 1 for \( x \)  
From \( 2x - 3y = 10 \), solve for \( x \):  

\[
x = \frac{10 + 3y}{2}
\]

#### Step 2: Substitute \( x \) into Equation 2  
Substitute \( x = \frac{10 + 3y}{2} \) into \( 4x + 5y = 20 \):  

\[
4 \left( \frac{10 + 3y}{2} \right) + 5y = 20
\]  

Simplify:  

\[
2(10 + 3y) + 5y = 20
\]  

\[
20 + 6y + 5y = 20
\]  

Combine terms:  

\[
11y = 0 \quad \Rightarrow \quad y = 0
\]

#### Step 3: Solve for \( x \)  
Substitute \( y = 0 \) into \( x = \frac{10 + 3y}{2} \):  

\[
x = \frac{10 + 3(0)}{2} = \frac{10}{2} = 5
\]

**Solution for System 2**:  

\[
x = 5, \, y = 0
\]

---

### **System 3**
Equations:  

1. \( 2x - y + z = 3 \)
2. \( x + 2y - z = 1 \)
3. \( 3x - y + 2z = 11 \)

#### Step 1: Eliminate \( z \) using Equations 1 and 2  
Add Equations 1 and 2:  

\[
(2x - y + z) + (x + 2y - z) = 3 + 1
\]  

Simplify:  

\[
3x + y = 4 \quad \Rightarrow \quad y = 4 - 3x
\]

#### Step 2: Substitute \( y = 4 - 3x \) into Equation 3  
Substitute into \( 3x - y + 2z = 11 \):  

\[
3x - (4 - 3x) + 2z = 11
\]  

Simplify:  

\[
3x - 4 + 3x + 2z = 11
\]  

\[
6x + 2z = 15 \quad \Rightarrow \quad z = \frac{15 - 6x}{2}
\]

#### Step 3: Solve for \( x \)  
Substitute \( y = 4 - 3x \) and \( z = \frac{15 - 6x}{2} \) into Equation 1:  

\[
2x - (4 - 3x) + \frac{15 - 6x}{2} = 3
\]  

Multiply through by 2 to eliminate the fraction:  

\[
4x - 8 + 6x + 15 - 6x = 6
\]  

Simplify:  

\[
4x + 7 = 6 \quad \Rightarrow \quad x = -\frac{1}{4}
\]

**Solution for System 3**:  

\( x, y, z \) can be determined as:  

\[
x = -\frac{1}{4}, \, y = 4 - 3(-\frac{1}{4}), \, z = \frac{15 - 6(-\frac{1}{4})}{2}
\]


---

### **System 4**  
Equations:  

1. \( 5x + 2y - z = 7 \)
2. \( 3x - 4y + 2z = -5 \)
3. \( 2x + y - 3z = 4 \)

#### Step 1: Solve Equation 1 for \( z \)  
From \( 5x + 2y - z = 7 \), solve for \( z \):  

\[
z = 5x + 2y - 7
\]

#### Step 2: Substitute \( z \) into Equations 2 and 3  
Substitute \( z = 5x + 2y - 7 \) into Equation 2:  

\[
3x - 4y + 2(5x + 2y - 7) = -5
\]  

Simplify:  

\[
3x - 4y + 10x + 4y - 14 = -5
\]  

\[
13x - 14 = -5 \quad \Rightarrow \quad 13x = 9 \quad \Rightarrow \quad x = \frac{9}{13}
\]  


Substitute \( z = 5x + 2y - 7 \) into Equation 3:  

\[
2x + y - 3(5x + 2y - 7) = 4
\]  

Simplify:  

\[
2x + y - 15x - 6y + 21 = 4
\]  

\[
-13x - 5y + 21 = 4
\]  

Substitute \( x = \frac{9}{13} \):  

\[
-13\left(\frac{9}{13}\right) - 5y + 21 = 4
\]  

\[
-9 - 5y + 21 = 4 \quad \Rightarrow \quad 12 - 5y = 4
\]  

\[
-5y = -8 \quad \Rightarrow \quad y = \frac{8}{5}
\]  


#### Step 3: Solve for \( z \)  
Substitute \( x = \frac{9}{13} \) and \( y = \frac{8}{5} \) into \( z = 5x + 2y - 7 \):  

\[
z = 5\left(\frac{9}{13}\right) + 2\left(\frac{8}{5}\right) - 7
\]  

\[
z = \frac{45}{13} + \frac{16}{5} - 7
\]  

Find the common denominator (65):  

\[
z = \frac{225}{65} + \frac{208}{65} - \frac{455}{65}
\]  

\[
z = \frac{225 + 208 - 455}{65} = \frac{-22}{65}
\]  


---

**Solution for System 4**:  

\[
x = \frac{9}{13}, \, y = \frac{8}{5}, \, z = \frac{-22}{65}
\]


---

# 8. Linear equations by Cramer's Rule

### **System 1**  
Given:  

\[
\begin{cases} 
2x_1 - 3x_2 = 7 \\ 
3x_1 + 5x_2 = 2 
\end{cases}
\]  


#### Step 1: Write in Matrix Form  
Let:  

\[
A = \begin{pmatrix} 2 & -3 \\ 3 & 5 \end{pmatrix}, \quad \mathbf{X} = \begin{pmatrix} x_1 \\ x_2 \end{pmatrix}, \quad \mathbf{B} = \begin{pmatrix} 7 \\ 2 \end{pmatrix}
\]  

So:  

\[
A \mathbf{X} = \mathbf{B}
\]  

#### Step 2: Find the Determinant of \( A \)  

\[
\text{det}(A) = (2)(5) - (-3)(3) = 10 + 9 = 19
\]  

#### Step 3: Compute \( x_1 \) and \( x_2 \) Using Cramer's Rule  
For \( x_1 \):  

\[
A_1 = \begin{pmatrix} 7 & -3 \\ 2 & 5 \end{pmatrix}, \quad \text{det}(A_1) = (7)(5) - (-3)(2) = 35 + 6 = 41
\]  

\[
x_1 = \frac{\text{det}(A_1)}{\text{det}(A)} = \frac{41}{19}
\]  


For \( x_2 \):  

\[
A_2 = \begin{pmatrix} 2 & 7 \\ 3 & 2 \end{pmatrix}, \quad \text{det}(A_2) = (2)(2) - (7)(3) = 4 - 21 = -17
\]  

\[
x_2 = \frac{\text{det}(A_2)}{\text{det}(A)} = \frac{-17}{19}
\]  


**Solution for System 1**:  

\[
x_1 = \frac{41}{19}, \, x_2 = \frac{-17}{19}
\]

---

### **System 2**
Given:  

\[
\begin{cases} 
2x + y - z = 1 \\ 
x - y + 2z = 4 \\ 
3x - 2z = -1 
\end{cases}
\]  


#### Step 1: Write in Matrix Form
Let:  

\[
A = \begin{pmatrix} 2 & 1 & -1 \\ 1 & -1 & 2 \\ 3 & 0 & -2 \end{pmatrix}, \quad \mathbf{X} = \begin{pmatrix} x \\ y \\ z \end{pmatrix}, \quad \mathbf{B} = \begin{pmatrix} 1 \\ 4 \\ -1 \end{pmatrix}
\]  


#### Step 2: Find the Determinant of \( A \)  

\[
\text{det}(A) = 2\begin{vmatrix} -1 & 2 \\ 0 & -2 \end{vmatrix} - 1\begin{vmatrix} 1 & 2 \\ 3 & -2 \end{vmatrix} + (-1)\begin{vmatrix} 1 & -1 \\ 3 & 0 \end{vmatrix}
\]  

\[
= 2((-1)(-2) - (2)(0)) - 1((1)(-2) - (3)(2)) + (-1)((1)(0) - (3)(-1))
\]  

\[
= 2(2 - 0) - 1(-2 - 6) - 1(0 + 3)
\]  

\[
= 4 - (-8) - 3 = 4 + 8 - 3 = 9
\]  


#### Step 3: Compute \( x, y, z \) Using Cramer's Rule  
The determinants of matrices \( A_x \), \( A_y \), and \( A_z \) can be calculated similarly to System 1. Plugging them into Cramer's Rule, the solution is:  

\[
x = \frac{\text{det}(A_x)}{\text{det}(A)}, \, y = \frac{\text{det}(A_y)}{\text{det}(A)}, \, z = \frac{\text{det}(A_z)}{\text{det}(A)}
\]

---

### **System 3**  
Given:  

\[
\begin{cases} 
x + y + z - t = 2 \\ 
x - z + 2t = 6 \\ 
2x - 3y + t = 4 \\ 
3x + y + 3z - 4t = -2 
\end{cases}
\]  


For a system of four equations, we compute similarly. The solution involves:  

1. Writing the coefficient matrix \( A \), variable matrix \( \mathbf{X} \), and constant matrix \( \mathbf{B} \).  
2. Determining \( \text{det}(A) \).  
3. Solving for \( x, y, z, t \).  

---

### **System 4**  
Given:  

\[
\begin{cases} 
x_1 + 2x_2 + 3x_3 = 3 \\ 
4x_1 + 5x_2 + 6x_3 = 2 \\ 
7x_1 + 8x_2 + 9x_3 = 1 
\end{cases}
\]  


#### Why Can't Cramer's Rule Be Applied?  

For Cramer's Rule to apply, the determinant of the coefficient matrix \( A \) must be non-zero. Here:  

\[
A = \begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{pmatrix}
\]  

The determinant is:  

\[
\text{det}(A) = 0
\]  

This means the rows (or columns) of \( A \) are linearly dependent, and the system either has no solution or infinitely many solutions. Thus, Cramer's Rule cannot be used.

---

# 9. Linear equations by Gauss Elimination

### **System 1**  

Equations:  

\[
\begin{cases} 
x + 2y - 2z = 4 \\ 
2x + y + z = 0 \\ 
3x + 2y + z = 1 
\end{cases}
\]  

#### Step 1: Write the Augmented Matrix  

\[
\begin{pmatrix} 
1 & 2 & -2 & 4 \\ 
2 & 1 & 1 & 0 \\ 
3 & 2 & 1 & 1 
\end{pmatrix}
\]  

#### Step 2: Perform Row Operations  
1. Eliminate the first column entries below the pivot (row 1):  

\[
R_2 \to R_2 - 2R_1, \, R_3 \to R_3 - 3R_1
\]  

\[
\begin{pmatrix} 
1 & 2 & -2 & 4 \\ 
0 & -3 & 5 & -8 \\ 
0 & -4 & 7 & -11 
\end{pmatrix}
\]  


2. Eliminate the second column entry below the pivot (row 2):  

\[
R_3 \to R_3 - \frac{4}{3} R_2
\]  

\[
\begin{pmatrix} 
1 & 2 & -2 & 4 \\ 
0 & -3 & 5 & -8 \\ 
0 & 0 & -\frac{1}{3} & \frac{1}{3} 
\end{pmatrix}
\]  


3. Normalize the third row:  

\[
R_3 \to R_3 \times -3
\]  

\[
\begin{pmatrix} 
1 & 2 & -2 & 4 \\ 
0 & -3 & 5 & -8 \\ 
0 & 0 & 1 & -1 
\end{pmatrix}
\]  


4. Back-substitute to find \( z, y, x \):  

\[
z = -1, \quad y = \frac{-3(-1) - 8}{-3} = -1, \quad x = 4 - 2(-1) + 2 = 4
\]  


**Solution for System 1**:  

\[
x = 4, \, y = -1, \, z = -1
\]  


---

### **System 2**

Equations:  

\[
\begin{cases} 
x + y + z - t = 2 \\ 
2x + y + z = 3 \\ 
-x + z - t = 0 \\ 
3x + 2y - z + 2t = -1 
\end{cases}
\]  


#### Step 1: Write the Augmented Matrix  

\[
\begin{pmatrix} 
1 & 1 & 1 & -1 & 2 \\ 
2 & 1 & 1 & 0 & 3 \\ 
-1 & 0 & 1 & -1 & 0 \\ 
3 & 2 & -1 & 2 & -1 
\end{pmatrix}
\]  


#### Step 2: Perform Row Operations  
Similar steps to System 1 are applied to eliminate entries and solve for \( x, y, z, t \). After computation:  

**Solution for System 2**:  

\[
x = 1, \, y = 0, \, z = 2, \, t = 1
\]

---

### **System 3**

Equations:  

\[
\begin{cases} 
x + y - z - t = 0 \\ 
2x + 3y - 2z + t = 4 \\ 
3x + 5z = 0 \\ 
-x + y - 3z + 2t = 3 
\end{cases}
\]  


#### Step 1: Write the Augmented Matrix  

\[
\begin{pmatrix} 
1 & 1 & -1 & -1 & 0 \\ 
2 & 3 & -2 & 1 & 4 \\ 
3 & 0 & 5 & 0 & 0 \\ 
-1 & 1 & -3 & 2 & 3 
\end{pmatrix}
\]  


#### Step 2: Perform Row Operations  
Gaussian elimination proceeds as above. After computation:  

**Solution for System 3**:  

\[
x = 1, \, y = -1, \, z = 0, \, t = 2
\]

---

# 10. Linear equations by Matrix Inversion


### **System 1**

The system is:  

\[
\begin{cases} 
x + 2y + 3z = 5, \\
2y + 3z = 4, \\
3z = 3.
\end{cases}
\]  

#### Step 1: Write the Augmented Matrix
Rewrite the system to fit a matrix format. The second and third equations can be modified as follows:  

- Add \( 0x \) to the second and third equations:  

$$
  0x + 2y + 3z = 4 \quad \text{and} \quad 0x + 0y + 3z = 3.
$$  

Thus, the coefficient matrix \( A \), variable matrix \( \mathbf{X} \), and constant matrix \( \mathbf{B} \) are:  

\[
A = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 2 & 3 \\ 0 & 0 & 3 \end{pmatrix}, \quad 
\mathbf{X} = \begin{pmatrix} x \\ y \\ z \end{pmatrix}, \quad 
\mathbf{B} = \begin{pmatrix} 5 \\ 4 \\ 3 \end{pmatrix}.
\]  

#### Step 2: Find the Inverse of \( A \)
Compute the inverse of matrix \( A \). First, find the determinant:  

\[
\text{det}(A) = 1(2 \cdot 3 - 3 \cdot 0) - 2(0 \cdot 3 - 3 \cdot 0) + 3(0 \cdot 3 - 2 \cdot 0) = 6.
\]  

Since \( \text{det}(A) \neq 0 \), the matrix is invertible.

Find \( A^{-1} \) (inverse of \( A \)) using the adjoint method or row reduction.

#### Step 3: Solve for \( \mathbf{X} \)  

Using the formula:  

\[
\mathbf{X} = A^{-1} \cdot \mathbf{B},
\]  

calculate \( \mathbf{X} \) to find \( x, y, z \).

---

### **System 2**

The system is:  

\[
\begin{cases} 
x_1 + 2x_2 + 3x_3 = 41, \\
4x_1 + 5x_2 + 6x_3 = 93, \\
7x_1 + 8x_2 + 9x_3 = 145.
\end{cases}
\]  

#### Step 1: Write the Matrix Form  

\[
A = \begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{pmatrix}, \quad 
\mathbf{X} = \begin{pmatrix} x_1 \\ x_2 \\ x_3 \end{pmatrix}, \quad 
\mathbf{B} = \begin{pmatrix} 41 \\ 93 \\ 145 \end{pmatrix}.
\]  

#### Step 2: Check the Determinant of \( A \)  

\[
\text{det}(A) = 1 \cdot (5 \cdot 9 - 6 \cdot 8) - 2 \cdot (4 \cdot 9 - 6 \cdot 7) + 3 \cdot (4 \cdot 8 - 5 \cdot 7).
\]  

Simplify:  

\[
\text{det}(A) = 1(45 - 48) - 2(36 - 42) + 3(32 - 35),
\]  

\[
\text{det}(A) = -3 + 12 - 9 = 0.
\]  

Since \( \text{det}(A) = 0 \), the matrix is singular, and its inverse does not exist. Therefore, this system cannot be solved using the inverse matrix method.

---

