# Python勉強用 基礎編

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

> 縦にn行、横にm列の行列を作成する場合もnp.array()を用いる。`a.shape`で配列aの形を確認できる。

```py
a = np.array(
    [[1, 2],
    [3, 4],
    [5, 6]])
print(a)
```

> `np.ndarray.reshape()`を使うことで、1次元の配列を2次元に整形して行列を作成することもできる。
引数に変形後の形を渡す。shapeの引数のうち一つを`-1`とすると自動で整形される。

```py
a = np.array([1, 2, 3, 4, 5, 6])
a1 = a.reshape(3, 2)
print(a1)

a2 = a.reshape(3, -1)
print(a2)
```

> 四則演算は1次元の時と同様に行うことができる。

```py
a = np.array([1, 2, 3, 4, 5, 6]).reshape(3, -1)
b = np.array([7, 8, 9, 10, 11, 12]).reshape(3, -1)

print("和: ", a + b) #ベクトルの和
# 和:  [[ 8 10]
# [12 14]
# [16 18]]
 
print("差: ", a - b) #ベクトルの差
# 差:  [[-6 -6]
# [-6 -6]
# [-6 -6]]

print("積: ", a * b) #アダマール積
# 積:  [[ 7 16]
# [27 40]
# [55 72]]

print("商: ", a / b) #ベクトルの各要素の商
# 商:  [[0.14285714 0.25      ]
# [0.33333333 0.4       ]
# [0.45454545 0.5       ]]

print("累乗:", a**2)
# 累乗: [[ 1  4]
# [ 9 16]
# [25 36]]
```

> sin(),log(),exp()などは1次元の時と同様に各要素で演算され配列として返る
```py
print("sin: ", np.sin(a))
# sin:  [[ 0.84147098  0.90929743]
# [ 0.14112001 -0.7568025 ]
# [-0.95892427 -0.2794155 ]]

print("log: ", np.log(a))
# log:  [[0.         0.69314718]
# [1.09861229 1.38629436]
# [1.60943791 1.79175947]]

print("exp: ", np.exp(a))
# exp:  [[  2.71828183   7.3890561 ]
# [ 20.08553692  54.59815003]
# [148.4131591  403.42879349]]
```

### axis(軸)

> 2次元配列の縦軸を`axis 0`、横軸を`axis 1`と呼び、np.mean(),np.max()などの集約関数ではaxisを指定することでaxisごとの演算結果を得られる。

```py
a = np.array([29, 37, 45, 56, 63, 74, 87, 91, 98, 102, 115, 120]).reshape(4, 3)
print(a)
print(np.max(a))
# [[ 29  37  45]
# [ 56  63  74]
# [ 87  91  98]
# [102 115 120]]
# 120

print("axis 0: ", np.max(a, axis=0))
# axis 0:  [102 115 120]

print("axis 1: ", np.max(a, axis=1))
# axis 1:  [ 45  74  98 120]

# keepdimsをTrueにすると2次元配列のまま返り値が得られる
print("axis 0: ", np.max(a, axis=0, keepdims=True))
# axis 0:  [[102 115 120]]

print("axis 1: ", np.max(a, axis=1, keepdims=True))
# axis 1:  [[ 45]
# [ 74]
# [ 98]
# [120]]
```

> NumpyではIndexを`a[axis0,axis1]`のように1つの`[]`で書くことができる。

```py
a = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12]).reshape(3, 4)
print(a)
# [[ 1  2  3  4]
# [ 5  6  7  8]
# [ 9 10 11 12]]

# 0行目を取得
print(a[0])
# [1 2 3 4]

# (0, 1)成分を取得
print(a[0][1])
# 2

print(a[0, 1])
# 2

# axis 0の0番目と2番目を取得
print(a[[0, 2]]) # a[0, 2]とは違う
# [[ 1  2  3  4]
# [ 9 10 11 12]]

# axis 1の0番目と2番目を取得
print(a[:, [0, 2]]) 
# [[ 1  3]
# [ 5  7]
# [ 9 11]]

# axis 0に指定するListや配列はaxis 0と同じ向き(縦向き)にする
print(a[[[0], [2]], [[1, 3]]]) 
# [[ 2  4]
# [10 12]]

# a[0, 1], a[2, 3]を取得
print(a[[0, 2], [1, 3]]) 
# [ 2 12]
```

