---
tags:
  - dev
  - devlog
  - elixir
created_at: 2023-09-30 10:13
aliases:
---
```elixir
empty_tuple = {}
one_element_tuple = {1}
multiple_element_tuple = {1, :a, "hello"}

elem(multiple_element_tuple, 2)
# => "hello"
```

- tuples can hold any type but fixed number of items
- `elem/2` to get the element; 0-indexing
- modifying a tuple is costly since the existing tuple needs to be created again
