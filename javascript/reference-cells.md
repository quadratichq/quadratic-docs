---
description: Reference cells from JavaScript.
---

# Reference cells

In Quadratic, [reference tables](reference-cells.md#block-9871b7ac3fa341da856503066f6f8e8c) and named outputs for simplest reference, [reference individual cells](reference-cells.md#block-9871b7ac3fa341da856503066f6f8e8c) from JavaScript for single values or [reference a range of cells](reference-cells.md#block-aea52dff303745f6b08db8ab3b24c4f6) for multiple values.&#x20;

## Referencing tables (and named outputs) <a href="#block-9871b7ac3fa341da856503066f6f8e8c" id="block-9871b7ac3fa341da856503066f6f8e8c"></a>

To reference a table, use the global function `q.cells` along with the table's name in the fashion outlined below.&#x20;

```javascript
// NOTE: uses the same A1 notation as Formulas
// References existing Table1 and is read in as array of arrays
let x = q.cells("Table1")

// Get a single column out of table into an array
let x = q.cells("Table1[column_name]")

// Get the table headers 
let x = q.cells("Table1[#HEADERS]")

// Reference a range of columns in a table
let x = q.cells("Table_name[[column_name:column_name]]")
```

## Referencing individual cells <a href="#block-9871b7ac3fa341da856503066f6f8e8c" id="block-9871b7ac3fa341da856503066f6f8e8c"></a>

To reference an individual cell, use the global function `q.cells` which returns the cell value.

<pre class="language-javascript"><code class="lang-javascript"><strong>// Reads the value in cell A1 and places in variable x 
</strong>let x = q.cells("A1")
</code></pre>

Any time cells dependent on other cells update, the dependent cell will also update. This means your code will execute in one cell if it is dependent on another. This is the behavior you want in almost all situations, including user inputs in the sheet that cause calculation in a JavaScript cell.&#x20;

## Referencing a range of cells <a href="#block-aea52dff303745f6b08db8ab3b24c4f6" id="block-aea52dff303745f6b08db8ab3b24c4f6"></a>

To reference a range of cells, use the same global function `q.cells()` which returns an array of arrays.&#x20;

```javascript
let let x = q.cells('A1:A5') // Returns a 1x5 array spanning from A1 to A5

let let x = q.cells('A1:C7') // Returns a 3x7 array of arrays spanning from A1 to C7

let let x = q.cells('A') // Returns all values in column A into a single array

let let x = q.cells('A:C') // Returns all values in columns A to C into an array of three arrays 

let let x = q.cells('A5:A') // Returns all values in column A starting at A5 and going down as an array 

let let x = q.cells('A5:C') // Returns all values in column A to C, starting at A5 and going down as an array of arrays
```

## Referencing another sheet

To reference another sheet's cells or range of cells use the following:&#x20;

<pre class="language-javascript"><code class="lang-javascript"><strong>// Use the sheet name as an argument for referencing range of cells 
</strong><strong>let x = q.cells("'Sheet_name_here'!A1:C9")
</strong><strong>
</strong><strong>// For individual cell reference 
</strong>let x = q.cells("'Sheet_name_here'!A1")
</code></pre>

## Unbounded ranges

### Unbounded column references&#x20;

To reference all the data in a column or set of columns without defining the range, use the following syntax.&#x20;

Column references span from set row (row 1 if not defined) to wherever the content in that column ends.&#x20;

<pre class="language-javascript"><code class="lang-javascript">// references all values in the column from row 1 to the end of the content 
<strong>let x = q.cells("A") // returns all the data in the column starting from row 1 to end of data 
</strong>
let x = q.cells("A:D") // returns all the data in columns A to D starting from row 1 to end of data in longest column

let x = q.cells("A5:A") // returns all values from A5 to the end of the content in column A 

let x = q.cells("A5:C") // returns all values from A5 to end of content in C

let x = q.cells("'Sheet2'!A:C") // same rules to reference in other sheets apply
</code></pre>

### Unbounded row references

To reference all the data in a row or set of rows without defining the range, use the following syntax.&#x20;

Row references span from the row set to wherever the content in that row ends.&#x20;

```javascript
// Returns all values in Row 1
let x = q.cells("1") 

// Returns all values in rows 1 to 3 
let x = q.cells("1:3") 

// Returns all values in Row 1
let x = q.cells("A1:1")

// Returns all values in Row 1 starting at column C
let x = q.cells("C1:1")

// Returns all values in Row 3 starting at column A
let x = q.cells("A3:3")

// Returns all values in Row 3 starting at column C 
let x = q.cells("C3:3")
```

## Relative vs absolute references

By default when you copy paste a reference it will update the row reference unless you use `$` notation in your references.&#x20;

```javascript
// Copy pasting this one row down will change reference to A2
let x = q.cells("A1")

// Copy pasting this one row down will keep reference as A1
let x = q.cells("A$1")

// Example using ranges - row references will not change
let x = q.cells("A$1:B$20")

// Only A reference will change when copied down
let x = q.cells("A1:B$20") 
```
