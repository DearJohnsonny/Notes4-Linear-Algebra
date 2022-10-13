<a href="https://dearjohnsonny.github.io/Notes-from-DearJohn/">Notes from DearJohn</a>

<a href="https://dearjohnsonny.github.io/Notes-from-DearJohn-2/">Notes from DearJohn-2</a>

<a href="https://dearjohnsonny.github.io/Notes-from-DearJohn-3/">Notes from DearJohn-3</a>

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/195361749-01b1343d-0dc6-497b-bbc1-1b0ae149ca5e.png" width="900">
</div>

# Introduction to Vectors and Matrics

## Lengths and Dot Products
The length $\|v\|$ of a vector v is the square root of $\boldsymbol{v} \cdot \boldsymbol{v}$ 

$$
\text { length }=\|\boldsymbol{v}\|=\sqrt{\boldsymbol{v} \cdot \boldsymbol{v}}=\left(v_1^2+v_2^2+\cdots+v_n^2\right)^{1 / 2}
$$

$\boldsymbol{v} \cdot \boldsymbol{v}$ 相当于 $V^T V$

## Inverse Matrices

1 If the square matrix $A$ has an inverse, then both $A^{-1} A=I$ and $A A^{-1}=I$.

2 The algorithm to test invertibility is elimination: $A$ must have $n$ (nonzero) pivots.

3 The algebra test for invertibility is the determinant of $A$ : $\operatorname{det} A$ must not be zero.

4 The equation that tests for invertibility is $A \boldsymbol{x}=0: \boldsymbol{x}=\mathbf{0}$ must be the only solution.

5 If $A$ and $B$ (same size) are invertible then so is $A B:(A B)^{-1}=B^{-1} A^{-1}$.

6 $A A^{-1}=I$ is $n$ equations for $n$ columns of $A^{-1}$. Gauss-Jordan eliminates $[A I]$ to $\left[I A^{-1}\right]$.

7 The last page of the book gives 14 equivalent conditions for a square $A$ to be invertible.

## A=LU分解法

对2×2矩阵，要得到U这个上三角矩阵，需要我们将2行1列的元消去，则需要E21这个矩阵，然后再求逆矩阵即可

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/195482901-fb755dad-6ca3-433e-a835-85b4726ac0de.png" width="500">
</div>

对于更广泛的情况（如三维方阵），也是一样的思路：

$$
\left(E_{32} E_{31} E_{21}\right) A=U \text { becomes } A=\left(E_{21}^{-1} E_{31}^{-1} E_{32}^{-1}\right) U \text { which is } A=L U \text {. }
$$

**Better balance from LDU**：A = L U is "unsymmetric" because U has the pivots on its diagonal where L has l's. This is easy to change. Divide U by a diagonal matrix D that contains the pivots. That leaves a new triangular matrix with l's on the diagonal(对角线): 

$$
\text { The triangular factorization can be written } A=L U \text { or } A=L D U \text {. }
$$

如下图的例子：

$$
\left[\begin{array}{ll}
1 & 0 \\
3 & 1
\end{array}\right]\left[\begin{array}{ll}
2 & 8 \\
0 & 5
\end{array}\right] \quad \text { splits further into } \quad\left[\begin{array}{ll}
1 & 0 \\
3 & 1
\end{array}\right]\left[\begin{array}{ll}
2 & \\
& 5
\end{array}\right]\left[\begin{array}{ll}
1 & 4 \\
0 & 1
\end{array}\right]
$$

## Transposes and Permutations转置与排列
1 The transposes of $A \boldsymbol{x}$ and $A B$ and $A^{-1}$ are $\boldsymbol{x}^{\mathrm{T}} A^{\mathrm{T}}$ and $B^{\mathrm{T}} A^{\mathrm{T}}$ and $\left(A^{\mathrm{T}}\right)^{-1}$.

2 The dot product (inner product) is $\boldsymbol{x} \cdot \boldsymbol{y}=\boldsymbol{x}^{\mathrm{T}} \boldsymbol{y}$. This is $(1 \times n)(n \times 1)=(1 \times 1)$. The outer product is $\boldsymbol{x} \boldsymbol{y}^{\mathbf{T}}=$ column times row $=(n \times 1)(1 \times n)=n \times n$ matrix .

