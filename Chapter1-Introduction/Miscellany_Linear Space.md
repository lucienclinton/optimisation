# Derivation 1——线性空间

---

## 1.a 线性空间基础

### 1.a.α 集合、映射和运算：

**集合——**交并补

**映射——**设 $A$ 与 $B$ 是两个集合.从集合 $A$ 到集合 $B$ 的一个映射，就是指一个规则 $\sigma$ ，使得 $A$ 中每一个元素 $a$ 都有 $B$ 中一个确定的元素 $b$ 与之对应，记为 $\sigma(a) = b$.

元素 $b$ 称为 **$a$ 在映射 $\sigma$ 下的像**，而 $a$ 称为 **$b$ 在映射 $\sigma$ 下的一个原像**.

从集合 $A$ 到 $A$ 自身的映射，有时也称为 $A$ 到自身的变换.

**两个映射相等**：如果集合 $A$ 到集合 $B$ 的两个映射 $\sigma$ 及 $\tau$ 满足：对于 $M$ 中的每个元素 $a$ 都有 $\sigma(a) = \tau(a)$，则称 $\sigma = \tau$ ；

**单射injective：** $\forall a_1, a_2 \in A:\ \sigma(a_1) = \sigma(a_2)\ \Rightarrow\ a_1= a_2$，一个像只有一个原像
（逆否—— $\forall a_1, a_2 \in A:\ a_1\ne a_2\ \Rightarrow\ \sigma(a_1) \ne \sigma(a_2)$不同的元素在映射下有不同的像）.

**满射surjective：**  $\forall b \in B,\ \exists a \in A,\ \text{s.t.}\ \sigma(a) = b$，（$B$ 中每个元素 $b$ 都是某个 $a \in A$ 的像， 即$\sigma(A) = B$），则称 $\sigma$ 是一个满射.若 $\sigma(A) \subsetneq B$，即存在 $b \in B$ 不是任何 $a \in A$ 的像，则 $\sigma$ 不是满射.

**双射bijective：**  $\sigma$ 即单又满，一一对应。此时映射可逆，**存在唯一的逆映射** $\sigma^{-1}: B \to A$，满足 $\sigma^{-1}(\sigma(a)) = a$ 对所有 $a \in A$ 成立.

**笛卡尔积** $A \times B$：定义为 $\displaystyle A \times B = \lbrace (a, b) \mid a \in A,\ b \in B \rbrace$

**代数运算**：可以看作是在集合 $A$ 上定义的、封闭于该集合的映射.一个 **$n$ 元代数运算**（也称 $n$ 元运算或 $n$-ary operation）是指映射：$\displaystyle f : A^n \to A$ .其中 $A^n = A \times A \times \cdots \times A$（$n$ 个 $A$ 的笛卡尔积）

- 一元运算：$f : A \to A$，如取负号或取绝对值；
- 二元运算：$f : A \times A \to A$，如加法、乘法、集合交等.

### 1.a.β 线性空间定义：

设有：<u>非空集合</u> $V$ ，<u>域</u> $F$，如果在 $V$ 上定义了两个封闭运算——加法和数乘：

- **运算封闭：**
  - **对加法 $\displaystyle V \times V \rightarrow V\ :\ (\boldsymbol{\alpha}, \boldsymbol{\beta}) \mapsto \boldsymbol{\alpha} + \boldsymbol{\beta}$ 封闭：** 任取 $\boldsymbol{\alpha}, \boldsymbol{\beta} \in V$，有 $\boldsymbol{\alpha} + \boldsymbol{\beta} \in V$；
  - **对数乘 $\displaystyle F \times V \rightarrow V\ :\ (k, \boldsymbol{\alpha}) \mapsto k \boldsymbol{\alpha}$ 封闭：** 任取 $k \in F$ 且 $\boldsymbol{\alpha} \in V$，有 $k \boldsymbol{\alpha} \in V$；

并且两个封闭运算满足以下 **8 条公理**：

- **加法相关：**
  - ① 交换律：$\boldsymbol{\alpha} + \boldsymbol{\beta} = \boldsymbol{\beta} + \boldsymbol{\alpha}$
  - ② 结合律：$(\boldsymbol{\alpha} + \boldsymbol{\beta}) + \boldsymbol{\gamma} = \boldsymbol{\alpha} + (\boldsymbol{\beta} + \boldsymbol{\gamma})$
  - ③ 零元：存在 $\boldsymbol{0} \in V$，使得 $\boldsymbol{\alpha} + \boldsymbol{0} = \boldsymbol{\alpha}$ （域必然有“0”）
  - ④ 逆元：每个 $\boldsymbol{\alpha} \in V$，存在 $-\boldsymbol{\alpha} \in V$ 使得 $\boldsymbol{\alpha} + (-\boldsymbol{\alpha}) = \boldsymbol{0}$
- **数乘相关：**
  - ⑤ 单位元：$1 \boldsymbol{\alpha} = \boldsymbol{\alpha}$ （域必然有“1”）
  - ⑥ 结合律：$k (l \boldsymbol{\alpha}) = (kl) \boldsymbol{\alpha}$
  - ⑦ 分配律1（标量对向量）：$k (\boldsymbol{\alpha} + \boldsymbol{\beta}) = k \boldsymbol{\alpha} + k \boldsymbol{\beta}$
  - ⑧ 分配律2（向量对标量）：$(k + l) \boldsymbol{\alpha} = k \boldsymbol{\alpha} + l \boldsymbol{\alpha}$

