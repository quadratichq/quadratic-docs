---
description: Using Criteria in formulas to match certain cells.
---

# Criteria

Some functions, such as `SUMIF()`, take a **criteria** parameter that other values are compared to. A criteria value can be a literal value, such as `1`, `FALSE`, `"blue"`, etc. A literal value checks for equality (case-insensitive). However, starting a string with a comparison operator enables more complex criteria:

| **Symbol**               | **Description**                                           |
| ------------------------ | --------------------------------------------------------- |
| `"=blue"` or `"==blue"`  | Equal comparison (supports [wildcards](wildcards.md))     |
| `"<>blue"` or `"!=blue"` | Not-equal comparison (supports [wildcards](wildcards.md)) |
| `"<blue"`                | Less-than comparison                                      |
| `">blue"`                | Greater-than comparison                                   |
| `"<=blue"`               | Less-than-or-equal comparison                             |
| `">=blue"`               | Greater-than-or-equal comparison                          |
