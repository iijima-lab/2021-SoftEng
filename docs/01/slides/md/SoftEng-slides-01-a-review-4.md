<script type="text/template">


----
### [4] 復習: 関数 (function)→ パターン-09/10
(<a href="#目次"> 目次に戻る </a>)

----
#### 関数定義

<!--
<img src="fig/01/a-review/26-a-pattern-09-function.png" width="300" height="100" alt="26-a-パターン-09-function">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/26-a-pattern-09-function.png" width="300" height="100" alt="26-a-パターン-09-function">

<!--
<img src="fig/01/a-review/26-b-pattern-09-function.png" width="300" height="100" alt="26-b-パターン-09-function">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/26-b-pattern-09-function.png" width="300" height="100" alt="26-b-パターン-09-function">

----
#### 関数: 前提としてのスキル(入門レベル)

  * 「関数」に関して，<span style="color: red; ">前提としてのスキルセット</span>と，<span style="color: red; ">この授業で更に追加されるスキルセット</span>がある
    * 「関数」に関連する概念は奥が深い
    * とりあえずは，入門レベルのスキルセットのみが前提
      * とうことで，「復習」の範囲は...
        * 関数の概念，関数の基本的な定義方法，関数の基本的な利用方法
        * 引数の概念(いわゆる位置パラメータの範囲のみ)
        * 返戻値(リターン値)の概念


- - - -
#### [用語] 関数名: 前提としてのスキル(入門レベル) 

  * <span style="color: red; ">関数名</span>
    * 英字で始まる英数字が推奨されている
      * 英字は小文字のみを使い，複合語の場合，アンダースコア( \_ )で区切るのが推奨されている
        * 文字コードがUTF-8(ユニコード)を前提としているので，漢字なども使えるが，非推奨
          * 我々には，わかりやすいけど，漢字圏でない国が多いので奨められない

- - - -
#### [用語] 引数: 前提としてのスキル(入門レベル) 

  * <span style="color: red; ">引数</span>
    * 「ひきすう」と読む(「いんすう」とは読まない)
      * 「ひきすう」という言葉は，最初のうちは聞き慣れていないかもしれませんが，割とすぐに馴染むようです．
  * <span style="color: red; ">仮引数(formal parameter)</span>
    * 関数定義中で，定義本体部で計算を表現するために，定義頭部で導入される変数名
      * ここでのformalの意味は...
        * 「公式的」，「儀礼的」，「堅苦しい」という意味ではない
        * 「数学的」とか，「論理的」という意味でもない
        * 単に，関数を定義するための「名目的に」「うわべ上」のものといった感じ
    * 単にパラメータ(parameter)というと，仮引数を指すことが一般的
      * この授業でも，混同しない範囲で，そのように使います．

- - - -
  * <span style="color: red; ">実引数(argument)</span>
    * 関数の呼び出し時に，関数へ引き渡される「実際の」値
      * 「実」の部分を強調するときには，actual argumentと呼ぶが...
        * actualを省くことが多く，単に，アーギュメント(argument)というと，実引数を指すことが一般的
        * もっとも，formalとactualの対比で，actual parameterという呼び方もある
    * アーギュメントという言葉は，日本語では聞きなれないので，
      * 混同しない範囲で，実引数のことを指すとも，パラメータで済ませてしまうこともあります
      * 例えば，「関数fに実引数5を引き渡す」ことを，「関数fにパラメータ5を与える」と言うこともよくあります

- - - -
#### [用語] 返戻値: 前提としてのスキル(入門レベル) 

  * <span style="color: red; ">返戻値</span>
    * 関数の返す値のこと
    * 「へんれいち」と読む
      * 返戻値という言葉は聞き慣れないかもしれませんね
        * 文字で書くときは短くてよいけれど，
        * 口で言うときは，リターン・バリューといった方がよく伝わります．

- - - -
#### [用語] 関数の副作用: 前提としてのスキル(入門レベル) 

  * 関数の<span style="color: red; ">副作用(side-effect)</span>
    * 関数は，計算して，返戻値を返すだけでなく，外部に影響を及ぼすこともあります


