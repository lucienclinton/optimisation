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

### 1.a.υ 线性空间的典型例子：

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

**线性相关**：『设 $\boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_n \in V$，若存在不全为零的 $k_1, \ldots, k_n \in F$，使得 $\displaystyle k_1 \boldsymbol{\alpha}_1 + \cdots + k_n \boldsymbol{\alpha}_n = \boldsymbol{0}$』，则称这组向量**线性相关**.

**线性无关**：『设 $\boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_n \in V$，若不存在不全为零的 $k_1, \ldots, k_n \in F$，使得 $\displaystyle k_1 \boldsymbol{\alpha}_1 + \cdots + k_n \boldsymbol{\alpha}_n = \boldsymbol{0}$ 』$\iff$『 仅有 $k_1 = \cdots = k_n = 0$ 能使线性组合等于 $\boldsymbol{0}$ 』，称这组向量**线性无关**.



判断向量组 $\boldsymbol\alpha_1, \boldsymbol\alpha_2, \dots, \boldsymbol\alpha_n \in \mathbb{F}^m$ 是否线性相关，就是考察方程  $\displaystyle x_1 \boldsymbol\alpha_1 + x_2 \boldsymbol\alpha_2 + \cdots + x_n \boldsymbol\alpha_n = \boldsymbol{0}$  是否有非零解：  
$\displaystyle
\begin{cases}
\alpha_{11}x_1 + \alpha_{12}x_2 + \cdots + \alpha_{1n}x_n = 0 \newline
\alpha_{21}x_1 + \alpha_{22}x_2 + \cdots + \alpha_{2n}x_n = 0 \newline
\quad\vdots \newline
\alpha_{m1}x_1 + \alpha_{m2}x_2 + \cdots + \alpha_{mn}x_n = 0
\end{cases}
$  

因此，向量组 $\boldsymbol\alpha_1, \boldsymbol\alpha_2, \dots, \boldsymbol\alpha_n$ 线性无关的充要条件是该齐次方程组只有零解，即 $x_1 = x_2 = \cdots = x_n = 0$.

**常用结论——**

- 单个向量 $\boldsymbol{\alpha}$ 线性相关的充要条件是 $\boldsymbol{\alpha} = \boldsymbol{0}$；<br>多个向量 $\boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_n$ 线性相关的充要条件是，存在一个向量 $\boldsymbol{\alpha}_i$ 是其余向量 $\boldsymbol α_i^-$ 的线性组合

- 设向量组 $\boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_r$ 线性无关，若它们可以由 $\boldsymbol{\beta}_1, \dots, \boldsymbol{\beta}_s$ 线性表出，则有 $r \leq s$.<br>
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
  > 
  >
  > 
  >
  > 因为向量组 $\boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_r$ 线性无关，所以其组成的矩阵的列向量线性无关，即：$\displaystyle \operatorname{r}(A)=\operatorname{r}([\boldsymbol{\alpha}_1 \ \cdots \ \boldsymbol{\alpha}_r]) = r$ ，同理 $\operatorname{r}(B)=s$ .
  >
  > 而根据矩阵乘积的秩的性质，有：$\displaystyle r=\operatorname{r}(A) = \operatorname{r}(B \cdot L^\top) \le \min \lbrace \operatorname{r}(B), \operatorname{r}(L^\top) \rbrace \le \operatorname{r}(B)=s$
  >
  > 从而得到：$\displaystyle r \le s$ .

- 若 $\lbrace \boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_r \rbrace$ 线性无关，而与 $\boldsymbol{\beta}$ 合并后线性相关，则 $\boldsymbol{\beta}$ 可被 $\lbrace \boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_r \rbrace$ 线性表出： $\displaystyle \boldsymbol{\beta} = k_1 \boldsymbol{\alpha}_1 + \cdots + k_r \boldsymbol{\alpha}_r$ ，且这个表示是唯一的.

  > 假设向量组 $\lbrace \boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_r, \boldsymbol{\beta} \rbrace$ 线性相关，
  > 则存在不全为零的标量 $k_1, \dots, k_r, l$，使得
  > $k_1 \boldsymbol{\alpha}_1 + \cdots + k_r \boldsymbol{\alpha}_r + l \boldsymbol{\beta} = \boldsymbol{0}$.
  >
  > ①若 $l = 0$，则原式为$k_1 \boldsymbol{\alpha}_1 + \cdots + k_r \boldsymbol{\alpha}_r = \boldsymbol{0}$，但由 $\boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_r$ 线性无关知，必有 $k_1 = \cdots = k_r = 0$，这与“$k_1, \dots, k_r, l$ 不全为零矛盾，故 $l \neq 0$.
  > 
  > 将上式两边除以 $l$，得$\boldsymbol{\beta} = -\dfrac{k_1}{l} \boldsymbol{\alpha}_1 - \cdots - \dfrac{k_r}{l} \boldsymbol{\alpha}_r$，
  > 故 $\boldsymbol{\beta}$ 可由 $\boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_r$ 线性表出.
  >
  > ②接下来证明唯一性（反证法）
  > 
  > 假设存在两组系数 $\lbrace k_1, \dots, k_r \rbrace$ 与 $\lbrace k_1', \dots, k_r' \rbrace$，使得
  >$\boldsymbol{\beta} = k_1 \boldsymbol{\alpha}_1 + \cdots + k_r \boldsymbol{\alpha}_r = k_1' \boldsymbol{\alpha}_1 + \cdots + k_r' \boldsymbol{\alpha}_r$，
  > 两式相减得：$(k_1 - k_1') \boldsymbol{\alpha}_1 + \cdots + (k_r - k_r') \boldsymbol{\alpha}_r = \boldsymbol{0}$.
  >
  > 由 $\boldsymbol{\alpha}_1, \dots, \boldsymbol{\alpha}_r$ 线性无关，必有 $k_i - k_i' = 0$，即 $k_i = k_i'$，对所有 $i$ 成立.
  > 
  > 因此，$\boldsymbol{\beta}$ 的线性表出方式唯一.

