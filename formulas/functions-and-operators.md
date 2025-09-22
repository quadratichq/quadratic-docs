---
description: Using formulas in the spreadsheet.
---

# Functions and operators

## Operators

| Precedence | Symbol           | Description                         |
| ---------- | ---------------- | ----------------------------------- |
| 1          | `x%`             | Percent (divides by 100)            |
| 2          | `+x`             | positive                            |
|            | `-x`             | negative                            |
| 3          | `a:b`            | cell range                          |
| 4          | `a..b`           | numeric range                       |
| 5          | `a^b or a**b`    | Exponentiation                      |
| 6          | `a*b`            | Multiplication                      |
|            | `a/b`            | Division                            |
| 7          | `a+b`            | Addition                            |
|            | `a-b`            | Subtraction                         |
| 8          | `a&b`            | String concatenation                |
| 9          | `a=b` or `a==b`  | Equal comparison                    |
|            | `a<>b` or `a!=b` | Not equal comparison                |
|            | `a<b`            | Less than comparison                |
|            | `a>b`            | Greater than comparison             |
|            | `a<=b`           | Less than or equal to comparison    |
|            | `a>=b`           | Greater than or equal to comparison |

## Mathematics functions

| **Function**                                                                    | **Description**                                                                                                                                                                                                                                                                                                                                                        |
| ------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `SUM([numbers...])`                                                             | Adds all values. Returns `0` if given no values.                                                                                                                                                                                                                                                                                                                       |
| `SUMIF(eval_range, criteria, [sum_range])`                                      | Evaluates each value based on some criteria, and then adds the ones that meet those criteria. If `sum_range` is given, then values in `sum_range` are added instead wherever the corresponding value in `eval_range` meets the criteria. See [the documentation](https://docs.quadratichq.com/formulas/criteria) for more details about how criteria work in formulas. |
| `SUMIFS(sum_range, eval_range1, criteria1, [more_eval_ranges_and_criteria...])` | Adds values from `numbers_range` wherever the criteria are met at the corresponding value in each `eval_range`. See [the documentation](https://docs.quadratichq.com/formulas/criteria) for more details about how criteria work in formulas.                                                                                                                          |
| `PRODUCT([numbers...])`                                                         | Multiplies all values. Returns `1` if given no values.                                                                                                                                                                                                                                                                                                                 |
| `ABS(number)`                                                                   | Returns the absolute value of a number.                                                                                                                                                                                                                                                                                                                                |
| `SQRT(number)`                                                                  | Returns the square root of a number.                                                                                                                                                                                                                                                                                                                                   |
| `CEILING(number, increment)`                                                    | Rounds a number up to the next multiple of `increment`. If `number` and `increment` are both negative, rounds the number down away from zero. Returns an error if `number` is positive but `significance` is negative. Returns `0` if `increment` is `0`.                                                                                                              |
| `FLOOR(number, increment)`                                                      | Rounds a number down to the next multiple of `increment`. If `number` and `increment` are both negative, rounds the number up toward zero. Returns an error if `number` is positive but `significance` is negative, or if `increment` is `0` but `number` is nonzero. Returns `0` if `increment` is `0` _and_ `number` is `0`.                                         |
| `INT(number)`                                                                   | Rounds a number down to the next integer. Always rounds toward negative infinity.                                                                                                                                                                                                                                                                                      |
| `POWER(base, exponent)`                                                         | Returns the result of raising `base` to the power of `exponent`.                                                                                                                                                                                                                                                                                                       |
| `PI()`                                                                          | Returns π, the circle constant.                                                                                                                                                                                                                                                                                                                                        |
| `TAU()`                                                                         | Returns τ, the circle constant equal to 2π.                                                                                                                                                                                                                                                                                                                            |

#### CEILING.MATH

`CEILING.MATH(number, [increment], [negative_mode])`

Examples:

* `CEILING.MATH(6.5)`
* `CEILING.MATH(6.5, 2)`
* `CEILING.MATH(-12, 5)`
* `CEILING.MATH(-12, 5, -1)`

Rounds a number up or away from zero to the next multiple of`increment`. If `increment` is omitted, it is assumed to be `1`.\
The sign of `increment` is ignored.

If `negative_mode` is positive or zero, then `number` is rounded\
up, toward positive infinity. If `negative_mode` is negative,\
then `number` is rounded away from zero. These are equivalent\
when `number` is positive, so in this case `negative_mode` has\
no effect.

If `increment` is zero, returns zero.

#### FLOOR.MATH

`FLOOR.MATH(number, [increment], [negative_mode])`

Examples:

* `FLOOR.MATH(6.5)`
* `FLOOR.MATH(6.5, 2)`
* `FLOOR.MATH(-12, 5)`
* `FLOOR.MATH(-12, 5, -1)`

Rounds a number down or toward zero to the next multiple of`increment`. If `increment` is omitted, it is assumed to be `1`.\
The sign of `increment` is ignored.

If `negative_mode` is positive or zero, then `number` is rounded\
down, toward negative infinity. If `negative_mode` is negative,\
then `number` is rounded toward zero. These are equivalent when`number` is positive, so in this case `negative_mode` has no\
effect.

If `increment` is zero, returns zero.

#### ROUND

`ROUND(number, [digits])`

Examples:

* `ROUND(6.553, 2)`

Rounds a number to the specified number of digits after the\
decimal point.

* If `digits` is 0 or omitted, then the number is rounded to the\
  nearest integer.
* If `digits > 0`, then the number is rounded to a digit after\
  the decimal point. For example, `ROUND(x, 2)` rounds `x` to\
  the nearest multiple of 0.01.
* If `digits < 0`, then the number is rounded to a digit before\
  the decimal point. For example, `ROUND(x, -2)` rounds `x` to\
  the nearest multiple of 100.

Ties are broken by rounding away from zero. For example,`ROUND(50, -2)` rounds to `100`.

#### ROUNDUP

`ROUNDUP(number, [digits])`

Examples:

* `ROUNDUP(6.553, 2)`

Rounds a number **away from zero** to the specified number of\
digits after the decimal point.

* If `digits` is 0 or omitted, then the number is rounded to an\
  integer.
* If `digits > 0`, then the number is rounded to a digit after\
  the decimal point. For example, `ROUNDUP(x, 2)` rounds `x` to\
  a multiple of 0.01.
* If `digits < 0`, then the number is rounded to a digit before\
  the decimal point. For example, `ROUNDUP(x, -2)` rounds `x` to\
  a multiple of 100.

#### ROUNDDOWN

`ROUNDDOWN(number, [digits])`

Examples:

* `ROUNDDOWN(6.553, 2)`

Rounds a number **toward zero** to the specified number of\
digits after the decimal point. This is exactly the same as`TRUNC()`.

* If `digits` is 0 or omitted, then the number is rounded to an\
  integer.
* If `digits > 0`, then the number is rounded to a digit after\
  the decimal point. For example, `ROUNDDOWN(x, 2)` rounds `x`\
  to a multiple of 0.01.
* If `digits < 0`, then the number is rounded to a digit before\
  the decimal point. For example, `ROUNDDOWN(x, -2)` rounds `x`\
  to a multiple of 100.

#### TRUNC

`TRUNC(number, [digits])`

Examples:

* `TRUNC(6.553, 2)`

Rounds a number **toward zero** to the specified number of\
digits after the decimal point. This is exactly the same as`ROUNDDOWN()`.

* If `digits` is 0 or omitted, then the number is rounded to an\
  integer.
* If `digits > 0`, then the number is rounded to a digit after\
  the decimal point. For example, `TRUNC(x, 2)` rounds `x` to a\
  multiple of 0.01.
* If `digits < 0`, then the number is rounded to a digit before\
  the decimal point. For example, `TRUNC(x, -2)` rounds `x` to a\
  multiple of 100.

#### MOD

`MOD(number, divisor)`

Examples:

* `MOD(3.9, 3)`
* `MOD(-2.1, 3)`

Returns the remainder after dividing `number` by `divisor`. The\
result always has the same sign as `divisor`.

Note that `INT(n / d) * d + MOD(n, d)` always equals `n` (up to\
floating-point precision).

#### EXP

`EXP(exponent)`

Examples:

* `EXP(1), EXP(2/3), EXP(C9)`

Returns the result of raising [Euler's number](https://en.wikipedia.org/wiki/E_\(mathematical_constant\)) _e_ to the power\
of `exponent`.

#### LOG

`LOG(number, [base])`

Examples:

* `LOG(100)`
* `LOG(144, 12)`
* `LOG(144, 10)`

Returns the [logarithm](https://en.wikipedia.org/wiki/Logarithm) of `number` to the base `base`. If`base` is omitted, it is assumed to be 10, the base of the[common logarithm](https://en.wikipedia.org/wiki/Common_logarithm).

#### LOG10

`LOG10(number)`

Examples:

* `LOG10(100)`

Returns the [base-10 logarithm](https://en.wikipedia.org/wiki/Common_logarithm) of `number`.

#### LN

`LN(number)`

Examples:

* `LN(50)`

Returns the [natural logarithm](https://en.wikipedia.org/wiki/Natural_logarithm) of `number`.

### Trigonometric functions

| **Function**       | **Description**                                                                                                                                  |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| `DEGREES(radians)` | Converts radians to degrees.                                                                                                                     |
| `RADIANS(degrees)` | Converts degrees to radians.                                                                                                                     |
| `SIN(radians)`     | Returns the [sine](https://en.wikipedia.org/wiki/Trigonometric_functions) of an angle in radians.                                                |
| `ASIN(number)`     | Returns the [inverse sine](https://en.wikipedia.org/wiki/Inverse_trigonometric_functions) of a number, in radians, ranging from 0 to π.          |
| `COS(radians)`     | Returns the [cosine](https://en.wikipedia.org/wiki/Trigonometric_functions) of an angle in radians.                                              |
| `ACOS(number)`     | Returns the [inverse cosine](https://en.wikipedia.org/wiki/Inverse_trigonometric_functions) of a number, in radians, ranging from 0 to π.        |
| `TAN(radians)`     | Returns the [tangent](https://en.wikipedia.org/wiki/Trigonometric_functions) of an angle in radians.                                             |
| `ATAN(number)`     | Returns the [inverse tangent](https://en.wikipedia.org/wiki/Inverse_trigonometric_functions) of a number, in radians, ranging from -π/2 to π/2.  |
| `CSC(radians)`     | Returns the [cosecant](https://en.wikipedia.org/wiki/Trigonometric_functions) of an angle in radians.                                            |
| `ACSC(number)`     | Returns the [inverse cosecant](https://en.wikipedia.org/wiki/Inverse_trigonometric_functions) of a number, in radians, ranging from -π/2 to π/2. |
| `SEC(radians)`     | Returns the [secant](https://en.wikipedia.org/wiki/Trigonometric_functions) of an angle in radians.                                              |
| `ASEC(number)`     | Returns the [inverse secant](https://en.wikipedia.org/wiki/Inverse_trigonometric_functions) of a number, in radians, ranging from 0 to π.        |
| `COT(radians)`     | Returns the [cotangent](https://en.wikipedia.org/wiki/Trigonometric_functions) of an angle in radians.                                           |
| `ACOT(number)`     | Returns the [inverse cotangent](https://en.wikipedia.org/wiki/Inverse_trigonometric_functions) of a number, in radians, ranging from 0 to π.     |
| `SINH(radians)`    | Returns the [hyperbolic sine](https://en.wikipedia.org/wiki/Hyperbolic_functions) of an angle in radians.                                        |
| `ASINH(number)`    | Returns the [inverse hyperbolic sine](https://en.wikipedia.org/wiki/Inverse_hyperbolic_functions) of a number, in radians.                       |
| `COSH(radians)`    | Returns the [hyperbolic cosine](https://en.wikipedia.org/wiki/Hyperbolic_functions) of an angle in radians.                                      |
| `ACOSH(number)`    | Returns the [inverse hyperbolic cosine](https://en.wikipedia.org/wiki/Inverse_hyperbolic_functions) of a number, in radians.                     |
| `TANH(radians)`    | Returns the [hyperbolic tangent](https://en.wikipedia.org/wiki/Hyperbolic_functions) of an angle in radians.                                     |
| `ATANH(number)`    | Returns the [inverse hyperbolic tangent](https://en.wikipedia.org/wiki/Inverse_hyperbolic_functions) of a number, in radians.                    |
| `CSCH(radians)`    | Returns the [hyperbolic cosecant](https://en.wikipedia.org/wiki/Hyperbolic_functions) of an angle in radians.                                    |
| `ACSCH(number)`    | Returns the [inverse hyperbolic cosecant](https://en.wikipedia.org/wiki/Inverse_hyperbolic_functions) of a number, in radians.                   |
| `SECH(radians)`    | Returns the [hyperbolic secant](https://en.wikipedia.org/wiki/Hyperbolic_functions) of an angle in radians.                                      |
| `ASECH(number)`    | Returns the [inverse hyperbolic secant](https://en.wikipedia.org/wiki/Inverse_hyperbolic_functions) of a number, in radians.                     |
| `COTH(radians)`    | Returns the [hyperbolic cotangent](https://en.wikipedia.org/wiki/Hyperbolic_functions) of an angle in radians.                                   |
| `ACOTH(number)`    | Returns the [inverse hyperbolic cotangent](https://en.wikipedia.org/wiki/Inverse_hyperbolic_functions) of a number, in radians.                  |

#### ATAN2

`ATAN2(x, y)`

Examples:

* `ATAN2(2, 1)`

Returns the counterclockwise angle, in radians, from the X axis\
to the point `(x, y)`. Note that the argument order is reversed\
compared to the [typical `atan2()`\
function](https://en.wikipedia.org/wiki/Atan2).

If both arguments are zero, returns zero.

### Statistics functions

| **Function**                                                           | **Description**                                                                                                                                                                                                                                                                                                                                                                                                           |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `AVERAGE([numbers...])`                                                | Returns the arithmetic mean of all values.                                                                                                                                                                                                                                                                                                                                                                                |
| `AVERAGEIF(eval_range, criteria, [numbers_range])`                     | Evaluates each value based on some criteria, and then computes the arithmetic mean of the ones that meet those criteria. If `range_to_average` is given, then values in `range_to_average` are averaged instead wherever the corresponding value in `range_to_evaluate` meets the criteria. See [the documentation](https://docs.quadratichq.com/formulas/criteria) for more details about how criteria work in formulas. |
| `COUNTIF(range, criteria)`                                             | Evaluates each value based on some criteria, and then counts how many values meet those criteria. See [the documentation](https://docs.quadratichq.com/formulas/criteria) for more details about how criteria work in formulas.                                                                                                                                                                                           |
| `COUNTIFS(eval_range1, criteria1, [more_eval_ranges_and_criteria...])` | Evaluates multiple values on they're respective criteria, and then counts how many sets of values met all their criteria. See [the documentation](https://docs.quadratichq.com/formulas/criteria) for more details about how criteria work in formulas.                                                                                                                                                                   |
| `MIN([numbers...])`                                                    | Returns the smallest value. Returns +∞ if given no values.                                                                                                                                                                                                                                                                                                                                                                |
| `MAX([numbers...])`                                                    | Returns the largest value. Returns -∞ if given no values.                                                                                                                                                                                                                                                                                                                                                                 |
| `VAR([numbers...])`                                                    | Returns the variance of all values (sample variance). Uses the formula: Σ(x - μ)²/(n-1) where μ is the mean and n is the count.                                                                                                                                                                                                                                                                                           |
| `STDEV([numbers...])`                                                  | Returns the standard deviation of all values (sample standard deviation). Uses the formula: √(Σ(x - μ)²/(n-1)) where μ is the mean and n is the count.                                                                                                                                                                                                                                                                    |

#### COUNT

`COUNT([numbers...])`

Examples:

* `COUNT(A1:C42, E17)`
* `SUM(A1:A10) / COUNT(A1:A10)`

Returns the number of numeric values.

* Blank cells are not counted.
* Cells containing an error are not counted.

#### COUNTA

`COUNTA([range...])`

Examples:

* `COUNTA(A1:A10)`

Returns the number of non-blank values.

* Cells with formula or code output of an empty string are\
  counted.
* Cells containing zero are counted.
* Cells with an error are counted.

#### COUNTBLANK

`COUNTBLANK([range...])`

Examples:

* `COUNTBLANK(A1:A10)`

Counts how many values in the range are empty.

* Cells with formula or code output of an empty string are\
  counted.
* Cells containing zero are not counted.
* Cells with an error are not counted.

### Logic functions

* `FALSE`, `false` (case-insensitive), and `0` are all considered falsey
* `TRUE`, `true` (case-insensitive), and all nonzero numbers are considered truthy
* Other values produce an error when used in a place expecting a boolean

When used as a number, `TRUE` is equivalent to `1` and `FALSE` is equivalent to `0`.

| **Function**               | **Description**                                                                                  |
| -------------------------- | ------------------------------------------------------------------------------------------------ |
| `TRUE()`                   | Returns `TRUE`.                                                                                  |
| `FALSE()`                  | Returns `FALSE`.                                                                                 |
| `NOT(boolean)`             | Returns `TRUE` if `a` is falsey and `FALSE` if `a` is truthy.                                    |
| `IF(condition, t, f)`      | Returns `t` if `condition` is truthy and `f` if `condition` is falsey.                           |
| `IFERROR(value, fallback)` | Returns `fallback` if there was an error computing `value`; otherwise returns `value`.           |
| `IFNA(value, fallback)`    | Returns `fallback` if there was a "no match" error computing `value`; otherwise returns `value`. |

#### AND

`AND([booleans...])`

Examples:

* `AND(A1:C1)`
* `AND(A1, B12)`

Returns `TRUE` if all values are truthy and `FALSE` if any value\
is falsey.

Returns `TRUE` if given no values.

#### OR

`OR([booleans...])`

Examples:

* `OR(A1:C1)`
* `OR(A1, B12)`

Returns `TRUE` if any value is truthy and `FALSE` if all values\
are falsey.

Returns `FALSE` if given no values.

#### XOR

`XOR([booleans...])`

Examples:

* `XOR(A1:C1)`
* `XOR(A1, B12)`

Returns `TRUE` if an odd number of values are truthy and `FALSE`\
if an even number of values are truthy.

Returns `FALSE` if given no values.

### String functions

| **Function**                | **Description**                                                                                                                                                                                                          |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `CONCATENATE([strings...])` | Same as `CONCAT`, but kept for compatibility.                                                                                                                                                                            |
| `LEN(s)`                    | Returns half the length of the string in [Unicode code-points](https://tonsky.me/blog/unicode/). This is often the same as the number of characters in a string, but not for certain diacritics, emojis, or other cases. |
| `LENB(s)`                   | Returns half the length of the string in bytes, using UTF-8 encoding.                                                                                                                                                    |
| `CODE(s)`                   | Same as `UNICODE`. Prefer `UNICODE`.                                                                                                                                                                                     |
| `CHAR(code_point)`          | Same as `UNICHAR`. Prefer `UNICHAR`.                                                                                                                                                                                     |
| `LOWER(s)`                  | Returns the lowercase equivalent of a string.                                                                                                                                                                            |
| `UPPER(s)`                  | Returns the uppercase equivalent of a string.                                                                                                                                                                            |
| `PROPER(s)`                 | Capitalizes letters that do not have another letter before them, and lowercases the rest.                                                                                                                                |
| `T(v)`                      | Returns a string value unmodified, or returns the empty string if passed a value other than a string.                                                                                                                    |
| `EXACT(s1, s2)`             | Returns whether two strings are exactly equal, using case-sensitive comparison (but ignoring formatting).                                                                                                                |

#### ARRAYTOTEXT

`ARRAYTOTEXT(array, [format])`

Examples:

* `ARRAYTOTEXT({"Apple", "banana"; 42, "Hello, world!"})`
* `ARRAYTOTEXT({"Apple", "banana"; 42, "Hello, world!"}, 1)`

Converts an array of values to a string.

If `format` is 0 or omitted, returns a human-readable\
representation such as `Apple, banana, 42, hello, world!`. If`format` is 1, returns a machine-readable representation in\
valid formula syntax such as `{"Apple", "banana", 42, "Hello, world!"}`. If `format` is any other value, returns an error.

#### CONCAT

`CONCAT([strings...])`

Examples:

* `CONCAT("Hello, ", C0, "!")`
* `"Hello, " & C0 & "!"`

[Concatenates](https://en.wikipedia.org/wiki/Concatenation) all\
values as strings.

`&` can also be used to concatenate text.

#### LEFT

`LEFT(s, [char_count])`

Examples:

* `LEFT("Hello, world!") = "H"`
* `LEFT("Hello, world!", 6) = "Hello,"`
* `LEFT("抱歉，我不懂普通话") = "抱"`
* `LEFT("抱歉，我不懂普通话", 6) = "抱歉，我不懂"`

Returns the first `char_count` characters from the beginning of\
the string `s`.

Returns an error if `char_count` is less than 0.

If `char_count` is omitted, it is assumed to be 1.

If `char_count` is greater than the number of characters in `s`,\
then the entire string is returned.

#### LEFTB

`LEFTB(s, [byte_count])`

Examples:

* `LEFTB("Hello, world!") = "H"`
* `LEFTB("Hello, world!", 6) = "Hello,"`
* `LEFTB("抱歉，我不懂普通话") = ""`
* `LEFTB("抱歉，我不懂普通话", 6) = "抱歉"`
* `LEFTB("抱歉，我不懂普通话", 8) = "抱歉"`

Returns the first `byte_count` bytes from the beginning of the\
string `s`, encoded using UTF-8.

Returns an error if `byte_count` is less than 0.

If `byte_count` is omitted, it is assumed to be 1. If`byte_count` is greater than the number of bytes in `s`, then\
the entire string is returned.

If the string would be split in the middle of a character, then`byte_count` is rounded down to the previous character boundary\
so the the returned string takes at most `byte_count` bytes.

#### RIGHT

`RIGHT(s, [char_count])`

Examples:

* `RIGHT("Hello, world!") = "!"`
* `RIGHT("Hello, world!", 6) = "world!"`
* `RIGHT("抱歉，我不懂普通话") = "话"`
* `RIGHT("抱歉，我不懂普通话", 6) = "我不懂普通话"`

Returns the last `char_count` characters from the end of the\
string `s`.

Returns an error if `char_count` is less than 0.

If `char_count` is omitted, it is assumed to be 1.

If `char_count` is greater than the number of characters in `s`,\
then the entire string is returned.

#### RIGHTB

`RIGHTB(s, [byte_count])`

Examples:

* `RIGHTB("Hello, world!") = "!"`
* `RIGHTB("Hello, world!", 6) = "world!"`
* `RIGHTB("抱歉，我不懂普通话") = ""`
* `RIGHTB("抱歉，我不懂普通话", 6) = "通话"`
* `RIGHTB("抱歉，我不懂普通话", 7) = "通话"`

Returns the last `byte_count` bytes from the end of the string`s`, encoded using UTF-8.

Returns an error if `byte_count` is less than 0.

If `byte_count` is omitted, it is assumed to be 1.

If `byte_count` is greater than the number of bytes in `s`, then\
the entire string is returned.

If the string would be split in the middle of a character, then`byte_count` is rounded down to the next character boundary so\
that the returned string takes at most `byte_count` bytes.

#### MID

`MID(s, start_char, char_count)`

Examples:

* `MID("Hello, world!", 4, 6) = "lo, wo"`
* `MID("Hello, world!", 1, 5) = "Hello"`
* `MID("抱歉，我不懂普通话", 4, 4) = "我不懂普"`

Returns the substring of a string `s` starting at the`start_char`th character and with a length of `char_count`.

Returns an error if `start_char` is less than 1 or if`char_count` is less than 0.

If `start_char` is past the end of the string, returns an empty\
string. If `start_char + char_count` is past the end of the\
string, returns the rest of the string starting at `start_char`.

#### MIDB

`MIDB(s, start_byte, byte_count)`

Examples:

* `MIDB("Hello, world!", 4, 6) = "lo, wo"`
* `MIDB("Hello, world!", 1, 5) = "Hello"`
* `MIDB("抱歉，我不懂普通话", 10, 12) = "我不懂普"`
* `MIDB("抱歉，我不懂普通话", 8, 16) = "我不懂普"`

Returns the substring of a string `s` starting at the`start_byte`th byte and with a length of `byte_count` bytes,\
encoded using UTF-8.

Returns an error if `start_byte` is less than 1 or if`byte_count` is less than 0.

If `start_byte` is past the end of the string, returns an empty\
string. If `start_byte + byte_count` is past the end of the\
string, returns the rest of the string starting at `start_byte`.

If the string would be split in the middle of a character, then`start_byte` is rounded up to the next character boundary and`byte_count` is rounded down to the previous character boundary\
so that the returned string takes at most `byte_count` bytes.

#### UNICODE

`UNICODE(s)`

Examples:

* `UNICODE("a")=97`
* `UNICODE("Alpha")=65`

Returns the first [Unicode](https://en.wikipedia.org/wiki/Unicode) code point in a string as a number.\
If the first character is part of standard (non-extended)[ASCII](https://en.wikipedia.org/wiki/ASCII), then this is the same as its ASCII number.

#### UNICHAR

`UNICHAR(code_point)`

Examples:

* `UNICHAR(97) = "a"`
* `UNICHAR(65) = "A"`

Returns a string containing the given [Unicode](https://en.wikipedia.org/wiki/Unicode) code unit. For\
numbers in the range 0-127, this converts from a number to its\
corresponding [ASCII](https://en.wikipedia.org/wiki/ASCII) character.

#### CLEAN

`CLEAN(s)`

Examples:

* `CLEAN(CHAR(9) & "(only the parenthetical will survive)" & CHAR(10))`

Removes nonprintable [ASCII](https://en.wikipedia.org/wiki/ASCII) characters 0-31 (0x00-0x1F) from a\
string. This removes tabs and newlines, but not spaces.

#### TRIM

`TRIM(s)`

Examples:

* `TRIM(" a b c ")="a b c"`

Removes spaces from the beginning and end of a string `s`, and\
replaces each run of consecutive space within the string with a\
single space.

[Other forms of whitespace](https://en.wikipedia.org/wiki/Whitespace_character), including tabs and\
newlines, are preserved.

#### NUMBERVALUE

`NUMBERVALUE(s, [decimal_sep], [group_sep])`

Examples:

* `NUMBERVALUE("4,000,096.25")`
* `NUMBERVALUE("4.000.096,25")`

Parses a number from a string `s`, using `decimal_sep` as the\
decimal separator and `group_sep` as the group separator.

If `decimal_sep` is omitted, it is assumed to be `.`. If`group_sep` is omitted, it is assumed to be `,`. Only the first\
character of each is considered. If the decimal separator and\
the group separator are the same or if either is an empty\
string, an error is returned.

The decimal separator must appear at most once in the string.\
The group separator must not appear at any point after a decimal\
separator. Whitespace may appear anywhere in the string.\
Whitespace and group separators are ignored and have no effect\
on the returned number.

### Array functions

| **Function** | **Description** |
| ------------ | --------------- |

#### FILTER

`FILTER(array, include, [if_empty])`

Examples:

* `FILTER(A1:C5, D1:D5, "No results")`
* `FILTER(A1:C5, {FALSE; TRUE; TRUE; FALSE; TRUE})`

Filters an array of values by a list of booleans.

`include` must contain either a single row or a single column. If`include` is a single column, then each value in it corresponds to a\
row from `array`; if `include` is a single row, then each value in\
it corresponds to a column from `array`. If the value in `include`\
is truthy, then the corresponding row/column\
from `array` is included in the output. If `include` contains a\
single value, then it corresponds to all of `array`.

If no rows/columns are included in the output, then `if_empty` is\
outputted instead. If no rows/columns are included in the outpu&#x74;_&#x61;nd_ `if_empty` is omitted, then an error is returned.

#### SORT

`SORT(array, [sort_index], [sort_order], [by_column])`

Examples:

* `SORT(A1:A100)`
* `SORT(A1:C50)`
* `SORT(A1:C50, 3)`
* `SORT(A1:C50, , -1)`
* `SORT(A1:C50, 2, -1)`
* `SORT(A1:F3,,, TRUE)`

Sorts an array of values.

`sort_index` specifies the entry within each row or column to\
sort by. For example, if `sort_index` is `3` when sorting by row\
then each row will be sorted based on its value in the third\
column. If `sort_index` is omitted, then the first entry is\
used.

`sort_order` specifies whether to sort in reverse order. If`sort_order` is `1` or omitted, then the array is sorted in\
ascending order. If it is `-1`, then the array is sorted in\
descending order.

If `by_column` is `true`, then the function operations on\
columns. If `by_column` is `false` or omitted, then the function\
operates on rows.

The sort is [stable](https://en.wikipedia.org/wiki/Sorting_algorithm#Stability).

#### UNIQUE

`UNIQUE(array, [by_column], [exactly_once])`

Examples:

* `UNIQUE()`

Removes duplicates rows or columns from an array.

Rows or columns are returned in the order they initially appear;\
subsequent appearances are removed.

If `by_column` is `true`, then the function operations on\
columns. If `by_column` is `false` or omitted, then the function\
operates on rows.

If `exactly_once` is true, then rows and columns that appear\
multiple times are omitted; only rows or columns that appear\
exactly once are included in the output.

#### SUMPRODUCT

`SUMPRODUCT([arrays...])`

Examples:

* `SUMPRODUCT(C2:C5, D2:D5)`

Multiplies arrays componentwise, then returns the sum of all the\
elements. All arrays must have the same size.

For example, `SUMPRODUCT(C2:C5, D2:D5)` is equivalent to`SUM(C2:C5 * D2:D5)`.

### Date & time functions

Other spreadsheet software treats dates, times, and durations as pure numbers, which can cause mistakes and can't represent operations like "plus one month". Instead, Quadratic has separate types of data for each of the following:

* **Date**, such as `April 8, 2024`
* **Time**, such as `2:30 PM`
* **Date time**, such as `April 8, 2024 2:30 PM`
* **Duration**, such as `6 months 15 days 1h30m12s`

In formulas:

* Dates can be constructed using `DATE()` (e.g., `DATE(2024, 4, 8)`)
* Times can be constructed using `TIME()` (e.g., `TIME(14, 30, 0)`)
* Date times can be constructed by adding a date and a time (e.g., `DATE(2024, 4, 8) + TIME(14, 30, 0)`)
* Durations can be constructed using `DURATION.YMD()`, `DURATION.HMS()`, or by adding them both (e.g., `DURATION.YMD(0, 6, 15) + DURATION.HMS(1, 30, 12)`)

Dates, times, and date times can be entered into a cell using the formats above, or other formats (such as `YYYY-MM-DD`). Durations can be entered using long form (such as `1 hour, 30 minutes, 12 seconds`) or short form (such as `1h30m12s`). Durations support the following units:

* **Years**, written `y`, `yr`, `year`, `yrs`, or `years`
* **Months**, written `mo`, `mon`, `month`, or `months`
* **Weeks**, written `w`, `week`, or `weeks`
* **Days**, written `d`, `day`, or `days`
* **Hours**, written `h`, `hr`, `hour`, `hrs`, or `hours`
* **Minutes**, written `m`, `min`, `minute`, `mins`, or `minutes`
* **Seconds**, written `s`, `sec`, `second`, `secs`, or `seconds`
* **Milliseconds**, written `ms`, `millisec`, `millisecond`, or `milliseconds`
* **Microseconds**, written `us`, `µs`, `microsec`, `microsecond`, or `microseconds`
* **Nanoseconds**, written `ns`, `nanosec`, `nanosecond`, or `nanoseconds`
* **Picoseconds**, written `ps`, `picosec`, `picosecond`, or `picoseconds`
* **Femtoseconds**, written `fs`, `femtosec`, `femtosecond`, or `femtoseconds`
* **Attoseconds**, written `as`, `attosec`, `attosecond`, or `attoseconds`

Quadratic automatically converts between years and months (with 1 year = 12 months) and between any units less than one month, but does not convert months into days because months vary in length.

In formulas:

Durations can also be constructed by subtracting two dates, two times, or two datetimes. Durations can be added to or subtracted from all of these types as well, including other durations.

| **Function** | **Description** |
| ------------ | --------------- |

#### NOW

`NOW()`

Examples:

* `NOW()`

Returns the current local date and time.

This depends on the time configuration of the computer where the\
formula is run, which may depend on timezone.

#### TODAY

`TODAY()`

Examples:

* `TODAY()`

Returns the current local date.

This depends on the time configuration of the computer where the\
formula is run, which may depend on timezone.

#### DATE

`DATE(year, month, day)`

Examples:

* `DATE(2024, 04, 08)`
* `DATE(1995, 12, 25)`
* `DATE(1965, 3, 18)`

Returns a specific date from a `year`, `month`, and `day`.

`year`, `month`, and `day` must be numbers, and are rounded to\
the nearest integer.

If `day` is outside the range of days in the given month, then\
it overflows and offsets the `month`. For example, `DATE(2024, 1, 99)` returns `2024-04-08`.

If `month` is outside the range from `1` to `12` (inclusive),\
then it overflows and offsets the `year`. For example,`DATE(2024, 13, 1)` returns `2025-01-01` and `DATE(2024, 0, 1)`\
returns `2023-12-01`.

_Note that February 29, 1900 does not exist._

To construct a date time, simply add a date and time. For\
example, `DATE(1965, 3, 18) + TIME(8, 34, 51)` was the second\
(in UTC) that Alexei Leonov began the first-ever spacewalk.

#### TIME

`TIME(hour, minute, second)`

Examples:

* `TIME(8, 34, 51)`
* `TIME(2, 56, 0)`
* `TIME(2,30,59.99)`

Returns a specific time from an `hour`, `minute`, and `second`.

`hour`, `minute`, and `second` must be numbers. `hour` and`minute` are rounded to the nearest integer, but `second` may\
have a fractional component.

If `second` is outside the range from `0` to `59` inclusive,\
then it is divided by 60. The remainder is used for `second` and\
the quotient is added to `minute`. For example, `TIME(9, 0, 844)` returns `9:14:04 AM`.

Similarly, if `minute` is outside the range from `0` to `59`\
inclusive, then it is divided by 60. The remainder is used for`minute` and the quotient is added to `hour`. For example,`TIME(16, 70, 45)` returns `5:10:45 PM` and `TIME(12, -1, -1)`\
returns `11:58:59 AM`.

If `hour` is outside the range from `0` to `23`, then it is\
divided by 24. The quotient is discarded and the remainder is\
used for `hour`. For example, `TIME(-8, 30, 0)` returns `4:30:00 PM`.

To construct a date time, simply add a date and time. For\
example, `DATE(1969, 7, 21) + TIME(2, 56, 0)` was the minute (in\
UTC) that Neil Armstrong became the first person to walk on the\
surface of the moon.

#### DURATION.YMD

`DURATION.YMD(years, months, days)`

Examples:

* `DURATION.YMD(0, 0, 60)`
* `DURATION.YMD(-5, 0, 0)`
* `DURATION.YMD(1, 6, 0)`

Returns a duration of `years`, `months`, and `days`.

`years`, `months`, and `days` must be numbers. `years` and`months` are rounded to the nearest integer, but `days` may have\
a fractional component.

Months and years are combined, but days are not. For example,`DURATION.YMD(5, -3, 50)` returns `4y 9mo 50d`.

To construct a duration longer than one day, simply construct\
another duration using `DURATION.YMD` and add it to this one.\
For example, `DURATION.YMD(1, 2, 3) + DURATION.HMS(4, 5, 6)`\
returns `1y 2mo 3d 4h 5m 6s`.

#### DURATION.HMS

`DURATION.HMS(hours, minutes, seconds)`

Examples:

* `DURATION.HMS(0, 2, 30)`
* `DURATION.HMS(6, 0, 0)`
* `DURATION.HMS(24, 0, 0)`

Returns a duration of `hours`, `minutes`, and `seconds`.

`hours`, `minutes`, and `seconds` must be numbers. `hours` and`minutes` are rounded to the nearest integer, but `seconds` may\
have a fractional component.

Seconds, minutes, and hours are combined. For example,`DURATION.YMD(1, 72, 72)` returns `2h 13m 12s`.

To construct a duration longer than one day, simply construct\
another duration using `DURATION.YMD` and add it to this one.\
For example, `DURATION.YMD(1, 2, 3) + DURATION.HMS(4, 5, 6)`\
returns `1y 2mo 3d 4h 5m 6s`.

#### YEAR

`YEAR(date)`

Examples:

* `YEAR(DATE(2024, 4, 8)) = 2024`
* `YEAR(TIME(30, 16, 45)) = 0`
* `YEAR(DURATION.HMS(6, 10, 15)) = 0`
* `YEAR(DURATION.YMD(1, 2, 3)) = 1`
* `YEAR(DURATION.YMD(-1, -2, 3)) = -2`
* `YEAR(DURATION.YMD(1, 2, 3) + DURATION.HMS(6, 10, 15)) = 1`
* `YEAR(DURATION.YMD(1, 2, 3) - DURATION.HMS(6, 10, 15)) = 1`
* `YEAR(-DURATION.YMD(1, 2, 3) + DURATION.HMS(6, 10, 15)) = -2`
* `YEAR(-DURATION.YMD(1, 2, 3) - DURATION.HMS(6, 10, 15)) = -2`

Returns the year portion of a date or duration.

* The year portion of a date or date time is typically between`1900` and `2100`.
* The year portion of a time is always `0`.
* The year portion of a duration is rounded down, and may be\
  negative. For example, the year portion of `1y 4mo` is `1` and\
  the year portion of `-1y -4mo` is `-2`.
* The year portion of a number of days is not well-defined, so\
  an error is returned.

#### MONTH

`MONTH(date)`

Examples:

* `MONTH(DATE(2024, 4, 8)) = 4`
* `MONTH(TIME(30, 16, 45)) = 0`
* `MONTH(DURATION.HMS(6, 10, 15)) = 0`
* `MONTH(DURATION.YMD(1, 2, 3)) = 2`
* `MONTH(DURATION.YMD(-1, -2, 3)) = 10`
* `MONTH(DURATION.YMD(1, 2, 3) + DURATION.HMS(6, 10, 15)) = 1`
* `MONTH(DURATION.YMD(1, 2, 3) - DURATION.HMS(6, 10, 15)) = 1`
* `MONTH(-DURATION.YMD(1, 2, 3) + DURATION.HMS(6, 10, 15)) = 1`
* `MONTH(-DURATION.YMD(1, 2, 3) - DURATION.HMS(6, 10, 15)) = 1`

Returns the month portion of a date or duration.

* The month portion of a date or date time is always between `1`\
  and `12` (inclusive).
* The month portion of a time is always `0`.
* The month portion of a duration is always between `0` and`11`, even if the duration is negative. For example, the month\
  portion of `1y 4mo` is `4` and the month portion of `-1y -4mo`\
  is `8`.
* The month portion of a number of days is not well-defined, so\
  an error is returned.

#### DAY

`DAY(date)`

Examples:

* `DAY(DATE(2024, 4, 8)) = 8`
* `DAY(TIME(30, 16, 45)) = 0`
* `DAY(DURATION.HMS(6, 10, 15)) = 0`
* `DAY(DURATION.YMD(1, 2, 3)) = 3`
* `DAY(DURATION.YMD(-1, -2, 3)) = 3`
* `DAY(DURATION.YMD(1, 2, 3) + DURATION.HMS(6, 10, 15)) = 3`
* `DAY(DURATION.YMD(1, 2, 3) - DURATION.HMS(6, 10, 15)) = 2`
* `DAY(-DURATION.YMD(1, 2, 3) + DURATION.HMS(6, 10, 15)) = -3`
* `DAY(-DURATION.YMD(1, 2, 3) - DURATION.HMS(6, 10, 15)) = -4`

Returns the day portion of a date or duration.

* The day portion of a date or date time is always between `1`\
  and `31` (inclusive).
* The day portion of a time is always `0`.
* The day portion of a duration is rounded down, and may be\
  negative.
* The day portion of a number of days is equal to its integer\
  part when rounded down.

#### HOUR

`HOUR(time)`

Examples:

* `HOUR(TIME(30, 16, 45)) = 6`
* `HOUR(TIME(30, 0, -1)) = 5`
* `HOUR(TIME(0, 0, 0)) = 0`
* `HOUR(TIME(0, 0, -1)) = 23`
* `HOUR(789.084) = 2`
* `HOUR(-789.084) = 57`
* `HOUR(DURATION.HMS(6, 10, 15)) = 6`
* `HOUR(DURATION.YMD(1, 2, 3)) = 0`
* `HOUR(DURATION.YMD(1, 2, 3) + DURATION.HMS(6, 10, 15)) = 6`
* `HOUR(DURATION.YMD(1, 2, 3) - DURATION.HMS(6, 10, 15)) = 17`
* `HOUR(-DURATION.YMD(1, 2, 3) + DURATION.HMS(6, 10, 15)) = 6`
* `HOUR(-DURATION.YMD(1, 2, 3) - DURATION.HMS(6, 10, 15)) = 17`

Returns the hour portion of a time or duration.

* The hour portion of a date is always zero.
* The hour portion of a time or date time is always between `0`\
  and `23` (inclusive).
* The hour portion of a duration is always between `0` and `23`\
  (inclusive), even if the duration is negative.
* The hour portion of a number of days is equal to its\
  fractional part, times `24`, rounded down. It is always\
  between `0` and `23` (inclusive), even if the original number\
  is negative.

#### MINUTE

`MINUTE(time)`

Examples:

* `MINUTE(TIME(30, 16, 45)) = 16`
* `MINUTE(TIME(30, 0, -1)) = 59`
* `MINUTE(TIME(0, 0, 0)) = 0`
* `MINUTE(TIME(0, 0, -1)) = 59`
* `MINUTE(789.001389) = 2`
* `MINUTE(-789.001389) = 57`
* `MINUTE(DURATION.HMS(6, 10, 15)) = 10`
* `MINUTE(DURATION.YMD(1, 2, 3)) = 0`
* `MINUTE(DURATION.YMD(1, 2, 3) + DURATION.HMS(6, 10, 15)) = 10`
* `MINUTE(DURATION.YMD(1, 2, 3) - DURATION.HMS(6, 10, 15)) = 49`
* `MINUTE(-DURATION.YMD(1, 2, 3) + DURATION.HMS(6, 10, 15)) = 10`
* `MINUTE(-DURATION.YMD(1, 2, 3) - DURATION.HMS(6, 10, 15)) = 49`

Returns the minute portion of a time or duration.

* The minute portion of a date is always zero.
* The minute portion of a time or date time is always between`0` and `59` (inclusive).
* The minute portion of a duration is always between `0` and`59` (inclusive), even if the duration is negative.
* The minute portion of a number of days is equal to its\
  fractional part, times `1440`, rounded down. It is always\
  between `0` and `59` (inclusive), even if the original number\
  is negative.

#### SECOND

`SECOND(time)`

Examples:

* `SECOND(TIME(30, 16, 45)) = 45`
* `SECOND(TIME(30, 0, -1)) = 59`
* `SECOND(TIME(0, 0, 0)) = 0`
* `SECOND(TIME(0, 0, -1)) = 59`
* `SECOND(0.5557291667) = 15`
* `SECOND(-0.5557291667) = 44`
* `SECOND(DURATION.HMS(6, 10, 15)) = 15`
* `SECOND(DURATION.YMD(1, 2, 3)) = 0`
* `SECOND(DURATION.YMD(1, 2, 3) + DURATION.HMS(6, 10, 15)) = 15`
* `SECOND(DURATION.YMD(1, 2, 3) - DURATION.HMS(6, 10, 15)) = 45`
* `SECOND(-DURATION.YMD(1, 2, 3) + DURATION.HMS(6, 10, 15)) = 15`
* `SECOND(-DURATION.YMD(1, 2, 3) - DURATION.HMS(6, 10, 15)) = 45`

Returns the second portion of a time or duration.

* The second portion of a date is always zero.
* The second portion of a time or date time is always between`0` and `59` (inclusive).
* The second portion of a duration is always between `0` and`59` (inclusive), even if the duration is negative.
* The second portion of a number of days is equal to its\
  fractional part, times `86400`, rounded down. It is always\
  between `0` and `59` (inclusive), even if the original number\
  is negative.

#### EDATE

`EDATE(day, months_offset)`

Examples:

* `EDATE(DATE(2024, 04, 08), 8)`

Adds a number of months to a date.

If the date goes past the end of the month, the last day in the\
month is returned.

#### EOMONTH

`EOMONTH(day, [months_offset])`

Examples:

* `EOMONTH(DATE(2024, 04, 08))`
* `EOMONTH(DATE(2024, 04, 08), 8)`

Returns the last day of the month that is `months_offset` months\
after `day`.

* If `months_offset` is zero, then the value returned is the\
  last day of the month containing `day`.
* If `months_offset` is positive, then the day returned is that\
  many months later.
* If `months_offset` is negative, then the day returned is that\
  many months earlier.

### Lookup functions

| **Function**               | **Description**                                    |
| -------------------------- | -------------------------------------------------- |
| `INDIRECT(cellref_string)` | Returns the value of the cell at a given location. |

#### VLOOKUP

`VLOOKUP(search_key, search_range, output_col, [is_sorted])`

Examples:

* `VLOOKUP(17, A1:C10, 3)`
* `VLOOKUP(17, A1:C10, 2, FALSE)`

Searches for a value in the first vertical column of a range and\
return the corresponding cell in another vertical column, or an\
error if no match is found.

If `is_sorted` is `TRUE`, this function uses a [binary search\
algorithm](https://en.wikipedia.org/wiki/Binary_search_algorithm),\
so the first column of `search_range` must be sorted, with\
smaller values at the top and larger values at the bottom;\
otherwise the result of this function will be meaningless. If`is_sorted` is omitted, it is assumed to be `false`.

If any of `search_key`, `output_col`, or `is_sorted` is an\
array, then they must be compatible sizes and a lookup will be\
performed for each corresponding set of elements.

#### HLOOKUP

`HLOOKUP(search_key, search_range, output_row, [is_sorted])`

Examples:

* `HLOOKUP(17, A1:Z3, 3)`
* `HLOOKUP(17, A1:Z3, 2, FALSE)`

Searches for a value in the first horizontal row of a range and\
return the corresponding cell in another horizontal row, or an\
error if no match is found.

If `is_sorted` is `TRUE`, this function uses a [binary search\
algorithm](https://en.wikipedia.org/wiki/Binary_search_algorithm),\
so the first row of `search_range` must be sorted, with smaller\
values at the left and larger values at the right; otherwise the\
result of this function will be meaningless. If `is_sorted` is\
omitted, it is assumed to be `false`.

If any of `search_key`, `output_col`, or `is_sorted` is an\
array, then they must be compatible sizes and a lookup will be\
performed for each corresponding set of elements.

#### XLOOKUP

`XLOOKUP(search_key, search_range, output_range, [fallback], [match_mode], [search_mode])`

Examples:

* `XLOOKUP("zebra", A1:Z1, A4:Z6)`
* `XLOOKUP({"zebra"; "aardvark"}, A1:Z1, A4:Z6)`
* `XLOOKUP(50, C4:C834, B4:C834, {-1, 0, "not found"}, -1, 2)`

Searches for a value in a linear range and returns a row or\
column from another range.

`search_range` must be either a single row or a single column.

**Match modes**

There are four match modes:

* 0 = exact match (default)
* -1 = next smaller
* 1 = next larger
* 2 = wildcard

See [the documentation](https://docs.quadratichq.com/formulas/wildcards) for more details about how wildcards work in formulas.

**Search modes**

There are four search modes:

* 1 = linear search (default)
* -1 = reverse linear search
* 2 = [binary\
  search](https://en.wikipedia.org/wiki/Binary_search_algorithm)
* -2 = reverse binary search

Linear search finds the first matching value, while reverse\
linear search finds the last matching value.

Binary search may be faster than linear search, but binary\
search requires that values are sorted, with smaller values at\
the top or left and larger values at the bottom or right.\
Reverse binary search requires that values are sorted in the\
opposite direction. If `search_range` is not sorted, then the\
result of this function will be meaningless.

Binary search is not compatible with the wildcard match mode.

**Result**

If `search_range` is a row, then it must have the same width as`output_range` so that each value in `search_range` corresponds\
to a column in `output_range`. In this case, the **search axis**\
is vertical.

If `search_range` is a column, then it must have the same height\
as `output_range` so that each value in `search_range`\
corresponds to a row in `output_range`. In this case, the**search axis** is horizontal.

If a match is not found, then `fallback` is returned instead. If\
there is no match and `fallback` is omitted, then returns an\
error.

If any of `search_key`, `fallback`, `match_mode`, or`search_mode` is an array, then they must be compatible sizes\
and a lookup will be performed for each corresponding set of\
elements. These arrays must also have compatible size with the\
non-search axis of `output_range`.

#### MATCH

`MATCH(search_key, search_range, [match_mode])`

Examples:

* `MATCH(12, {10, 20, 30})`
* `MATCH(19, {10, 20, 30}, -1)`
* `MATCH("A", {"a"; "b"; "c"}, 0)`

Searches for a value in a range and returns the index of the\
first match, starting from 1.

If `match_mode` is `1` (the default), then the index of th&#x65;_&#x67;reatest value less than_ `search_key` will be returned. In\
this mode, `search_range` must be sorted in ascending order,\
with smaller values at the top or left and larger values at the\
bottom or right; otherwise the result of this function will be\
meaningless.

If `match_mode` is `-1`, then the index of the _smallest value_\
_greater than_ `search_key` will be returned. In this mode,`search_range` must be sorted in ascending order, with larger\
values at the top or left and smaller values at the bottom or\
right; otherwise the result of this function will be\
meaningless.

If `match_mode` is `0`, then the index of the first valu&#x65;_&#x65;qual_ to `search_key` will be returned. In this mode,`search_range` may be in any order. `search_key` may also be a\
wildcard.

See [the documentation](https://docs.quadratichq.com/formulas/wildcards) for more details about how wildcards work in formulas.

#### INDEX

`INDEX(range, [row], [column], [range_num])`

Examples:

* `INDEX({1, 2, 3; 4, 5, 6}, 1, 3)`
* `INDEX(A1:A100, 42)`
* `INDEX(A6:Q6, 12)`
* `INDEX((A1:B6, C1:D6, D1:D100), 1, 5, C6)`
* `E1:INDEX((A1:B6, C1:D6, D1:D100), 1, 5, C6)`
* `INDEX((A1:B6, C1:D6, D1:D100), 1, 5, C6):E1`
* `INDEX(A3:Q3, A2):INDEX(A6:Q6, A2)`

Returns the element in `range` at a given `row` and `column`. If\
the array is a single row, then `row` may be omitted; otherwise\
it is required. If the array is a single column, then `column`\
may be omitted; otherwise it is required.

If `range` is a group of multiple range references, then the\
extra parameter `range_num` indicates which range to index from.

When `range` is a range references or a group of range\
references, `INDEX` may be used as part of a new range\
reference.

### Financial functions

Financial functions for calculating loan payments, interest rates, and other financial calculations.

| **Function** | **Description** |
| ------------ | --------------- |

#### PMT

`PMT(rate, nper, pv, [fv], [payment_type])`

Examples:

* `PMT(0.08/12, 12*5, 10000)`
* `PMT(0.06/12, 24, 5000, 0, 1)`

Calculates the payment for a loan based on constant payments and a constant interest rate.

* rate: The interest rate per period (e.g., 0.08/12 for 8% annual rate with monthly payments)
* nper: The total number of payments (e.g., 5\*12 for 5 years of monthly payments)
* pv: The present value (the loan amount)
* \[fv]: The future value (default 0)
* \[type]: When payments are due (0=end of period, 1=beginning of period, default 0)

Returns the negative of the payment amount (since it represents money you pay out).

### Not yet implemented

We are continually adding new formula functions; see the [list of functions that we are currently building](https://github.com/quadratichq/quadratic/issues/337). If there is a formula function that is not implemented and not on that list please [contact us](https://www.quadratichq.com/contact).&#x20;
