# 線形代数
## 目次

1. [ベクトルの定義](#anchor1)
2. [n次元ベクトル](#anchor2)
3. [内積](#anchor3)
4. [外積](#anchor4)
5. [行列の定義と計算](#anchor5)
6. [行列の積](#anchor6)




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

### 和,差,スカラー倍

和と差、スカラー倍は各成分ごとに行われる。

```math
\begin{bmatrix} a_1 \\ a_2 \\ \vdots \\ a_n \end{bmatrix}
\pm
\begin{bmatrix} b_1 \\ b_2 \\ \vdots \\ b_n \end{bmatrix}
=
\begin{bmatrix} a_1 \pm b_1 \\ a_2 \pm b_2 \\ \vdots \\ a_n \pm b_n \end{bmatrix}
```
```math
\begin{bmatrix} a_1 \\ a_2 \\ \vdots \\ a_n \end{bmatrix}
=
\begin{bmatrix} c a_1 \\ c a_2 \\ \vdots \\ c a_n \end{bmatrix}
```
(例)
```math
3 \begin{bmatrix} 1 \\ 2 \\ 3 \\ 4 \end{bmatrix}
-
\begin{bmatrix} 5 \\ 6 \\ 7 \\ 8 \end{bmatrix}
=
\begin{bmatrix} 3 \\ 6 \\ 9 \\ 12 \end{bmatrix}
-
\begin{bmatrix} 5 \\ 6 \\ 7 \\ 8 \end{bmatrix}
=
\begin{bmatrix} -2 \\ 0 \\ 2 \\ 4 \end{bmatrix}
```

#### (例題)
```math
a = \begin{bmatrix} 2 \\ 1 \\ -4 \\ 3 \end{bmatrix},
b = \begin{bmatrix} 3 \\ 2 \\ -2 \\ 0 \end{bmatrix},
c = \begin{bmatrix} -1 \\ 3 \\ 4 \\ -1 \end{bmatrix}
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
&(1)& 3a+2b = \begin{bmatrix} 12 \\ 7 \\ -16 \\ 9 \end{bmatrix} \\
&(2)& -2a+3b-c = \begin{bmatrix} 6 \\ 1 \\ -2 \\ -5 \end{bmatrix} \\
&(3)& 3(a-2b)-2c = \begin{bmatrix} -10 \\ -15 \\ -8 \\ 11 \end{bmatrix}
\end{eqnarray}
```




<a id="anchor3"></a>

## 3. 内積

### n次元ベクトルの内積

```math
a = \begin{bmatrix} a_1 \\ a_2 \\ \vdots \\ a_n \end{bmatrix}
,
b = \begin{bmatrix} b_1 \\ b_2 \\ \vdots \\ b_n \end{bmatrix}
```
の内積 $a \cdot b$は次のように定義される。

```math
a \cdot b
=
\begin{bmatrix} a_1 \\ a_2 \\ \vdots \\ a_n \end{bmatrix}
\begin{bmatrix} b_1 \\ b_2 \\ \vdots \\ b_n \end{bmatrix}
=
a_1 b_1 + a_2 b_2 + \dots + a_n b_n
```

### 直交と長さ

$a \cdot b = 0$ のとき、 $a$と $b$は直交しているという。

$a$の長さは

```math
|a| = \sqrt{a \cdot a} = \sqrt{{a_1}^2 + {a_2}^2 + \dots + {a_n}^2}
```

### 内積の性質

```math
\begin{eqnarray}
&(1)& a \cdot b = b \cdot a \\
&(2)& a \cdot (b + c) = a \cdot b + a \cdot c \\
&(3)& \mathsf{定数xに対し, } (x a) \cdot b = x(a \cdot b)
\end{eqnarray}
```

(例)
```math
\begin{bmatrix} 1 \\ 2 \\ 3 \\ 4 \end{bmatrix}
-
\begin{bmatrix} 5 \\ 6 \\ 7 \\ 8 \end{bmatrix}
=
1 \cdot 5 + 2 \cdot 6 + 3 \cdot 7 + 4 \cdot 8 = 70
```

#### (例題)
```math
a = \begin{bmatrix} 1 \\ 2 \\ 3 \\ 4 \end{bmatrix},
b = \begin{bmatrix} -3 \\ 2 \\ 0 \\ -1 \end{bmatrix}
```
について、(1)~(4)を求める。
```math
\begin{eqnarray}
&(1)& a \cdot b \\ &(2)& |a| \\ &(3)& |b| \\ &(4)& (2a + b) \cdot (a - 2b)
\end{eqnarray}
```

#### (解答)
(1)
```math
\begin{eqnarray}
a \cdot b &=& \begin{bmatrix} 1 \\ 2 \\ 3 \\ 4 \end{bmatrix} \cdot
\begin{bmatrix} -3 \\ 2 \\ 0 \\ -1 \end{bmatrix} \\
&=&
1 \cdot (-3) + 2 \cdot 2 + 3 \cdot 0 + 4 \cdot + (-1) \\
&=& -3
\end{eqnarray}
```
(2)
```math
|a| = \sqrt{1^2 + 2^2 + 3^2 + 4^2} \\
\sqrt{30}
```
(3)
```math
|b| = \sqrt{(-3)^2 + 2^2 + 0^2 + (-1)^2} \\
\sqrt{14}
```
(4)
```math
\begin{eqnarray}
(2a + b) \cdot (a - 2b) &=& 2 |a|^2 - 3a \cdot b - 2 |b|^2 \\
&=& 2 \cdot 30 - 3 \cdot (-3) - 2 \cdot 14 \\
&=& 41
\end{eqnarray}
```



<a id="anchor4"></a>

## 4. 外積

### 3次元ベクトルの外積

```math
a = \begin{bmatrix} a_1 \\ a_2 \\ a_3 \end{bmatrix}
,
b = \begin{bmatrix} b_1 \\ b_2 \\ b_3 \end{bmatrix}
```
3次元ベクトル $a$と $b$の外積は
```math
a \times b = 
\begin{bmatrix} 
a_2 b_3 - b_2 a_3 \\ a_3 b_1 - b_3 a_1 \\ a_1 b_2 - b_1 a_2 
\end{bmatrix}
```

### 外積の性質

```math
\begin{eqnarray}
&(1)& a \times b = -b \times a \\
&(2)& a \times (b + c) = a \times b + a \times c \\
&(3)& (xa) \times b = a \times (xb) = x(a \times b) \\
&(4)& a \times b \mathsf{と, } a,b \mathsf{は直交である。} (a \times b) \cdot a = (a \times b) \cdot b = 0
\end{eqnarray}
```

(例)
```math
a = \begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix} \\
b = \begin{bmatrix} 4 \\ 5 \\ 6 \end{bmatrix}
```
に対し、 $a \times b$を求める。

```math
a \times b =
\begin{bmatrix} 
2 \cdot 6 - 5 \cdot 3 \\ 3 \cdot 4 - 6 \cdot 1 \\ 1 \cdot 5 - 4 \cdot 2 
\end{bmatrix} =
\begin{bmatrix} 
-3 \\ 6 \\ -3
\end{bmatrix}
```

#### (例題)
```math
a = \begin{bmatrix} 5 \\ 1 \\ -3 \end{bmatrix},
b = \begin{bmatrix} -2 \\ 3 \\ 4 \end{bmatrix}
```
について、 $a \times b$を求める。また、 $a \times b$と $a,b$が直交することを確かめる。

#### (解答)

$a \times b$を求める。
```math
\begin{eqnarray}
a \times b &=& 
\begin{bmatrix} 5 \\ 1 \\ -3 \end{bmatrix} \times 
\begin{bmatrix} -2 \\ 3 \\ 4 \end{bmatrix} \\
&=& \begin{bmatrix} 
1 \cdot 4 - 3 \cdot (-3) \\ (-3) \cdot (-2) - 4 \cdot 5 \\ 5 \cdot 3 - (-2) \cdot 1 
\end{bmatrix}
= \begin{bmatrix} 
13 \\ -14 \\ 17 
\end{bmatrix}
\end{eqnarray}
```
$a \times b$と $a,b$が直交することは $(a \times b) \cdot a = 0$と $(a \times b) \cdot a = 0$で確かめられる。

```math
\begin{eqnarray}
(a \times b) \cdot a &=& \begin{bmatrix} 13 \\ -14 \\ 17 \end{bmatrix} 
\cdot \begin{bmatrix} 5 \\ 1 \\ -3 \end{bmatrix} \\
&=& 13 \cdot 5 + (-14) \cdot 1 + 17 \cdot (-3) \\
&=& 65 - 14 - 51 = 0
\end{eqnarray}
```
```math
\begin{eqnarray}
(a \times b) \cdot b &=& \begin{bmatrix} 13 \\ -14 \\ 17 \end{bmatrix} 
\cdot \begin{bmatrix} -2 \\ 3 \\ 4 \end{bmatrix} \\
&=& 13 \cdot (-2) + (-14) \cdot 3 + 17 \cdot 4 \\
&=& -26 - 42 - 68 = 0
\end{eqnarray}
```



<a id="anchor5"></a>

## 5. 行列の定義と計算

### 行列

数を縦にm個、横にn個並べたものを $(m \times n)$行列という。
```math
A = \begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots  & \vdots  & \ddots & \vdots  \\
a_{m1} & a_{m2} & \cdots & a_{mn} 
\end{bmatrix}
```
m次元ベクトルは $m \times 1$行列である。

行列の横一行を行といい、縦一列を列という。i行j列nにある数 $a_{ij}$を行列の $(i,j)$成分という。

### 和,差,スカラー倍

行列の和,差,スカラー倍は成分ごとに求める。
```math
\begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots  & \vdots  & \ddots & \vdots  \\
a_{m1} & a_{m2} & \cdots & a_{mn} 
\end{bmatrix}
+ 
\begin{bmatrix}
b_{11} & b_{12} & \cdots & b_{1n} \\
b_{21} & b_{22} & \cdots & b_{2n} \\
\vdots  & \vdots  & \ddots & \vdots  \\
b_{m1} & b_{m2} & \cdots & b_{mn} 
\end{bmatrix} \\
=
\begin{bmatrix}
a_{11} + b_{11} & a_{12} + b_{12} & \cdots & a_{1n} +b_{1n} \\
a_{21} + b_{21} & a_{22} + b_{22} & \cdots & a_{2n} +b_{2n} \\
\vdots  & \vdots  & \ddots & \vdots  \\
a_{m1} + b_{m1} & a_{m2} + b_{m2} & \cdots & a_{mn} +b_{mn} 
\end{bmatrix}
```

(例)
```math
\begin{eqnarray}
&&3 \begin{bmatrix}
1 & 0 & 2 \\
-2 & 1 & -3
\end{bmatrix}
-
\begin{bmatrix}
2 & -2 & 3 \\
-5 & 3 & 1
\end{bmatrix} \\
&&=
\begin{bmatrix}
3 & 0 & 6 \\
-6 & 3 & -9
\end{bmatrix}
-
\begin{bmatrix}
2 & -2 & 3 \\
-5 & 3 & 1
\end{bmatrix} \\
&&=
\begin{bmatrix}
1 & 2 & 3 \\
-1 & 0 & -10
\end{bmatrix}
\end{eqnarray}
```

#### (例題)
```math
A = \begin{bmatrix}
1 & 0 & 3 \\
-1 & 4 & 2 
\end{bmatrix},
B = \begin{bmatrix}
2 & 3 & 1 \\
-1 & -2 & -3 
\end{bmatrix}
```
について、 
```math
\begin{eqnarray}
&(1)& A + B \\ &(2)& 3A \\ &(3)& 4A - 3B
\end{eqnarray}
```
を求める。

#### (解答)

(1)
```math
\begin{eqnarray}
A + B &=& \begin{bmatrix}
1 & 0 & 3 \\
-1 & 4 & 2 
\end{bmatrix} + \begin{bmatrix}
2 & 3 & 1 \\
-1 & -2 & -3 
\end{bmatrix} \\
&=&
\begin{bmatrix}
3 & 3 & 4 \\
-2 & 2 & -1 
\end{bmatrix}
\end{eqnarray}
```
(2)
```math
\begin{eqnarray}
3A &=& 3 \begin{bmatrix}
1 & 0 & 3 \\
-1 & 4 & 2 
\end{bmatrix} \\
&=&
\begin{bmatrix}
3 & 0 & 9 \\
-3 & 12 & 6 
\end{bmatrix}
\end{eqnarray}
```
(3)
```math
\begin{eqnarray}
4A - 3B &=& \begin{bmatrix}
4 & 0 & 12 \\
-4 & 16 & 8 
\end{bmatrix}
-
\begin{bmatrix}
6 & 9 & 3 \\
-3 & -6 & -9 
\end{bmatrix} \\
&=&
\begin{bmatrix}
-2 & -9 & 9 \\
-1 & 22 & 17 
\end{bmatrix}
\end{eqnarray}
```



<a id="anchor6"></a>

## 6. 行列の積

### 行列の積






数式サンプル
```math
M = \begin{bmatrix}
\frac{5}{6} & \frac{1}{6} & 0           \\
\frac{5}{6} & 0           & \frac{1}{6} \\
0           & \frac{5}{6} & \frac{1}{6}
\end{bmatrix}
```


![img](img/orange.png)
