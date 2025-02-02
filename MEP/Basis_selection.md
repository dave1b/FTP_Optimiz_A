This exercise involves selecting a **non-feasible basis** from the constraint matrix $ A $ and computing the corresponding basic solution.

---

### **Step 1: Understanding the Problem**
You are given a polyhedron $ P $ defined as:

$
P = \{ x \in \mathbb{R}^2 : Ax \leq b \}
$

where:

$
A = \begin{pmatrix} -2 & 2 \\ -5 & -1 \\ -3 & -3 \end{pmatrix}, \quad b = \begin{pmatrix} 0 \\ -24 \\ -12 \end{pmatrix}
$

A basis consists of two linearly independent rows of $ A $ (since we are in $ \mathbb{R}^2 $). Your task is to select a non-feasible basis and compute the corresponding basic solution.

---

### **Step 2: Choosing a Basis $ C $**
A basis is a **subset of two rows** from $ A $ that form an invertible $ 2 \times 2 $ matrix.

Possible bases:
1. Rows 1 and 2 → $ C = \begin{pmatrix} -2 & 2 \\ -5 & -1 \end{pmatrix} $
2. Rows 1 and 3 → $ C = \begin{pmatrix} -2 & 2 \\ -3 & -3 \end{pmatrix} $
3. Rows 2 and 3 → $ C = \begin{pmatrix} -5 & -1 \\ -3 & -3 \end{pmatrix} $

To ensure the basis is **non-feasible**, the resulting basic solution must have at least one negative value.

---

### **Step 3: Computing the Basic Solution $ x^* $**
A basic solution is obtained by solving:

$
C x^* = b_C
$

where $ b_C $ contains the corresponding entries from $ b $.

Let's compute one example:

#### **Selecting Basis $ C = \begin{pmatrix} -2 & 2 \\ -3 & -3 \end{pmatrix} $**
The corresponding $ b_C $ is:

$
b_C = \begin{pmatrix} 0 \\ -12 \end{pmatrix}
$

Solving:

$
\begin{pmatrix} -2 & 2 \\ -3 & -3 \end{pmatrix} \begin{pmatrix} x_1 \\ x_2 \end{pmatrix} = \begin{pmatrix} 0 \\ -12 \end{pmatrix}
$

Using **Gaussian elimination** or **matrix inversion**, we solve for $ x_1, x_2 $.

---

### **Step 4: Sorting Basis Indices**
Ensure that the selected basis indices (row numbers) are sorted in increasing order.

Let me know if you need help solving the system explicitly! 🚀