---
tags:
  - dev
  - nvim
created_at: 2023-09-28 17:28
aliases:
---
## Problem
i wanted to increase the size of the preview window in telescope.nvim

## Solution
- check out `telescope.layout` in help; specifically layout strategies
- learned about `layout_strategy` which can be set to `horizontal`, `vertical`, `center`, etc...
- this can be further customized in `layout_config`; some are specific to the strategy
```lua
defaults = {
  layout_strategy = "horizontal",
  layout_config = {
    horizontal = {
      preview_width = 0.4, -- percentage of screen; specific to horizontal
      preview_cutoff = 100, -- number of columns before preview is hidden
    }
  }
}
```

useful in customizing telescope layout, resizing preview window