------

### 1.b.β 向量组生成的子空间（张成空间）

若 $S = \lbrace \boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_n \rbrace$ 是 $V$ 中一组向量，定义 $S$ 的所有线性组合组成的集合为

$\displaystyle \text{span}(S) = \lbrace k_1 \boldsymbol{\alpha}_1 + \cdots + k_n \boldsymbol{\alpha}_n \mid k_i \in F \rbrace$，

称为 $S$ **张成的子空间**，记作 $\langle \boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_n \rangle$.它是 $V$ 的子空间，且是包含 $S$ 的最小子空间.

------

### 1.b.δ 基与维数

设 $V$ 是域 $F$ 上的线性空间.

若一组向量 $\lbrace \boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_n \rbrace \subset V$ 既线性无关，又张成 $V$，则称这组向量是 $V$ 的一组**基**.

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

### 1.b.ζ 基变换与坐标变换（留待后续章节详细展开）

不同基下，向量的坐标向量不同.若已知两个基之间的变换关系（变换矩阵），可实现坐标向量间的转换.后续将在“基变换”章节详细说明.

------

是否需要我继续整理 **1.c 子空间与向量组的秩**？也欢迎你就刚才内容提出反驳、补充或新的要求.







明白，以下是完整的 **1.c 子空间与向量组的秩** 部分，延续你此前的风格与编号系统，分为三个小节：$\text{1.c.}\alpha$（定义与判别）、$\text{1.c.}\beta$（向量组的秩）、$\text{1.c.}\gamma$（子空间的和、交与维数公式）.

------

## 1.c 子空间与向量组的秩

------

### 1.c.α 子空间的定义与判别

设 $V$ 是域 $F$ 上的线性空间.若 $U \subseteq V$ 是 $V$ 的一个非空子集，且在加法与数乘下封闭，并满足线性空间的八条运算公理，则称 $U$ 为 $V$ 的一个**子空间**（subspace）.

**子空间判别准则（两步法）**：

设 $U \subseteq V$，$V$ 是域 $F$ 上的线性空间.若满足：

1. **加法封闭**：$\boldsymbol{\alpha}, \boldsymbol{\beta} \in U \Rightarrow \boldsymbol{\alpha} + \boldsymbol{\beta} \in U$；
2. **数乘封闭**：$k \in F,\ \boldsymbol{\alpha} \in U \Rightarrow k \boldsymbol{\alpha} \in U$；

则 $U$ 为 $V$ 的子空间.

证明子空间也是线性空间，即证明满足八条公理

> 公理①②⑤⑥⑦⑧成立（继承自原空间 $V$）
>
> 公理③（零向量存在性）：
>  因为 $U$ 非空，取 $\boldsymbol{\alpha} \in U$，令 $k = 0 \in F(域的定义)$，则 $k \cdot \boldsymbol{\alpha} = \boldsymbol{0} \in U$，说明 $U$ 中包含零向量（零元）
>
> 公理④（加法逆元存在性）：
>  对任意 $\boldsymbol{\beta} \in U$，令 $k = -1 \in F$，则 $ U \ni k \cdot \boldsymbol{\beta}=(-1) \cdot \boldsymbol{\beta} \xlongequal{\boldsymbol{\beta} \in V，根据1.a.δ\_3} -\boldsymbol{\beta}$，说明每个向量在 $U$ 中都有加法逆元。

**常见子空间例子：**

