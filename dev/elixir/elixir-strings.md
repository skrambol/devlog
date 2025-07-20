---
tags:
  - dev
  - devlog
  - elixir
created_at: 2023-09-30 10:46
aliases:
---
```elixir
"Hello" <> " World!"
"1 1 2 #{2+1}"
"""
heredoc
example
"""
# => "heredoc\nexample\n"
```

- `<>/2` used to concatenate strings
- `#{}` used in string interpolation
- `""" ... """` heredoc allows for multi line strings
	- interpreted as with `\n`
	- take note of the trailing `\n`
