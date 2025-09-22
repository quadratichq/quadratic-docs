---
description: Write formulas that operate on many cells at once.
---

# Arrays

An array can be written using `{}`, with `,` between values within a row and `;` between rows. For example, `{1, 2, 3; 4, 5, 6}` is an array with two rows and three columns:

| 1 | 2 | 3 |
| - | - | - |
| 4 | 5 | 6 |

Arrays cannot be empty and every row must be the same length.

Numeric ranges (such as `1..10`) and cell ranges (such as `A1:A10`) also produce arrays. All operators and most functions can operate on arrays, following these rules:

1. Operators always operate element-wise. For example, `{1, 2, 3} + {10, 20, 30}` produces `{11, 22, 33}`.
2. Functions that take a fixed number of values operate element-wise. For example, `NOT({TRUE, TRUE, FALSE})` produces `{FALSE, FALSE, TRUE}`.
3. Functions that can take any number of values expand the array into individual values. For example, `SUM({1, 2, 3})` is the same as `SUM(1, 2, 3)`.

When arrays are used element-wise, they must be the same size. For example, `{1, 2} + {10, 20, 30}` produces an error.

When an array is used element-wise with a single value, the value is expanded into an array of the same size. For example, `{1, 2, 3} + 10` produces `{11, 12, 13}`.
