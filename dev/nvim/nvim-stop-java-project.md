---
tags:
  - dev
  - nvim
  - nvim-java
  - spring-boot
created_at: 2025-07-18 07:14
---
## Problem
stopping java / Spring Boot application inside nvim

## Solution
- `:JavaRunnerStopMain`
- this stops Java project from running
- does not close created window by `:JavaRunnerRunMain` [nvim-run-java-project](nvim-run-java-project.md)

useful in stopping Java project inside nvim