满足以上8条条件，我们称 $V$ 为 $F$ 上的线性空间.例如，$\mathbb{R}^n$ 是 $\mathbb{R}$ 上的线性空间，$\mathbb{C}^n$ 是 $\mathbb{C}$ 上的线性空间.

### 1.a.γ 线性空间的典型例子：

1. **$\mathbb{R}^n$：实数域 $\mathbb{R}$ 上的 $n$ 维几何向量空间**
    以原点为起点的所有 $n$ 维向量构成的集合 ${\mathbb{R}}^n$ ，在向量加法和数量乘法下，构成实数域 $\mathbb{R}$ 上的一个线性空间；

2. **$F^n$：域 $F$ 上的 $n$ 维向量空间/线性空间**
    域 $F$ 上所有 $n$ 元有序组组成的集合 $F^n$，定义加法为对应分量相加，数量乘法为 $K$ 中元素与各分量分别相乘.这是域 $F$ 上的 $n$ 维向量空间；

3. **矩阵空间 $\mathbb{M}_{s \times n}(K)$**
    数域 $K$ 上所有 $s \times n$ 矩阵构成的集合，在矩阵加法和数量乘法（广播）下，是数域 $K$ 上的线性空间；

4. **多项式空间 $K[x]$**
    数域 $K$ 上（以数域 $K$ 中元素作为系数的）所有一元多项式构成的集合，在多项式加法和数量乘法下，构成数域 $K$ 上的一个线性空间；

5. **次数小于 $n$ 的多项式空间 $K[x]_n$**
    数域 $K$ 上所有次数小于 $n$ 的一元多项式在加法和数量乘法下仍封闭，构成一个 $K$ 上的线性空间，记作

   $K[x]_n = \{f(x) \in K[x] \mid \deg(f) < n\}$；

6. **复数空间 $\mathbb{C}$ 作为实数域 $\mathbb{R}$ 上的线性空间**
    复数集 $\mathbb{C}$ 可以看作是实数域 $\mathbb{R}$ 上的一个线性空间。其加法为复数加法，数量乘法为实数与复数相乘；

7. **域 $F$ 本身**
    域 $F$ 可以看成是它自身上的线性空间。其加法与数量乘法分别是 $F$ 中的加法与乘法；

8. **函数空间 $F^X$**
    给定任意非空集合 $X$ 和数域 $F$，所有从 $X$ 到 $F$ 的函数组成的集合 $F^X$，在函数加法与数量乘法下构成一个线性空间：

   - 加法：$(f + g)(x) = f(x) + g(x)$
   - 数量乘法：$(kf)(x) = k \cdot f(x)$
   - 零元：零函数 $0(x) = 0$ ，对所有 $x \in X$

### 1.a.δ 线性空间的性质：

设 $V$ 是域 $F$ 上的线性空间，下面列出由线性空间八条公理推导出的基本性质，并给出推导过程：

1. **零元唯一性：** 若 $\boldsymbol{0}_1$ 与 $\boldsymbol{0}_2$ 均满足 $\forall \boldsymbol{\alpha} \in V$ 有 $\boldsymbol{\alpha} + \boldsymbol{0}_i = \boldsymbol{\alpha},\ \text{(i=1,2)}$，则 $\boldsymbol{0}_1 = \boldsymbol{0}_2$.

    > $\boldsymbol{0}_1 \xlongequal{\text{$\boldsymbol{0}_2$ 是零元}} \boldsymbol{0}_1 + \boldsymbol{0}_2 \xlongequal{\text{$\boldsymbol{0}_1$ 是零元}} \boldsymbol{0}_2$，故零元唯一.

2. **逆元唯一性：** $\forall \boldsymbol{\alpha} \in V$，$\exists$ 唯一的向量 $-\boldsymbol{\alpha}$ 使得 $\boldsymbol{\alpha} + (-\boldsymbol{\alpha}) = \boldsymbol{0}$.

   > 设 $\boldsymbol{\beta}, \boldsymbol{\gamma}$ 都是 $\boldsymbol{\alpha}$ 的加法逆元，即 $\boldsymbol{\alpha} + \boldsymbol{\beta} = \boldsymbol{0}$ 且 $\boldsymbol{\alpha} + \boldsymbol{\gamma} = \boldsymbol{0}$，则有$\boldsymbol{\beta} \xlongequal{\text{③零元定义}} \boldsymbol{\beta} + \boldsymbol{0} \xlongequal{\text{④逆元定义}} \boldsymbol{\beta} + (\boldsymbol{\alpha} + \boldsymbol{\gamma}) \xlongequal{\text{②结合律}} (\boldsymbol{\beta} + \boldsymbol{\alpha}) + \boldsymbol{\gamma} \xlongequal{\text{④逆元定义}} \boldsymbol{0} + \boldsymbol{\gamma} \xlongequal{\text{③零元定义}} \boldsymbol{\gamma}$，故逆元唯一.

3. **逆元的数乘等价定义：**设 $\boldsymbol{\alpha} \in V$，有 $-1 \cdot \boldsymbol{\alpha} = -\boldsymbol{\alpha}$（标量 $-1$ 乘以向量 $\boldsymbol{\alpha}$ 等于其逆元）.

   > $\displaystyle \boldsymbol{\alpha} + (-1 \cdot \boldsymbol{\alpha}) = (1 + (-1)) \cdot \boldsymbol{\alpha} = 0 \cdot \boldsymbol{\alpha} = \boldsymbol{0} \quad \xrightarrow{\text{2逆元唯一性}} \quad -1 \cdot \boldsymbol{\alpha} = -\boldsymbol{\alpha}$.

