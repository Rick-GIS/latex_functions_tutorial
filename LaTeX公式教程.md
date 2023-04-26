<head>
    <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
    <script type="text/x-mathjax-config">
        MathJax.Hub.Config({
            tex2jax: {
            skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
            inlineMath: [['$','$']]
            }
        });
    </script>
</head>
# LaTeX公式基本教程

> 本教程涉及的内容仅数学公式，不涉及整个LaTeX排版系统的用法。
>
> 涉及的公式不超过<b>数学一</b>范围。
>
> 部分Markdown编辑器不支持LaTeX渲染，此文档应使用支持LaTeX渲染的编辑器打开才可以显示公式效果。

## 数学模式

在LaTeX数学模式中，公式有两种形式——行内公式和行间公式。前者公式嵌入在行内，适用于简单短小的公式；后者居中独占一行，适用于比较长或重要的公式。公式中的空格均会被忽略，可以使用命令\quad或\qquad实现空格。

在行间公式中，命令\tag{n}可以进行手动编号。

### 行内公式

在两个美元符号$之间打出公式即可，VS Code和Jupyter Notebook可以直接使用行内公式。

部分Markdown编辑器不支持行内公式，还有部分（如Typora）需要在设置里打开，具体的设置方式参见实际使用的编辑器说明。

```latex
这是一个行内公式：$ f(x)=a+b $
```

这是一个行内公式：$ f(x) = a + b $

### 行间公式

在一对美元符号$$之间打出公式即可。

Markdown使用$$渲染公式。

```latex
$$ f(x)=a+b $$
```

$$
f(x) = a + b
$$

### 右侧编号

\tag{n}命令，n为式子编号。

```latex
$$ f(x)=a+b\tag{1.1}$$
```

$$
f(x) = a + b \tag{1.1}
$$

## 数学结构

### 简单运算

拉丁字母、阿拉伯数字和 + - * / = 运算符均可以直接输入获得。

\pm为加减（正负）±

\cdot表示乘法的圆点，\times表示乘号×，\div表示÷

\cdots表示省略号（连续的3个点···）

\neq或\ne表示不等号≠

\equiv表示恒等于

\bmod表示取模（取余）

\approx表示约等于≈

```latex
$$ x+2-3*4/6=4/y+x \cdot y $$
```

$$
x+2-3*4/6=4/y+x\cdot y
$$

```latex
$$ 1+2+3+\cdots+100=5050 $$
```

$$
1+2+3+\cdots+100=5050
$$



```latex
$$ 
0 \neq 1 \quad
x \equiv x \quad
1=9 \bmod 2 \quad
$$
```

$$
0 \neq 1 \quad
x \equiv x \quad
1 = 9 \bmod 2
$$

### 上下标

^为上标

_为下标

'为导数，几个英文单引号就是几阶导数

- 排列数公式[^注]

```latex
$$ \mathrm{A}_n^r=\frac{n!}{(n-r)!} $$
```

$$
\mathrm{A}_n^r=\frac{n!}{(n-r)!}
$$

[^注]:计算器上和部分教科书写作P而不是A。

- 组合数公式
```latex
$$ \mathrm{C}_n^r=\frac{n!}{r!(n-r)!} $$
```

$$
\mathrm{C}_n^r=\frac{n!}{r!(n-r)!}
$$



偏导数符号∂用\part{}或\partial{}表示

Nabla算子符号∇用\nabla表示

- 二元函数的梯度

```latex
$$
\mathbf{grad}f(x,y)=\frac{\part{f}}{\part{x}}\vec{i}+\frac{\part{f}}{\part{y}}\vec{j}=\nabla f
$$
```

$$
\mathbf{grad}f(x,y)=\frac{\part{f}}{\part{x}}\vec{i}+\frac{\part{f}}{\part{y}}\vec{j}=\nabla f
$$



如果上下标不止一个字符，应使用大括号括起来。

```latex
$$ a_{ij}^2 + b_{2}^{3} = x^t + y' + x''_{12} $$
```

