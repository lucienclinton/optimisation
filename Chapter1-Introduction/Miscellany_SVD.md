# Derivation 2——SVD

## 2.a 铺垫知识

### 2.a.α 特征值eigenvalue 和 特征向量eigenvector（方阵才有）

设矩阵 $A \in \mathbb{R}^{n \times n}$，如果存在一个非零向量 $x \in \mathbb{R}^n$ 和一个标量 $\lambda \in \mathbb{R}$（或 $\mathbb{C}$），使得 $\displaystyle A x = \lambda x$，那么称 $\lambda$ 是矩阵 $A$ 的特征值（eigenvalue），$x$ 是对应的特征向量（eigenvector）.

这个等式表示：矩阵 $A$ 作用在向量 $x$ 上，只是将它“拉伸”或“缩放”（改变大小），而不改变其方向.

特征值的求解可以转化为：$\displaystyle \vert A-\lambda I\vert = 0$，其中 $I \in \mathbb{R}^{n \times n}$是单位矩阵.

### 2.a.β 几何重数algebraic multiplicity 和 代数重数geometric multiplicity（方阵，针对某一个特征值 $\lambda$ 才有）

设矩阵 $A \in \mathbb{R}^{n \times n}$ ，**对于其一个特征值 $\lambda$，**可以定义：

**几何重数**（geometric multiplicity）是指线性方程 $(A - \lambda I)x = 0$ 的解空间维数，也就是特征值 $\lambda$ 对应的特征向量所构成子空间的维数.换句话说，它等于矩阵 $A - \lambda I$ 的零空间的维度.

**代数重数**（algebraic multiplicity）是指 $\lambda$ 作为特征多项式 $\displaystyle \vert A-\lambda I\vert$ 的一个根的重数（ $(t−λ)$ 的次数）.

几何重数总是小于或等于代数重数.即$\displaystyle \text{geom. mult.}(\lambda) \leq \text{alg. mult.}(\lambda)$ 

**【例】**考虑矩阵$\displaystyle A = \begin{bmatrix} 2 & 1 & 0 & 0 & 0 \newline 0 & 2 & 1 & 0 & 0 \newline 0 & 0 & 2 & 0 & 0 \newline 0 & 0 & 0 & 3 & 1 \newline 0 & 0 & 0 & 0 & 3 \end{bmatrix}$

因为 $A$ 是上三角矩阵，所以特征值就是主对角线上的数：$\lambda_1 = 2, \quad \lambda_2 = 3$.

- $\lambda = 2$ 出现 3 次（代数重数 $\text{AM}(2) = 3$），$\lambda = 3$ 出现 2 次（代数重数 $\text{AM}(3) = 2$）

计算 $\ker(A - 2I)$ 和 $\ker(A - 3I)$ 的维数：

- $A - 2I = \begin{bmatrix}
   0 & 1 & 0 & 0 & 0 \newline
   0 & 0 & 1 & 0 & 0 \newline
   0 & 0 & 0 & 0 & 0 \newline
   0 & 0 & 0 & 1 & 0 \newline
   0 & 0 & 0 & 0 & 1
   \end{bmatrix}$
   其秩为4，所以 $\dim\ker(A - 2I) = n - \operatorname{rank}(A - \lambda I)=5-4=1$。
   即 $\text{GM}(2) = 1 < \text{AM}(2) = 3$。
- 同理 $\text{GM}(3) = 1 < \text{AM}(3) = 2$。

## 2.b 相似对角化Similar Diagonalization (SD) /特征值分解Eigen-Value Decomposition (EVD)

### 2.b.α 相似 (Similarity)

**定义**：设 $A, B \in K^{n \times n}$。如果存在可逆矩阵 $P \in K^{n \times n}$，使得$B = P^{-1} A P$ ，则称 $A$ 与 $B$ **相似** (similar)，记作 $A \sim B$.

**基本性质**：

