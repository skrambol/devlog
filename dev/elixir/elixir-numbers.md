---
tags:
  - dev
  - devlog
  - elixir
created_at: 2023-09-29 12:48
aliases:
---
```elixir
integer = 3
float = 3.45

int_to_float = integer * float
float_to_int = trunc(float)
```

- `Integer`, `Float`
- basic arithmetic operations are defined in `Kernel` module
- functions that return boolean should, by convention, end with a `?`; also applies to variables
- `trunc/1` to convert float to int