> `np.ix_()`を使うと`a[[[0], [2]], [[1, 3]]]`のような読みにくい構造を簡単に表せる。
```py
idx = np.ix_([0, 2], [1, 3])
print(a[idx])
# [[ 2  4]
# [10 12]]
```

> 2次元配列もスライシング可能である。
```py
# aの0行目から1行目までを取り出す
print(a[0:2])
# [[1 2 3 4]
# [5 6 7 8]]

# aの0列目から2列目までを取り出す
print(a[:, 0: 3])
# [[ 1  2  3]
# [ 5  6  7]
# [ 9 10 11]]

# aの0行目から1行目かつ0列目から2列目を取り出す
print(a[0: 2, 0: 3])
# [[1 2 3]
# [5 6 7]]
```

> 2次元配列でもindexが同じshapeであれば、ブールインデックス参照できる
```py
a = np.array([1, 2, 3, 4, 5, 6, 7, 8]).reshape(2, 4)

print(a)
# [[1 2 3 4]
# [5 6 7 8]]

idx = a%3 == 0 # aのうち3の倍数である値を抜き出す
print(idx)
# [[False False  True False]
# [False  True False False]]

print(a[idx])
# [3 6]

# axis 1にブールインデックスを指定
print(a[:, [False, True, False, True]])
# [[2 4]
# [6 8]]

# 2つのaxisにブールインデックスを指定して交差した部分を得る
print(a[np.ix_([True, True], [True, True, False, True])])
# [[1 2 4]
# [5 6 8]]

```

<a id="anchor4"></a>

## 4. Numpy(その他)

### 科学定数

> Numpyでは$\pi やe$などの科学定数の他に，$\infty$に対応する`np.inf`がある。

```py
print("円周率: ", np.pi)
# 円周率:  3.141592653589793

print("ネイピア数: ", np.e)
# ネイピア数:  2.718281828459045

print("正の無限大: ", np.inf)
# 正の無限大:  inf

print("負の無限大: ", - np.inf)
# 負の無限大:  -inf

print(1 + np.inf,1 - np.inf)
# inf -inf
```

### 乱数を持つ配列

> Numpyには乱数を扱う`random`ライブラリがある。
```py
from numpy import random
```

> random.rand() : [0, 1]上の一様乱数を一つ生成
>
> random.randn() : 標準正規分布(平均0, 分散1)に従う乱数を一つ生成
>
> random.normal(mean,std,shape) : 平均と分散を指定することでその正規分布に従う乱数を生成できるshapeを指定した場合は、正規分布に従う乱数をshapeの数生成する
>
> random.randint() : 整数を乱数として生成する
>
> random.seed(seed) : seedを設定することで生成する乱数を固定できる

```py
# [0, 1]上の一様乱数を一つ生成
print(random.rand())

# 引数にshapeをかくとそのshapeの一様乱数が生成される
print(random.rand(5)) # 長さ5(=shapeが(5, ) )の1次元配列
print(random.rand(5, 5)) # shapeが(5, 5)の2次元配列　

#rand()ではなくrandn()を使うことで正規分布からサンプリングできる

# 標準正規分布(平均0, 分散1)に従う乱数を一つ生成
print(random.randn())

# 引数にshapeをかくとそのshapeの乱数が生成される
print(random.randn(5)) # 長さ5(=shapeが(5, ) )の1次元配列
print(random.randn(5, 5)) # shapeが(5, 5)の2次元配列　

print(random.normal(100, 10)) # 平均100, 分散10の正規分布に従う乱数
print(random.normal(100, 10, 5)) # 平均100, 分散10の正規分布に従う乱数を5つ持つ1次元配列として作成
print(random.normal(100, 10, (5, 5))) 
# 平均100, 分散10の正規分布に従う乱数を値にもつshape (5, 5)の2次元配列として作成

print(random.randint(4)) # 0~3の整数を生成
print(random.randint(2, 10, (3, 3))) # 2~9の整数をランダムに値にもつshape (3, 3)の2次元配列を生成

random.seed(seed=32) # seedは任意のint

# 何回実行しても値は同じ
print(random.rand(5))
print(random.randint(2, 10, (3, 3)))
```

