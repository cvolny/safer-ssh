# safer-ssh

A wrapper for ssh to make CanonicalizeHostname and Host blocks' user rules a little safer/more visible.

# Usage:

Copy the script into your local/user's bin, make it executable, then set an alias.
I like to place this in your shell config (bashrc/zshrc):

```
export PATH="$HOME/bin:$PATH"
alias ssh=$HOME/bin/safer-ssh
```
