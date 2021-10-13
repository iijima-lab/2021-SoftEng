<script type="text/template">


----
### [1] 復習: 制御構造(Control_Structure)
(<a href="#目次"> 目次に戻る </a>)

  * <span style="color: red; ">構造化プログラミング (structured programming)</span>
    * <span style="color: red; ">手続き的(procedural)プログラミング</span>と呼ばれる，一般によく使われているタイプのプログラミング言語では...
      * <span style="color: red; ">(ブロック中の文の)逐次実行〈連接〉, 〈条件分岐〉，〈反復/ループ〉</span>といった<span style="color: red; ">制御構文</span>をもとに，構造的にプログラミングを記述するものが多くあります
    * プログラムの構造が明解で，<span style="color: red; ">トップダウン</span>に扱うことができるため，比較的，
      * <span style="color: red; ">読みやすく(理解しやすく）</span>，<span style="color: red; ">書きやすい</span>ものとなりえます

----
### [1-a] 条件分岐 (if文)
(<a href="#目次"> 目次に戻る </a>)



- - - -

#### → 参考リンク: if文

  * チュートリアル: [if文](https://docs.python.org/ja/3/tutorial/controlflow.html#if-statements)
  * ドキュメント: [if文](https://docs.python.org/ja/3/reference/compound_stmts.html#the-if-statement)

- - - -
### Ex_01: if分岐 (if_selection) → パターン-01

  * <span style="color: red; ">〈条件式〉</span>を評価して<span style="color: red; ">〈真〉(True)のとき</span>だけ，
    * 〈if-ブロック〉を実行する
  * 評価結果が<span style="color: red; ">〈偽〉(False)のとき</span>は，
    * 何もしない


<!--
<img src="fig/01/a-review/02-a-pattern-01-if.png" width="200" height="100"  alt="02-a-パターン-01-if ">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/02-a-pattern-01-if.png" width="200" height="100"  alt="02-a-パターン-01-if ">

<!--
<img src="fig/01/a-review/02-b-pattern-01-flow-if.png" width="120" height="150" alt="02-b-パターン-01-flow-if">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/02-b-pattern-01-flow-if.png" width="120" height="150" alt="02-b-パターン-01-flow-if">

  * ブロック</span>は，字下げ(indentation)</span>で範囲を指定する
    * 字下げは，空白文字(半角空白かTab)
      * 半角空白4文字を推奨</span>
        * 間違えて，全角空白が混入すると発見しにくいので注意
      * Tab文字を1つというのもありだが...あまり推奨しない
        * 1回押せば字下げできるので速く打てるが，Tabの表示幅はアプリケーションの設定によって異なるので，意外と不便
        * エディタの支援機能で，前の行に基づいて自動字下げするエディタも多いので，このメリットは小さい
        * インデントの仕方は統一する
          * 半角空白列と，Tab文字の両方を混在させてはいけない
          * この混在も，発見しにくいので注意

- - - -
  * <span style="color: red; ">代入</span>
    * =は，代入．右辺の数式の評価結果を，左辺の変数に代入する
  * <span style="color: red; ">比較演算子</span>
    * <は，大小比較
      * 他の大小比較としては，<, <=, >, >=
    * <span style="color: red; ">等号</span>は==, <span style="color: red; ">不等号</span>は!=
  * <span style="color: red; ">\# 以降</span>は，<span style="color: red; ">コメント(注釈)</span>であり，実行されない

----
#### 例題(Example)-01: [if文]  整数の大小比較

  * 変数xと変数yに代入された整数の大小比較
    * xがyより小さいときには，
      * その旨を表示してください 
    * さもなくば
      * 何もしない


- - - -
```python
# ===== [例題-01: if文] 変数xと変数yに代入された整数の大小比較 =====
#   * xがyより小さいときには，その旨を表示してください 

x = 3
y = 5
if x < y:
    print( "xはyより小さい" )
```

----
### Ex_02: if_else分岐 → パターン-02`

  * <span style="color: red; ">〈条件式〉</span>を評価して<span style="color: red; ">〈真〉(True)のとき</span>は，
    * 〈if-ブロック〉を実行する
  * 評価結果が<span style="color: red; ">〈偽〉(False)のとき</span>は，
    * 〈else-ブロック〉(ブロック2)を実行する

----
<!--
<img src="fig/01/a-review/04-a-pattern-02-if_else.png" width="200" height="100" alt="04-a-パターン-02-if_else">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/04-a-pattern-02-if_else.png" width="200" height="100" alt="04-a-パターン-02-if_else">

<!--
<img src="fig/01/a-review/04-b-pattern-02-flow-if_else.png" width="200" height="150" alt="04-b-パターン-02-flow-if_else">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/04-b-pattern-02-flow-if_else.png" width="200" height="150" alt="04-b-パターン-02-flow-if_else">

- - - -
  * <span style="color: red; ">%</span>は<span style="color: red; ">剰余演算子</span>
    * a % bは，aをbで割った余り
      * 2で割った余りがゼロ(2で割り切れる)なら，偶数 


----
#### 例題(Example)-02: [if-else文] 変数xに代入した整数の偶奇判定

  * xに3を代入してから，xの値の偶奇判定結果を表示する
    * 2で割った余りがゼロ(2で割り切れる)なら，偶数


- - - -
```python
# ===== [例題-02: for文] 変数xに代入した整数の偶奇判定 =====
# * xに3を代入してから，xの値の偶奇判定結果を表示する
#   * 2で割った余りがゼロ(2で割り切れる)なら，偶数
    
x = 3

if x % 2 == 0:
    print( "xは偶数" )
else:
    print( "xは奇数" )
```

----
#### 練習問題(Practice)-01: [if-else文] 3の倍数判定

 * (1) xという変数に，好きな100未満の正の整数を代入してください
 * (2) その変数が，3の倍数なら"fizz"，さもなくば，その整数をそのまま，表示してください


- - - -
```python
# ===== [練習問題-01: if-else文] 3の倍数判定 =====
#  * (1) xという変数に，好きな100未満の正の整数を代入してください
#  * (2)その変数が，3の倍数なら"fizz"，さもなくば，その整数をそのまま，表示してください

# ----- (1) -----
x = 33
# ----- (2) -----
if ★★★穴埋め★★★:
    print( "fizz" )
else:
    print( x )
```


----
### Ex_03: if_elif_else分岐 → パターン-03

  * <span style="color: red; ">〈条件式-1〉</span>を評価して<span style="color: red; ">〈真〉(True)のとき</span>は，
    * 〈ブロック-1〉を実行する
  * <span style="color: red; ">さもなくば</span>，
    * <span style="color: red; ">〈条件式-2〉</span>を評価して<span style="color: red; ">〈真〉(True)のとき</span>は，
      * 〈ブロック-2〉を実行する
    * <span style="color: red; ">さもなくば</span>，
      * <span style="color: red; ">〈条件式-3〉</span>を評価して<span style="color: red; ">〈真〉(True)のとき</span>は，
        * 〈ブロック-3〉を実行する
      * <span style="color: red; ">さもなくば</span>，
        * 〈ブロック-4〉を実行する

- - - -
<!--
<img src="fig/01/a-review/06-a-pattern-03-if_elif_else.png" width="200" height="100" alt="06-a-パターン-03-if_elif_else">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/06-a-pattern-03-if_elif_else.png" width="200" height="100" alt="06-a-パターン-03-if_elif_else">

<!--
<img src="fig/01/a-review/06-b-pattern-03-flow-if_elif_else.png" width="200" height="150" alt="06-b-パターン-03-flow-if_elif_else">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/06-b-pattern-03-flow-if_elif_else.png" width="200" height="150" alt="06-b-パターン-03-flow-if_elif_else">


----
#### 例題(Example)-03: [if-elif-else文] 現在(プログラム実行時)の時刻に適した挨拶を表示する

  * (1) 現在(プログラム実行時)の時刻を整数で取得します
    * datetimeモジュールを使用します
      * import 文でモジュールの使用宣言をした後，
      * datetime.datetime.now().hourで現在時刻が取得できます
      * 今のところ，「おまじない」になってしまっているかもしれませんが
        * 追々，詳細を解説していきますので，理解していきましょう


- - - -
  * (2) 現在の時刻を表示します
    * f文字列(書式付き文字列)
      * 文字列の開始引用符の前にfを付けます
        * 文字列中の中括弧内に指定した変数を，その値を展開できます
    　  * 少し，古めの解説などでは，文字列の書式設定には，書式演算子(%)やformat()メソッドを使っていますが，
          * 今では，このf文字列を使った方が読みやすく書きやすいでしょう
          * ちなみに，f文字列のfはformat(書式)に由来します

- - - -
  * (3) 時刻に適した挨拶を表示します
    * 午前3時以前と午後6時以降: こんばんは
    * 午前4時～午前5時: おはようございます．お早いですね
    * 午前6時～午前9時: おはようございます
    * 午前10時～午後5時: こんにちは


----
```python
# ===== [例題-03: if-elif-else文] 

# ----- (1) 現在(プログラム実行時)の時刻を整数で取得します -----
#  * datetimeモジュールを使用します
#    * import 文でモジュールの使用宣言をした後，
#    * datetime.datetime.now().hourで現在時刻が取得できます
import datetime
hour_now = datetime.datetime.now().hour
```

- - - -
```python
# ----- (2) 現在の時刻を表示します -----
#  * f文字列(書式付き文字列)では，
#    * 中括弧内に指定した変数の値を展開できます
print( f"今の時刻は，{hour_now}時です．" )
```

- - - -
```python
# ----- (3) 時刻に適した挨拶を表示します -----
#  * 時刻に適した挨拶
#    * 午前3時以前と午後6時以降: こんばんは
#    * 午前4時～午前5時: おはようございます．お早いですね
#    * 午前6時～午前9時: おはようございます
#    * 午前10時～午後5時: こんにちは
```

- - - -
```python
if hour_now <= 3 or hour_now > 17:
    print( "こんばんは" )
elif hour_now <= 5:
    print( "おはようございます", "お早いですね" )
elif hour_now <= 9:
    print( "おはようございます" )
elif hour_now <= 17:
    print( "こんにちは" )
```

----
#### 練習問題(Practice)-02: [if-elif-else文] fizz/buzz判定

  * (1) xという変数に，好きな100未満の正の整数を代入してください
  * (2) その変数が，3の倍数なら"fizz"，5の倍数なら"buzz"，その両方を満たすなら"fizzbuzz"，いずれでもなければ，その整数をそのまま，表示してください
  * note:
    * 2つの条件式の論理積は，二項演算子andで表現します
      * 「『3の倍数』かつ『5の倍数』」の「かつ」ですね
      * これは，3と5の最小公倍数15を使って，『15の倍数』として表現できます（し，そうした方が若干計算が速くなるときたいできますが）が，
        * あえて，論理積(and)を使ってみてください



- - - -
```python
# ===== [練習問題-01: if-elif-else文] fizz/buzz判定 =====
#  * (1) xという変数に，好きな100未満の正の整数を代入してください
#  * (2) その変数が，3の倍数なら"fizz"，5の倍数なら"buzz"，その両方を満たすなら"fizzbuzz"，いずれでもなければ，その整数をそのまま，表示してください
#  * note:
#    * 2つの条件式の論理積は，二項演算子andで表現します

# ----- (1) -----
x = 30
```

- - - -
```python
# ----- (2) -----
if ★★★穴埋め★★★:
    print( "fizzbuzz" )
elif ★★★穴埋め★★★:
    print( "fizz" )
elif ★★★穴埋め★★★:
    print( "buzz" )
else:
    print( x )
```

----


<a href="./SoftEng-slides-01-a-review-1-b.html"> 次へ ([1] 復習: 制御構造 / [1-b] 反復/ループ (for文)) </a>

</script>