4. **向量加法的消去律：** 若 $\boldsymbol{\alpha} + \boldsymbol{\beta} = \boldsymbol{\gamma} + \boldsymbol{\beta}$，则 $\boldsymbol{\alpha} = \boldsymbol{\gamma}$.

   > 两边加上 $-\boldsymbol{\beta}$，有 $\boldsymbol{\alpha} + (\boldsymbol{\beta} + (-\boldsymbol{\beta})) = \boldsymbol{\gamma} + (\boldsymbol{\beta} + (-\boldsymbol{\beta}))$，即 $\boldsymbol{\alpha} + \boldsymbol{0} = \boldsymbol{\gamma} + \boldsymbol{0}$，所以 $\boldsymbol{\alpha} = \boldsymbol{\gamma}$.

5. **零标量乘任意向量等于零向量：** 对任意 $\boldsymbol{\alpha} \in V$，有 $0 \cdot \boldsymbol{\alpha} = \boldsymbol{0}$.

    > $\displaystyle 0 \cdot \boldsymbol{\alpha} = (0 + 0) \cdot \boldsymbol{\alpha} = 0 \cdot \boldsymbol{\alpha} + 0 \cdot \boldsymbol{\alpha} \quad \xrightarrow{\text{4消去律}} \quad 0 \cdot \boldsymbol{\alpha} = \boldsymbol{0}$.

6. **任意标量乘零向量等于零向量：** 对任意 $k \in F$，有 $k \cdot \boldsymbol{0} = \boldsymbol{0}$.

    > $\displaystyle k \cdot \boldsymbol{0} \xlongequal{\text{③零元定义}} k \cdot (\boldsymbol{0} + \boldsymbol{0}) = k \cdot \boldsymbol{0} + k \cdot \boldsymbol{0} \quad \xrightarrow{4消去律} \quad \boldsymbol{0} = k \cdot \boldsymbol{0}$.

7. **$k \cdot \boldsymbol{\alpha} = \boldsymbol{0}$ 的充要条件：** 若 $k \in F$，$\boldsymbol{\alpha} \in V$，则 $k \cdot \boldsymbol{\alpha} = \boldsymbol{0}$ 当且仅当 $k = 0$ 或 $\boldsymbol{\alpha} = \boldsymbol{0}$.

    > $\Rightarrow$：若 $k = 0$，显然成立；若 $k \neq 0$，则两边乘以 $k^{-1}$ 得 $\boldsymbol{0} = k^{-1} \boldsymbol{0} = k^{-1} (k \cdot \boldsymbol{\alpha}) = 1 \cdot \boldsymbol{\alpha} = \boldsymbol{\alpha}$，故 $\boldsymbol{\alpha} = \boldsymbol{0}$.<br>$\Leftarrow$：若 $k=0$ 或 $\boldsymbol{\alpha} = \boldsymbol{0}$，显然有 $k \cdot \boldsymbol{\alpha} = \boldsymbol{0}$.

8. 从**域**的定义出发：

    - $0$ 是加法单位元，一定存在；
    - $1$ 是乘法单位元，一定存在且 $1 \ne 0$ .

------

## 1.b 维数、基与坐标

### 1.b.α 线性组合与线性表出、线性相关与线性无关

**线性组合**：设 $V$ 是域 $F$ 上的线性空间，$\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \ldots, \boldsymbol{\alpha}_n \in V$，$k_1, k_2, \ldots, k_n \in F$，则向量 $\displaystyle \boldsymbol{\beta} = k_1 \boldsymbol{\alpha}_1 + k_2 \boldsymbol{\alpha}_2 + \cdots + k_n \boldsymbol{\alpha}_n$ 称为 $\boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_n$ 的一个**线性组合**，$k_i$ 称为相应的系数.

**线性表出**：若存在一组系数 $k_1, \ldots, k_n$ 使得 $\boldsymbol{\beta} = k_1 \boldsymbol{\alpha}_1 + \cdots + k_n \boldsymbol{\alpha}_n$ 成立，则称 $\boldsymbol{\beta}$ **可由** $\boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_n$ **线性表出**.

**等价**：可以相互线性表出.具有<u>自反性</u>、<u>对称性</u>和<u>传递性</u>.

**线性相关**：『设 $\boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_n \in V$，若<u>存在不全为零</u>的 $k_1, \ldots, k_n \in F$，使得 $\displaystyle k_1 \boldsymbol{\alpha}_1 + \cdots + k_n \boldsymbol{\alpha}_n = \boldsymbol{0}$』，则称这组向量**线性相关**.

**线性无关**：『设 $\boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_n \in V$，若不存在不全为零的 $k_1, \ldots, k_n \in F$，使得 $\displaystyle k_1 \boldsymbol{\alpha}_1 + \cdots + k_n \boldsymbol{\alpha}_n = \boldsymbol{0}$ 』$\iff$『 仅有 $k_1 = \cdots = k_n = 0$ 能使线性组合等于 $\boldsymbol{0}$ 』，称这组向量**线性无关**.



