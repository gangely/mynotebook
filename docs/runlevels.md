Runlevels
==
about: changing runlevel with systemd commands
## rescue (single user mode)
warning: in single user mode
- a *single* tty terminal (use `tmux`)
- network is *down* (NO SSH)

### boot in single-user mode 
edit temporarily `linux ..` GrUB entry and add at the end of line:
```
[linux ..] systemd.unit=rescue.target
```
### switch to rescue.target
```
systemctl isolate rescue.target
```



## multi-user
### boot in multi-user mode
edit temporarily 'linux ..' GrUB entry and add at the end of line:
```
[linux ..] systemd.unit=multi-user.target
```

### switch to multi-user.target
```
systemctl isolate multi-user.target
```

