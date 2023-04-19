# Markdownの記法

MarkdownではHTMLで用いるタグが記述できるが、インラインHTMLスタイルに関してはGithubなど一部のparserでは対応していない。

<参考>[Qiita マークダウン記法 一覧表・チートシート](https://qiita.com/kamorits/items/6f342da395ad57468ae3)

## 見出し
```html
# 見出しh1
## 見出しh2
```
### 見出しh3
#### 見出しh4

## リスト
```html
- 箇条書き
  - タブでインデント
```
- 箇条書き
  - タブでインデント

## 番号つきリスト
```html
1. 番号つきリスト
1. 番号つきリスト
1.にすれば番号は自動で振られる
```
1. 番号つきリスト
1. 番号つきリスト

## 空行,改行
```html
半角スペース2つ  または<br>
```
半角スペース2つ  または<br>

## インライン表示
```html
`テキスト`
```
`テキスト`

## コードの挿入
````html
```py
print("hello")
```
````
```py
print("hello")
```

## リンクの挿入
```html
[タイトル](URL)
```
[タイトル](URL)

## 引用
```html
> テキスト
>> テキスト
```
> テキスト
>> テキスト

## 画像の挿入
```html
![代替テキスト](画像のパス)
```
![代替テキスト](画像のパス)

## サイズ指定して画像を挿入
```html
<img width="数値" alt="代替テキスト" src="URL">
```
<img width="数値" alt="代替テキスト" src="URL">

## テーブルの挿入
```html
|あ|い|う|
|---|---|---|
|か|き|く|

| 左寄せ | 中央 | 右寄せ |
| :-- | :-: | --: |
| あ | あ | あ |
```
|あ|い|う|
|---|---|---|
|か|き|く|

| 左寄せ | 中央 | 右寄せ |
| :-- | :-: | --: |
| あ | あ | あ |

## 文字色
```html
<font color="Red">あか</font>
<span style="color: blue; ">あお</span>
```
<font color="Red">あか</font>
<span style="color: blue; ">あお</span>

## 太字
```html
**太字**
```
**太字**

## 斜体
```html
*テキスト*
```
*テキスト*

## 打ち消し線
```html
~~テキスト~~
```
~~テキスト~~

## 水平線
```html
***
---
```
***
---

## 注釈
```html
テキスト[^1]

[^1]: 注釈内容
```
テキスト[^1]

[^1]: [https://www.google.co.jp/]

## チェックボックス
```html
- [ ] リスト１
- [x] リスト２
```
- [ ] リスト１
- [x] リスト２

# GoogleColabでの小技
<参考><a href="https://qiita.com/john-rocky/items/e5802cdd15dc2e34cb84">Qiita _ ColabにUIをつける小技集</a>

<参考>[公式のドキュメント](https://colab.research.google.com/notebooks/forms.ipynb)

## セルのタイトル
```py
#@title セルのタイトル
```

## フォーム
```py
#@title フォーム
raw_input = None #@param {type:"raw"}
variable = "フォームが変数に反映されます"#@param {type:"string"}
# 数値の場合は　#@param {type:"number"}
```

## 選択肢
```py
#@title 選択肢
dropdown = '2nd option' #@param ["1st option", "2nd option", "3rd option"] {allow-input: true}
raw_dropdown = raw_input #@param [1, "raw_input", "False", "'string'"] {type:"raw"}
```
## 日付入力
```py
#@title 日付入力
date_input = '2023-02-20' #@param {type:"date"}
```

## スライドバー
```py
#@title スライドバー
number_slider = 0.1 #@param {type:"slider", min:-1, max:1, step:0.1}
```
## チェックボックス
```py
#@title チェックボックス
boolean_checkbox = True #@param {type:"boolean"}
```

## セル内でのマークダウン
```py
#@title セル内でのマークダウン
#@markdown ---
#@markdown #Big
#@markdown ###Middle
#@markdown #####Little
#@markdown ---
```

## ボタン
```py
#@title ボタン
from IPython.display import display, Javascript
from google.colab import output
from google.colab.output import eval_js


js = Javascript('''
            async function load_image() {
                const div = document.createElement('div');
                var button = document.createElement('button');
                var log = document.createElement('div');

                button.textContent = "button";
                button.onclick = function(){
                    log.innerHTML = "Button Clicked.";
                }
                div.appendChild(button)
                div.appendChild(log)

                document.querySelector("#output-area").appendChild(div);
                return
                } ''')

display(js)
eval_js('load_image()')
```

