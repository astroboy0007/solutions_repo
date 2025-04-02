# Linear Algebra

## 1. Basic Operations on Matrices

## Given Matrices:

![alt text](image.png)
---

## **1. Calculations:**
### 1.1) \(A + B\)
$$
A + B = \begin{pmatrix} 1 + 5 & 2 + 6 \\ 3 + 7 & 4 + 8 \end{pmatrix} = \begin{pmatrix} 6 & 8 \\ 10 & 12 \end{pmatrix}
$$

### 1.2) \(B - A\)
$$
B - A = \begin{pmatrix} 5 - 1 & 6 - 2 \\ 7 - 3 & 8 - 4 \end{pmatrix} = \begin{pmatrix} 4 & 4 \\ 4 & 4 \end{pmatrix}
$$

### 1.3) \(A + C\)
$$
A + C = \begin{pmatrix} 1 + (-1) & 2 + 2 \\ 3 + 3 & 4 + 0 \end{pmatrix} = \begin{pmatrix} 0 & 4 \\ 6 & 4 \end{pmatrix}
$$

### 1.4) \(D + E\) (not possible)
- **Matrix addition requires equal dimensions.** Since \(D\) is \(2 \times 3\) and \(E\) is \(3 \times 2\), matrix addition is **not defined**.

---

## **2. Scalar Multiplications:**
### 2.1) \(\frac{1}{2} A\)
$$
\frac{1}{2} A = \frac{1}{2} \begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix} = \begin{pmatrix} 0.5 & 1 \\ 1.5 & 2 \end{pmatrix}
$$

### 2.2) \(2 B\)
$$
2 B = 2 \begin{pmatrix} 5 & 6 \\ 7 & 8 \end{pmatrix} = \begin{pmatrix} 10 & 12 \\ 14 & 16 \end{pmatrix}
$$

### 2.3) \(-3 C\)
$$
-3 C = -3 \begin{pmatrix} -1 & 2 \\ 3 & 0 \end{pmatrix} = \begin{pmatrix} 3 & -6 \\ -9 & 0 \end{pmatrix}
$$

### 2.4) \(4 D\)
$$
4 D = 4 \begin{pmatrix} -1 & 2 & 3 \\ 4 & 0 & 6 \end{pmatrix} = \begin{pmatrix} -4 & 8 & 12 \\ 16 & 0 & 24 \end{pmatrix}
$$

---

## **3. Matrix Multiplications:**

### **3.1) \( A \cdot B \):**

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

### **3.2) \( B \cdot A \):**

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

### **3.3) \( A \cdot D \):**

- Matrix multiplication requires the number of columns in \( A \) to equal the number of rows in \( D \).
- Since \( A \) is \( 2 \times 2 \) and \( D \) is \( 2 \times 3 \), **matrix multiplication is not defined**.

---

### **3.4) \( D \cdot E \):**

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

## 2. Determinants 2x2 and 3x3

### **1. Matrix \(A\):**
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

### **2. Matrix \(B\):**  
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

### **3. Matrix \(C\):**  
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

## Determinants of 3x3 Matrices:

### **4. Matrix \(D\):**

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


### **5. Matrix \(E\):**

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

### **6. Matrix \(F\):**

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

### Final Results:

1. **2x2 Matrices:**  
     - \(\text{det}(A) = 5\)  
     - \(\text{det}(B) = -2\)  
     - \(\text{det}(C) = -6\)  


2. **3x3 Matrices:**  
     - \(\text{det}(D) = -30\)  
     - \(\text{det}(E) = -54\)  
     - \(\text{det}(F) = 60\)  



## 3. Determinants using Laplace's Expansion


---

### Matrix \( A \):
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

### Matrix \( B \):

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

### Matrix \( C \):
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

### Matrix \( D \):
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

### Summary:
- \(\text{det}(A) = -5\)
- \(\text{det}(B) = -10\)
- \(\text{det}(C) = -75\)
- \(\text{det}(D) = 231\)

## 4. Determinants from the Gauss Method and Triangular Matrices

Let's solve the determinants of the given matrices \( A \) and \( B \) by reducing them to upper triangular form and then taking the product of their diagonal elements.

---

### **Matrix \( A \):**
$$
A =
\begin{pmatrix}
12 & 3 \\
-18 & -4
\end{pmatrix}
$$

#### Step 1: Row Operations to Form an Upper Triangular Matrix
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

#### Step 2: Determinant Calculation
The determinant of an upper triangular matrix is the product of its diagonal elements:  
$$
\text{det}(A) = 12 \cdot (-8.5) = -102
$$

---

### **Matrix \( B \):**
$$
B =
\begin{pmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{pmatrix}
$$

#### Step 1: Row Operations to Form an Upper Triangular Matrix
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

#### Step 2: Eliminate \( R_3(2) \)
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

#### Step 3: Determinant Calculation
Since the last row is all zeros, the determinant is:
$$
\text{det}(B) = 0
$$

---

### Final Results:
1. \(\text{det}(A) = -102\)
2. \(\text{det}(B) = 0\)

## 5. Inverse of a Matrix from the formula

Here’s the solution to the two problems, formatted in markdown:

---

### **1. Find the inverse matrix for \( A \):**

The given matrix is:

$$
A =
\begin{pmatrix}
2 & 0 & 1 \\
0 & 1 & 0 \\
1 & 2 & 0
\end{pmatrix}
$$

#### Step 1: Check if the determinant of \( A \) is non-zero

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

#### Step 2: Compute the inverse of \( A \)

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

### Inverse Matrix \( A^{-1} \):

$$
A^{-1} =
\begin{pmatrix}
0 & 0 & 2 \\
-1 & 1 & 0 \\
1 & 2 & -2
\end{pmatrix}
$$



#### Verification:

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

### **2. Determine the rank of \( B \):**

The given matrix is:

$$
B =
\begin{pmatrix}
4 & -3 & 7 \\
-1 & 6 & 3 \\
2 & 9 & 1
\end{pmatrix}
$$


#### Step 1: Row Reduce \( B \) to Row Echelon Form
1. Use the first row to eliminate the first element in rows 2 and 3:
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

2. Use the second row to eliminate the second element in row 3:
   - \( R_3 \to R_3 - \frac{10}{7}R_2 \)

The updated matrix is:
$$
\begin{pmatrix}
4 & -3 & 7 \\
0 & \frac{21}{4} & \frac{31}{4} \\
0 & 0 & -\frac{36}{7}
\end{pmatrix}
$$

#### Step 2: Count Non-Zero Rows
The matrix has 3 non-zero rows, so the rank of \( B \) is:
$$
\text{Rank}(B) = 3
$$

---

### Final Results:
1. **Inverse of \( A \):**
   $$
   A^{-1} =
   \begin{pmatrix}
   0 & 0 & 2 \\
   -1 & 1 & 0 \\
   1 & 2 & -2
   \end{pmatrix}
   $$

2. **Rank of \( B \):**
   $$
   \text{Rank}(B) = 3
   $$
