---
tags:
  - dev
  - devlog
  - elixir
created_at: 2023-09-30 09:42
aliases:
---
```elixir
def number(n \\ 13)
def number(n) when n < 10, do: "Dream bigger!"
def number(n) when n > 100, do: "Not that big..."
```

- elixir functions can be redefined multiple times given a different clause or arguments
- they can also have guard claues `when n < 10`
- function arguments can have default values denoted by `\\`
- function with multiple clauses and a default value should declare a function header (function with no body; like in example)
- order of declaration matters, whichever pattern/clause is matched that will be the executed function

useful when pattern matching the parameters to the clauses
