---
tags:
  - dev
  - apt
created_at: 2025-07-18 07:14
aliases:
---
## Problem
trying to search if java is installed in wsl2. tried doing `apt search jdk` but the output is a long list

## Solution
- `apt list --installed <query>`
- based on [stackexchange answer](https://unix.stackexchange.com/a/306951)

useful in searching only installed apt packages