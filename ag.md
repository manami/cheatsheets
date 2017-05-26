# Ag (the silver searcher) notes

http://qiita.com/key-amb/items/160754af63ab08b18d8f

* `ag -l <単語>` 指摘した文字列が入ったファイル名のリストだけ表示する
* `ag` + `-Q` + `単語名` -単語を検索
ag -l '富士宮駅' -G '1\d\.tpl$'
ag -l '富士宮駅' -G 'highway' --ignore 'pc'

よく使うフラグの説明：
![image](https://cloud.githubusercontent.com/assets/6726985/26495775/d89c4952-425f-11e7-95f8-1d20c86606b4.png)

全てのフラグの説明：
https://github.com/ggreer/the_silver_searcher/blob/master/doc/ag.1.md