- - - -
      * 詳しいことは，復習の一環として，追々取りあげますが，
        * <span style="color: red; ">グローバル変数(大域変数)</span>
          * 関数定義の外側(<span style="color: red; ">グローバルスコープ</span>)で初期化された変数
          * グローバル変数の値を，global宣言をしたうえで，変更することもあります
          * グローバル変数の値は，global宣言がなくても，参照はできます
        * <span style="color: red; ">ローカル変数(局所変数)</span>
          * 関数定義の内側(<span style="color: red; ">関数スコープ</span>)で初期化された変数
            * 関数定義の外側では使えない
            * グローバル変数と同じ名前でローカル変数を初期化した
      * 画面表示や，ファイルへの出力もありえます
        * これらも関数の副作用に含まれます

- - - -
    * 副作用の方を主体とする場合もあります
      * その場合，<span style="color: red; ">手続き(procedure)</span>と呼び，定義方法を替えるプログラミング言語もありますが
        * Pythonでは，あえて区別していません．
      * 一方で，副作用を持たない関数を，<span style="color: red; ">純粋(pure)な関数(function)</span>と呼ぶこともあります．

- - - -
#### 関数: 前提としてのスキル(入門レベル)

  * 「関数」の理解
    * 関数という「計算装置」が，「入力として引数を受け取り（引き渡されて），計算作業をして，返戻値を返す」という理解の仕方が一般的かもしれません．
      * 一般的なfunctionの意味は，元々，「機能」とか「作用」ですから，特定の機能を備えた装置と考えるのはわかりやすいでしょう
      * 特に「副作用」を考慮すると，この理解の仕方はピンときます
    * ですが，特に「副作用」を含まず，返戻値のみ期待する，純粋(pure)な関数の場合では，以下のように理解されることもあります
      * 実引数へ関数を適用する(function application)と，返戻値に置き換えられる
      * 数学でいう「写像(mapping)」という意味では，わかりやすいかもしれませんが，副作用の存在が抜け落ちてしまいますね

- - - -
#### 関数: この授業の中で補われるスキル(入門レベル→初級レベル)

  * この授業初級レベルのスキルセットとして，この授業で更に追加される(予定)のもの
    * <span style="color: red; ">キーワード引数(keyword parameter)，デフォールト値，
    * <span style="color: red; ">可変長引数
      * 辞書やタプルを取り上げた後で，取り上げます
    * <span style="color: red; ">高階関数(higher-order function)
      * 関数を引数として渡したり，返戻値として返したりする関数
      * Pythonでは，関数を，一種の「値」(第一級(first-class)オブジェクトと言います)として扱えるので，
        こうした関数が定義・利用できます．
    * <span style="color: red; ">関数閉包(closure)
      * 変数のスコープ(有効範囲)について復習し，高階関数について取り上げた後で，取り上げます

----
### Ex_17: 関数 (function)

#### 関数定義 (function definition)

  * <span style="color: red; ">関数定義</span>
    * <span style="color: red; ">ヘッダ (定義頭部)</span>
      * defで始まり，〈関数名〉と，括弧で囲まれカンマ(,)で区切られた〈仮引数の並び〉と，コロン(:)が続く
    * <span style="color: red; ">ボディ (定義本体)</span>
      * 返戻値があるときは，<span style="color: red; ">return文</span>で指定する
        * returnは，〈文〉であり〈関数〉ではないので，直後の括弧は必要ないが，
        * 私はあえてつけることが多い
          * 但し，タプル(今回は説明しない)を形成する括弧と混同しないように注意

- - - -
#### 例題(Example)-17: [関数] 整数の偶奇判定する関数

  * 整数の偶奇判定する関数を定義する
    * 結果は，文字列で返す

<!--
<img src="fig/01/a-review/28-a-ex-17-code-function.png" width="300" height="100" alt="28-a-例題-17-code-function">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/28-a-ex-17-code-function.png" width="300" height="100" alt="28-a-例題-17-code-function">


