---
title: Formula.js
layout: home
---

## Use it

### In browser

Powered by [jsDelivr](https://www.jsdelivr.com/), you can use the latests version of Formula.js:

```html
<script src="https://cdn.jsdelivr.net/npm/jstat@1.9.2/dist/jstat.min.js"></script> 
<script src="https://cdn.jsdelivr.net/gh/formulajs/formulajs@2.2.3/dist/formula.min.js"></script>
```

### In node

The package is not yet pushed to NPM, but you can already install it like that in your package.json:

```json
{
  "dependencies": {
    "formulajs": "github:formulajs/formulajs#semver:^2.2.3",
  },
}
```

## Play with it

With Formula.js you can recreate spreadsheet formula with JavaScript using the functions you know.

You can review some usages and play online on the [functions pages](/functions).

### Spreadsheet to JavaScript syntax

Considering the following spreadsheet:

![Spreadsheet screenshot of a SUM function](/assets/img/spreadsheet-sum.png)

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
