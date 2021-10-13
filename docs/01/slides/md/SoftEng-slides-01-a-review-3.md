<script type="text/template">


----
### [3] 復習: データ構造 (data structure) / コンテナ(container)
(<a href="#目次"> 目次に戻る </a>)

----
### [3-a] リストの要素の列挙 (list_enumeration)→ パターン-07
(<a href="#目次"> 目次に戻る </a>)

  * 各括弧の間に，<span style="color: red; ">要素</span>を，カンマで区切って並べる
    * (例) [ 1, 2, 3 ]  や [ "a", "b", "c" ]
    * 要素のデータ型(タイプ)は，異なっていてもよい
      * (例) [ 1, "b", 3 ] 
    * リストを要素とするリストもかまわない
      * (例) [ [ 1, 2 ], [ 1, 2, [ 3, 4 ], 5 ]


- - - -
<!--
<img src="fig/01/a-review/20-a-pattern-07-list_enumeration.png" width="200" height="80" alt="20-a-パターン-07-list_enumeration">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/20-a-pattern-07-list_enumeration.png" width="200" height="80" alt="20-a-パターン-07-list_enumeration">


----
### Ex_13: リストの要素の列挙 (list_enumeration)

----
#### 例題(Example)-13: [リスト] リストの要素</span>を順に表示する

  * リスト[ "a", "b", "c" ]の要素を順に表示する

<!--
<img src="fig/01/a-review/21-b-ex-13-data-list_enumeration.png" width="120" height="80" alt="21-b-例題-13-data-list_enumeration">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/21-b-ex-13-data-list_enumeration.png" width="120" height="80" alt="21-b-例題-13-data-list_enumeration">



- - - -
```python
# ===== [例題-13: リスト]  リストの要素を順に表示する =====
#  * リスト[ "a", "b", "c" ]の要素を順に表示する

for x in [ "a", "b", "c" ]:
    print( x )
```

----
### Ex_14: リストの要素の列挙 (list_enumeration) 

----
#### 例題(Example)-14: [リスト] 整数リストの要素の総和を求める  

  * [ 1, 2, 3, 4, 5 ]の総和を求める


- - - -
<!--
<img src="fig/01/a-review/22-b-ex-14-data-list_enumeration.png" width="200" height="80" alt="22-b-例題-14-code-list_enumeration">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/22-b-ex-14-data-list_enumeration.png" width="200" height="80" alt="22-b-例題-14-code-list_enumeration">



- - - -
```python
# ===== [例題-14: リスト]  整数リストの要素の総和を求める =====
#  * [ 1, 2, 3, 4, 5 ]の総和を求める

sum = 0
for x in [ 1, 2, 3, 4, 5 ]:
    sum += x
print( sum )
```

----
### [3-b] リストの内包表記 (list_comprehension)→ パターン-08
(<a href="#目次"> 目次に戻る </a>)


- - - -
<!--
<img src="fig/01/a-review/23-a-pattern-08-list_comprehension.png" width="300" height="80" alt="23-a-パターン-08-list_comprehension">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/23-a-pattern-08-list_comprehension.png" width="300" height="80" alt="23-a-パターン-08-list_comprehension">

  * <span style="color: red; ">〈範囲〉</span>の各要素のうち，<span style="color: red; ">〈条件式〉</span>が成り立つものを順次，<span style="color: red; ">〈制御変数〉</span>に代入し，<span style="color: red; ">〈式〉</span>での計算結果を列挙したリスト

----
### Ex_15: リストの内包表記 (list_comprehension)

----
#### 例題(Example)-15: [リストの内包表記 ] 0～9まで整数の二乗から成るリストを生成する

  * 内包定義でリストを生成する

<!--
<img src="fig/01/a-review/24-b-ex-15-data-list_comprehension.png" width="200" height="100" alt="24-b-例題-15-data-list_comprehension">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/24-b-ex-15-data-list_comprehension.png" width="200" height="100" alt="24-b-例題-15-data-list_comprehension">

  * 0～9までの〈範囲〉の整数を，それぞれ二乗して作られるリスト


- - - -

```python
# ===== [例題-15: リスト]  0～9まで整数の二乗から成るリストを生成する =====
#  * 内包表記でリストを生成する

print( [ x ** 2 for x in range( 10 ) ] )
```

----
### Ex_16: リストの内包表記  (list_comprehension)

----
#### 例題(Example)-16: [リストの内包表記 ] 0～9までの〈範囲〉の中の奇数だけを列挙したリストを生成する

  * 内包表記でリストを生成する

<!--
<img src="fig/01/a-review/25-b-ex-16-data-list_comprehension.png" width="200" height="100" alt="25-b-例題-16-data-list_comprehension">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/25-b-ex-16-data-list_comprehension.png" width="200" height="100" alt="25-b-例題-16-data-list_comprehension">

  * 0～9までの〈範囲〉の中の奇数だけを列挙したリスト


- - - -
```python
# ===== [例題-16: リスト]  0～9までの〈範囲〉の中の奇数だけを列挙したリストを生成する =====
#  * 内包表記でリストを生成する

print( [ x for x in range( 10 ) if x % 2 == 1] )
```

----
#### 練習問題(Practice)-07: [リストの内包表記]  2次元の表: 「九九の表」

  * <span style="color: red; ">「各行を意味するリストの，リスト」</span>で，
    * <span style="color: red; ">2次元の表</span>ないし<span style="color: red; ">行列(Matrix)</span>を表現できます
    * それを作るには，<span style="color: red; ">リストの内包表記を2重に使う</span>こともできます



- - - -
  * Pythonでは，他言語で書かれたライブラリを使うことで，高速化を図ることがよくあります
    * Pythonよく使われるモジュール
      * Numpyパッケージ
        * Vector, Matrix, Tensorなどを扱うのに，C言語で作られて実行速度が速いNumpyのArrayをよく使います
      * Pandasパッケージ
        * 大規模な表を扱うには，PandasのDataFrameをよく使います
      * HDF5パッケージ
        * 比較的最近では，階層的な表データを扱うのにHDF5もよくつかわれています


- - - -
    * 基本的なPythonの言語処理系は，実行速度が遅い部類に属します
      * 遅い原因は，インタープリタ方式（逐次実行方式）だからです
        * 通訳方式といってもよいでしょう．
          * 典型的には，プログラムのソースコートを1行ずつ実行時に解析しながら実行します
        * 実行前に，プログラムを



- - - -
```python
# ===== [練習問題-07: リストの内包表記] 2次元の表: 「九九の表」 =====
#  * 「各行を意味するリストの，リスト」で，
#   * 2次元の表ないし行列(Matrix)を表現できます
#   * それを作るには，リストの内包表記を2重に使うこともできます

table_kuku = ★★★穴埋め★★★

print( table_kuku )


- - - -
# ----- おまけ: pprintモジュールのpprint()関数を使うと，
# -----         少しだけ，読みやすく整形して表示してくれます
#  * pprintという名称は，pretty printに由来します

print() # 1行空けるだけ

import pprint
pprint.pprint( table_kuku )
```

----


<a href="./SoftEng-slides-01-a-review-4.html"> 次へ ([4] 復習: 関数 ) </a>

</script>

