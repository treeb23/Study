# 線形代数
## 目次

1. [ベクトルの定義](#anchor1)
2. [n次元ベクトル](#anchor2)

数式サンプル
```math
M = \begin{bmatrix}
\frac{5}{6} & \frac{1}{6} & 0           \\
\frac{5}{6} & 0           & \frac{1}{6} \\
0           & \frac{5}{6} & \frac{1}{6}
\end{bmatrix}
```


<a id="anchor1"></a>

## 1. ベクトルの定義

### ベクトルの表し方

```math
a = \begin{bmatrix}
       a_1  \\[0.3em]
       a_2       
     \end{bmatrix}
```
$\vec{a}$のように $\to$は使わず、アルファベットの太文字で表す。

数を縦に並べる。 $a_1$を第1成分, $a_2$を第2成分という。


### 和,差,スカラー倍

```math
a = \begin{bmatrix} a_1\\a_2 \end{bmatrix} \pm \begin{bmatrix} b_1\\b_2 \end{bmatrix} 
= \begin{bmatrix} a_1 \pm b_1\\a_2 \pm b_2 \end{bmatrix}
```
```math
c\begin{bmatrix} a_1\\a_2 \end{bmatrix} 
= \begin{bmatrix} c a_1 \\c a_2 \end{bmatrix}
```

(例)
```math
3 \begin{bmatrix} 1\\2 \end{bmatrix} - \begin{bmatrix} 5\\6 \end{bmatrix} 
= \begin{bmatrix} 3\\6 \end{bmatrix} - \begin{bmatrix} 5\\6 \end{bmatrix}
= \begin{bmatrix} -2\\0 \end{bmatrix}
```

#### (例題)
```math
a = \begin{bmatrix} 2\\1 \end{bmatrix},
b = \begin{bmatrix} 3\\2 \end{bmatrix},
c = \begin{bmatrix} -1\\3 \end{bmatrix}
```
について、(1)~(3)を求める。
```math
\begin{eqnarray}
&(1)& 3a+2b \\ &(2)& -2a+3b-c \\ &(3)& 3(a-2b)-2c
\end{eqnarray}
```

#### (解答)
```math
\begin{eqnarray}
&(1)& 3a+2b = \begin{bmatrix} 12\\7 \end{bmatrix} \\
&(2)& -2a+3b-c = \begin{bmatrix} 6\\1 \end{bmatrix} \\
&(3)& 3(a-2b)-2c = \begin{bmatrix} -10\\-15 \end{bmatrix} 
\end{eqnarray}
```

<a id="anchor2"></a>

## 2. n次元ベクトル

### n次元ベクトルとは

実数を(縦に)n個並べたもの
```math
a = \begin{bmatrix} a_1 \\ a_2 \\ \vdots \\ a_n \end{bmatrix}
```
をn次元ベクトルと呼ぶ。 $a_1$が第1成分, $a_2$が第2成分,…である。



![img](img/orange.png)
