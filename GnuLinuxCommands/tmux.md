First exit all tmux sessions. Then create `~/.tmux.conf` and add these lines to have VIM-like shortcuts to change panes:

```
bind h select-pane -L
bind j select-pane -D
bind k select-pane -U
bind l select-pane -R
``` 
