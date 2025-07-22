---
tags:
  - dev
  - devlog
  - elixir
created_at: 2023-09-29 16:09
---
```elixir
cond do
  x > 10 -> :this_might_be_the_way
  y < 7 -> :or_that_might_be_the_way
  true -> :this_is_the_default_way
end
```

- similar to normal switch case
- enters every branch as long as condition is true

useful for creating if-else but multiple passthrough in elixir
