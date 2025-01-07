# tmux

### Config

```bash
# ~/.tmux.conf

set -g @plugin 'tmux-plugins/tmux-resurrect'
set -g @plugin 'tmux-plugins/tmux-continuum'

set -g mode-keys emacs
set -g status-keys emacs

set -g mouse on # scrolling

set-option -g prefix2 C-a
set -g @continuum-restore 'on'

set -g base-index 1

# status bar black and white

set -g default-terminal "screen-256color"

set -g status-bg black
set -g status-fg white
```

Do not forget to source and installing
```bash
tmux source-file ~/.tmux.conf # sourcing
set-window-option mode-keys emacs

prefix I #  installing 
```

### Create and manage sessions

```bash
tmux ls # list
tmux new -s cool # new named session
tmux rename-session not-cool # rename
tmux a -t not-cool # attach
tmux kill-session -t not-cool # delete session
tmux swi -t other # switching session
```


### Moving 

Use prefix `ctrl+a` or `ctrl+b`

All `tmux` commands like `ls`can be run using the `:` eg. `prefix : ls`

```bash
prefix ? # list all shorcuts
prefix d # detach
prefix s # list sessions
prefix $ # name session
prefix t # big clock
prefix : # prompt

# Scroll

prefix [ # enables scroll mode, q to quit

# Windows

prefix c # create window
prefix w # list windows
prefix n # next window
prefix p # previous window
prefix f # find window
prefix , # name window
swap-window -t server # swaps windows order
prefix & # kill window

# Splits

prefix % # vertical split
prefix \" # horizontal split 
prefix o # swap panes
prefix q # show pane numbers
prefix x # kill pane
prefix + # break pane into window 
prefix - # restore pane from window
prefix <space> # layouts toggle 
prefix q # Show pane 
prefix { # (Move the current pane left)
prefix } # (Move the current pane right)
prefix z # toggle pane zoom
```
