# Ag notes

http://qiita.com/key-amb/items/160754af63ab08b18d8f

* `ag -l <単語>` 指摘した文字列が入ったファイル名のリストだけ表示する
* `ag` + `-Q` + `単語名` -単語を検索
ag -l '富士宮駅' -G '1\d\.tpl$'
ag -l '富士宮駅' -G 'highway' --ignore 'pc'
