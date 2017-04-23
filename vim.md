### Vim notes

## 画面整理
* `Ctrl + P => Ctrl + v` - Open selected file in vertical split
* `Ctrl + P => Ctrl + x` - Open selected file in horizontal spli
* `Ctrl + x` - 上下に画面
* `ggVG` - 行を揃える

## 変換
* `ci'` - Change inside '' * `ci"` - Change inside ""
* `ci<` - Change inside <>
* `cc` - Change entire line

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

## 削除
* `Shift + C` - delete all sentence from the key
* `rm -rf temp-dir` - ディレクトリを内部のファイルごと削除
* `dw` -カーソルが存在する位置以降の単語を単語の最後の空白も含めて削除する
* `de` -カーソルが存在する位置以降の単語を単語の最後の空白も含めず削除する

## 検索
* `/` -前の文字を検索 * `?` -後の文字を検索
* `/\(hoge\|huga\)` -複数の文字を検索
* `set hlsearch` -検索した箇所にハイライト * `set hls is` -した箇所にハイライト 
* `%s/old/new/g` -１行内でマッチした文字列すべてを置換
* `set ic` -大文字・小文字を無視 * `set noic` -大文字・小文字を無視を無効
* `Ag + `name`` -cssファイルを探す


## コピー
* `yi"` - Yank inside "" (コピー)
* `yw` -単語1語をコピー