$$
a_{ij}^2 + b_{2}^{3} = x^t + y' + x''_{12}
$$

### 根号和分式

\sqrt{expression}为平方根（根号）

\sqrt[n]{expression}为n次方根（n次根号）

\frac{numerator}{denominator}为分式，前为分子，后为分母

```latex
$$ \sqrt{x} + \sqrt{x^2+\sqrt{y}} = \sqrt[3]{k_i} - \frac{x}{m} $$
```

$$
\sqrt{x} + \sqrt{x^2+\sqrt{y}} = \sqrt[3]{k_i} - \frac{x}{m}
$$

### 上下水平线

\overline{}为上水平线

\underline{}为下水平线

```latex
$$ \overline{x+y} \qquad \underline{x+y} $$
```

$$
\overline{x+y} \qquad \underline{x+y}
$$

### 上下大括号

\overbrace{}为上大括号

\underbrace{}为下大括号

上下标符号^和_可以使用在这里。

```latex
$$ \overbrace{1+2+3+\cdots+n}^{n} \quad \underbrace{a+b+c+\cdots+z}_{26}$$
```

$$
\overbrace{1+2+3+\cdots+n}^{n} \quad \underbrace{a+b+c+\cdots+z}_{26}
$$

### 向量

\vec{}表示向量，常用于单个小写字母

\overrightarrow{}表示箭头向右的向量

\overleftarrow{}表示箭头向左的向量

```latex
$$ \vec{a} + \overrightarrow{AB} + \overleftarrow{CD} $$
```

$$
\vec{a} + \overrightarrow{AB} + \overleftarrow{CD}
$$

### 左侧有大符号的运算（积分、极限、求和、乘积）

\lim{}为极限符号lim

\sum{}为求和SIGMA

\prod{}为乘积PI

\int{}为积分符号**∫**，\iint{}为二重积分**∬**，\iiint{}为三重积分**∭**，支持到四重积分\iiiint{}

\oint{}为闭合曲线积分**∮**，\oiint{}为闭合曲面积分**∯**，支持到闭合体积分\oiiint{}∰


#### 极限lim

下标中的箭头用\to

无穷大用\infty

正负无穷直接在\infty前加+/-即可

- 两个重要极限

```latex
\lim_{x\to0}\frac{\sin x}{x}=1 \\
\lim_{x\to\infty}(1+\frac{1}{x})^x=\mathrm{e} 
```

$$
\lim_{x\to0}\frac{\sin x}{x}=1 \\ \lim_{x\to\infty}(1+\frac{1}{x})^x=\mathrm{e}
$$



#### 求和∑（SIGMA）

- p级数（超调和级数）

```latex
$$ \sum_{n=1}^{\infty}\frac{1}{n^p}=1+\frac{1}{2^p}+\frac{1}{3^p}+\cdots+\frac{1}{n^p}+\cdots $$
```

$$
\sum_{n=1}^{\infty}\frac{1}{n^p}=1+\frac{1}{2^p}+\frac{1}{3^p}+\cdots+\frac{1}{n^p}+\cdots
$$

- e<sup>x</sup>在x=0处泰勒展开

```latex
e^x=\sum^{\infty}_{n=0}\frac{x^n}{n!}=1+\frac{x}{1!}+\frac{x^2}{2!}+\frac{x^3}{3!}+\cdots+\frac{x^n}{n!}+\cdots
```

$$
e^x=\sum^{\infty}_{n=0}\frac{x^n}{n!}=1+\frac{x}{1!}+\frac{x^2}{2!}+\frac{x^3}{3!}+\cdots+\frac{x^n}{n!}+\cdots
$$



#### 乘积∏（PI）

- n阶范德蒙行列式的结果

```latex
$$ \prod_{1 \le j \lt i \le n}(x_i-x_j) $$ 
```

$$
\prod_{1\le j\lt i\le n}(x_i-x_j)
$$

#### 积分∫

^{}定义积分上限，_{}定义积分下限