系数矩阵为 $\displaystyle A = [\boldsymbol\alpha_1 \ \boldsymbol\alpha_2 \ \cdots \ \boldsymbol\alpha_r]=\begin{bmatrix} \alpha_{11} & \alpha_{12} & \cdots & \alpha_{1n} \newline \alpha_{21} & \alpha_{22} & \cdots & \alpha_{2n} \newline \vdots & \vdots & \ddots & \vdots \newline\alpha_{m1} & \alpha_{m2} & \cdots & \alpha_{mn} \end{bmatrix}$，未知量列向量为 $\displaystyle \boldsymbol{x} = \begin{pmatrix} x_1 \newline x_2 \newline\vdots \newline x_n \end{pmatrix}$，系数列向量为 $\displaystyle \boldsymbol{b} = \begin{pmatrix} b_1 \newline b_2 \newline \vdots \newline b_m \end{pmatrix}$.<br>

①向量组 $\boldsymbol\alpha_1, \boldsymbol\alpha_2, \dots, \boldsymbol\alpha_n \in \mathbb{F}^m$ 是否线性相关，等价于考察方程  $\displaystyle x_1 \boldsymbol\alpha_1 + x_2 \boldsymbol\alpha_2 + \cdots + x_n \boldsymbol\alpha_n = \boldsymbol{0}(\boldsymbol{Ax}=\boldsymbol{0})$  是否有非零解（齐次线性方程组必有解，至少有一个零解）：  
$$
\displaystyle
\begin{cases}
\alpha_{11}x_1 + \alpha_{12}x_2 + \cdots + \alpha_{1n}x_n = 0 \newline
\alpha_{21}x_1 + \alpha_{22}x_2 + \cdots + \alpha_{2n}x_n = 0 \newline
\quad\vdots \newline
\alpha_{m1}x_1 + \alpha_{m2}x_2 + \cdots + \alpha_{mn}x_n = 0
\end{cases}
$$
$\boldsymbol\alpha_1, \boldsymbol\alpha_2, \dots, \boldsymbol\alpha_n$ 线性无关 $\iff$ 齐次线性方程组 $\boldsymbol{Ax}=\boldsymbol{0}$ 只有零解，即 $\boldsymbol{x}=\boldsymbol{0}$

$\boldsymbol\alpha_1, \boldsymbol\alpha_2, \dots, \boldsymbol\alpha_n$ 线性相关 $\iff$ 齐次线性方程组 $\boldsymbol{Ax}=\boldsymbol{0}$ 有非零解$\iff$矩阵 $\boldsymbol{A}$ 的行、列向量线性相关$\iff$矩阵 $\boldsymbol{A}$ 不满秩

②向量 $\boldsymbol{b}$ 能否由向量组 $\boldsymbol \alpha_1, \dots, \boldsymbol\alpha_n$ 线性表出，即判断非齐次线性方程组 $\displaystyle x_1 \boldsymbol\alpha_1 + x_2 \boldsymbol\alpha_2 + \cdots + x_n \boldsymbol\alpha_n = \boldsymbol{b}(A \boldsymbol{x} = \boldsymbol{b})$ 是否有解，对应的方程组为：
$$
\displaystyle 
\begin{cases} 
\alpha_{11} x_1 + \alpha_{12} x_2 + \cdots + \alpha_{1n} x_n = b_1 \newline 
\alpha_{21} x_1 + \alpha_{22} x_2 + \cdots + \alpha_{2n} x_n = b_2 \newline
\quad\vdots \newline
\alpha_{m1} x_1 + \alpha_{m2} x_2 + \cdots + \alpha_{mn} x_n = b_m 
\end{cases}
$$
 $\boldsymbol{b}$ 能由向量组 $\boldsymbol{\alpha}_1, \dots, \boldsymbol\alpha_n$ 线性表出 $\iff$ 非齐次线性方程组 $\boldsymbol{Ax}=\boldsymbol{b}$ 有解 $\iff \boldsymbol{b} \in \boldsymbol L(\boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_n)$ 

 $\boldsymbol{b}$ 不能由向量组 $\boldsymbol{\alpha}_1, \dots, \boldsymbol\alpha_n$ 线性表出 $\iff$ 非齐次线性方程组 $\boldsymbol{Ax}=\boldsymbol{b}$ 无解

### 1.b.β 线性相关、线性无关的性质和推论

- 单个向量 $\boldsymbol{\alpha}$ 线性相关的充要条件是 $\boldsymbol{\alpha} = \boldsymbol{0}$；<br>多个向量 $\boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_n$ 线性相关的充要条件是，存在一个向量 $\boldsymbol{\alpha}_i$ 是其余向量 $\boldsymbol α_i^-$ 的线性组合

