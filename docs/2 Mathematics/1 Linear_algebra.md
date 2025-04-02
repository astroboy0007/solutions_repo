# Linear Algebra


## Given Matrices:
1. **Matrix \(A\):**
   $$
   A = \begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix}
   $$

2. **Matrix \(B\):**
   $$
   B = \begin{pmatrix} 5 & 6 \\ 7 & 8 \end{pmatrix}
   $$

3. **Matrix \(C\):**
   $$
   C = \begin{pmatrix} -1 & 2 \\ 3 & 0 \end{pmatrix}
   $$

4. **Matrix \(D\):**
   $$
   D = \begin{pmatrix} -1 & 2 & 3 \\ 4 & 0 & 6 \end{pmatrix}
   $$

5. **Matrix \(E\):**
   $$
   E = \begin{pmatrix} 1 & 2 \\ 4 & 5 \\ 7 & 8 \end{pmatrix}
   $$

---

## **1. Calculations:**
#### 1.1) \(A + B\)
$$
A + B = \begin{pmatrix} 1 + 5 & 2 + 6 \\ 3 + 7 & 4 + 8 \end{pmatrix} = \begin{pmatrix} 6 & 8 \\ 10 & 12 \end{pmatrix}
$$

#### 1.2) \(B - A\)
$$
B - A = \begin{pmatrix} 5 - 1 & 6 - 2 \\ 7 - 3 & 8 - 4 \end{pmatrix} = \begin{pmatrix} 4 & 4 \\ 4 & 4 \end{pmatrix}
$$

#### 1.3) \(A + C\)
$$
A + C = \begin{pmatrix} 1 + (-1) & 2 + 2 \\ 3 + 3 & 4 + 0 \end{pmatrix} = \begin{pmatrix} 0 & 4 \\ 6 & 4 \end{pmatrix}
$$

#### 1.4) \(D + E\) (not possible)
- **Matrix addition requires equal dimensions.** Since \(D\) is \(2 \times 3\) and \(E\) is \(3 \times 2\), matrix addition is **not defined**.

---

## **2. Scalar Multiplications:**
#### 2.1) \(\frac{1}{2} A\)
$$
\frac{1}{2} A = \frac{1}{2} \begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix} = \begin{pmatrix} 0.5 & 1 \\ 1.5 & 2 \end{pmatrix}
$$

#### 2.2) \(2 B\)
$$
2 B = 2 \begin{pmatrix} 5 & 6 \\ 7 & 8 \end{pmatrix} = \begin{pmatrix} 10 & 12 \\ 14 & 16 \end{pmatrix}
$$

#### 2.3) \(-3 C\)
$$
-3 C = -3 \begin{pmatrix} -1 & 2 \\ 3 & 0 \end{pmatrix} = \begin{pmatrix} 3 & -6 \\ -9 & 0 \end{pmatrix}
$$

#### 2.4) \(4 D\)
$$
4 D = 4 \begin{pmatrix} -1 & 2 & 3 \\ 4 & 0 & 6 \end{pmatrix} = \begin{pmatrix} -4 & 8 & 12 \\ 16 & 0 & 24 \end{pmatrix}
$$

---

## **3. Matrix Multiplications:**

#### **3.1) \( A \cdot B \):**

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

#### **3.2) \( B \cdot A \):**

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

#### **3.3) \( A \cdot D \):**

- Matrix multiplication requires the number of columns in \( A \) to equal the number of rows in \( D \).
- Since \( A \) is \( 2 \times 2 \) and \( D \) is \( 2 \times 3 \), **matrix multiplication is not defined**.

---

#### **3.4) \( D \cdot E \):**

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

## Final Results:


### Matrix Addition

1. **\(A + B\):**
$$
A + B =
\begin{pmatrix}
1 & 2 \\
3 & 4
\end{pmatrix}
+
\begin{pmatrix}
5 & 6 \\
7 & 8
\end{pmatrix}
=
\begin{pmatrix}
6 & 8 \\
10 & 12
\end{pmatrix}
$$

2. **\(B - A\):**
\[
B - A =
\begin{pmatrix}
5 & 6 \\
7 & 8
\end{pmatrix}
-
\begin{pmatrix}
1 & 2 \\
3 & 4
\end{pmatrix}
=
\begin{pmatrix}
4 & 4 \\
4 & 4
\end{pmatrix}
\]

3. **\(A + C\):**
\[
A + C =
\begin{pmatrix}
1 & 2 \\
3 & 4
\end{pmatrix}
+
\begin{pmatrix}
-1 & 2 \\
3 & 0
\end{pmatrix}
=
\begin{pmatrix}
0 & 4 \\
6 & 4
\end{pmatrix}
\]

4. **\(D + E\):**
- **Not Defined:** Matrix addition requires matrices of equal dimensions (\(D\) is \(2 \times 3\), while \(E\) is \(3 \times 2\)).

---

### Scalar Multiplication

1. **\(\frac{1}{2} A\):**
\[
\frac{1}{2} A =
\frac{1}{2}
\begin{pmatrix}
1 & 2 \\
3 & 4
\end{pmatrix}
=
\begin{pmatrix}
0.5 & 1 \\
1.5 & 2
\end{pmatrix}
\]

2. **\(2B\):**
\[
2B =
2
\begin{pmatrix}
5 & 6 \\
7 & 8
\end{pmatrix}
=
\begin{pmatrix}
10 & 12 \\
14 & 16
\end{pmatrix}
\]

3. **\(-3C\):**
\[
-3C =
-3
\begin{pmatrix}
-1 & 2 \\
3 & 0
\end{pmatrix}
=
\begin{pmatrix}
3 & -6 \\
-9 & 0
\end{pmatrix}
\]

4. **\(4D\):**
\[
4D =
4
\begin{pmatrix}
-1 & 2 & 3 \\
4 & 0 & 6
\end{pmatrix}
=
\begin{pmatrix}
-4 & 8 & 12 \\
16 & 0 & 24
\end{pmatrix}
\]

---

### Matrix Multiplication

1. **\(A \cdot B\):**
\[
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

2. **\(B \cdot A\):**
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

3. **\(A \cdot D\):**
- **Not Defined:** Matrix multiplication requires the number of columns in \(A\) (\(2\)) to match the number of rows in \(D\) (\(3\)).

4. **\(D \cdot E\):**
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
=
\begin{pmatrix}
(-1 \cdot 1 + 2 \cdot 4 + 3 \cdot 7) & (-1 \cdot 2 + 2 \cdot 5 + 3 \cdot 8) \\
(4 \cdot 1 + 0 \cdot 4 + 6 \cdot 7) & (4 \cdot 2 + 0 \cdot 5 + 6 \cdot 8)
\end{pmatrix}
=
\begin{pmatrix}
34 & 40 \\
46 & 56
\end{pmatrix}
\]

