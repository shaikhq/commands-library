# Useful Shell Commands

# tmux (a tool equivalent to screen)
__create a session__
```shell
tmux new-session -s mysession
```
__detach from a session__
`Ctrl+b` followed by `d`

__list sessions__
```shell
tmux ls
```
__attach to a session__
```shell
tmux attach -t [session id]
```
__kill a session__
```shell
tmux kill-session -t [session id]
```