\mathrm{}用于将数学斜体变成正体（罗马体），微分符号d不是变量，不使用斜体。

积分符号的运用见以下例子***等号左端***的表达方式：

- 定积分定义式

```latex
$$ 
\int_{a}^{b}f(x)\mathrm{d}x
=
\lim_{n\to+\infty}\sum^{n}_{i=1}f[a+\frac{i}{n}(b-a)]\frac{b-a}{n} 
$$
```

$$
\int_{a}^{b}f(x)\mathrm{d}x=\lim_{n\to+\infty}\sum^{n}_{i=1}f[a+\frac{i}{n}(b-a)]\frac{b-a}{n}
$$

- 二重积分极坐标

```latex
$$ 
\iint_{D}f(\rho\cos\theta,\rho\sin\theta)\rho\mathrm{d}\rho\mathrm{d}\theta
=
\int_\alpha^\beta\mathrm{d}\theta\int_{\phi_1(\theta)}^{\phi_2(\theta)}f(\rho\cos\theta,\rho\sin\theta)\rho\mathrm{d}\rho
$$
```

$$
\iint_{D}f(\rho\cos\theta,\rho\sin\theta)\rho\mathrm{d}\rho\mathrm{d}\theta=\int_\alpha^\beta\mathrm{d}\theta\int_{\phi_1(\theta)}^{\phi_2(\theta)}f(\rho\cos\theta,\rho\sin\theta)\rho\mathrm{d}\rho
$$

- 三重积分球面坐标（仅数学一）

```latex
$$ 
\iiint_{\Omega}F(r,\phi,\theta)r^2\sin\phi\mathrm{d}r\mathrm{d}\phi\mathrm{d}\theta
=
\int_{\theta_1}^{\theta_2}\mathrm{d}\theta\int_{\phi_1}^{\phi_2}\mathrm{d}\phi\int_{r_1(\phi,\theta)}^{r_2(\phi,\theta)}F(r,\phi,\theta)r^2\sin\phi\mathrm{d}r 
$$
```

$$
\iiint_{\Omega}F(r,\phi,\theta)r^2\sin\phi\mathrm{d}r\mathrm{d}\phi\mathrm{d}\theta
=
\int_{\theta_1}^{\theta_2}\mathrm{d}\theta\int_{\phi_1}^{\phi_2}\mathrm{d}\phi\int_{r_1(\phi,\theta)}^{r_2(\phi,\theta)}F(r,\phi,\theta)r^2\sin\phi\mathrm{d}r
$$

- 格林公式（仅数学一）

```latex
$$ 
\oint_LP\mathrm{d}x+Q\mathrm{d}y
=
\iint_D(\frac{\part{Q}}{\part{x}}-\frac{\part{P}}{\part{y}})\mathrm{d}x\mathrm{d}y
$$
```

$$
\oint_LP\mathrm{d}x+Q\mathrm{d}y=\iint_D(\frac{\part{Q}}{\part{x}}-\frac{\part{P}}{\part{y}})\mathrm{d}x\mathrm{d}y
$$

- 高斯公式（仅数学一）

```latex
$$ 
\oiint_{\part{\Omega}}P\mathrm{d}y\mathrm{d}z+Q\mathrm{d}z\mathrm{d}x+R\mathrm{d}x\mathrm{d}y
=
\iiint_{\Omega}(\frac{\part{P}}{\part{x}}+\frac{\part{Q}}{\part{y}}+\frac{\part{R}}{\part{z}})\mathrm{d}x\mathrm{d}y\mathrm{d}z
$$
```

$$
\oiint_{\part{\Omega}}P\mathrm{d}y\mathrm{d}z+Q\mathrm{d}z\mathrm{d}x+R\mathrm{d}x\mathrm{d}y=\iiint_{\Omega}(\frac{\part{P}}{\part{x}}+\frac{\part{Q}}{\part{y}}+\frac{\part{R}}{\part{z}})\mathrm{d}x\mathrm{d}y\mathrm{d}z
$$

### 省略号

