# LET & LAMBDA

## LET & LAMBDA

Quadratic supports Excel's modern formula-composition functions, letting you name intermediate values and define custom functions inline.

### LET

`LET(name1, value1, ..., calculation)` defines named values inside a formula, then uses them in a final calculation. It improves readability and avoids repeating expressions.

```
=LET(revenue, SUM(Sales[Amount]), cost, SUM(Costs[Amount]), revenue - cost)
```

### LAMBDA

`LAMBDA(param1, ..., calculation)` defines a reusable custom function inline. Combine it with array functions — `MAP`, `REDUCE`, `BYROW`, `BYCOL`, `SCAN`, and `MAKEARRAY` — to apply custom logic across ranges:

```
=MAP(A1:A10, LAMBDA(x, x * 1.08))
```

```
=REDUCE(0, B1:B20, LAMBDA(acc, v, acc + MAX(v, 0)))
```

### ISOMITTED

Inside a `LAMBDA`, `ISOMITTED(argument)` returns `TRUE` if an optional argument was not supplied — useful for default values.

### STOCKHISTORY

Quadratic also supports the Excel-compatible `STOCKHISTORY` function for retrieving historical stock prices directly in the sheet:

```
=STOCKHISTORY("AAPL", "2025-01-01", "2025-12-31")
```

For richer financial data — fundamentals, statements, news, technical indicators — see Financial data in Python.

For the full function reference, see Functions and operators.
