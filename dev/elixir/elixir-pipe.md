---
tags:
  - dev
  - devlog
  - elixir
created_at: 2023-09-30 10:52
aliases:
---
```elixir
"hello"
|> String.upcase()
|> Kernel.<>("?!")
# => "HELLO?!"
```

- `|>` passes the previous expression as the first argument of the function
