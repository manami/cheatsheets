### Git

## commitの事後確認　２個前までのcommitを確認
* git log --stat -2

## 他のブランチをmergeする①
* git checkout <something_branch_name>
* git pull origin <something_branch_name>
* git checkout <my_branch_name>
* git merge <something_branch_name>
* fix conflict
* git push origin <my_branch_name>

## 他のブランチをmergeする②
* `git commit <my branch>`
* `git checkout <someone's branch>`
* `git pull`
* `git checkout <someone's branch>`
* `git rebase <someone's branch>`
* `fix conflict`
* `git push origin <my branch>`
* `then someone's branch comes int o my branch`

## 移動とセットでブランチを作成する。
* `git checkout -b <branchname>`

## ブランチを削除する。
* `git branch -d <branchname>`

## 複数ファイルをaddする
ファイルをスペース区切りで複数指定することができる。
* `1. git add readme1.md readme2.md`
http://kimromi.hatenablog.jp/entry/2015/08/04/082357

## ファイル名変更
* `1. ag "/testA/course/am/" -l | xargs sed -i '' -e 's@testA/course/am@testA/course/testB@g'`
* `2. mv am.tpl testB.tpl`
* `※1&2 - testAフォルダーから実行`

## Gitの内側 - Gitの参照
* `cat .git/HEAD` - .git/HEAD にカレントのブランチが記録されている。
* `cat .git/refs/heads/master` - origin リモートの master ブランチを調べる。

## renaming files
* `1. Change file name`
* `2. git add <new-file-name>`
* `3. git rm <old-file-name>`

## moving files
* `1. move third_file.txt to first_directory/third_file.txt`
* `2. git mv third_file.txt first_directory/third_file.txt` - git statusするとrenamedと表示される
* `3. git commit -m "commit message"`

## ファイルを削除
* `1. rm <file-name>` - ファイルを削除
* `2. git commit -m "commit-message"` - ファイルを削除した情報をコミットしてoriginとローカルを一致させる。

## バックアップ
* `mkdir ~/Desktop/application_backup`
* `cp -R application/* ~/Desktop/application_backup/`

## ローカルの内容を消して、リモートブランチに合わせる
* `git stash`
* `git reset origin/<ブランチ名>`
* `git stash pop`

## Junkファイル削除（compiles）
* rm -rf application/modules/default/views/compiles/

## ローカルとリモートブランチを合わせる
* `git fetch`
* `git l origin<branch-name>`
* `git l <branch-name>`
* `※ git lのコミットのログを見て比較する`
* `※ originの方にローカルにないコミットがあったらstashしてpullしないといけない`
* `※ ローカルにoriginにないコミットがある場合はpushしないといけない`

## コンフリクト対応
* `1. git fetch`
* `2. git stash`
* `3. git reset --hard origin/modify-20170711_googlemap修正・おトク追加(飛騨高山)他`
* `4. git stash pop`
* `5. git add .`
* `6. git commit -m "<ブランチ名>"`

## git でローカルの情報を捨てて、リモートの情報を反映、developとマージする
* `1. git checkout .` - 現在のローカルの情報を捨てる
* `2. git remote -v` - remoteのリポジトリをみる
* `3. git fetch` - remoteのリポジトリをfetchする
* `4. git pull origin [branch-name]` - remoteのリポジトリをpullする
* `5. git checkout develop` 
* `6. git pull origin develop`

## pullするときはクリーンな状態（編集中のファイルがない）に必ずする！
## ローカルの変更を捨てて100%クリーンにしてoriginの状態にする
* `git fetch`
* `git reset --hard origin/<ブランチ名>`
* `そのあとは通常通り開発してOK

## ローカルとリポジトリの差分を確認する
* `git diff ローカルのSHA リモートのSHA` 

### ルートディレクトリを起点として拡がるツリー構造：
![directory_picture](http://imgur.com/VblKqZN.jpg)

* `ls ~/Desktop` - 「ホームディレクトリ」内の「デスクトップ」の情報をみる。(チルダ展開)
* `ls /System` - 「ルートディレクトリ」内のシステムの情報をみる

## 絶対パス (ルートディレクトリ（/）から始まる)
* `/Users/Macuser/Downloads/Test.txt` - ホームディクトリ(Macuser)のダウンロード内の「Test.txt」というファイルの絶対パス

## 相対パス (カレントディレクトリから位置を指定する方法)
* `../Dropbox/Test.txt` - ホームディレクトリ（Macuser)のDropboxにある「Test.txt」と言うファイルへの相対パス
