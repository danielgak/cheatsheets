# tmux

### Config

```bash
# ~/.tmux.conf

set-option -g prefix2 C-a

set -g base-index 1
```

### Create and manage sessions

```bash
tmux source-file ~/.tmux.conf # sourcing
tmux ls # list
tmux new -s cool # new named session
tmux rename-session not-cool # rename
tmux a -t not-cool # attach
tmux kill-session -t not-cool # delete session
tmux swi -t other # switching session
```


### Moving 

Use prefix `ctrl+a` or `ctrl+b`

```bash
prefix ? # list all shorcuts
prefix d # detach
prefix s # list sessions
prefix $ # name session
prefix t # big clock
prefix : # prompt

# Windows

prefix c # create window
prefix w # list windows
prefix n # next window
prefix p # previous window
prefix f # find window
prefix , # name window
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