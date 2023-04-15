# 線形代数
## 目次

1. [ベクトルの定義](#anchor1)
2. [n次元ベクトル](#anchor2)
3. [内積](#anchor3)
4. [外積](#anchor4)
5. [行列の定義と計算](#anchor5)
6. [行列の積](#anchor6)
7. [行列の性質](#anchor7)
8. [いろいろな行列](#anchor8)
9. [行列の基本変形](#anchor9)



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
( $1 \times m$行列) $\times$ ( $m \times 1$行列)はスカラーとなる。
```math
\begin{eqnarray}
&&\begin{bmatrix}
a_{11} a_{12} \cdots a_{1m}
\end{bmatrix}
\begin{bmatrix}
b_{11} \\ b_{21} \\ \vdots \\ b_{m1}
\end{bmatrix} \\
=
&&a_{11} b_{11} + a_{12} b_{21} + \cdots + a_{1m} b_{m1}
\end{eqnarray}
```
( $l \times m$行列) $\times$ ( $m \times n$行列)は( $l \times n$行列)となる。

$c_{ij} = a_{i1} b_{1j} + a_{i2} b_{2j} + \cdots + a_{im} b_{mj}$
```math
\begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1m} \\
a_{21} & a_{22} & \cdots & a_{2m} \\
\vdots  & \vdots  & \ddots & \vdots  \\
a_{l1} & a_{l2} & \cdots & a_{lm} 
\end{bmatrix}
\begin{bmatrix}
b_{11} & b_{12} & \cdots & b_{1n} \\
b_{21} & b_{22} & \cdots & b_{2n} \\
\vdots  & \vdots  & \ddots & \vdots  \\
b_{m1} & b_{m2} & \cdots & b_{mn} 
\end{bmatrix} \\
=
\begin{bmatrix}
c_{11} & c_{12} & \cdots & c_{1n} \\
c_{21} & c_{22} & \cdots & c_{2n} \\
\vdots  & \vdots  & \ddots & \vdots  \\
c_{l1} & c_{l2} & \cdots & c_{ln}
\end{bmatrix}
```

(例)
```math
\begin{eqnarray}
&& \begin{bmatrix}
1 & 2 & 3 \\
4 & 5 & 6
\end{bmatrix}
\begin{bmatrix}
3 & -2 \\
-2 & 1 \\
-1 & 0 
\end{bmatrix} \\
&&=
\begin{bmatrix}
1 \cdot 3 + 2 \cdot (-2) + 3 \cdot (-1) & 1 \cdot (-2) + 2 \cdot 1 + 3 \cdot 0 \\
4 \cdot 3 + 5 \cdot (-2) + 6 \cdot (-1) & 4 \cdot (-2) + 5 \cdot 1 + 6 \cdot 0
\end{bmatrix} \\
&&=
\begin{bmatrix}
-4 & 0 \\
-4 & -3 
\end{bmatrix}
\end{eqnarray}
```

#### (例題)
```math
A = \begin{bmatrix}
0 & 1 & 2 \\
-1 & 2 & 1 
\end{bmatrix},
B = \begin{bmatrix}
1 & 0 \\
0 & 1 \\
3 & -1
\end{bmatrix},
x = \begin{bmatrix}
4 \\
-1 \\
2
\end{bmatrix}
```
について、 
```math
\begin{eqnarray}
&(1)& AB \\ &(2)& BA \\ &(3)& Ax
\end{eqnarray}
```
を求める。

#### (解答)

(1)
```math
\begin{eqnarray}
AB &=& \begin{bmatrix}
0 & 1 & 2 \\
-1 & 2 & 1
\end{bmatrix}
\begin{bmatrix}
1 & 0 \\
0 & 1 \\
3 & -1 
\end{bmatrix} \\
&=&
\begin{bmatrix}
0 \cdot 1 + 1 \cdot 0 + 2 \cdot 3 & 0 \cdot 0 + 1 \cdot 1 + 2 \cdot (-1) \\
(-1) \cdot 1 + 2 \cdot 0 + 1 \cdot 3 & (-1) \cdot 0 + 2 \cdot 1 + 1 \cdot (-1)
\end{bmatrix} \\
&=&
\begin{bmatrix}
6 & -1 \\
2 & 1 
\end{bmatrix}
\end{eqnarray}
```
(2)
```math
\begin{eqnarray}
BA &=& \begin{bmatrix}
1 & 0 \\
0 & 1 \\
3 & -1 
\end{bmatrix}
\begin{bmatrix}
0 & 1 & 2 \\
-1 & 2 & 1
\end{bmatrix} \\
&=&
\begin{bmatrix}
1 \cdot 0 + 0 \cdot (-1) & 1 \cdot 1 + 0 \cdot 2 & 1 \cdot 2 + 0 \cdot 1 \\
0 \cdot 0 + 1 \cdot (-1) & 0 \cdot 1 + 1 \cdot 2 & 0 \cdot 2 + 1 \cdot 1 \\
3 \cdot 0 + (-1) \cdot (-1) & 3 \cdot 1 + (-1) \cdot 2 & 3 \cdot 2 + (-1) \cdot 1
\end{bmatrix} \\
&=&
\begin{bmatrix}
0 & 1 & 2 \\
-1 & 2 & 1 \\
1 & 1 & 5
\end{bmatrix}
\end{eqnarray}
```
(3)
```math
\begin{eqnarray}
Ax &=& \begin{bmatrix}
0 & 1 & 2 \\
-1 & 2 & 1
\end{bmatrix}
\begin{bmatrix}
4 \\
-1 \\
2 
\end{bmatrix} \\
&=&
\begin{bmatrix}
0 \cdot 4 + 1 \cdot (-1) + 2 \cdot 2 \\
(-1) \cdot 4 + 2 \cdot (-1) + 1 \cdot 2
\end{bmatrix} \\
&=&
\begin{bmatrix}
3 \\
-4
\end{bmatrix}
\end{eqnarray}
```



<a id="anchor7"></a>

## 7. 行列の性質

### 転置行列

Aの行と列を入れ替えた行列をAの転置行列といい、 ${}^tA$と書く。
```math
{}^tA = {}^t \begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots  & \vdots  & \ddots & \vdots  \\
a_{m1} & a_{m2} & \cdots & a_{mn} 
\end{bmatrix}
=
\begin{bmatrix}
a_{11} & a_{21} & \cdots & a_{m1} \\
a_{12} & a_{22} & \cdots & a_{m2} \\
\vdots  & \vdots  & \ddots & \vdots  \\
a_{1n} & a_{2n} & \cdots & a_{mn} 
\end{bmatrix}
```

### 行列の性質
```math
\begin{eqnarray}
&(1)& A(B + C) = AB + AC \\
&(2)& (A + B)C = AC + BC \\
&(3)& (AB)C = A(BC) = ABC \\
&(4)& {}^t(AB) = {}^tB {}^tA
\end{eqnarray}
```
$AA \cdots A = A^n$である。

一般に $AB \neq BA$である(積は交換できない)。

```math
\begin{eqnarray}
&&AB = \begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix}
\begin{bmatrix}
2 -1 \\
-1 1
\end{bmatrix}
=
\begin{bmatrix}
0 1 \\
2 1
\end{bmatrix} \\
&&BA = \begin{bmatrix}
2 & -1 \\
-1 & 1
\end{bmatrix}
\begin{bmatrix}
1 2 \\
3 4
\end{bmatrix}
=
\begin{bmatrix}
-1 0 \\
2 2
\end{bmatrix} 
\neq AB
\end{eqnarray}
```

#### (例題)
```math
A = \begin{bmatrix}
2 & 0 \\
0 & 2 
\end{bmatrix},
B = \begin{bmatrix}
0 & 1 \\
1 & 0
\end{bmatrix},
C = \begin{bmatrix}
-1 & 2 & 0 \\
3 & -2 & 1
\end{bmatrix}
```
について、 
```math
\begin{eqnarray}
&(1)& {}^tC \\ &(2)& (A - B)C
\end{eqnarray}
```
を求める。

#### (解答)

(1)
```math
\begin{eqnarray}
{}^tC &=& {}^t 
\begin{bmatrix}
-1 & 2 & 0 \\
3 & -2 & 1 
\end{bmatrix}
&=&
\begin{bmatrix}
-1 & 3 \\
2 & -2 \\
0 & 1
\end{bmatrix}
\end{eqnarray}
```
(2)
```math
\begin{eqnarray}
(A - B)C &=& AC - BC \\
&=& \begin{bmatrix}
-2 & 4 & 0 \\
6 & -4 & 2
\end{bmatrix}
-
\begin{bmatrix}
3 & -2 & 1 \\
-1 & 2 & 0 
\end{bmatrix} \\
&=&
\begin{bmatrix}
-5 & 6 & -1 \\
7 & -6 & 2 
\end{bmatrix}
\end{eqnarray}
```



<a id="anchor8"></a>

## 8. いろいろな行列

### 零行列

すべての成分が0の行列を零行列といい、 $\boldsymbol{0}$で表す。
```math
\boldsymbol{0} = \begin{bmatrix}
0 & 0 & \cdots & 0 \\
0 & 0 & \cdots & 0 \\
\vdots  & \vdots  & \ddots & \vdots  \\
0 & 0 & \cdots & 0
\end{bmatrix}
```

### 正方行列

$n \times n$行列をn次正方行列という。
```math
A = \begin{bmatrix}
a_{11} & a_{21} & \cdots & a_{n1} \\
a_{12} & a_{22} & \cdots & a_{n2} \\
\vdots  & \vdots  & \ddots & \vdots  \\
a_{1n} & a_{2n} & \cdots & a_{nn} 
\end{bmatrix}
```

### 単位行列

n次正方行列 $E_n$を(n次)単位行列という。
```math
E_n = \begin{bmatrix}
1 & 0 & \cdots & 0 \\
0 & 1 & \cdots & 0 \\
\vdots  & \vdots  & \ddots & \vdots  \\
0 & 0 & \cdots & 1 
\end{bmatrix}
```

### 逆行列

n次正方行列 $A,B$が $AB = BA = E_n$を満たすとき、BをAの逆行列といい、 $B = A^{-1}$と書く。

すなわち、 $AA^{-1} = A^{-1}A = E_n$

(例) 
```math
\mathsf{2次正方行列}
A = \begin{bmatrix} 2 & 3 \\ 5 & 8 \end{bmatrix}
\mathsf{に対し, }
A^{-1} = \begin{bmatrix} 8 & -3 \\ -5 & 2 \end{bmatrix}
```
```math
AA^{-1} \mathsf{を求めると、}
\begin{bmatrix}
1 & 0 \\
0 & 1
\end{bmatrix}
\mathsf{であることがわかる}
```

#### 2次正方行列の逆行列

```math
A = \begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
\mathsf{に対し、}
ad - bc \neq 0
\mathsf{が成り立つとき、} \\
A^{-1} = \begin{bmatrix}
a & b \\
c & d
\end{bmatrix}^{-1}
=
\frac{1}{ad-bc} \begin{bmatrix}
d & -b \\
-c & a
\end{bmatrix}
```

#### (例題)
```math
A = \begin{bmatrix}
5 & 7 \\
2 & 3 
\end{bmatrix},
B = \begin{bmatrix}
4 & -3 \\
6 & -5
\end{bmatrix}
```
について、 
```math
\begin{eqnarray}
&(1)& AE_2 \\ &(2)& A^{-1} \\ &(3)& B^{-1}
\end{eqnarray}
```
を求める。

#### (解答)

(1)
```math
\begin{eqnarray}
AE_2 =
\begin{bmatrix}
5 & 7 \\
2 & 3 
\end{bmatrix}
\begin{bmatrix}
1 & 0 \\
0 & 1 
\end{bmatrix}
=
\begin{bmatrix}
5 & 7 \\
2 & 3 
\end{bmatrix}
=
A
\end{eqnarray}
```
(2)
```math
\begin{eqnarray}
A^{-1} =
\begin{bmatrix}
5 & 7 \\
2 & 3 
\end{bmatrix} ^{-1}
=
\frac{1}{5 \cdot 3 - 7 \cdot 2}
\begin{bmatrix}
3 & -7 \\
-2 & 5 
\end{bmatrix}
=
\begin{bmatrix}
3 & -7 \\
-2 & 5 
\end{bmatrix}
\end{eqnarray}
```
(3)
```math
\begin{eqnarray}
B^{-1} =
\begin{bmatrix}
4 & -3 \\
6 & -5 
\end{bmatrix} ^{-1}
=
\frac{1}{4 \cdot (-5) - (-3) \cdot 6}
\begin{bmatrix}
-5 & 3 \\
-6 & 4 
\end{bmatrix}
=
\frac{1}{2}
\begin{bmatrix}
-5 & 3 \\
-6 & 4 
\end{bmatrix}
=
\begin{bmatrix}
\frac{5}{2} & -\frac{3}{2} \\
3 & -2 
\end{bmatrix}
\end{eqnarray}
```



<a id="anchor9"></a>

## 9. 行列の基本変形

### 








![img](img/orange.png)
