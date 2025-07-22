---
tags:
  - dev
  - shell
  - find
created_at: 2023-09-29 17:36
---
## Problem
- looking for a way to remove the `.git` since the directory is included in the tmux-sessionizer
- tried looking in `man` by searching for "exclude" and "ignore" but no dice

## Solution
- ended up with google search "linux find command ignore" and found [this answer](https://superuser.com/a/397325)
- looking back, it `!` is included in the man page under operators

useful in excluding a file/directory from `find`