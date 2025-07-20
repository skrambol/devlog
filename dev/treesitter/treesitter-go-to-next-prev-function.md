---
tags:
  - dev
  - nvim
  - treesitter
  - navigation
created_at: 2023-09-27 12:31
aliases:
  - "2023-09-27"
---
with treesitter, it is possible to navigate the code by going to the next/previous function or method

`[m` goes to the start of the previous function (will go to current one if cursor is inside a function)
`]m` goes to the start of the next function

useful when navigating codebase via its functions