### 線形代数の基本的な演算

```py
x = np.arange(1, 4)
y = np.arange(6, 9)
A = np.arange(1, 10).reshape(3, 3)
B = random.randint(1, 10, (3, 3))

print(x)
# [1 2 3]

print(y)
# [6 7 8]

print(A)
# [[1 2 3]
# [4 5 6]
# [7 8 9]]

print(B)
# [[1 4 3]
# [6 4 3]
# [9 4 3]]
```

> `np.transpose()`または`np.ndarray.T`で転置できる

```py
print(np.transpose(A))
# [[1 4 7]
# [2 5 8]
# [3 6 9]]

print(A.T)
# [[1 4 7]
# [2 5 8]
# [3 6 9]]
```

> 内積や行列積は`np.dot()`や`np.matmul()`または`@`を使う。
```py
# xとyの内積
print(np.dot(x, y))
# 44

print(np.matmul(x, y))
# 44

print(x@y)
# 44

# AとBの行列積
print(np.dot(A, B))
# [[ 40  24  18]
# [ 88  60  45]
# [136  96  72]]

print(np.matmul(A, B))
# [[ 40  24  18]
# [ 88  60  45]
# [136  96  72]]

print(A@B)
# [[ 40  24  18]
# [ 88  60  45]
# [136  96  72]]
```

> 1次元配列は2次元配列として扱う方が扱いやすい。5次元ベクトルを扱うとき、`shape(5, )`の1次元配列ではなく`shape(5, 1)`の2次元配列とすれば転置などが可能となる。

```py
a = np.array([1, 2, 3, 4, 5])

# axisが1つしかないので転置前後で変わらない
print(a)
# [1 2 3 4 5]

print(a.T)
# [1 2 3 4 5]

# aを横ベクトルの2次元配列にする
a = a.reshape(1, -1)
print(a)
# [[1 2 3 4 5]]

print(a.T)
# [[1]
# [2]
# [3]
# [4]
# [5]]
```

### 線形代数計算ライブラリ`linalg`

```py
from numpy import linalg as LA
```

```py
A = np.arange(1, 10).reshape(3, 3)
B = random.randint(1, 10, (3, 3))

# 行列式を求める
print(LA.det(A))
# 0.0

print(LA.det(B))
# -208.99999999999997

# 逆行列を求める
#print(LA.inv(A)) Aは非正則行列のためエラー
print(LA.inv(B))
# [[-0.02392344 -0.03349282  0.20095694]
# [-0.00956938  0.18660287 -0.11961722]
# [ 0.16267943 -0.1722488   0.03349282]]
```
```py
# ノルムを求める(デフォルトはL2ノルム(ユークリッド距離))
print(LA.norm(A))
# 16.881943016134134

print(LA.norm(B))
# 14.628738838327793

# 引数ordを指定するとLpノルムに対応
print(LA.norm(A, ord=1)) # ord=1はマンハッタン距離
# 18.0

print(LA.norm(B, ord=np.inf)) # ordをnp.infにするとL∞ノルム(最大値ノルム)になる
# 17.0
```



<a id="anchor5"></a>

## 5. Matplotlib





<a id="anchor6"></a>

## 6. Pandas





![img](img/orange.png)
