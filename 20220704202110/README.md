# manage clipboard through ssh

## Situation

I run a linux VM and ssh to it through my host machine (windows or mac), inside that ssh I run tmux and also my whole workflow

## Problem

I can't copy from inside tmux or vi and get that content on the host machine to paste on another applications

## Solution

I have three scripts(stoled from rob)
- [ppp](https://github.com/rwxrob/dot/blob/main/scripts/ppp)
- [yyy](https://github.com/rwxrob/dot/blob/main/scripts/yyy)
- [ddd](https://github.com/rwxrob/dot/blob/main/scripts/ddd)

So basically with this scripts I just use magicwands in vi to pipe that content to a tmp buf (https://rwx.gg/tools/editors/vi/how/magic/)

For tmux I just insert this binding to create the same pipe on copy mode:

```
bind -T copy-mode-vi 'C-Space' send-keys -X copy-pipe-and-cancel 'yyy'
```

On my host machine I run: `ssh <name-host-ssh-machine> 'ppp'` and boom, my content is just available 🤯🤯🤯🤯🤯
