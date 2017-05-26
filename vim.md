# Vim notes

## Surround Vim
http://motw.mods.jp/Vim/surround.html

* `yss'` - 文章全体にシングルクウォート y(yank)s(surround)s(sentence)
* `ds'` - 文章全体のシングルクウォートを削除 d(delete)s(surround)
* `vl(選択したい箇所まで)S'` - 選択した箇所にシングルクウォート
* `di'` - シングルクウォート内を削除 d(delete)i(inside)
* `cs'"` - シングルクウォートをダブルクウォートに変える c(change)s(surround) 
* `ysiw'` - カーソルがある単語を’で囲む y(yank)s(surrond)iw(inner word)
* `ci'` - c(change)i(inside)

## 画面整理
* `Ctrl + P => Ctrl + v` - Open selected file in vertical split
* `Ctrl + P => Ctrl + x` - Open selected file in horizontal spli
* `Ctrl + x` - 上下に画面
* `ggVG` - 行を揃える

## 変換
* `ci'` - Change inside '' * `ci"` - Change inside ""
* `ci<` - Change inside <>
* `cc` - Change entire line
* `yt> + Ctrl + v + 6J + Shift I + Command V + Escape + .` - Change multiple lines

説明：
![2017-05-15 22 37 23](https://cloud.githubusercontent.com/assets/17440627/26060157/238ae4c2-39bf-11e7-92ee-eaf2a1d792c0.jpg)

## 検索コマンド
* `Ctrl + P` - Open file search window
* `Ctrl + n` - Search css property 

## 移動系コマンド
* `+` - 下の行の先頭へ
* `-` - 上の行の先頭へ
* `gj` - 下へ一つ
* `gk` - 上へ一つ
* `Ctrl + o` - 場所だけ過去に戻る
* `Ctrl + i` - 場所だけ進む
* `Shift + J` -スペースあり連結 * `g + Shift + J` -スペースなし連結 * `5J` -5行一度にスペースあり連結 * `5gJ` -5行一度にスペースなし連結
* `Ctrl + u` - 上にスクロール
* `Ctrl + d` - 下にスクロール
* `Ctrl + G` -場所を記憶
* `数値 + G` -記憶済みの数値行へジャンプ
* `tree -L <number>` - <number>までtreeを表示する

## 削除
* `Shift + C` - delete all sentence from the key
* `rm -rf temp-dir` - ディレクトリを内部のファイルごと削除
* `dw` -カーソルが存在する位置以降の単語を単語の最後の空白も含めて削除する
* `de` -カーソルが存在する位置以降の単語を単語の最後の空白も含めず削除する
* `:e!` - 保存した場所へ

## 空白削除コマンド
* `g/~ *$/d` - 空白行を削除
* `%s/^ *$//gc` - 半角空白で構成されている行の空白だけ削除
* `%s/ *$//gc` - 行末の空白を削除 

## 検索
* `/` -前の文字を検索 * `?` -後の文字を検索
* `/\(hoge\|huga\)` -複数の文字を検索
* `set hlsearch` -検索した箇所にハイライト * `set hls is` -した箇所にハイライト 
* `%s/old/new/g` -１行内でマッチした文字列すべてを置換
* `set ic` -大文字・小文字を無視 * `set noic` -大文字・小文字を無視を無効
* `Ag + `name`` -cssファイルを探す
* `Ag` + `-g` + `単語名` -単語を検索
* `Ag -Q <単語>` 正規表現使わないで単語を探す
* `スペース` + `e`  -同じパスのファイル名まで指定して開く

## コピー
* `yi"` - Yank inside "" (コピー)
* `yw` - 単語1語をコピー
* `"_D` - コピーした単語をレジスタに保存、削除して、履歴を残さない

## ペースト
* '0v$hy' - /nを除いて１行コピーする
* [レジスタ使い方](http://qiita.com/0829/items/0b3f63798b6910623efc)
* [レジスタ参"_d{motion} ブラックホールレジスタ レジスタに影響しない
* 'ayiw' - レジスタaに単語を登録
* 'ap' - レジスタaの単語をpaste
* 'P' - さっきのレジスタを貼り付ける

# 動き：
![2017-05-15 22 43 42](https://cloud.githubusercontent.com/assets/17440627/26060426/01d31de4-39c0-11e7-9785-187f960b1143.jpg)

# リプレイス：
```
ag '期間H' -G '(highway|otoku)' -l | xargs sed -iE 's/期間H/期間 : H/g' {}

```

・sed [コマンドオプション] '[範囲指定] s/[置換対象文字列]/[置換後文字列]/g' [入力ファイル]
(sedコマンド    スクリプトを直接記述[-e] : 入力ファイルを編集[-i] ※[-i]がない場合は標準出力に書かれる)

・xargs - 前のコマンド(コマンド1)で取得した値(標準出力)を利用してxargsで指定した別のコマンド(コマンド2)に引数として渡して実行させる事ができるコマンド
※引数を標準入力から与えるときに使う
(オプション      -E【文字列】:【文字列】をファイル終端文字として設定する。【文字列】が登場したら、それ以降の入力は無視する。)
```
コマンド1 | xargs コマンド2

``
*[インフラエンジニアなら覚えておきたいxargs](https://orebibou.com/2015/07/%E3%82%A4%E3%83%B3%E3%83%95%E3%83%A9%E3%82%A8%E3%83%B3%E3%82%B8%E3%83%8B%E3%82%A2%E3%81%AA%E3%82%89%E8%A6%9A%E3%81%88%E3%81%A6%E3%81%8A%E3%81%8D%E3%81%9F%E3%81%84%E3%80%8Exargs%E3%80%8F/)
(オプション      -I:引数の値を明示的に利用する
                    通常、ただxargsでコマンドを指定した場合、渡された引数はそのまま処理されるが、例えばファイル名の末尾に何か文字列を付け加えたりしたい事もあるだろう。
                    そんなときは、「-I」オプションを使用し、コマンドで引数を明示的に使用すればいい。通常は、「{}」で引数の使用を表している。

```
                    コマンド1 | xargs -I{} コマンド2 {}

```
例えば「/work」フォルダ配下にあるファイルに対し、元のファイル名の後ろに「.bk」という文字列を付け足してコピーする場合、以下のようにする。

```

find /work -type f | xargs -t -I{} cp {} {}.bk

```

*[複数のファイルに対して特定の言を一気に置き換えする方法](http://qiita.com/fnobi/items/6761eb7c64ab1b0d98eb)
http://www.atmarkit.co.jp/ait/articles/1610/13/news015.html
*[sedによる文字列操作](http://ni66ling.hatenadiary.jp/entry/20141227/1419661468)

# sedコマンド :
* `-e` - スクリプトを直接記述
* `-i` - 入力ファイルを編集
* `-p` - xargsで生成したコマンドを本当に実行するかどうかを確認させる
* `-t` - xargsで指定されたコマンドの実行内容を表示させる