\ldots点位于基线上（和逗号等高并排）

\cdots点设置为居中

\vdots使其垂直（常用于矩阵）

\ddots对角线排列（常用于矩阵）

- 斐波那契数列

```latex
\{a_n\}=1,1,2,3,5,8,13,21,34,\ldots,\frac{\sqrt{5}}{5[(\frac{1}{\phi})^n-(-\phi)^n]} 
(\phi=\frac{1-\sqrt{5}}{2}\approx0.618) 
```

$$
\{a_n\}=1,1,2,3,5,8,13,21,34,\ldots,\frac{\sqrt{5}}{5[(\frac{1}{\phi})^n-(-\phi)^n]}\\(\phi=\frac{\sqrt{5}-1}{2}\approx0.618)
$$

- e的泰勒展开式（Peano余项）
```latex
e^x=1+x+\frac{x^2}{2!}+\cdots+\frac{x^n}{n!}+\omicron(x^n)
```

$$
e^x=1+x+\frac{x^2}{2!}+\cdots+\frac{x^n}{n!}+\omicron(x^n)
$$



### 估计值、平均值、扰动符号

\hat{}为估计值符号（变量上的脱字符^）

\bar{}为平均值符号（变量上的横线-）

\tlide{}为变量加扰动后的值符号（变量上的波浪线~）

```latex
\hat{x} \quad \bar{x} \quad \tilde{x}
```

$$
\hat{x} \quad \bar{x} \quad \tilde{x}
$$

LaTeX不支持直接使用波浪线符号，亦不支持其转义，应使用\sim：

```latex
X\sim B(5,0.3)
```

$$
X\sim B(5,0.3)
$$



## 矩阵

### 括号

矩阵需要用\begin{type}\end{type}包裹，type为括号类型

type可以为matrix（无括号）、bmatrix（中括号）、Bmatrix（大括号）、vmatrix（单竖线，行列式）、Vmatrix（双竖线）、pmatrix（圆括号）

&分隔列，\\分隔行

- 范德蒙行列式

```latex
\boldsymbol{\mathbf{V}} = 
\begin{vmatrix}1 & x_1 & x_1^2 & \dots & x_1^{m-1} \\ 
1 & x_2 & x_2^2 & \dots & x_2^{m-1} \\ 
1 & x_3 & x_3^2 & \dots & x_3^{m-1} \\ 
\vdots & \vdots & \vdots & \ddots & \vdots \\ 
1 & x_n & x_n^2 & \dots & x_n^{m-1}
\end{vmatrix}
=\prod_{1\le j\lt i\le n}(x_i-x_j)
```

$$
\boldsymbol{\mathbf{V}} = 
\begin{vmatrix}1 & x_1 & x_1^2 & \dots & x_1^{m-1} \\ 
1 & x_2 & x_2^2 & \dots & x_2^{m-1} \\ 
1 & x_3 & x_3^2 & \dots & x_3^{m-1} \\ 
\vdots & \vdots & \vdots & \ddots & \vdots \\ 
1 & x_n & x_n^2 & \dots & x_n^{m-1}
\end{vmatrix}
=\prod_{1\le j\lt i\le n}(x_i-x_j)
$$

### 分块矩阵

\begin{}\end{}结构里可以嵌套

如有分块元素全为某个数的部分，用\large NUMBER即可表示整个区域

```latex
\mathbf{diag}(1,1,1,1)=
\begin{bmatrix}
\begin{matrix}1 & 0\\ 0 & 1 \end{matrix} & \Large 0\\
\Large 0 & \begin{matrix}1 & 0 \\ 0 & 1\end{matrix}
\end{bmatrix}
```

$$
\mathbf{diag}(1,1,1,1)=
\begin{bmatrix}
\begin{matrix}1&0\\0&1\end{matrix}& \Large 0\\
\Large 0 &\begin{matrix}1&0\\0&1\end{matrix}
\end{bmatrix}
$$

### 矩阵与其他结合
- 斯托克斯公式行列式（仅数学一）

