---
tags:
  - dev
  - devlog
  - elixir
created_at: 2023-09-29 11:55
aliases:
---
```elixir
defmodule Calculator do
    @magic_number 1337
    def add(x, y) do
        x + y
    end

    # returns an error if invoked outside of this module
    defp private_subtract(x, y), do: x - y
end
```

- all named functions must be inside a module
- functions inside a module are available to other modules, but still needs to be prefixed by module name if different module
- last expression are implicitly returned
- `def` used to define function, `defp` private usable only inside same module
- one liner is also possible, take note of comma
- function "arity", the number of argument it accepts
- use PascalCase when naming modules, snake_case for functions (might end with ? or !)
- `@name val` - module attributes; think of C macro since these are expanded on compilation

useful in defining modules and functions in elixir
