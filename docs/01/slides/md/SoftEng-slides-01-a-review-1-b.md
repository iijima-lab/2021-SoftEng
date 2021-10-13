<script type="text/template">


----
### [1-b] 反復/ループ (for文)
(<a href="#目次"> 目次に戻る </a>)

- - - -
#### → 参考リンク: for文

  * チュートリアル: [for文](https://docs.python.org/ja/3/tutorial/controlflow.html#for-statements)
  * ドキュメント: [for文](https://docs.python.org/ja/3/tutorial/controlflow.html#for-statements)


----
### Ex_04: forループ (for_loop) → パターン-04

<!--
<img src="fig/01/a-review/08-a-pattern-04-for.png" width="150" height="150" alt="08-a-パターン-04-for">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/08-a-pattern-04-for.png" width="150" height="150" alt="08-a-パターン-04-for">

  * <span style="color: red; ">for文</span>
    * <span style="color: red; ">〈範囲〉</span>の要素を，順に<span style="color: red; ">〈制御変数〉</span>に代入しながら，<span style="color: red; ">〈ブロック〉</span>を反復実行する


- - - -
  * よく使われる〈範囲〉の指定方法-1
    * <span style="color: red; ">range()関数</span>
      * <span style="color: red; ">range( stop )</span>
        * 0から始めて，パラメータstopの「手前」までの範囲
          * stopの値を含まないことに注意
          * (例) range( 10 ) : 0～9までの範囲(10回繰り返す)
      * <span style="color: red; ">range( start, stop )</span>
        * startから始めて，パラメータstopの「手前」までの範囲
          * つまり，startを省略するとゼロとなる
          * (例) range( 3, 10 ) : 3～9までの範囲
      * <span style="color: red; ">range( start, stop, step )</span>
        * stepずつ，制御変数の値が変化する
          * つまり，stepを省略すると1となるが，1以外を指定することができる
            * (例) range( 3, 10, 2 ) : 3, 5, 7, 9
          * stepに負の値を指定することもできる
            * (例) range( 10, 3, -2 ) : 10, 8, 6, 4


- - - -
<!--
<img src="fig/01/a-review/08-b-pattern-04-flow-for.png" width="200" height="150" alt="08-b-パターン-04-flow-for">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/08-b-pattern-04-flow-for.png" width="200" height="150" alt="08-b-パターン-04-flow-for">


----
#### 例題(Example)-04: [for文]  0～4までの偶数

  * やりたいこと
    * 0～4までの整数で，偶数のものだけを表示する
  * フィルタのような挙動をさせるパターンです
    * ループの中で
      * 制御変数が特定の条件を満たすときだけ，
        * 何らかのアクションを実施します
    


- - - -
```python
# ===== [例題-04: for文]  0～4までの偶数 =====
#  * 0～4までの整数で，偶数のものだけを表示する 

for x in range( 5 ):
    if x % 2 == 0:
        print( x )
```

----
#### 練習問題(Practice)-02: [for文] 0～10までの3の倍数

  * やりたいこと
    * 0～10までの整数で，3の倍数だけを表示する
  * 上限値以外は，基本的には，上の例題と同じだが，
    * よりシンプルに，stepを3にしたrange()関数を使って，3つおきに表示させください


----
```python
# ===== [練習問題-02: for文] 0～10までの3の倍数 =====
#  * 0～10までの整数で，3の倍数のものだけを表示する 
#    * シンプルに，stepを3にしたrange()関数を使って，3つおきに表示させください

for x in ★★★穴埋め★★★:
    print( x )
```

----
### Ex_05: forループ (for_loop)

<!--
<img src="fig/01/a-review/10-b-ex-05-flow-for_break.png" width="200" height="150" alt="10-b-例題-05-flow-for_break">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/10-b-ex-05-flow-for_break.png" width="200" height="150" alt="10-b-例題-05-flow-for_break">

- - - -
  * <span style="color: red; ">break文</span>は，ループ(forループも後述のwhileループも)を脱出させる制御構文である
    * 多重のループであっても，実行するbreak文を囲む一番内側のループだけを抜ける
    * 通常，if文と組み合わせて，何らかの条件が成立した場合脱出させる
      * ループ中の異常検出なども典型的であるが，必ずしも異常時だけに使うわけではない
     * for文にelse-節をつけると，breakせずにループを完了したときのみ実行される，〈elseブロック〉を書くこともできる 
       * いずれ，例題を通して，初級スキルセットとして導入するかもしれませんが，入門スキルセットとしては扱いません(ので現時点で知識になくて支障ありません)

----
#### 例題(Example)-05: [for文/break文]  0～4までループする中で，3が出現したら中断する

  * そもそもが，0～3までループさせることと等価だが...
    * あえてbreak文でループを中断させる
    * 3は表示する


- - - -
```python
# ===== [例題-05: for文/break文] 0～4までループする中で，3が出現したら中断する =====
#  * あえてbreak文でループを中断させる

for x in range( 5 ):
    print( x )
    if x == 3:
        break
```

- - - -
  * <span style="color: red; ">continue文</span>
    * break文と同様に，if文と組み合わせて，ある条件が成立したときだけ，ループ実行を制御する構文，continue文がある
    * ループを抜けるのではなく，その回の〈反復実行ブロック〉の残りの実行を飛ばして，次の周回に入るように，ループを継続する制御文
       * if-else構文でも同等のことができるので，ここでは省略します

----
### Ex_06: forループ (for_loop)

<!--
<img src="fig/01/a-review/11-b-ex-06-flow-for.png" width="150" height="150" alt="11-b-例題-06-flow-for">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/

----
#### 例題(Example)-06: [for文] 0～9までの総和を計算し，表示する

  * 変数sum に，0～9までの総和を求める
    * +=は，加算代入演算子
      * sum += x は， sum = sum + x と等価である
      * 複合代入演算子（累算代入演算子)の一種であり，他にも，-=や*=などがあります
  * ループの外側に，累積的に計算結果を更新していく変数(ここではsum)を置くパターンです


- - - -
```python
# ===== [例題-06: for文] 0～9までの総和を計算し，表示する =====

sum = 0

for x in range( 10 ):
    sum += x

print( sum )
```

----
#### 練習問題(Practice)-03: [for文]  二重ループ: 「九九の表」を表示する

  * 以下のような「九九の表」を表示してください
    * for文の入れ子(ネスティング)
      * for文の内側で，別のfor文を回す二重ループ
      * 行のループの内側で．列のループを回すとよさそうですね
    * 解答欄の計算セルの下に，この練習問題に取り組むにあたり，「役立つ知識」を2つ載せてありますので，ご覧ください

- - - -
```
 |01|02|03|04|05|06|07|08|09|
 |02|04|06|08|10|12|14|16|18|
 |03|06|09|12|15|18|21|24|27|
 |04|08|12|16|20|24|28|32|36|
 |05|10|15|20|25|30|35|40|45|
 |06|12|18|24|30|36|42|48|54|
 |07|14|21|28|35|42|49|56|63|
 |08|16|24|32|40|48|56|64|72|
 |09|18|27|36|45|54|63|72|81|
```


- - - -
```python
# ===== [練習問題-03: for文] 二重ループ: 「九九の表」を表示する =====
#  * 九九の表を表示する

for ★★★穴埋め★★★:
    print( " |", end="" )
    ★★★穴埋め★★★:
        print( f"{(row * col):02}|", end="" )
    print()
```

- - - -
  * 「九九の表」の実装上，必要な他の知識(1)
    * print()関数での，行末の改行の抑制
      * オプションパラメータendを使います
        * まず，「おまじない」として導入すると...
          * abcという文字列の表示後，改行させないためには
            * print( "abc", end="" )
        * 意味合いを簡単に説明すると
          * endパラメータは，表示後に「追加表示する文字列」
          * endパラメータを省略すると，暗黙値(default value)として改行文字(\n)が使用されます
            * すなわち，print( "abc" )はprint( "abc", end="\n" )と等価となります
    * 以下の計算セルで試してみてください

- - - -
```python
print( "abc" )
print( "abc", end="" ) # 改行しないので，次の行とつながる
print( "def" )
```

- - - -
```python
# 表に横罫線を入れる（練習問題では求めません）
print( "+", end="" )
for col in range( 1, 10 ):
    print( "--+", end="" )
print()
```


- - - -
  * 「九九の表」の実装上，必要な他の知識(2)
    * f文字列(書式付き文字列)での，10進整数の桁数指定
      * f"{x:5}"と指定すると，xを5桁で表示します
        * 値が5桁未満の場合，左に空白を埋めます
          * f"{x:05}"と指定すると，空白の代わりにゼロを埋めます
        * 値が5桁以上の場合は桁数指定は無視します
          * 5桁以上の数値を5桁で切ってしまったらこまりますよね．



- - - -
```python
x = 123; y = 12345678
print( f" {x:5} " )
print( f"|{x:5}|" )
print( f"|{x:5}|" )
print( f"|{y:5}|" )
```

----
### Ex_07: forループ (for_loop)


----
#### 例題(Example)-07: [for文] 0～20までの中で，3の倍数と5の倍数のそれぞれの個数を数える

  * これも，例題-08と同様のパターンです
    * ループの外側で，変数を初期化し，
      * ここでは，カウンタする変数(count_...)です
    * その変数を，ループの周回の度に，条件に応じて更新していきます
    * 結果は，ループの終了後に，その変数に，得られます

- - - -
  * 計算結果は...
    * 0～20までの中での3の倍数: 0,3,6,9,12,15,18
      * その個数は: 7
    * 0～20までの中での3の倍数: 0,5,10,15,20
      * その個数は: 5



- - - -
```python
# ===== [例題-07: for文] 0～20までの中で，3の倍数と5の倍数のそれぞれの個数を数える =====

count_multiple_of_3 = 0
count_multiple_of_5 = 0
```

- - - -
```python

for x in range( 21 ):
    if x % 3 == 0:
       count_multiple_of_3 += 1
    if x % 5 ==0:
       count_multiple_of_5 += 1
```

- - - -
```python
print( "3の倍数の個数: ", count_multiple_of_3 )
print( "5の倍数の個数: ", count_multiple_of_5 )
```

----
### Ex_08: forループ (for_loop)

  * <span style="color: red; ">forループでの〈範囲〉の指定方法-2</span>
    * <span style="color: red; ">文字列</span>や，<span style="color: red; ">リスト(後述)</span>のように，<span style="color: red; ">〈列〉(シーケンス)</span>を〈範囲〉指定に使うと...
      * その〈列〉(シーケンス)の要素を順に，<span style="color: red; ">制御変数</span>に代入しながら，ループする


- - - -
<!--
<img src="fig/01/a-review/13-b-ex-08-flow-for.png" width="200" height="150" alt="13-b-例題-08-flow-for">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/13-b-ex-08-flow-for.png" width="200" height="150" alt="13-b-例題-08-flow-for">

<!--
<img src="fig/01/a-review/13-c-ex-08-data-for.png" width="200" height="80" alt="13-c-例題-08-data-for">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/13-c-ex-08-data-for.png" width="200" height="80" alt="13-c-例題-08-data-for">


- - - -
  * 〈文字列〉を構成する〈文字〉を文字列として順に表示する
    * <span style="color: red; ">〈添え字(index)〉
      * 〈文字列〉では，0で始まる添え字(index)で指定することで，その位置の文字に文字列としてアクセスすることができる
      * (例) "abcdef"[3] → "d"
    * <span style="color: red; ">〈スライス〉
      * 部分範囲を指定する〈スライス〉で，部分文字列を取得することもできる
        * [start:stop:step]
      * (例) "abcdef"[1:4] → "bcd"
      * (例) "abcdef"[1:4:2] → "bd"



- - - -
```python
print( "abcdef"[1:4]  )
print( "abcdef"[1:4:2] )
```

----
#### 例題(Example)-08: [for文]  文字列中の各文字を，順に一行ずつ表示する

  * 文字列は，繰り返し可能オブジェクト(iterable)なので，for文での反復実行の制御に使うことができる


- - - -
```python
# ===== [例題-08: for文] 文字列中の各文字を，順に一行ずつ表示する =====
# * 文字列は，繰り返し可能オブジェクト(iterable)なので，
#   * for文での反復実行の制御に使うことができる

for c in "abcdef":
    print( c )
```

----
#### 練習問題(Practice)-04: [for文] 文字列中の数字の総和(左から数字以外の文字が出るまで)

  * 与えられた文字列の中に，数字以外の文字が出現するまで
    * 左端から1文字ずつ順に数字を，1桁の数値に変換して，
    * 総和を求める
  * 文字列(長さ1)が数字であるかどうかを判定するメソッド
    * 文字列.isdigit()
      * (例) "5".isdigit()
      * (例) "g".isdigit()
  * 整数を意味する文字列を，数値へ変換するメソッド
    * int( 文字列 )
      * (例) int( "5" ) → 5


- - - -
```python
# ===== [練習問題-04: for文] 文字列中の数字の総和(左から数字以外の文字が出るまで) =====
#  * 与えられた文字列の中に，数字以外の文字が出現するまで
#   * 左端から1文字ずつ順に数字を，1桁の数値に変換して，
#   * 総和を求める
# * 文字列(長さ1)が数字であるかどうかを判定するメソッド
#   * 文字列.isdigit()
#     * (例) "5".isdigit()
#     * (例) "g".isdigit()
# * 整数を意味する文字列を，数値へ変換するメソッド
#   * int( 文字列 )
#     * (例) int( "5" ) → 5

```

- - - -
```python
sum = 0
for c in "12345q6789":
    if ★★★穴埋め★★★:
        x = int( c )
        sum += x
    else:
        ★★★穴埋め★★★

print( sum )
```


- - - -
#### 数値へ変換できる文字列かどうかを判定するメソッド

  * <span style="color: red; ">数値へ変換できる文字列かどうかを判定するメソッド</span>
    * <span style="color: red; ">「1文字の数字」を意味する文字列かどうか</span>は判定できる
      * 文字列.isdigit()
    * <span style="color: red; ">「正の整数」へ変換可能かどうか</span>も判定できる
      * 文字列.isnumeric()
    * しかし，<span style="color: red; ">負の整数や，小数点のある実数は判定できない</span>
      * それを実装するには，もう少しスキルが必要ですから，いずれ取り組みましょう
        * 方法(1): <span style="color: red; ">例外処理</span>を使う
          * ← 安直な方法
        * 方法(2): <span style="color: red; ">正規表現</span>を使う
          * ← 適切な正規表現を構築するのは，なかなか難しい

- - - -
```python
print( "isdigit: 5は数字か?: ", "5".isdigit() )
print( "isdigit: cは数字か?: ", "c".isdigit() )

print( "isnumeric: 123は 正の整数文字列か?: ", "123".isnumeric() )
print( "isnumeric: -123は正の整数文字列か?: ", "-123".isnumeric() )
print( "isnumeric: 12.3は正の整数文字列か?: ", "12.3".isnumeric() )
```


----


<a href="./SoftEng-slides-01-a-review-1-c.html"> 次へ ([1] 復習: 制御構造 / [1-c] 反復/ループ (while文)) </a>

</script>

