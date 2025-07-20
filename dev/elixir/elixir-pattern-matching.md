---
tags:
  - dev
  - devlog
  - elixir
created_at: 2023-09-30 10:16
aliases:
---
```elixir
defmodule Example do
  def named_function(:a = variable_a) do
    {variable_a, 1}
  end
end

Example.named_function(:a)
# => {:a, 1}

Example.named_function(:b)
# => FunctionClauseError

[head | tail] = [1, 2, 3]
# => head = 1
# => tail = [2,3]

2 = 3
# => MatchError; cannot match 3 to 2
```

- `=/2` is a match operator, not assignment
  - match right to left (think of assigning)
	- pattern on left matches the pattern on the right
- definitely helpful for function clauses
