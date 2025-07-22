---
tags:
  - dev
  - devlog
  - elixir
created_at: 2023-09-29 14:01
---
```elixir
function_variable = fn param ->
  param + 1
end

variable = &(&1 + 1)

function_variable.(6)
variable.(9)
```

- `fn` keyword for anonymous functions
- `&` shorthand for declaring anonymous functions, access params by `&1` etc
- `.` dot operator is used to invoke the anonymous function.
	- also to avoid ambiguity between `def`ined functions and anonymous functions [*](https://elixirforum.com/t/why-do-we-use-a-dot-to-call-a-function/8210/5)

useful for anonymous function declaration and invoke in elixir
