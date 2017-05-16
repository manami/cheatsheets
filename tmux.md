### Tmux Notes
http://www.task-notes.com/entry/20150711/1436583600

Open tmux for current folder:

    tat

start new:

    tmux

start new with session name:

    tmux new -s myname

attach:

    tmux a  #  (or at, or attach)

attach to named:

    tmux a -t <session-name>

list sessions:

    tmux ls

kill session:

    tmux kill-session -t myname

Kill all the tmux sessions:

    tmux ls | grep : | cut -d. -f1 | awk '{print substr($1, 0, length($1)-1)}' | xargs kill

## Session
* `tat` - Open tmux for current folder
* `Ctrl B + d` - 作業している状態を保持したままputtyを終了できる（プログラムは裏で動いたまま） 
* `tmux kill-session -t <session-name>` - 直近にアタッチしていたセッションを削除
* `tmux a -t <session-name>` -  既に作成されたアタッチに入ること

## Window
* `Ctrl B + n` - Go to next window
* `Ctrl B + p` - Go to previous window
* `Ctrl B + z` - Zoom
* `Ctrl B + c` - New window
* `tmux a -t <session-name>` - New window
* `Ctrl B + w` - choose window 
* `Ctrl B + ,` - windowに名前をつける 
* `Ctrl B + &` - tmux内のウィンドウを削除を逆順移動
* `exit` - delete window
* `&` - delete window (forced termination)

## Pane
* `Ctrl B + %` - Vertical split pane
* `Ctrl B + "` - Horizontal split pane
* `Ctrl B + x` - Delete pane
* `Ctrl B + !` - Break pane