1. 相似是一个等价关系：
   - **自反性**：$A \sim A$，取 $P = I$。
   - **对称性**：若 $A \sim B$，则 $B \sim A$，取 $P^{-1}$。
   - **传递性**：若 $A \sim B$ 且 $B \sim C$，则 $A \sim C$，取 $P Q$。
2. 相似矩阵保留许多不变量：
   - 相同的**特征多项式**（带 $\lambda$ 的多项式）；
   - 相同的**特征值**（包括 $\lambda$ 对应的代数重数和代数重数）；
   - 相同的**行列式**（是特征多项式的常数项）和**迹**。
3. 几何意义：
    相似变换对应于对向量空间基的更换。换句话说，$A$ 与 $B$ 表示的是同一个线性算子，只是基不同。

### 2.b.β 相似对角化/特征值分解

**条件**：设矩阵 $A \in \mathbb{C}^{n \times n}$。<u>若 $A$ 有 $n$ 个线性无关的特征向量</u>，则 $A$ 可**相似对角化**，即：

存在可逆矩阵 $U$ 和对角矩阵 $\Lambda$，使得 $A = U \Lambda U^{-1}$。



下面给出计算 $U$ 的步骤：

Step 1：解特征多项式 $\det(A-\lambda I)=0$，得到 $A$ 全部的特征向量 $u_1,u_2,\dots, u_n$ 和对应的特征值 $\lambda_1\geq\lambda_2\geq\dots\geq\lambda_n$ （可能有重复的部分）.

Step 2：将这些线性无关的特征向量作为列向量拼成矩阵 $U=[u_1,u_2,\dots,u_n]$，并将全部特征值构造成对角矩阵 $\Lambda=\text{diag}(\lambda_1,\lambda_2,\dots,\lambda_n)$，其中 $\lambda_i$ 对应于列向量 $u_i$。

Step 3：因此有 ：
$$
AU=A[u_1,u_2,\dots,u_n]=[Au_1,Au_2,\dots,Au_n]=[\lambda_1u_1,\lambda_2u_2,\dots,\lambda_nu_n]\newline=[u_1,u_2,\dots,u_n]·\begin{bmatrix} \lambda_1 & 0 & \cdots & 0 \newline 0 & \lambda_2 & \cdots & 0 \newline \vdots & \vdots  & \ddots & \vdots \newline 0 & 0 & \cdots & \lambda_n \end{bmatrix}=U·\Lambda
$$
两侧同时右乘 $U^{-1}$ ，得 $A = U \Lambda U^{-1}$， $U$ 即为所求。



$A$ 可对角化的**充要条件**是：

-  $A$ 有 $n$ 个线性无关的特征向量。
-  $\mathbb{C}^n$ 是 $A$ 的各个特征子空间的直和。
-  $A$ 的几何重数等于代数重数，即 $A$ 有完全的特征向量系。

$A$ 可对角化的**充分条件**是：

-  $A$ 有 $n$ 个互不相同的特征值（在实数域/复数域）。

**定理（可对角化的充分条件）**
 设矩阵 $A \in \mathbb{C}^{n\times n}$（或 $\mathbb{R}^{n\times n}$）。若 $A$ 有 $n$ 个互不相同的特征值 $\lambda_1,\lambda_2,\dots,\lambda_n$，则 $A$ 可相似对角化。

**证明：** 以下证明 $A \in \mathbb{C}^{n\times n}$ 的情况

1. 设 $u_i$ 是 $A$ 的特征向量，对应于特征值 $\lambda_i$，即$Au_i = \lambda_i u_i,\quad i=1,2,\dots,n$. 若 $\lambda_i \neq \lambda_j$，则 $u_i,u_j$ 必定线性无关

