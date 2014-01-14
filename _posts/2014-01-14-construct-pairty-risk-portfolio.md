---
layout: post
title: 说说风险均摊投资组合的构建方法
comments: true
categories:
- life
tags:
- 风险均摊
- 投资组合
- R
---


### 引子

我们在筛选出备选股票之后，要解决的另外一个问题是确定备选股票在投资组合中的权重向量：

$$ w=\( w_1,w_2,...,w_n \) $$

其中，$ 0<w_{i}< 1,i=1,2,...,n $。

权重的可选集是个无限集合，我们要选取其中最优的一个作为目标权重，怎么判断最优与否？那得首先确定一个判断最优与否的方法或者说函数。常用的方法是收益-风险法，即如果一个权重能够使投资组合的收益最大，风险最小，那么它就是好的。如果用标准差来刻画风险，那么，就有评价函数:

$$ U(R,\sigma) $$

其中，$ \frac{\partial U(\cdot )}{\partial R} > 0 $，$ \frac{\partial U(\cdot )}{\partial \sigma} < 0 $。

$ U(\cdot) $最简单的形式如下：

$$
U_p = aR_{p} + b \sigma \_{p}
$$

其中，$ a > 0 $，$ b < 0 $；$ R_{p} $是组合的收益率，$ \sigma \_{p} $是组合的标准差。显然：

$$ R_{p} = w'R $$

$$
\sigma \_p = w'Rw
$$

其中，$ R=(R_1,R_2,...,R_n) $是组合中各证券的收益率。

把$ R_{p} $和$\sigma \_p $带入$U_p$，解出令$U_p$最小的$ w $即可。

当然，也有其它理念，比如，下面要说的风险均摊。它是指我们要选出来这样一个权重，这个权重确定的投资组合中，各个证券的风险占证券投资总的风险的比例是相同的。

### 风险均摊的理论基础

由前面的公式可知：

$$
\sigma \_{p}=
$$

变形得到：



\begin{bmatrix}
w_1&w_2&..&w_n
\end{bmatrix}
\begin{bmatrix}
 c_{11} &c_{12} &.. &c_{1n} \\ 
 c_{21} &c_{22} &.. &c_{2n} \\ 
 ..     &..     &.. &..     \\ 
 c_{n1} &c_{n2} &.. &c_{nn} 
\end{bmatrix}
\begin{bmatrix}
w_1\\ 
w_2\\ 
.. \\
w_n\\ 
\end{bmatrix}

$$

\sigma \_{p}=\begin{bmatrix}
wc_{\cdot 1} & wc_{\cdot 2} &..  & wc_{\cdot j}
\end{bmatrix}\begin{bmatrix}
w_1\\ 
w_2\\ 
.\\
w_n\\ 
\end{bmatrix}

$$