----
```python
# ===== [例題-17-a: 関数] 整数の偶奇判定する関数を定義する =====
#  * 整数の偶奇判定する関数を定義する
#    * 結果は，文字列で返す

def judge( x ):
    if x % 2 == 0:
         return( "偶数" )
    else:
         return( "奇数" )
```

- - - -
#### 関数適用 (function application) / 関数呼び出し (function invocation)

<!--
<img src="fig/01/a-review/28-b-ex-17-code-function.png" width="300" height="100" alt="28-b-例題-17-code-function">
-->
<img src="https://iijima-lab.github.io/2021-SoftEng/fig/01/a-review/28-b-ex-17-code-function.png" width="300" height="100" alt="28-b-例題-17-code-function">


----
```python
# ===== [例題-17-b: 関数] 整数の偶奇判定する関数を利用する =====
#  * 整数の偶奇判定する関数を利用する
#    * 結果は，文字列で返される

print( "5は" + judge( 5 ))
```

- - - -
```python
# ===== [例題-17-b: 関数] 整数の偶奇判定する関数を利用する =====
#  * 整数の偶奇判定する関数を利用する
#    * 結果は，文字列で返される

for x in range( 7 ):
    print( str( x ) + "は" + judge( x ) )
```

----
### Ex_18: 関数 (function)

- - - -
#### 関数定義 (function definition)


----
#### 例題(Example)-18: [関数] 偶数か否かを判定する関数を定義する

  * 偶数か否かを判定する関数を定義する
    * 結果はTrue/Falseで返す

- - - -
```python
# ===== [例題-18-a: 関数] 偶数か否かを判定する関数を定義する =====
#  * 偶数か否かを判定する関数を定義する
#    * 結果はTrue/Falseで返す

def is_even( x ):
    return x % 2 == 0
```

- - - -
#### 関数適用 (function application) / 関数呼び出し (function invocation)


```python
# ===== [例題-18-b: 関数] 偶数か否かを判定する関数を利用する =====
#  * 偶数か否かを判定する関数を利用する
#    * 結果はTrue/Falseで返される
```

- - - -
```python
for x in range( 7 ):
    if is_even( x ):
         print( str( x ) + "は偶数" )
    else:
         print( str( x ) + "は奇数" )
```

----
#### 練習問題(Practice)-08-a: [関数]  倍数か否かを判定する関数multiply_by( x, m )を定義する

  * 引数xが，引数mの倍数か否かを判定する関数multiply_by( x, m )を定義する


```python
# ===== [練習問題-08-a: 関数] 倍数か否かを判定する関数を定義する =====
#  * 引数xが，引数mの倍数か否かを判定する関数multiply_by( x, m )を定義する

def multiply_by( x, m ):
    return( ★★★穴埋め★★★ )

# ===== [テスト] =====
print( f"15は3の倍数か? { multiply_by( 15, 3 ) }" )
print( f"15は5の倍数か? { multiply_by( 15, 5 ) }" )
print( f"11は5の倍数か? { multiply_by( 11, 5 ) }" )
```

----
#### 練習問題(Practice)-08-b: [関数]  倍数か否かを判定する関数multiply_by( x, m )を利用する

  * キーボードから，正の整数を読み込み，以下の判定を繰り返して，結果を表示します
    * 3の倍数か
    * 5の倍数か
    * どちらでもないか
  * 正の整数の代わりに，exitもしくはquitと入力すると，ループを終了します


- - - -
```python
# ===== [練習問題-08-b: 関数] 倍数か否かを判定する関数を利用する =====
#  * 引数xが，引数mの倍数か否かを判定する関数multiply_by( x, m )を利用する
#   * キーボードから，正の整数を読み込み，以下の判定を繰り返して，結果を表示する
#    * 3の倍数か
#    * 5の倍数か
#    * どちらでもないか
#  * 正の整数の代わりに，exitもしくはquitと入力すると，
#    * ループを終了する
```

- - - -
```python
print( "入力された正の整数が，3の倍数か5の倍数か，" )
print( "　　　そのどちらでもないか，を判定します" )
print( "  * 正の整数を繰り返し入力してください" )
print( "  * exitもしくはquitが入力されたら，ループを終了する" )
```

