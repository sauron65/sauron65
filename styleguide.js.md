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

Always use ESM (set `"type": "module"` in `package.json`). Avoid using default exports and default imports. Avoid using npm packages with a lot of dependencies.

imports and exports like this:
```js
//module.js

export let y = 8;
```
