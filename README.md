# Preference

## 写在最前面

本笔记主要记录 Lucien Clinton 自 2025 年暑假开始学习最优化的过程，包括网课笔记、理论推导与 Python/R 实现代码。为贯彻“学以致用，理论联系实际”的原则，每一章节末尾均附上对应的编程实现。

在首次尝试使用 Docsify 搭建笔记网站的过程中遇到诸多挑战：Typora、GitHub与 Docsify 在LateX上的兼容性问题频繁出现，网络上相关参考资料也相对有限。因此，笔记前言也记录在过程中遇到的问题与解决方案，便于日后查阅参考。

最后祝愿自己学有所获！

<div align="right">2025年7月5日</div>

## 遇到的各种问题

#### 1.{}在Typora行内公式和行外公式环境下可见但在网页中出错——

在Typora里面显示如下：

![在Typora没有遇到问题](images/00-a大括号在Typora没有问题.png)

但是在docsify架构的网页里面，虽然尝试使用了五种不同的架构方式：

```markdown
$X = \left{ x \in \mathbb{R}^n \ \middle| \ \begin{aligned} &c_i(x) \leq 0, && i = 1,2,\dots, m \ &c_i(x) = 0, && i = m+1, m+2, \dots, m+\ell \end{aligned} \right}$ 

$$ X = \left{ x \in \mathbb{R}^n ,\middle|, \begin{cases} c_i(x) \leq 0, & i = 1, 2, \dots, m \ c_i(x) = 0, & i = m+1, \dots, m+\ell \end{cases} \right} $$ $$ X = \Bigg{ x \in \mathbb{R}^n ,\Bigg|, \begin{cases} c_i(x) \leq 0, & i = 1, 2, \dots, m \ c_i(x) = 0, & i = m+1, \dots, m+\ell \end{cases} \Bigg} $$

$$ X = \left{ x \in \mathbb{R}^n ,\middle|, \begin{cases} c_i(x) \leq 0, & i = 1, 2, \dots, m \ c_i(x) = 0, & i = m+1, \dots, m+\ell \end{cases} \vphantom{\begin{cases} \end{cases}} \right} $$

$$ X = \left{ x \in \mathbb{R}^n ,\middle|, \begin{aligned} &c_i(x) \leq 0, && i = 1, 2, \dots, m \ &c_i(x) = 0, && i = m+1, \dots, m+\ell \end{aligned} \right} $$

$$ X = \left\lbrace x \in \mathbb{R}^n ,\middle|, \begin{aligned} &c_i(x) \leq 0, && i = 1, 2, \dots, m \ &c_i(x) = 0, && i = m+1, \dots, m+\ell \end{aligned} \right\rbrace $$
```

但是都没有效果（其实第五个可以，但是还需要改一点）：

![00-b大括号在docsify出现问题](images\00-b大括号在docsify出现问题.png)

目前推测为docsify的**MathJax**在配置时误解了`\{`的含义，而且不能正确配对`\left`和`\right`

目前发现可行的解决方案是

1. 使用``包裹在行内代码或者行外代码外，效果如下：
   `$X = \left\{ x \in \mathbb{R}^n \ \middle| \ \begin{aligned}&c_i(x) \leq 0, && i = 1,2,\dots, m \\&c_i(x) = 0, && i = m+1, m+2, \dots, m+\ell\end{aligned}\right\}$`，勉强能看，颜色还不错

2. 使用`\lbrace`和`\rbrace`代替{}包裹

   ```markdown
    X = \left\lbrace x \in \mathbb{R}^n \ \middle|\  
   \begin{aligned}
   &c_i(x) \leq 0, && i = 1, 2, \dots, m \newline
   &c_i(x) = 0,    && i = m+1,m+2， \dots, m+\ell
   \end{aligned}
   \right\rbrace
   ```

   效果如下：$ X = \left\lbrace x \in \mathbb{R}^n \ \middle|\  
   \begin{aligned}
   &c_i(x) \leq 0, && i = 1, 2, \dots, m \newline
   &c_i(x) = 0,    && i = m+1,m+2， \dots, m+\ell
   \end{aligned}
   \right\rbrace$