> 以下“行列式”表达方式***仅出于便于记忆和笔算目的，其数学意义并不正确***。

```latex
\oint_{\Gamma}P\mathrm{d}x+Q\mathrm{d}y+R\mathrm{d}z
=
\iint_{\Sigma}
\begin{vmatrix}
\mathrm{d}y\mathrm{d}z & \mathrm{d}z\mathrm{d}x & \mathrm{d}x\mathrm{d}y \\
\frac{\part}{\part{x}} & \frac{\part}{\part{y}} & \frac{\part}{\part{z}} \\
P & Q & R
\end{vmatrix}
```

$$
\oint_{\Gamma}P\mathrm{d}x+Q\mathrm{d}y+R\mathrm{d}z=\iint_{\Sigma}\begin{vmatrix}\mathrm{d}y\mathrm{d}z&\mathrm{d}z\mathrm{d}x&\mathrm{d}x\mathrm{d}y\\\frac{\part}{\part{x}}&\frac{\part}{\part{y}}&\frac{\part}{\part{z}}\\P&Q&R\end{vmatrix}
$$

```latex
\oint_{\Gamma}P\mathrm{d}x+Q\mathrm{d}y+R\mathrm{d}z
=
\iint_{\Sigma}
\begin{vmatrix}
\cos{\alpha} & \cos{\beta} & \cos{\gamma} \\
\frac{\part}{\part{x}} & \frac{\part}{\part{y}} & \frac{\part}{\part{z}} \\
P & Q & R
\end{vmatrix}
\mathrm{d}s
```

$$
\oint_{\Gamma}P\mathrm{d}x+Q\mathrm{d}y+R\mathrm{d}z=\iint_{\Sigma}\begin{vmatrix}\cos{\alpha}&\cos{\beta}&\cos{\gamma}\\\frac{\part}{\part{x}}&\frac{\part}{\part{y}}&\frac{\part}{\part{z}}\\P&Q&R\end{vmatrix}\mathrm{d}s
$$



## 希腊字母

在LaTeX中通过反斜杠\加上其字母读音实现，将读音首字母大写即可输入其大写形式，详见下表：

```
希腊字母表
Α α：Alpha
Β β：Beta
Γ γ：Gamma
Δ δ：Delte
Ε ε：Epsilon
Ζ ζ：Zeta
Ε η：Eta
Θ θ：Theta
Ι ι：Iota
Κ κ：Kappa
Λ λ：Lambda
Μ μ：Mu
Ν ν：Nu
Ξ ξ：Xi
Ο ο：Omicron
∏ π：Pi
Ρ ρ：Rho
∑ σ：Sigma
Τ τ：Tau
Υ υ：Upsilon
Φ φ：Phi
Χ χ：Chi
Ψ ψ：Psi
Ω ω：Omega
```

- 一维正态分布概率密度
```latex
$$ 
f(x)=\frac{1}{\sqrt{2\pi}\sigma}\mathrm{e}^{-\frac{(x-\mu)^2}{2\sigma^2}}
$$
```

$$
f(x)=\frac{1}{\sqrt{2\pi}\sigma}\mathrm{e}^{-\frac{(x-\mu)^2}{2\sigma^2}}
$$



## 多行公式

### 公式组合

公式组合使用\begin{case}\end{case}包裹

&分隔公式与条件

- 修正线性单元（ReLU函数）

```latex
f(x) = \begin{cases}
x, & x\gt0 \\
0,& x\leq0 \\
\end{cases}
```

$$
f(x) = \begin{cases}
x, & x\gt0 \\
0,& x\leq0 \\
\end{cases}
$$

### 公式拆分

使用\begin{split}\end{split}包裹

&=对齐等号

- 倍角公式（余弦）

```latex
\begin{split}
\cos 2x &= \cos^2x - \sin^2x \\
&=2\cos^2x-1
\end{split}
```

$$
\begin{split}
\cos 2x &= \cos^2x - \sin^2x \\
&=2\cos^2x-1
\end{split}
$$

