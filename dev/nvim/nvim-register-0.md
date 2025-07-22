---
tags:
  - dev
  - nvim
  - nvim-registers
created_at: 2023-10-17 06:42
---
- register `0` is the last text object you yanked
- this is retained even if you have deleted something with `d` or `x`
- `"0p` in normal mode will paste the last yank

useful in pasting last yank regardless if `d` is used