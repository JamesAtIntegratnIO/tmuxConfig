# My TMUX Config

This setup requires [tmuxp](https://github.com/tmux-python/tmuxp). Follow the
directions there to install it.

## Hard Way

* Link `tmux.conf.symlink` to `~/.tmux.conf`
* Link the files in `./tmuxp` into `~/.tmuxp/`

## Easy Way
* run `./boostrap.sh`

## Setup tmux and vim for 256color and italic

### Create `xterm-256color-italic.terminfo`
```
xterm-256color-italic|xterm with 256 colors and italic,
  sitm=\E[3m, ritm=\E[23m,
  use=xterm-256color,]]
```

### Create `xterm-256color.terminfo`
```
tmux-256color|tmux with 256 colors,
  ritm=\E[23m, rmso=\E[27m, sitm=\E[3m, smso=\E[7m, Ms@,
  khome=\E[1~, kend=\E[4~,
  use=xterm-256color, use=screen-256color,
```

### Install them
```
$ tic -x xterm-256color-italic.terminfo
$ tic -x tmux-256color.terminfo
```

### Configure tmux

Add this to your `~/.tmux.conf` (I've done this for you)
```
set -g default-terminal 'tmux-256color'
set -as terminal-overrides ',xterm*:Tc:sitm=\E[3m'
```

### Configure vim
Add this to your `~/.vimrc`. (If you are using mine then I've done this as well)
```
let &t_8f="\<Esc>[38;2;%lu;%lu;%lum"
let &t_8b="\<Esc>[48;2;%lu;%lu;%lum"
set termguicolors
```

### Configure ssh alias
Add this to your `~/.bashrc` or `~/.zshrc`
```
alias ssh='TERM=xterm-256color ssh'
```
