<script type="text/template">


----
### [2] 復習: 入出力 (I/O; input/output) → パターン-06
(<a href="#目次"> 目次に戻る </a>)

- - - -
<!--
<img src="fig/01/a-review/17-a-pattern-06-input.png" width="200" height="100" alt="17-a-パターン-06-input">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/17-a-pattern-06-input.png" width="200" height="100" alt="17-a-パターン-06-input">

- - - -
### [2-a] input関数
(<a href="#目次"> 目次に戻る </a>)

----
### Ex_11: input関数 / print関数

   * <span style="color: red; ">標準入出力</span> (ターミナル・ウィンドウ / Windowsならコマンド・プロンプト)
     * 標準入力 (キーボード入力)
       * <span style="color: red; ">input関数</span>
     * 標準出力 (コンソール出力 / 画面出力)
       * <span style="color: red; ">print関数</span>

----
#### 例題(Example)-11: [input関数]   基本的な使い方

  * 標準入力 (キーボード入力)から，文字列を受け取ります
    * input関数の引数は，入力を促すために，表示される文字列です
      * プロンプト・メッセージないし入力促進文字列と言います
    * input関数の返戻値(返す値)は，入力された文字列です



- - - -
```python
# ===== 例題(Example)-11: [input関数] 基本的な使い方 ====
# * input関数の基本的な使い方
#   * 標準入力 (キーボード入力)から，文字列を受け取る

x = input( "何か文字列を入力してください: " )
print( "入力されたのは" + x )
```


----
### Ex_12: input関数 / print関数


- - - -
#### 例題(Example)-12: [input関数/for文]  ループの回数をキーボードから入力する

  * input関数の返戻値は文字列(str)なので
    * 数値として利用するには，整数(int)へ変換する必要があります
      * int( 文字列 )で変換します

- - - -
```python
# ===== [例題-12: [input関数/for文] ループの回数をキーボードから入力する ====
# * input関数の返戻値は文字列(str)なので
#   * 数値として利用するには，整数(int)へ変換する必要がある
#     * int( 文字列 )で変換する

x = input( "1桁の整数を入力してください: " )
for y in range( int( x ) ):
    print( y )
```

----
#### 練習問題(Practice)-06: [input関数/while文] 必要な個数の正整数データを入力する

  * 正の整数の入力を繰り返して，表示する
    * 正の整数以外のものが入力されたら，エラー表示する
    * exitもしくはquitが入力されたら，ループを終了する
    * 事前にデータ数がわからないときは，
      * for文ではなく，while文がふさわしい

- - - -
```python
# ===== [練習問題-06: input関数/while文] 必要な個数の正整数データを入力する ====
# * 正の整数の入力を繰り返して，表示する
#   * 正の整数以外のものが入力されたら，エラー表示する
#   * exitもしくはquitが入力されたら，ループを終了する
#   * 事前にデータ数がわからないときは，
#     * for文ではなく，while文がふさわしい

print( "正の整数を繰り返し入力してください" )
print( "　　exitもしくはquitが入力されたら，ループを終了する" )
```

- - - -
```python
while ★★★穴埋め★★★:
    x_str = input( "正の整数> " )
    if x_str == "exit" or x_str == "quit":
        print( "ループを終了する" )
        ★★★穴埋め★★★
    if ★★★穴埋め★★★:
        x_int = int( x_str )
        print( f"入力された{ x_int }" )
    else:
        print( "入力エラー: 正の整数ではない" )
```

----


<a href="./SoftEng-slides-01-a-review-3.html"> 次へ ([3] 復習: データ構造 / リスト ) </a>

</script>

