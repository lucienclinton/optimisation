# Derivation 2——SVD

## 2.a 铺垫知识

#### 特征值eigenvalue 和 特征向量eigenvector（方阵才有）

设矩阵 $A \in \mathbb{R}^{n \times n}$，如果存在一个非零向量 $x \in \mathbb{R}^n$ 和一个标量 $\lambda \in \mathbb{R}$（或 $\mathbb{C}$），使得 $\displaystyle A x = \lambda x$，那么称 $\lambda$ 是矩阵 $A$ 的特征值（eigenvalue），$x$ 是对应的特征向量（eigenvector）.

这个等式表示：矩阵 $A$ 作用在向量 $x$ 上，只是将它“拉伸”或“缩放”（改变大小），而不改变其方向.

特征值的求解可以转化为：$\displaystyle \vert A-\lambda I\vert = 0$，其中 $I \in \mathbb{R}^{n \times n}$是单位矩阵.

### 1.a.ii 几何重数algebraic multiplicity 和 代数重数geometric multiplicity（方阵，针对某一个特征值 $\lambda$ 才有）

设矩阵 $A \in \mathbb{R}^{n \times n}$ ，对于其一个特征值 $\lambda$，可以定义：

**几何重数**（geometric multiplicity）是指线性方程 $(A - \lambda I)x = 0$ 的解空间维数，也就是特征值 $\lambda$ 对应的特征向量所构成子空间的维数.换句话说，它等于矩阵 $A - \lambda I$ 的零空间的维度.

**代数重数**（algebraic multiplicity）是指 $\lambda$ 作为特征多项式 $\displaystyle \vert A-\lambda I\vert$ 的一个根的重数（ $(t−λ)$ 的次数）.

几何重数总是小于或等于代数重数.即$\displaystyle \text{geom. mult.}(\lambda) \leq \text{alg. mult.}(\lambda)$ 

## 1.b 相似对角化 Similar Diagonalization

相似对角化是指对一个方阵 $A \in \mathbb{C}^{n \times n}$，若存在一个可逆矩阵 $P$ 使得 $P^{-1} A P = D$，其中 $D$ 是**对角矩阵**，则称 $A$ **可相似对角化**（is diagonalizable）.

$D$ 的对角元是 $A$ 的特征值，$P$ 的列向量是 $A$ 的特征向量.

若 $A$ 是**实对称矩阵**或**复正规矩阵**，还可以通过**酉相似对角化**（unitary similarity）来实现

SVD 则对所有实或复矩阵 $A \in \mathbb{C}^{m \times n}$ 都适用.它将 $A$ 分解为 $A = U \Sigma V^*$，其中 $U \in \mathbb{C}^{m \times m}$ 和 $V \in \mathbb{C}^{n \times n}$ 是酉矩阵，$\Sigma \in \mathbb{R}^{m \times n}$ 是对角矩阵，对角元为非负的奇异值，表示矩阵在正交基下的伸缩强度.

两者的主要区别在于，相似对角化是以 $P^{-1} A P$ 的形式对矩阵在自身空间中简化，它反映的是矩阵的谱结构和特征向量性质，适用于研究矩阵幂、稳定性等问题；而 SVD 是以 $U^* A V$ 的形式将矩阵视为从一个空间映射到另一个空间的变换，关注的是矩阵的范数结构、投影和压缩性质.SVD 总能应用于任意矩阵，而相似对角化则不然.

举个例子，设 $A = \begin{bmatrix} 2 & 1 \ 0 & 2 \end{bmatrix}$，这个矩阵只有一个特征值 2，对应一个线性无关的特征向量，因此它不可对角化，但仍然可以进行 SVD 分解，其奇异值为非负实数，分解形式为 $A = U \Sigma V^T$，其中 $U$ 和 $V$ 是正交矩阵.

总结来说，SVD 是一种更通用的分解方法，它总是存在并提供一组正交基，而相似对角化仅适用于特定类型的方阵，两者的目标和应用领域也不同.

SVD 