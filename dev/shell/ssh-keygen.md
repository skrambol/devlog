---
tags:
  - dev
  - ssh
created_at: 2025-07-18 07:14
aliases:
---
## Problem
every time there is a new setup, a new SSH key must be created for GitHub
i should have memorized it by now

## Solution
- here are the steps to create SSH key
	- generate key `ssh-keygen -t ed25519 -C "email"`
	- run ssh-agent `eval $("ssh-agent")`
- to save to GitHub, `cat /path/to/ssh_key.pub` copy and put GitHub keys

useful in generating SSH keys for GitHub