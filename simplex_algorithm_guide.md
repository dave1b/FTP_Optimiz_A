### How to solve a LP with the Simplex Algorithm for inequalities

 #### Example Problem:
$$
\text{min} \ 3x_1 + x_2
$$
subject to:

$$
\begin{align}
x_1 + 2x_2 &\geq 2 \tag{1}\\
-x_1 + x_2 &\leq 1 \tag{2}\\
x_1 &\leq 3 \tag{3}\\
x_2 &\leq 2 \tag{4}\\
x_2 &\geq 0 \tag{5}
\end{align}
$$

---
Since the version of the Simplex Algorithm discussed in the course applies to maximization problems in inequality form,
the given minimization problem has to be converted into a maximization problem:
#### **Maximizing Problem in Inequality Form**
$$
\text{max} -3x_1 - x_2
$$
subject to:

$$
\begin{align}
-x_1 - 2x_2 &\leq -2 \tag{1}\\
-x_1 + x_2 &\leq 1 \tag{2}\\
x_1 &\leq 3 \tag{3}\\
x_2 &\leq 2 \tag{4}\\
-x_2 &\leq 0 \tag{5}
\end{align}
$$
--- 

$A = \begin{pmatrix} -1 & -2 \\ -1 & 1 \\ 1 & 0 \\ 0 & 1 \\ 0 & -1 \end{pmatrix}$, $b = \begin{pmatrix} -2 \\ 1 \\ 3 \\ 2 \\ 0 \end{pmatrix}$, $c = \begin{pmatrix} -3 & -1 \end{pmatrix}^T$

### Steps:
#### 1. Always bring to **maximization** form.
#### 2. Convert **equality** constraints to **inequalities** ( $\leq$).
#### 3. Start at a feasible vertex $v$.
#### 4. Basis $A_B$ and associated right-hand side $b_B$.
   A_B = $\begin{pmatrix} -1 & -2 \\ 0 & -1 \end{pmatrix}, \quad  b_B = \begin{pmatrix} -2 \\ 0 \end{pmatrix}$
#### 5. Calculate the
   inverse $A_B^{-1}$ = $\bar{A}$ = $\begin{pmatrix} -1 & -2 \\ 0 & -1 \end{pmatrix}^{-1}$= $\begin{pmatrix} -1 & 2 \\ 0 & -1 \end{pmatrix}$

$v$ = $A_B^{-1}b_B$ = $\begin{pmatrix} 2 \\ 0 \end{pmatrix}$, $v$ is the feasible vertex.

#### 6. Vector $u^T$ is calculated as

$u^T = c^T \bar{A} = \begin{pmatrix} -3 & -1 \end{pmatrix} \begin{pmatrix} -1 & 2 \\ 0 & -1 \end{pmatrix} = \begin{pmatrix} 3 & -5 \end{pmatrix}$

#### 7. If all elements of $u^T$ are $\geq 0$, then the current vertex is optimal solution.
#### 8. The second element of $u^T$ is negative. We define the direction $d$ as the second column
   of $\bar{A}_5$ = $\begin{pmatrix} 2 \\ -1 \end{pmatrix}$.
#### 9. Determine $\lambda$ such that

$ A(v + \lambda d) = Av + \lambda A d =
\begin{pmatrix} -1 & -2 \\ -1 & 1 \\ 1 & 0 \\ 0 & 1 \\ 0 & -1 \end{pmatrix}
\begin{pmatrix} 2 \\ 0 \end{pmatrix} + \lambda
\begin{pmatrix} -1 & -2 \\ -1 & 1 \\ 1 & 0 \\ 0 & 1 \\ 0 & -1 \end{pmatrix}
\begin{pmatrix} -2 \\ 1 \end{pmatrix} $

$ = \begin{pmatrix} -2 \\ -2 \\ 2 \\ 0 \\ 0 \end{pmatrix} + \lambda
\begin{pmatrix} 0 \\ 3 \\ 1 \\ -1 \\ 0 \end{pmatrix}
\leq
\begin{pmatrix} -2 \\ 1 \\ 3 \\ 2 \\ 0 \end{pmatrix} = b $

#### 10. $ \lambda^*$ = $\min \left\{ \frac{b_i - a^iv}{a^id} : i \in \left\{ 1,.,.,m \right\}, a^id > 0 \right\}  $

$\min \left\{ \frac{1-(-2)}{3}, \frac{2-0}{1}\right\} = 1$
The min is obtained at index $k$ = 2.

#### 10. Build new basis selection $B'$ by removing index $j$ from $B$ and adding index $k$
    $B' = B - j + k = \left\{ 1, 5 \right\} - 5 + 2 = \left\{ 1, 2 \right\}$

$v' = v + \lambda^*d = \begin{pmatrix} 2 \\ 0 \end{pmatrix} + 1 \begin{pmatrix} -2 \\ 1 \end{pmatrix} = \begin{pmatrix} 0 \\ 1 \end{pmatrix}$

set $B := B'$

#### 11. Repeat steps 5-10 until all elements of $u^T$ are $\geq 0$.