- **替换定理**：向量组 $\boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_r$ 可以由向量组 $\boldsymbol{\beta}_1, \dots, \boldsymbol{\beta}_s$ 线性表出，且向量组 $\boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_r$ 线性无关，则有 $r \leq s$.<br>**替换定理逆否命题**：向量组 $\boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_r$ 可以由向量组 $\boldsymbol{\beta}_1, \dots, \boldsymbol{\beta}_s$ 线性表出，且 $r > s$，则 $\boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_r$ 线性相关<br>
  推论：两个<u>线性无关</u>的、<u>等价</u>的向量组，其向量个数相同.

  > 由题设，存在系数矩阵$L = (l_{ij}) \in \mathbb{F}^{r \times s}$，使得 $\displaystyle \boldsymbol\alpha_i = \sum_{j=1}^{s} l_{ij}\cdot \boldsymbol\beta_j$，即：
  >
  > $\displaystyle \underbrace{[\boldsymbol\alpha_1 \ \boldsymbol\alpha_2 \ \cdots \ \boldsymbol\alpha_r]}_{n \times r}^{\LARGE A}=
  > \underbrace{[\boldsymbol\beta_1 \ \boldsymbol\beta_2 \ \cdots \ \boldsymbol\beta_s]}_{n \times s}^{\LARGE B}
  > \cdot
  > \underbrace{
  > \begin{bmatrix}
  > \ell_{11} & \ell_{21} & \cdots & \ell_{r1} \newline
  > \ell_{12} & \ell_{22} & \cdots & \ell_{r2} \newline
  > \vdots    & \vdots    & \ddots & \vdots    \newline
  > \ell_{1s} & \ell_{2s} & \cdots & \ell_{rs}
  > \end{bmatrix}
  > }_{s \times r}^{\LARGE L^\top}$
  >
  > `$$\displaystyle \underbrace{[\boldsymbol\alpha_1 \ \boldsymbol\alpha_2 \ \cdots \ \boldsymbol\alpha_r]}_{n \times r}^{\LARGE A}=
  > \underbrace{[\boldsymbol\beta_1 \ \boldsymbol\beta_2 \ \cdots \ \boldsymbol\beta_s]}_{n \times s}^{\LARGE B}
  > \cdot
  > \underbrace{
  > \begin{bmatrix}
  > \ell_{11} & \ell_{21} & \cdots & \ell_{r1} \newline
  > \ell_{12} & \ell_{22} & \cdots & \ell_{r2} \newline
  > \vdots    & \vdots    & \ddots & \vdots    \newline
  > \ell_{1s} & \ell_{2s} & \cdots & \ell_{rs}
  > \end{bmatrix}
  > }_{s \times r}^{\LARGE L^\top}$$`
  >
  > 因为向量组 $\boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_r$ 线性无关，所以其组成的矩阵的列向量线性无关，即：$\displaystyle \operatorname{r}(A)=\operatorname{r}([\boldsymbol{\alpha}_1 \ \cdots \ \boldsymbol{\alpha}_r]) = r$ ，同理 $\operatorname{r}(B)=s$ .
  >
  > 而根据矩阵乘积的秩的性质，有：$\displaystyle r=\operatorname{r}(A) = \operatorname{r}(B \cdot L^\top) \le \min \lbrace \operatorname{r}(B), \operatorname{r}(L^\top) \rbrace \le \operatorname{r}(B)=s$
  >
  > 从而得到：$\displaystyle r \le s$ .
  
- 整体相关 $\Rightarrow$ 部分相关；整体无关 $\Rightarrow$ 部分无关<br>接长相关 $\Rightarrow$ 部分相关；部分无关 $\Rightarrow$ 整体无关

-   $\boldsymbol{\beta}$ 可被 $\lbrace \boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_r \rbrace$ 线性表出：$\displaystyle \boldsymbol{\beta} = k_1 \boldsymbol{\alpha}_1 + \cdots + k_r \boldsymbol{\alpha}_r$ ，则<br> $\lbrace \boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_r \rbrace$ 线性无关$\iff$这个表示唯一.

  > $\Rightarrow$：（反证法）
  >
  > 假设存在两组系数 $\lbrace k_1, \dots, k_r \rbrace$ 与 $\lbrace k_1', \dots, k_r' \rbrace$，使得
  > $\boldsymbol{\beta} = k_1 \boldsymbol{\alpha}_1 + \cdots + k_r \boldsymbol{\alpha}_r = k_1' \boldsymbol{\alpha}_1 + \cdots + k_r' \boldsymbol{\alpha}_r$，
  > 两式相减得：$(k_1 - k_1') \boldsymbol{\alpha}_1 + \cdots + (k_r - k_r') \boldsymbol{\alpha}_r = \boldsymbol{0}$.
  >
  > 由 $\boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_r$ 线性无关，必有 $k_i - k_i' = 0$，即 $k_i = k_i'$，对所有 $i$ 成立.
  >
  > 因此，$\boldsymbol{\beta}$ 的线性表出方式唯一.
  >
  > $\Leftarrow$：（反证法）
  >  若该表示不唯一，则存在不同的两组系数，使得相同的 $\boldsymbol{\beta}$ 有两种不同的线性表出形式，
  >  两式相减后得到非零系数线性组合为零向量，说明 $\lbrace \boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_r \rbrace$ 线性相关，矛盾。
  >  故 $\lbrace \boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_r \rbrace$ 线性无关。

- 若 $\lbrace \boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_r \rbrace$ 线性无关，而与 $\boldsymbol{\beta}$ 合并后线性相关，则 $\boldsymbol{\beta}$ 可被 $\lbrace \boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_r \rbrace$ 线性表出： $\displaystyle \boldsymbol{\beta} = k_1 \boldsymbol{\alpha}_1 + \cdots + k_r \boldsymbol{\alpha}_r$ ，且这个表示是唯一的.
- 含零向量的向量组一定线性相关
- $n$ 维单位向量组线性无关
- 任何由 $n + k$ 个 $n$ 维向量组成的向量组必定线性相关

### 1.b.γ 极大线性无关组及其性质

设向量组 $\boldsymbol\alpha_1, \boldsymbol\alpha_2, \dots, \boldsymbol\alpha_n \in V$，令 $I = \lbrace 1, 2, \dots, n \rbrace$，取 $R \subseteq I$，记 $A_R = \lbrace \boldsymbol\alpha_i \mid i \in R \rbrace$ ， $A_{R^c} = \lbrace \boldsymbol\alpha_i \mid i \in I \setminus R \rbrace$。若 $A_R$ 线性无关，且对任意 $j \in R^c$，集合 $A_{R \cup \lbrace j \rbrace}$ 都线性相关，则称 $A_R$ 是在 $\lbrace \boldsymbol\alpha_1, \dots, \boldsymbol\alpha_n \rbrace$ 中的**极大线性无关组**。

