---
description: Using Wildcards in formulas to match certain cells.
---

# Wildcards

Wildcard patterns can be used with several formula functions, including `MATCH` (with a `match_mode`of `0`) and `XLOOKUP`(with `match_mode` of `2`). They can also be used in [criteria](criteria.md) with any equality-based comparison (`=`, `==`, `<>`, `!=`, or no operator)

In wildcards, the special symbols `?` and `*` can be used to match certain text patterns: `?` matches any single character and `*` matches any sequence of zero or more characters. For example, `DEFEN?E` matches the strings `"defence"` and `"defense"`, but not `"defenestrate"`. `*ATE` matches the strings `"ate"`, `"inflate"`, and `"late"`, but not `"wait"`. Multiple `?` and `*` are also allowed.

To match a literal `?` or `*`, prefix it with a tilde `~`: for example, `COUNTIF(A1:A10, "HELLO~?")` matches only the string `"Hello?"` (and uppercase/lowercase variants).

To match a literal tilde `~` in a string with `?` or `*`, replace it with a double tilde `~~`. For example, `COUNTIF(A1:A10, "HELLO ~~?")` matches the strings `"hello ~Q"`, `"hello ~R"`, etc. If the string does not contain any `?` or `*`, then tildes do not need to be escaped.
