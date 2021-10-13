<script type="text/template">

----
### [1-c] 反復/ループ (while文)
(<a href="#目次"> 目次に戻る </a>)

  * <span style="color: red; ">while文</span>は，<span style="color: red; ">〈条件〉</span>が成り立っている間，<span style="color: red; ">〈反復実行ブロック〉</span>を繰り返し実行する構文である

----
#### → 参考リンク: while文

  * ドキュメント: [while文](https://docs.python.org/ja/3/reference/compound_stmts.html#the-while-statement)

----
### Ex_09: whileループ (while_loop) → パターン-05

<!--
<img src="fig/01/a-review/14-a-pattern-05-while.png" width="200" height="100" alt="14-a-パターン-05-while">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/14-a-pattern-05-while.png" width="200" height="100" alt="14-a-パターン-05-while">

- - - -
  * 以下のfor文と同様の挙動を，while文で書いてみましょう

<!--
<img src="fig/01/a-review/15-b-ex-09-code-while.png" width="150" height="80" alt="15-b-例題-09-code-while">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/15-b-ex-09-code-while.png" width="150" height="80" alt="15-b-例題-09-code-while">

<!--
<img src="fig/01/a-review/15-c-ex-09-flow-while.png" width="200" height="150" alt="15-c-例題-09-flow-while">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/15-c-ex-09-flow-while.png" width="200" height="150" alt="15-c-例題-09-flow-while">


----
#### 例題(Example)-09: [while文]  0～4までのループ回数を，順に表示する

  * 0～4までのループ回数を，順に表示する

- - - -
```python
# ===== [例題-09: while文] 0～4までのループ回数を，順に表示する =====
# * 0～4までのループ回数を，順に表示する

x = 0
while x < 5:
    print( x )
    x += 1  
```

----
### Ex_10: whileループ (while_loop)

<!--
<img src="fig/01/a-review/16-b-ex-10-flow-while.png" width="200" height="150" alt="16-b-例題-10-flow-while ">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/16-b-ex-10-flow-while.png" width="200" height="150" alt="16-b-例題-10-flow-while ">

----
#### 例題(Example)-10: [while文/break文]  0～4までのループ回数を，順に表示する

  * 0～4までのループ回数を，順に表示する
    * 制御変数を増やしていく無限ループから，
      * 制御変数が5になったときに脱出する
  * <span style="color: red; ">無限ループ</span>を作るには，while文の条件式をTrueにすればよい

- - - -
```python
# ===== [例題-10: while文]  =====
# * 0～4までのループ回数を，順に表示する
#   * 制御変数を増やしていく無限ループから，
#     * 制御変数が5になったときに脱出する
# * 無限ループを作るには，while文の条件式をTrueにすればよい
```

- - - -
```python
x = 0
while True:
    if x == 5:
        break
    print( x )
    x += 1
```

----
#### 練習問題(Practice)-05: [while文] 二乗したときに50未満となるような整数列

  * 0から始めて，二乗したときに50未満である間，整数を表示する
  * <span style="color: red; ">線形探索パターン</span>
    * 二乗したときに50未満になる最大の整数を探索することにも相当する
  * <span style="color: red; ">for文とwhile文の使い分け</span>
    * for文を使うとき
      * 基本的にループの回数や，制御変数の変化する系列が事前にわかっているとき
    * while文を使うとき
      * ループを実行してみないと，ループ回数などが事前にわからないときなど
      * もちろん，この練習問題に限って言えば
        * 平方根を計算し，小数点以下を切り捨てることで，ループ回数は事前にわかりますが...

----
```python
# ===== [練習問題-05: while文] 二乗したときに50未満となるような整数列 =====
# * 0から始めて，二乗したときに50未満である間，整数を表示する
# * 線形探索パターン
#   * 二乗したときに50未満になる最大の整数を探索することにも相当する

x = 0
while ★★★穴埋め★★★:
    print( x, x ** 2 )
    x += 1
```

----


<a href="./SoftEng-slides-01-a-review-2.html"> 次へ ([2] 復習: 入出力 (I/O; input/output)) </a>

</script>