**性质 1（存在性）**
 对有限向量组 $\lbrace \boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_n \rbrace$，极大线性无关组一定存在

**性质 2（张成性）**
 若 $A_R$ 是极大线性无关组，则有 $\displaystyle \boldsymbol{L}(\boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_n) = \boldsymbol{L}(A_R)$。

> 若存在 $\boldsymbol{\alpha}_j \notin \boldsymbol{L}(A_R)$，则 $A_{R \cup \lbrace j \rbrace}$ 仍线性无关，与极大性矛盾。

**性质 3（等基数）**
 若 $A_R$ 和 $A_S$ 都是 $\lbrace \boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_n \rbrace$ 中的极大线性无关组，则 $|R| = |S|=\operatorname{r}(\boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_n)$。

**性质 4（延拓性）** ——空间任一线性无关组都可扩展为基（加上原向量组 $\lbrace \boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_n \rbrace$ 的子集）
若 $B = \lbrace \boldsymbol{\beta}_1, \dots, \boldsymbol{\beta}_r \rbrace\subseteq \boldsymbol{L}(\boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_n)$ 且 $B$ 线性无关，则存在 $S \subseteq I$，使得 $B \cup A_S$ 是原向量组的一个极大线性无关组。

**性质 5（替换性）**
 若 $B = \lbrace \boldsymbol{\beta}_1, \dots, \boldsymbol{\beta}_r \rbrace\subseteq \boldsymbol{L}(\boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_n)$ 且 $B$ 线性无关，$C = \lbrace \boldsymbol{\gamma}_1, \dots, \boldsymbol{\gamma}_s \rbrace$ 张成相同的子空间，则 $r \leq s$，且可以从 $C$ 中替换出 $r$ 个向量与 $B$ 交换，得到新的生成元组而不改变生成空间。

> 证明分为 $r$ 步：
>
>  第1步，因为 $\boldsymbol{\beta}_1$ 在子空间中，所以 $\boldsymbol{\beta}_1$ 可以表示为 $\boldsymbol{C}$ 中向量的线性组合，即 $\displaystyle \boldsymbol{\beta}_1 = a_1 \boldsymbol{\gamma}_1 + a_2 \boldsymbol{\gamma}_2 + \dots + a_s \boldsymbol{\gamma}_s$。至少有一个系数 $a_j \neq 0$，否则 $\boldsymbol{\beta}_1$ 会是零向量，这与 $B$ 线性无关矛盾。不妨设 $a_1 \neq 0$，则可以解出 $\boldsymbol{\gamma}_1$ 为 $\displaystyle \boldsymbol{\gamma}_1 = \frac{1}{a_1} \boldsymbol{\beta}_1 - \frac{a_2}{a_1} \boldsymbol{\gamma}_2 - \dots - \frac{a_s}{a_1} \boldsymbol{\gamma}_s$，于是 $\boldsymbol{L}(\boldsymbol{\gamma}_1, \boldsymbol{\gamma}_2, \dots, \boldsymbol{\gamma}_s) = \boldsymbol{L}(\boldsymbol{\beta}_1, \boldsymbol{\gamma}_2, \dots, \boldsymbol{\gamma}_s)$。
>
> 第2步，同理处理 $\boldsymbol\beta_2$。 $\boldsymbol\beta_2$ 可以表示为 $\boldsymbol\beta_1, \boldsymbol\gamma_2, \dots, \boldsymbol\gamma_s$ 的线性组合。由于 $B$ 的线性无关性，必然存在某个 $\boldsymbol\gamma_j$（前面步骤中未被替换过）的系数 $a_k \neq 0$。假设是 $\boldsymbol\gamma_2$，则解出 $\displaystyle \boldsymbol\gamma_2 = \frac{1}{a_2} \boldsymbol\beta_2 - \frac{a_1}{a_2} \boldsymbol\beta_1 - \sum_{i=3}^s \frac{a_i}{a_2} \boldsymbol\gamma_i$，并将 $\boldsymbol\gamma_2$ 替换为 $\boldsymbol\beta_2$，得到新集合 $\lbrace \boldsymbol\beta_1, \boldsymbol\beta_2, \boldsymbol\gamma_3, \dots, \boldsymbol\gamma_s \rbrace$。
>
> 证明 $r \leq s$：若$r > s$，则 $\boldsymbol\gamma$ 先被替换完，则第 $s+1$ 步时 $\boldsymbol\beta_{s+1}$ 可以表示为 $\boldsymbol\beta_1, \boldsymbol\beta_2, \dots, \boldsymbol\beta_s$ 的线性组合，这与 $B$ 线性无关矛盾
>
> 如此归纳到第 $r$ 步，最终得到的向量组 $\lbrace \boldsymbol\beta_1, \dots, \boldsymbol\beta_r, \boldsymbol\gamma_k, \dots \rbrace$ 仍然生成原来的子空间

### 1.b.δ 基与维数

设 $V$ 是域 $F$ 上的线性空间，若一组向量 $\lbrace \boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_n \rbrace \subset V$ 既线性无关，又张成 $V$，则称这组向量是 $V$ 的一组**基**.

基的定义意味着：

- 任一 $\boldsymbol{\beta} \in V$ 可**唯一地表示为基的线性组合**；
- 基的向量个数 $n$ 称为 $V$ 的**维数**，记作 $\dim V = n$；

