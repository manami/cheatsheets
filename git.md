### Git

## ファイル名変更
* `1. ag "/testA/course/am/" -l | xargs sed -i '' -e 's@testA/course/am@testA/course/testB@g'`
* `2. mv am.tpl testB.tpl`
* `※1&2 - testAフォルダーから実行`

## バックアップ
* `mkdir ~/Desktop/application_backup`
* `cp -R application/* ~/Desktop/application_backup/`

## ローカルの内容を消して、リモートブランチに合わせる
* `git stash`
* `git reset origin/<ブランチ名>`
* `git stash pop`

## ローカルとリモートブランチを合わせる
* `git fetch`
* `git l origin<branch-name>`
* `git l <branch-name>`
`※ git lのコミットのログを見て比較する
※ originの方にローカルにないコミットがあったらstashしてpullしないといけない
※ ローカルにoriginにないコミットがある場合はpushしないといけない`

## コンフリクト対応
* `1. git fetch`
* `2. git stash`
* `3. git reset --hard origin/modify-20170711_googlemap修正・おトク追加(飛騨高山)他`
* `4. git stash pop`
* `5. git add .`
* `6. git commit -m "<ブランチ名>"`

## pullするときはクリーンな状態（編集中のファイルがない）に必ずする！
## ローカルの変更を捨てて100%クリーンにしてoriginの状態にする
* `git fetch`
* `git reset --hard origin/<ブランチ名>`
* `そのあとは通常通り開発してOK

## ローカルとリポジトリの差分を確認する
* `git diff ローカルのSHA リモートのSHA` 

### 動き：
!(https://do-zan.com/wp-content/uploads/2016/01/6ff83de97010e92e21e3794e0aacfda0.png)

