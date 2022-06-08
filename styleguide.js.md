# sauron65's JavaScript styleguide

## ES6+
always try use ES6+

NEVER use `var` (except for in pollyfills)

no need to use an IIFE, because of modules and top-level `await`

use `const` by default, use `let` if it gets reassigned

## naming

```js
const CONSTANTS_LIKE_THIS = "value";

let variablesLikeThis;

function functionsLikeThis() { 
}

class ClassesLikeThis {
}


```

## modules

Always use ESM (set `"type": "module"` in `package.json`). Commonjs can be used when needed, but avoid it, and allways use `.cjs` for commonjs files. Avoid using default exports and default imports. Avoid using npm packages with a lot of dependencies.

imports and exports like this:
```js
// module.js

// export at declaration
export let y = 8;
const x = 418;
let z = 32;

// or at end of file
export { x, z };

// main.js

import { x, y, z } from "./module.js";

// when importing node.js builtin modules,
// prefer:
import * as path from "path";

// or

import { join } from "path";

// over:
import path from "path";
```
## file naming

name files either the name of the main export (variable/class/function), or if no main export in particular, something descriptive in lowerCamelCase, or with-hyphens-seperating.

## whitespace

Indentation should be 2 spaces. Line endings should be `LF` and not `CRLF`. Put single blank lines were it feels appropriate.

### functions

function expressions:
```js
/*space between function         +--- space after comma
       and parentheses ---+      |     +--- space between parenthesis and {
                          |      |     |
                          V      V     V*/
thingWithCallback(function (arg1, arg2) {
  const a = arg1 + arg2;
  const b = a * arg2;
  return b + a;
});
```
use arrow functions when needed. they are needed when otherwise you would need to do:
```js
const that = this;
thingWithCallback(function (value) {
  that.method(512, value);
});
```

### if/else if/else

```js
// if spacing like this:
if (condition) {
  doSomething();
} else if (otherCondition) {
  doSomethingElse();
} else {
  doADifferentThing();
}
```

### switch

```js
switch (thing) {
  case 8:
    doSomething();
    break;
  case 256:
    doSomethingElse();
    break;
  case 17:
    doYetAnotherThing();
    break;
  default:
    doAnotherDifferentThing();
    break;
}
```

## Values

### strings
use double quotes for strings. if the string contains double quotes and not single quotes, use single quotes. If it contains both double and single quotes, use double quotes/template literals. For combing strings/multiline strings, use template literals
```js
const string = "abcd";
const string2 = "this string says: \"it's a string\"";
const pathString = `./${getValue()}.json`;
```