若 $V$ 存在有限个基向量，则称 $V$ 是**有限维**空间，否则为**无限维**.

例如：

- $\dim \mathbb{R}^n = n$；
- $\dim K[x]_n = n$（次数小于 $n$ 的一元多项式空间）；
- $\dim \mathbb{M}_{s \times t}(K) = st$；

------

### 1.b.ε 坐标表示与坐标向量

设 $V$ 是 $F$ 上 $n$ 维线性空间，$\lbrace \boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_n \rbrace$ 是一组基.则任意 $\boldsymbol{\beta} \in V$ 可唯一写为

$\displaystyle \boldsymbol{\beta} = k_1 \boldsymbol{\alpha}_1 + \cdots + k_n \boldsymbol{\alpha}_n$，

则称 $k_1, \ldots, k_n$ 是 $\boldsymbol{\beta}$ 在该基下的**坐标**，将其写成列向量

$\displaystyle [\boldsymbol{\beta}] = \begin{bmatrix}k_1 \ \vdots \ k_n \end{bmatrix}$，

称为 $\boldsymbol{\beta}$ 相对于该基的**坐标向量**.

------

## 1.c 线性子空间基础

### 1.c.α 线性子空间

**线性子空间 linear subspace：**
设 $V$ 是域 $F$ 上的线性空间，<u>若 $U \subseteq V$，且 $U$ 在 $V$ 的加法与数乘下自身也构成一个 $F$ 上的线性空间</u>，则称 $U$ 是 $V$ 的线性子空间（linear subspace）

证明是线性空间很麻烦，所以使用充要条件，**充要条件为：**

1. $U$ 是 $V$ 的<u>非空</u>子集（通常验证 $\boldsymbol 0 \in U$）；
2. $U$ <u>对加法与数乘封闭</u>，即：
   - 加法封闭：$\forall\ \boldsymbol\alpha, \boldsymbol\beta \in U$，有 $\boldsymbol\alpha + \boldsymbol\beta \in U$；
   - 数乘封闭：$\forall\ k \in F,\ \boldsymbol\alpha \in U$，有 $k \boldsymbol\alpha \in U$.

>  $\Rightarrow$：构成一个 $F$ 上的线性空间 $\Rightarrow$ 1.和2.显然成立
>
>  $\Leftarrow$：1.和2. $\Rightarrow$ 构成一个 $F$ 上的线性空间（证明满足八条公理）
>
> 公理①②⑤⑥⑦⑧成立（继承自原空间 $V$）
>
> 公理③（零向量存在性）：
> 因为 $U$ 非空，取 $\boldsymbol{\alpha} \in U$，令 $k = 0 \in F(域的定义)$，则 $k \cdot \boldsymbol{\alpha} = \boldsymbol{0} \in U$，说明 $U$ 中包含零向量（零元）
>
> 公理④（加法逆元存在性）：
> 对任意 $\boldsymbol{\beta} \in U$，令 $k = -1 \in F$，则 $ U \ni k \cdot \boldsymbol{\beta}=(-1) \cdot \boldsymbol{\beta} \xlongequal{\boldsymbol{\beta} \in V，根据1.a.δ\_3} -\boldsymbol{\beta}$，说明每个向量在 $U$ 中都有加法逆元.

**常见子空间例子：**

1. $V = \mathbb{R}^3$ 中所有形如 $(x, y, 0)$ 的向量构成一个二维子空间；
2. $\mathbb{M}_{n \times n}(F)$ 中所有对称矩阵构成其一个子空间；
3. 多项式空间 $K[x]$ 中次数 $\leq 2$ 的多项式组成 $K[x]_3$ 是 $K[x]$ 的子空间；
4. $V$ 中任意向量组 $\boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_n$ 张成的集合 $\langle \boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_n \rangle$ 是 $V$ 的一个子空间；
5. $\lbrace \boldsymbol{0} \rbrace$ 和 $V$ 本身都是 $V$ 的子空间，称为**零子空间**与**平凡子空间**.

### 1.b.β 向量组张成空间和秩

$\displaystyle \text{Span}(\boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_n) =\boldsymbol L(\boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_n) =\lbrace k_1 \boldsymbol{\alpha}_1 + \cdots + k_n \boldsymbol{\alpha}_n \mid k_i \in F \rbrace$，称为 $S$ **生成的子空间**，也可记作 $\langle \boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_n \rangle$.它是 $V$ 的子空间，且是包含 $\lbrace \boldsymbol \alpha_1, \ldots, \boldsymbol{\alpha}_n\rbrace$ 的最小子空间

设 $V$ 是域 $F$ 上的线性空间，$\boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_s \in V$，则称

- $\displaystyle \text{span}(\boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_s)$ 为该向量组张成的子空间；
- 该子空间的维数称为这组向量的**秩**（rank），记为 $\displaystyle \operatorname{rank}(\boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_s)$.

------

### 1.c.γ 线性空间的基

**线性相关与无关**

设 $V$ 是域 $K$ 上的线性空间。

- $V$ 的一个有限子集 $\lbrace\alpha_1, \ldots, \alpha_s\rbrace$ 称为**线性相关/无关** $\Longleftrightarrow$ $\alpha_1, \ldots, \alpha_s$ **线性相关相关/无关**。
- $V$ 的一个无限子集 $S$ 称为**线性相关** $\Longleftrightarrow$  $S$ 中存在一个有限子集线性相关
- $V$ 的一个无限子集 $S$ 称为**线性无关** $\Longleftrightarrow$  $S$ 中任意一个有限子集线性无关

