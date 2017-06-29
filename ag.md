# Ag (the silver searcher) notes

http://qiita.com/key-amb/items/160754af63ab08b18d8f

## Search file
* `ag -g "application/modules/default.*index"`    [.* = 0以上の任意の文字が何個でも入る]
* `ag  <p class="abc"> -G "application/.*"`
* `ag -l <単語>` 指摘した文字列が入ったファイル名のリストだけ表示する
* `ag -l 'abc' -G '1\d\.tpl$'`
* ag -l 'abc' -G 'abcd' --ignore 'pc'
* `ag` + `-Q` + `単語名` -単語を検索

よく使うフラグの説明：
![image](https://cloud.githubusercontent.com/assets/6726985/26495775/d89c4952-425f-11e7-95f8-1d20c86606b4.png)

全てのフラグの説明：
https://github.com/ggreer/the_silver_searcher/blob/master/doc/ag.1.md