1. $V = \mathbb{R}^3$ 中所有形如 $(x, y, 0)$ 的向量构成一个二维子空间；
2. $\mathbb{M}_{n \times n}(F)$ 中所有对称矩阵构成其一个子空间；
3. 多项式空间 $K[x]$ 中次数 $\leq 2$ 的多项式组成 $K[x]_3$ 是 $K[x]$ 的子空间；
4. 任意向量组 $\boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_n$ 张成的集合 $\langle \boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_n \rangle$ 是一个子空间；
5. $\lbrace \boldsymbol{0} \rbrace$ 和 $V$ 本身都是 $V$ 的子空间，称为**零子空间**与**平凡子空间**.

------

### 1.c.β 向量组的秩

设 $V$ 是域 $F$ 上的线性空间，$\boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_s \in V$，则称

- $\displaystyle \text{span}(\boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_s)$ 为该向量组张成的子空间；
- 该子空间的维数称为这组向量的**秩**（rank），记为 $\displaystyle \operatorname{rank}(\boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_s)$.

------

**等价定义**：

- 向量组 $\lbrace \boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_s \rbrace$ 中取出一个极大线性无关子集，其向量个数就是该向量组的秩.

**性质与结论**：

1. $\displaystyle \operatorname{rank}(\boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_s) \leq s$；
2. 若该组向量线性无关，则秩为 $s$；
3. 若向量组中存在线性相关关系，则秩小于 $s$；
4. 若 $\boldsymbol{\alpha}_1, \ldots, \boldsymbol{\alpha}_s$ 张成子空间 $U$，且 $\dim U = r$，则一定存在 $r$ 个线性无关向量组成 $U$ 的一个基，其余向量可由该基线性表出.

------

**例**：

向量组 $\left\lbrace \begin{bmatrix} 1 \ 2 \end{bmatrix},\ \begin{bmatrix} 3 \ 6 \end{bmatrix},\ \begin{bmatrix} 1 \ 0 \end{bmatrix} \right\rbrace$ 的秩为 2，其中 $\begin{bmatrix} 3 \ 6 \end{bmatrix}$ 是 $\begin{bmatrix} 1 \ 2 \end{bmatrix}$ 的倍数，可去掉.

------

### 1.c.γ 子空间的和、交与维数公式

设 $U, W$ 是线性空间 $V$ 的两个子空间，定义：

- **交集** $U \cap W$：所有同时属于 $U$ 和 $W$ 的向量，仍为子空间；
- **和空间** $U + W$：所有可表示为 $\boldsymbol{u} + \boldsymbol{w}$（其中 $\boldsymbol{u} \in U,\ \boldsymbol{w} \in W$）的向量所组成的集合，是包含 $U$ 与 $W$ 的最小子空间.

形式化定义：

$\displaystyle U + W = \lbrace \boldsymbol{\alpha} \in V \mid \boldsymbol{\alpha} = \boldsymbol{u} + \boldsymbol{w},\ \boldsymbol{u} \in U,\ \boldsymbol{w} \in W \rbrace$

------

**维数公式（Grassmann 公式）**：

设 $U, W \subseteq V$ 是有限维子空间，则有：

$\displaystyle \dim(U + W) = \dim U + \dim W - \dim(U \cap W)$

**推论**：

- 若 $U \cap W = \lbrace \boldsymbol{0} \rbrace$，则 $\displaystyle \dim(U + W) = \dim U + \dim W$，称 $U, W$ **直和**；
- 若 $U + W = V$ 且 $U \cap W = \lbrace \boldsymbol{0} \rbrace$，则称 $V$ 是 $U$ 与 $W$ 的**直和**，记作 $V = U \oplus W$.

------

是否需要我现在将整个 `1.a + 1.b + 1.c` 生成一个完整 LaTeX 文件或 Markdown 模板？或者我们进入 **1.d 向量的坐标变换与过渡矩阵**？











## 1.c 线性子空间基础

### 1.c.α 线性子空间

**线性子空间 linear subspace：**
设 $V$ 是域 $F$ 上的线性空间，若 $U \subseteq V$，且 $U$ 在 $V$ 的加法与数乘下自身也构成一个 $F$ 上的线性空间，则称 $U$ 是 $V$ 的线性子空间（linear subspace）

**即充要条件为：**

1. $U$ 是 $V$ 的<u>非空</u>子集（通常验证 $\boldsymbol 0 \in U$）；
2. $U$ <u>对加法与数乘封闭</u>[^封闭运算]，即：
   - 加法封闭：$\forall\ \boldsymbol\alpha, \boldsymbol\beta \in U$，有 $\boldsymbol\alpha + \boldsymbol\beta \in U$；
   - 数乘封闭：$\forall\ k \in F,\ \boldsymbol\alpha \in U$，有 $k \boldsymbol\alpha \in U$.

[^封闭运算]:这两个封闭运算客观满足 **8 条公理**，在线性空间 $V$ 里满足，在线性空间 $U$ 里也一定满足



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