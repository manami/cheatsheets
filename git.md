###Git

##ファイル名変更
* 1`ag "/highlights/course/am/" -l | xargs sed -i '' -e 's@highlights/course/am@highlights/course/turner@g'`
* 2`mv am.tpl turner.tpl`
※1,2ともにhighlightsフォルダーから実行

##バックアップ
mkdir ~/Desktop/application_backup
`cp -R application/* ~/Desktop/application_backup/`

## ローカルの内容を消して、リモートブランチに合わせる
* git stash
* git reset origin/<ブランチ名>
* git stash pop

## ローカルとリモートブランチを合わせる
* git fetch
* git l origin<branch-name>
* git l <branch-name>
* git lのコミットのログを見て比較する
 * originの方にローカルにないコミットがあったらstashしてpullしないといけない
 * ローカルにoriginにないコミットがある場合はpushしないといけない

## コンフリクト対応
1. git fetch
2. git stash
3. git reset --hard origin/modify-20170711_googlemap修正・おトク追加(飛騨高山)他
4. git stash pop
5. git add .
6. git commit -m "<ブランチ名>"

## プールするときはクリーンな状態（編集中のファイルがない）じゃないといけない!!!!!!!!!!!
## ローカルの変更を捨てて100%クリーンにoriginの状態にする
* git fetch
* git reset --hard origin/<ブランチ名>
* そのあとは安心して開発していい（いつもの通り）

## ローカルとリポジトリの差分を確認する
git diff ローカルのSHA リモートのSHA 
