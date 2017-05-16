### Tmux Notes
http://www.task-notes.com/entry/20150711/1436583600

## Session
* `tat` - Open tmux for current folder
* `tmux` - start new
* `Ctrl B + d` - 作業している状態を保持したままputtyを終了できる（プログラムは裏で動いたまま） 
* `tmux kill-session -t <session-name>` - kill session
* `tmux a # (or at, or attach)` - attach
* `tmux a -t <session-name>` -  attach to named
* `tmux ls` - list sessions
* `kill session` - tmux kill-session -t <session-name>
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



start new with session name:
    tmux new -s myname

