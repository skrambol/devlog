---
tags:
  - dev
  - devlog
  - elixir
created_at: 2023-09-30 11:37
aliases:
---
```elixir
# If the key is an atom:
%{atom_key: 1}

# If the key is a different type:
%{1 => :atom_value}

# You can even mix these if the atom form comes second:
%{"first_form" => :a, atom_form: :b}
```

- maps are key-value pairs
- `%{key: value}` - if key is atom
- `%{key => value}`
