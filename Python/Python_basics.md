# Python勉強用

## 目次

1. [関数](#anchor1)
2. [Numpy(1次元配列)](#anchor2)
3. [Numpy(2次元配列)](#anchor3)
4. [Numpy(その他)](#anchor4)
5. [Matplotlib](#anchor5)
6. [Pandas](#anchor6)


<a id="anchor1"></a>

## 1. 関数

```py
def 関数名(引数1,引数2,…);
    処理
    return 戻り値
```

で定義、

```
関数名(引数1,引数2,…)
```

で呼び出す

```py
def func_default(a, b, c=100):
    print(f'a={a}, b={b}, c={c}')

func_default(1, 10)
# a=1, b=10, c=100

func_default(1, 10, 200)
# a=1, b=10, c=200
```

のようにデフォルト引数を設定できる

```py
def func_args(*args):
    print(args)

func_args(1, 10)
# (1, 10)

func_args(1, 10, 100, 1000)
# (1, 10, 100, 1000)
```

のように`*args`は複数の引数がタプルとして受け取られる。`**kwargs`は複数のキーワード引数が辞書として受け取られる。

呼び出し時にリストやタプルに*をつけて指定すると、要素が展開（アンパック）され順番に位置引数として指定される。

```py
def func(a, b, c):
    print(f'a={a}, b={b}, c={c}')

l = [1, 10, 100]
func(*l)
# a=1, b=10, c=100
```

関数呼び出し時に辞書に**をつけて指定すると、要素のキーが引数名、値が引数の値として展開されてキーワード引数として指定される。

```py
d = {'a': 1, 'b': 10, 'c': 100}
func(**d)
# a=1, b=10, c=100
```

returnで複数の値をカンマ区切りで指定するとタプルが返される。

```py
def func_return_multi(a, b):
    return a + b, a * b, a / b

x, y, z = func_return_multi(3, 4)
print(x)
# 7
```


<a id="anchor2"></a>

## 2. Numpy(1次元配列)

### np.ndarray

> ベクトルの和と内積を求めるために、Numpyのnp.ndarrayというN次元配列にPythonのリストをnp.array()で変換する。

```py
import numpy as np
from numpy import random
```

```py
a = [1, 2, 3, 4, 5, 6]
b = [7, 8, 9, 10, 11, 12]
```

```py
a = np.array(a)
b = np.array(b)
print("和:", a+b)
print("内積:", np.dot(a, b))
```


> 四則演算は行列の各要素について行われる

```py
a = np.array([1, 2, 3, 4, 5, 6])
b = np.array([7, 8, 9, 10, 11, 12])

print("和: ", a + b) #ベクトルの和
# 和:  [ 8 10 12 14 16 18]

print("差: ", a - b) #ベクトルの差
# 差:  [-6 -6 -6 -6 -6 -6]

print("積: ", a * b) #アダマール積
# 積:  [ 7 16 27 40 55 72]

print("商: ", a / b) #ベクトルの各要素の商
# 商:  [0.14285714 0.25       0.33333333 0.4        0.45454545 0.5       ]

print("累乗:", a**2) #a^2
# 累乗: [ 1  4  9 16 25 36]
```


> 条件演算も同様に各要素で演算され配列として返る

```py
a = np.array([1, 2, 3, 4, 5, 6])
b = np.array([1, 3, 3, 3, 5, 5])

print("a==a: ", a==a)
# a==a:  [ True  True  True  True  True  True]

print("a==b: ", a==b)
# a==b:  [ True False  True False  True False]

print("a>b: ", a>b)
# a>b:  [False False False  True False  True]
```

> sin(), log(), exp()なども同様に演算される

```py
print("sin: ", np.sin(a))
# sin:  [ 0.84147098  0.90929743  0.14112001 -0.7568025  -0.95892427 -0.2794155 ]

print("log: ", np.log(a))
# log:  [0.         0.69314718 1.09861229 1.38629436 1.60943791 1.79175947]

print("exp: ", np.exp(a))
# exp:  [  2.71828183   7.3890561   20.08553692  54.59815003 148.4131591
 403.42879349]
```

> max(), sum(), mean(), std()は全体に対して一つの値を返す

```py
a = np.array([1, 2, 3, 4, 5, 6])
b = np.array([1, 3, 3, 3, 5, 5])

print("max: ", np.max(a)) # 最大値
# max:  6

print("sum: ", np.sum(a)) # 合計値
# sum:  21

print("mean: ", np.mean(a)) # 平均値
# mean:  3.5

print("std: ", np.std(a)) # 標準偏差
# std:  1.707825127659933
```

> 二項演算では長さや次元が違う場合、長さを揃えて計算される

```py
print("3a = ", 3*a)
# 3a =  [ 3  6  9 12 15 18]
```

> 配列aとbの結合は次のように行う

```py
print("aとbの連結: ", np.r_[a, b])
# aとbの連結:  [1 2 3 4 5 6 1 3 3 3 5 5]
```

> pythonのリストに変換するにはlist()を使う

```py
print(a)
# [1 2 3 4 5 6]

print(list(a))
# [1, 2, 3, 4, 5, 6]
```

### インデックス

> `[]`を使うことで任意の位置の値を取得できる
> aの後ろから1番目の要素は`a[-1]`で取得できる

```py
print("前から4番目の値はa[3]=", a[3])
# 前から4番目の値はa[3]= 4

print("後ろから4番目の値はa[-4]=", a[-4])
# 後ろから4番目の値はa[-4]= 3

print("前から1,2,4番目は", a[[0, 1, 3]])
# 前から1,2,4番目は [1 2 4]
```

> `start: end: step`で初項start,公差stepの等差数列で終項はend未満最大の数になるようにスライシングできる
>
> 省略も可能

```py
a = list(range(20)) # 0~19を要素にもつlist
print(a)
# [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19]

print(a[2: 15: 3])
# [2, 5, 8, 11, 14]

print(a[: 15: 3])
# [0, 3, 6, 9, 12]

print(a[2: : 3])
# [2, 5, 8, 11, 14, 17]

print(a[2: 15])
# [2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14]
```

> Numpyでは1次元配列に対してブールインデックス参照できる

```py
a = np.array([1, 3, 5, 7, 9, 11, 13, 15])
bidx = [True, True, False, True, False, True, False, False]

print(a[bidx])
# [ 1  3  7 11]

print(a[a % 5 == 0])
# [ 5 15]
```


<a id="anchor3"></a>

## 3. Numpy(2次元配列)

### 行列の作成


<a id="anchor5"></a>

## 5. Matplotlib

### 科学定数



<a id="anchor6"></a>

## 6. Pandas





![img](img/orange.png)