# JavaScript Core Concepts -- Technical Paper

## 1. Different Data Types in JavaScript

-   **Primitive types**: string, number, boolean, null, undefined,
    symbol, bigint\
-   **Reference types**: object, array, function, date, regexp, etc.

------------------------------------------------------------------------

## 2. let, var, const

-   **let** → block scoped, can be reassigned but not redeclared.\
-   **const** → block scoped, must be initialized, cannot be
    reassigned.\
-   **var** → function scoped, allows redeclaration, hoisted.

------------------------------------------------------------------------

## 3. Why We Must Not Use `var`

-   Function-scoped → confusing in block code.\
-   Hoisted to the top → may lead to bugs.\
-   Can be redeclared in the same scope.\
    **Best practice:** Use `let` and `const`.

------------------------------------------------------------------------

## 4. Why Using Global Variables Is Bad

-   Pollutes global namespace.\
-   High chance of name collisions.\
-   Harder to debug and maintain.\
-   Makes code less modular and reusable.

------------------------------------------------------------------------

## 5. Truthy and Falsy Values

**Falsy values:** `false`, `0`, `-0`, `0n`, `""`, `null`, `undefined`,
`NaN`.\
All other values are **truthy**.

------------------------------------------------------------------------

## 6. Function Hoisting

-   Function declarations are hoisted (can be called before defined).\
-   Function expressions & arrow functions are not hoisted.

------------------------------------------------------------------------

## 7. Function Without Return Statement

-   Implicitly returns `undefined`.

------------------------------------------------------------------------

## 8. Different Ways of Declaring a Function

-   Function declaration\
-   Function expression\
-   Arrow function\
-   Anonymous function\
-   Immediately Invoked Function Expression (IIFE)

------------------------------------------------------------------------

## 9. Pass by Reference and Pass by Value

-   **Primitives** → passed by value (copy created).\
-   **Objects/arrays** → passed by reference (changes affect original).

------------------------------------------------------------------------

## 10. Different Types of Loops

-   **for loop** → numeric iteration.\
-   **for..in** → iterates over keys of object.\
-   **for..of** → iterates over values of iterable (arrays, strings,
    maps).\
-   **forEach()** → executes callback for each element in an array.

------------------------------------------------------------------------

## 11. Searching MDN

-   Official resource: [MDN Web Docs](https://developer.mozilla.org/)\
-   Provides documentation, examples, and browser compatibility.

------------------------------------------------------------------------

## 12. Popular Array Utility Methods

-   `map`, `filter`, `reduce`, `forEach`, `some`, `every`, `find`,
    `includes`, `sort`, `concat`, `slice`, `splice`

------------------------------------------------------------------------

## 13. Popular String Utility Methods

-   `split`, `slice`, `substring`, `toUpperCase`, `toLowerCase`, `trim`,
    `replace`, `includes`, `startsWith`, `endsWith`

------------------------------------------------------------------------

## 14. Popular Object Utility Methods

-   `Object.keys`, `Object.values`, `Object.entries`, `Object.assign`,
    `Object.freeze`, `Object.seal`

------------------------------------------------------------------------

## 15. forEach vs map/filter/reduce

-   **forEach** → side effects (logging, DOM updates).\
-   **map** → transform array → returns new array.\
-   **filter** → filter elements → returns new array.\
-   **reduce** → combine into single value.

------------------------------------------------------------------------

## 16. Immutable vs Mutable Methods

-   **Immutable** (returns new copy): `map`, `filter`, `slice`,
    `concat`.\
-   **Mutable** (modifies original): `push`, `pop`, `splice`, `sort`.

------------------------------------------------------------------------

## 17. Error Handling (try-catch)

``` js
try {
  riskyOperation();
} catch (error) {
  console.error(error.message);
}
```

------------------------------------------------------------------------

## 18. Throwing Errors

-   `throw new Error("Message")` → creates error object with stack
    trace.\
-   `throw "Message"` → throws a string (less informative).

------------------------------------------------------------------------

## 19. Reading Error Messages & Stack Trace

-   Shows type, message, and file/line number.\
-   Practice debugging daily.

------------------------------------------------------------------------

## 20. Importance of Catch Block

-   Prevents program crash.\
-   Allows graceful handling of errors.

------------------------------------------------------------------------

## 21. Spread Operator

``` js
let arr = [1, 2, 3];
let arr2 = [...arr, 4];
```

------------------------------------------------------------------------

## 22. Template Literals

``` js
let name = "Rohan";
console.log(`Hello, ${name}!`);
```

------------------------------------------------------------------------

## 23. Default Parameters

``` js
function greet(name = "Guest") {
  console.log("Hello " + name);
}
```

------------------------------------------------------------------------

## 24. Destructuring

``` js
let [a, b] = [1, 2];
let {x, y} = {x: 10, y: 20};
```

------------------------------------------------------------------------

## 25. Closures

-   A closure is a function that remembers its lexical scope even when
    executed outside it.

``` js
function outer() {
  let count = 0;
  return function inner() {
    count++;
    return count;
  }
}
```

------------------------------------------------------------------------

## 26. Arrow Functions vs Regular Functions

-   Arrow → no `this`, shorter syntax.\
-   Regular → has `this` bound to object.

------------------------------------------------------------------------

## 27. === vs ==

-   `==` → loose equality (type coercion).\
-   `===` → strict equality (no coercion).

------------------------------------------------------------------------

## 28. Why `value === undefined` is Better than `!value`

-   `!value` treats `0`, `""`, `false`, `null`, and `undefined` as
    falsy.\
-   `value === undefined` checks explicitly.

------------------------------------------------------------------------

## 29. Array Utility Methods Chaining

``` js
let result = arr.filter(n => n > 2).map(n => n * 2).reduce((a, b) => a + b, 0);
```

------------------------------------------------------------------------

## 30. null vs undefined

-   **undefined** → variable declared but not assigned.\
-   **null** → explicit absence of value.

------------------------------------------------------------------------

## 31. Importing and Exporting Modules

``` js
// export
module.exports = { myFunc };

// import
const { myFunc } = require("./file");
```

------------------------------------------------------------------------

## 32. Console Methods

-   `console.log` → normal logging.\
-   `console.error` → errors.\
-   `console.warn` → warnings.\
-   `console.info` → info messages.\
-   `console.table` → tabular output.

------------------------------------------------------------------------

## 33. Best Practices

-   Consistent indentation.\
-   Clear variable names.\
-   Avoid global variables.\
-   Use `const` and `let`.\
-   Comment important logic.\
-   Keep functions small and reusable.

------------------------------------------------------------------------

## 34. Passing Functions to Other Functions

``` js
function greet(cb) {
  cb("Hello");
}
greet(msg => console.log(msg));
```

------------------------------------------------------------------------

## 35. Named vs Anonymous Functions

-   **Named** → easier debugging, reusable.\
-   **Anonymous** → used inline, often as callbacks.

------------------------------------------------------------------------

## 36. Variable Number of Arguments

``` js
function sum(...nums) {
  return nums.reduce((a, b) => a + b, 0);
}
```

------------------------------------------------------------------------

# ✅ Conclusion

These core JavaScript concepts are the foundation for writing clean,
efficient, and maintainable code. Practicing them daily will help
solidify your understanding and make you a stronger developer.