2. 假设 $\displaystyle \sum_{i=1}^n c_i u_i = 0$ ，对任意 $j$，左乘 $(A-\lambda_j I)$：

   $\displaystyle (A-\lambda_j I)\Bigl(\sum_{i=1}^n c_i u_i\Bigr) = \sum_{i=1}^n c_i (A-\lambda_j I)u_i  = \sum_{i=1}^n c_i (\lambda_i-\lambda_j)u_i = 0.$

   其中 $i=j$ 的项为0，实际上是 $\displaystyle \sum_{i,i\neq j}^n c_i (\lambda_i-\lambda_j) u_i = 0$.

    $\because\lambda_i \neq \lambda_j$，$\therefore\displaystyle \sum_{i,i\neq j}^n c_i  u_i = 0$ ，而 $\displaystyle \sum_{i=1}^n c_i u_i = 0$ ， $\therefore c_ju_j=0$ ，$\therefore c_j=0,\quad \forall j$。

3. $\because\displaystyle \sum_{i=1}^n c_i u_i = 0\Longrightarrow c_j=0,\quad \forall j $ ，$\therefore{u_1,u_2,\dots,u_n}$ 线性无关。$\therefore A$ 有 $n$ 个线性无关的特征向量，即 $A$ 可对角化。

**【例】是否能相似对角化要考虑数域**考虑矩阵 $A = \begin{bmatrix} 0 & -1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 2 \end{bmatrix}$.

1. 计算特征多项式：$\det(A-\lambda I) = \begin{vmatrix} -\lambda & -1 & 0 \\ 1 & -\lambda & 0 \\ 0 & 0 & 2-\lambda \end{vmatrix} = (\lambda^2+1)(2-\lambda)$.

2. 特征值为 $\lambda_1=i, \lambda_2=-i, \lambda_3=2$。

   - 对 $\lambda_1=i$，解 $(A-iI)x=0$，得到特征向量 $u_1=\begin{bmatrix} i \newline 1 \newline 0 \end{bmatrix}$。

   - 对 $\lambda_2=-i$，解 $(A+iI)x=0$，得到特征向量 $u_2=\begin{bmatrix} -i \newline 1 \newline 0 \end{bmatrix}$。

   - 对 $\lambda_3=2$，解 $(A-2I)x=0$，得到特征向量 $u_3=\begin{bmatrix} 0 \newline 0 \newline 1 \end{bmatrix}$。

3. 构造对角化：$U = \begin{bmatrix} i & -i & 0 \\ 1 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix}, \quad \Lambda = \begin{bmatrix} i & 0 & 0 \\ 0 & -i & 0 \\ 0 & 0 & 2 \end{bmatrix}$. 于是有$A = U \Lambda U^{-1}$.

​	这个矩阵在 $\mathbb{R}$ 上不可对角化，但是在 $\mathbb{C}$ 上可以对角化。

## 2.c 实对称矩阵、正交和对角化的关系

### 2.c.α 实对称矩阵的一些性质



### 2.c.β 正交orthogonal

**正交定义**：设 $u, v \in \mathbb{R}^n$，如果它们的内积为零：$u^\top v = 0$，则称 $u$ 与 $v$ **正交**（orthogonal）。

- 如果 $u^\top u = 1$，则称 $u$ 是**单位向量**（unit vector）。
- 一组向量 $\lbrace u_1, u_2, \dots, u_n \rbrace$ 若两两正交且每个向量都是单位向量，则称它们组成**正交标准基**（orthonormal basis）。

**正交矩阵**：

- 若 $Q \in \mathbb{R}^{n\times n}$ 且列向量两两正交且为单位向量：$Q^\top Q = Q Q^\top = I$，，则称 $Q$ 是**正交矩阵**（orthogonal matrix）

- 正交矩阵的性质：

  1. 可逆且 $Q^{-1} = Q^\top$。

  2. 保长度：$\Vert Qx \Vert = \Vert x \Vert$。

  3. 保内积/保角度：向量之间的夹角不变。

      $\displaystyle \cos\theta' = \frac{(Qx)^\top (Qy)}{\Vert Qx \Vert \, \Vert Qy \Vert} = \frac{x^\top y}{\Vert x \Vert \, \Vert y \Vert} = \cos\theta$

