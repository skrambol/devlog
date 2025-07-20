---
tags:
  - dev
  - nvim
  - treesitter
  - selection
created_at: 2023-09-27 12:05
aliases:
  - "2023-09-27"
---
it is possible to select (visual mode) the treesitter node
```lua
incremental_selection = {
  enable = true,
  keymaps = {
  init_selection = '<C-space>',
  node_incremental = '<C-space>',
  scope_incremental = '<C-s>',
  node_decremental = '<M-space>',
},
```

it goes like `variable -> expression/line -> outer scope (if-block, function)`

useful when moving/deleting a whole function