---
title: Formula.js
layout: home
---

## Use it

### In browser

Powered by [jsDelivr](https://www.jsdelivr.com/), you can use the latest version of Formula.js:

```html
<script src="https://cdn.jsdelivr.net/npm/jstat@1.9.2/dist/jstat.min.js"></script> 
<script src="https://cdn.jsdelivr.net/gh/formulajs/formulajs@2.5.0/dist/formula.min.js"></script>
```

### In node

Install the package:

```json
npm i @formulajs/formulajs
```

## Play with it

With Formula.js you can recreate spreadsheet formula with JavaScript using the functions you know.

You can review some usages and play online on the [functions pages](/functions).

### Spreadsheet to JavaScript syntax

Considering the following spreadsheet:

{% include image.html url="/assets/img/spreadsheet-sum.png" description="Spreadsheet screenshot of a SUM function" %}

The Formula.js equivalent would be:

```javascript
// =SUM(A1:C1)
formulajs.SUM([1, 2 , 3])
// returns > 6

// =SUM(A1:C2)
formulajs.SUM([[1, 2 , 3], [4, 5, 6]])
// returns > 21
```

### JavaScript differs from Excel

Formula.js tries to recreate the formula you know and like from your spreadsheet tool. However the two environments
differs from each other.

For example `=2^3` is a valid Excel function that will return `8`. The `^` operator means something else in JavaScript 
(`2^3` return `1`, you can learn more [here why](https://www.w3schools.com/js/js_bitwise.asp)). With Formula.js you
can write `formulajs.POWER(2, 3)` which is equivalent to `Math.pow(2, 3)` in plain JavaScript.

## Migration guide

### From formulajs

If you were previously using [formulajs from Sutoiku](https://www.npmjs.com/package/formulajs), some functions have been
removed, due to dependency simplification.

Text functions:

`FIXED, TEXT, DOLLAR, VALUE`

Math functions:

`MDETERM, MINVERSE, MMULT, MUNIT`

Otherwise the 2 packages are fully compatible. You can swap them.

### From @handsontable/formulajs

The code of this package is originally forked from [@handsontable/formulajs](https://github.com/handsontable/formula.js#readme)
 version 2.0.2 (released in January 2020). The two packages were identical at the time. There is no regression, only 
 fixes and new functions since the fork.