- - - -
```python
while True:
    x_str = input( "正の整数> " )
    if x_str == "exit" or x_str == "quit":
        print( "ループを終了する" )
        break
    if x_str.isnumeric():
        x_int = int( x_str )
        if ★★★穴埋め★★★:
            print( f"{x_int}は，3の倍数です" )
        if ★★★穴埋め★★★:
            print( f"{x_int}は，5の倍数です" )
        if ★★★穴埋め★★★:
            print( f"{x_int}は，3の倍数でも5の倍数もありません" )
    else:
        print( "入力エラー: 正の整数ではない" )
```

----
#### 練習問題(Practice)-09-a: [関数] fizz/buzz文字列を返す関数を定義する

  * 以下の関数を定義する
    * 関数fizzbuss_str( x ): 
      * 与えられた正の整数xに対し，fizz/buzz文字列を返す
    * 練習問題-09で定義した関数multiply_by( x, m )を利用してください
  * fizz/buzz文字列とは，以下のように定義します
    * xが3の倍数であり，かつ5の倍数でないなら，"fizz"
    * xが5の倍数であり，かつ3の倍数でないなら，"buzz"
    * xが3の倍数であり，かつ5の倍数であるなら，"fizzbuzz"
    * いずれでもなければ，その正整数そのもの



- - - -
```python
# ===== [練習問題-09-a: 関数定義] 関数を定義する =====
#  * fizz/buzz文字列を返す関数を定義する
#   * 関数fizzbuss_str( x ): 
#     * 与えられた正の整数xに対し，fizz/buzz文字列を返す
#   * 練習問題-09で定義した関数multiply_by( x, m )を利用してください
# * fizz/buzz文字列とは，以下のように定義します
#   * xが3の倍数であり，かつ5の倍数でないなら，"fizz"
#   * xが5の倍数であり，かつ3の倍数でないなら，"buzz"
#   * xが3の倍数であり，かつ5の倍数であるなら，"fizzbuzz"
#   * いずれでもなければ，その正整数そのもの
```

- - - -

```python
def fizzbuss_str( x ):
    if ★★★穴埋め★★★:
        # 3と5の最小公倍数である15の倍数判定でも同等
        return( "fizzbuzz" )
    elif ★★★穴埋め★★★:
        return( "fizz" )
    elif ★★★穴埋め★★★:
        return( "buzz" )
    else:
        return( str( x ) )
```

- - - -

```python
# ===== [テスト] =====
print( f"30のfizz/buzz文字列は: { fizzbuss_str( 30 ) }" )
print( f"20のfizz/buzz文字列は: { fizzbuss_str( 20 ) }" )
print( f"18のfizz/buzz文字列は: { fizzbuss_str( 18 ) }" )
```

----
#### 練習問題(Practice)-09-b: [関数] fizzbuss_str()関数を利用する

  * キーボードから，正の整数を読み込み，そのfizz/buzz文字列を表示することを繰り返します
    * fizzbuss_str()関数を使って下さい
  * 正の整数の代わりに，exitもしくはquitと入力すると，ループを終了します

- - - -
```python
# ===== [練習問題-09-b: 関数] 関数を利用する =====
#  * 引数xが，引数mの倍数か否かを判定する関数multiply_by( x, m )を利用する
#   * キーボードから，正の整数を読み込み，対応するfizz/buzz文字列を表示する
#  * 正の整数の代わりに，exitもしくはquitと入力すると，
#    * ループを終了する
```

- - - -

```python

print( "入力された正の整数に対応するfizz/buzz文字列を表示する" )
print( "  * 正の整数を繰り返し入力してください" )
print( "  * exitもしくはquitが入力されたら，ループを終了する" )
```

- - - -

```python

while True:
    x_str = input( "正の整数> " )
    if x_str == "exit" or x_str == "quit":
        print( "ループを終了する" )
        break
    if x_str.isnumeric():
        x_int = int( x_str )
        print( ★★★穴埋め★★★ )
    else:
        print( "入力エラー: 正の整数ではない" )

```


</script>

