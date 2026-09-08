# safer-ssh

A wrapper for ssh to make CanonicalizeHostname and Host blocks' user rules a little safer/more visible.

# Usage:

Copy the script into your local/user's bin, make it executable, then set an alias.
I like to place this in your shell config (bashrc/zshrc):

```
export PATH="$HOME/bin:$PATH"
alias ssh=$HOME/bin/safer-ssh
```

## New Connections:

```
% ssh dc01
safer-ssh ==> FIRST TIME for dc01 -> root@dc01.example.com (192.168.1.2)
connect? [y/N] y
root@dc01 $
```

## Repeat Connections (nothing changes; no prompt):

```
% ssh dc01
root@dc01 $
```

## Repeat Connections (a change; prompt):

```
# when a different fqdn
% ssh dc01
safer-ssh ==> CHANGED: dc01 was apache@dc01.example.com (192.168.1.2)
safer-ssh ==> CURRENT: dc01 now apache@dc01.different.net (192.168.1.2)
connect? [y/N]

# when a different ip address
% ssh dc01
safer-ssh ==> CHANGED: dc01 was apache@dc01.example.com (192.168.1.2)
safer-ssh ==> CURRENT: dc01 now apache@dc01.example.com (192.168.2.2)
connect? [y/N]

# when a different username
% ssh dc01
safer-ssh ==> CHANGED: dc01 was apache@dc01.example.com (192.168.1.2)
safer-ssh ==> CURRENT: dc01 now root@dc01.example.com (192.168.1.2)
connect? [y/N]
```