3 The idea behind $A^{\mathrm{T}}$ is that $A \boldsymbol{x} \cdot \boldsymbol{y}$ equals $\boldsymbol{x} \cdot A^{\mathrm{T}} \boldsymbol{y}$ because $(A \boldsymbol{x})^{\mathrm{T}} \boldsymbol{y}=\boldsymbol{x}^{\mathrm{T}} A^{\mathrm{T}} \boldsymbol{y}=\boldsymbol{x}^{\mathrm{T}}\left(A^{\mathrm{T}} \boldsymbol{y}\right)$.

4 A symmetric matrix has $S^{\mathrm{T}}=\boldsymbol{S}$ (and the product $A^{\mathrm{T}} A$ is always symmetric).

5 An orthogonal matrix has $\boldsymbol{Q}^{\mathrm{T}}=\boldsymbol{Q}^{-1}$. The columns of $Q$ are orthogonal unit vectors.

6 A permutation matrix $\boldsymbol{P}$ has the same rows as $I$ (in any order). There are $\boldsymbol{n}$ ! different orders.

7 Then $P x$ puts the components $x_1, x_2, \ldots, x_n$ in that new order. And $P^{\mathrm{T}}$ equals $P^{-1}$.

$$
\text { The transpose of } A^{\mathrm{T}} A \text { is } A^{\mathrm{T}}\left(A^{\mathrm{T}}\right)^{\mathrm{T}} \text { which is } A^{\mathrm{T}} A \text { again. }
$$

The matrix $A A^{\mathrm{T}}$ is also symmetric，for instance: 

$$
A A^{\mathrm{T}}=\left[\begin{array}{rr}
2 & -1 \\
-1 & 2
\end{array}\right] \text { and } A^{\mathrm{T}} A=\left[\begin{array}{rrr}
1 & -1 & 0 \\
-1 & 2 & -1 \\
0 & -1 & 1
\end{array}\right]
$$

If $S=S^{\mathrm{T}}$ is factored into $L D U$ with no row exchanges, then $U$ is exactly $L^{\mathrm{T}}$.

The symmetric factorization of a symmetric matrix is $S=L D L^{\mathrm{T}}$.

# Spaces of Vectors 

M The vector space of all real 2 by 2 matrices.
F The vector space of all real functions $f(x)$.
$\mathrm{Z}$ The vector space that consists only of a zero vector.

## 关于列空间column space
**The column space** consists of all linear combinations of the columns. The combinations are all possible vectors $A x$. They fill the column space $C(A)$.

The system $A x=b$ is solvable if and only if $b$ is in the column space of $A$.

列空间是一种用向量空间中的向量来张成子空间的方法，但可以将其推广：
**Important** Instead of columns in $\mathbf{R}^m$, we could start with any set $\mathbf{S}$ of vectors in a vector space $\mathbf{V}$. To get a subspace $\mathbf{S S}$ of $\mathbf{V}$, we take all combinations of the vectors in that set:

$$
\begin{gathered}
\mathbf{S}=\text { set of vectors in } \mathbf{V} \text { (probably not a subspace) } \\
\mathbf{S S}=\text { all combinations of vectors in } \mathbf{S} \text { (definitely a subspace) } \\
\mathbf{S S}=\text { all } c_1 \boldsymbol{v}_1+\cdots+c_N \boldsymbol{v}_N=\text { the subspace of } \mathbf{V} \text { "spanned" by } \mathbf{S}
\end{gathered}
$$

## 关于零空间The Nullspace of A: Solving Ax = 0 and Rx = 0
1 The nullspace $\boldsymbol{N}(A)$ in $\mathbf{R}^n$ contains all solutions $\boldsymbol{x}$ to $A \boldsymbol{x}=\mathbf{0}$. This includes $\boldsymbol{x}=\mathbf{0}$.

2 Elimination (from $A$ to $U$ to $R$ ) does not change the nullspace: $\boldsymbol{N}(A)=\boldsymbol{N}(U)=\boldsymbol{N}(R)$.

3 The reduced row echelon form $R=\operatorname{rref}(A)$ has all pivots $=1$, with zeros above and below.

4 If column $j$ of $R$ is free (no pivot), there is a "special solution" to $A \boldsymbol{x}=\mathbf{0}$ with $x_j=1$.

5 Number of pivots $=$ number of nonzero rows in $R=\operatorname{rank} \boldsymbol{r}$. There are $n-r$ free columns.

6 Every matrix with $m < n$ has nonzero solutions to $A \boldsymbol{x}=\mathbf{0}$ in its nullspace.
