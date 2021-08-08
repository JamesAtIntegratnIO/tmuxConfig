# My TMUX Config

This setup requires [tmuxp](https://github.com/tmux-python/tmuxp). Follow the
directions there to install it.

* Link `tmux.conf.symlink` to `~/.tmux.conf`

* Link the files in `./tmuxp` into `~/.tmuxp/`

## Tmux cheet sheet

### Shell commands

```shell
tmux new-session -s ${sessionName}              # Create new named session 
```

### Must learn leader commands

```
leader- s                                       # List sessions
leader- $                                       # rename current sessoin
```
