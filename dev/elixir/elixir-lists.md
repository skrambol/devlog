---
tags:
  - dev
  - devlog
  - elixir
created_at: 2023-09-29 14:46
---
```elixir
list = [1, 2, 3, 4]

# [1] represented in [head | tail] notation
[1 | []]

# [1, 2, 3] represented in [head | tail] notation
[1 | [2 | [3 | []]]]
```

- (linked) lists can hold any type
- each list can be deconstructed in `[head | tail]` where `head` is the first element and tail is the trailing elements
	- `tail` can be blank if list is one element only

useful in remembering `[head | tail]` for elixir lists