**基**

设 $V$ 是域 $K$ 上的线性空间。若 $S$（有限或无限子集）  $\subset V$ 同时满足：

1. **生成性**： $V$ 中任意一个向量可以由 $S$ 中的有限多个向量线性表出；
2. **线性无关性**： $S$ 是线性无关的

则称 $S$ 为线性空间 $V$ 上的<u>一个</u>基

设 $V = {0}$，由于 $0$ 不能出现在任何线性无关组中，因此 $V$ 的基是**空集** $\varnothing$。

按照约定：$\dim \{0\} = 0.$

------

### 1.c.δ 线性空间的维数

**定义**：设 $V$ 是域 $K$ 上的线性空间。

- 若 $V$ 存在一个有限基，则称 $V$ 为**有限维线性空间**。此时所有基所含向量的个数相同，这个数 $n$ 称为 $V$ 的**维数**，记作 $\dim V=n$。

  **推论（关于 $\dim V = n$ 的性质）**：设 $\dim V = n$，则有：

  1. $V$ 中任意 $n$ 个线性无关向量必是 $V$ 的一组基。
  2. $V$ 中任意 $n$ 个向量生成 $V$ 当且仅当它们是 $V$ 的一组基。
  3. $V$ 中任意 $n+1$ 个向量必然线性相关。

- 若 $V$ 不存在有限基，则称 $V$ 为**无限维线性空间**。此时说 $V$ 的维数是**无限**，记作 $\dim V=\infty$。

**维数相等**

有限维空间的一个重要结论是：$\text{若 V 是有限维空间，则任意两个基的向量个数相等。}$

若 $V$ 不是有限维的，则称 $V$ 是**无限维空间**。在这种情况下，$V$ 的任何一个基必定是无限集。
 原因是：若存在一个有限基，则 $V$ 就是有限维的，与假设矛盾。

| 空间                                                   | 基                         | 维数   |
| ------------------------------------------------------ | -------------------------- | ------ |
| $V = {0}$                                              | $\varnothing$              | $0$    |
| $\mathbb{R}^n$                                         | ${e_1, e_2, \ldots, e_n}$  | $n$    |
| 所有次数 $\leq m$ 的实系数多项式空间 $P_m(\mathbb{R})$ | ${1, x, x^2, \ldots, x^m}$ | $m+1$  |
| 所有实系数多项式空间 $P(\mathbb{R})$                   | 无有限基                   | 无限维 |

**坐标的定义**：设 ${e_1, \dots, e_n}$ 是 $V$ 的一组基，则 $V$ 中任意向量 $v$ 都可以唯一表示为基向量的线性组合：

$$v = a_1 e_1 + a_2 e_2 + \dots + a_n e_n,$$

其中 $a_1, \dots, a_n \in K$。将向量 $v$ 在基 ${e_1, \dots, e_n}$ 下的系数组成的 $n$ 维列向量

$${e} = \begin{bmatrix} a_1 \\ a_2 \\ \vdots \\ a_n \end{bmatrix}$$

称为 $v$ 相对于基 ${e_1, \dots, e_n}$ 的**坐标**。

好的 👍 你现在已经整理了 **维数**、**有限维与无限维的区别**、**基的唯一向量数** 以及 **坐标的定义**，很完整了。接下来在 **1.c.ο 子空间的交与并** 这一小节，可以这样自然衔接：

------

### 1.c.ε 子空间的交与并

**定义**：设 $V$ 是域 $K$ 上的线性空间，$U, W \subseteq V$ 为 $V$ 的两个子空间。

- **交**：$U \cap W = \lbrace v \in V \mid v \in U \text{ 且 } v \in W \rbrace$，仍然是 $V$ 的子空间。
- **并**：$U \cap W = \lbrace v \in V \mid v \in U \text{ 或 } v \in W \rbrace$ 不一定是 $V$ 的子空间，因为 $U \cup W$ 未必对加法封闭。
- $和$：定义$U + W = \lbrace u + w \mid u \in U\rbrace$ 为 $U$ 与 $W$ 的**和**。这是包含 $U \cup W$ 的最小子空间。

**维数公式（有限维情形）**：
若 $U, W$ 是有限维子空间，则 $\dim U + \dim W =\dim(U + W) + \dim(U \cap W).$

------

直和

很好 👍，你已经把交、并、和写清楚了，接下来补充 **直和** 部分：

------

### 1.c.ζ 子空间的直和

**定义**：设 $U, W \subseteq V$ 为两个子空间。若

1. $U \cap W = {0}$；
2. $U + W = V$；

则称 $V$ 是 $U$ 与 $W$ 的**直和**，记作 $V = U \oplus W$.

更一般地，若 $U_1, U_2, \dots, U_k \subseteq V$ 满足

- $V = U_1 + U_2 + \cdots + U_k$，
- 并且对于每个 $i$，$U_i \cap (U_1 + \cdots + U_{i-1} + U_{i+1} + \cdots + U_k) = {0}$，

则称 $V$ 是 $U_1, \dots, U_k$ 的直和，记作 $V = U_1 \oplus U_2 \oplus \cdots \oplus U_k$.

------

**性质**：

1. 若 $V = U \oplus W$，则 $V$ 中每个向量 $v$ 都能唯一表示为

   $v = u + w, \quad u \in U, \; w \in W.$

2. 在有限维情形下，若 $V = U \oplus W$，则

   $\dim V = \dim U + \dim W$.

------

