# JavaScript and CSS Technical Concepts

## 1. Currying in JavaScript

Currying is a functional programming technique in JavaScript where a
function with multiple arguments is transformed into a series of
functions, each taking a single argument.\
For example:

``` javascript
function add(a) {
  return function(b) {
    return a + b;
  };
}

console.log(add(5)(3)); // Output: 8
```

This technique allows **reusability** and **function customization**.

------------------------------------------------------------------------

## 2. Events in JavaScript

An **event** is an action or occurrence recognized by the browser, such
as user interactions or system-generated signals.

### Common Types of Events:

1.  **Mouse Events** -- e.g., `click`, `dblclick`, `mouseenter`,
    `mouseleave`\
2.  **Keyboard Events** -- e.g., `keydown`, `keyup`, `keypress`\
3.  **Form Events** -- e.g., `submit`, `focus`, `blur`, `change`\
4.  **Window Events** -- e.g., `load`, `resize`, `scroll`, `unload`\
5.  **Touch Events** (mobile) -- e.g., `touchstart`, `touchmove`,
    `touchend`

------------------------------------------------------------------------

## 3. Drawbacks of Promises compared to Callbacks

While Promises improve readability over callbacks, they still have some
drawbacks: - **Verbosity**: For very simple async operations, callbacks
may be shorter.\
- **Error handling**: Errors may be swallowed if `.catch()` is not
used.\
- **Complexity in branching**: When multiple dependent or conditional
async tasks exist, promise chaining can get complicated.\
- **Not cancellation-friendly**: Promises cannot be easily canceled once
started, unlike some callback-driven systems.

------------------------------------------------------------------------

## 4. Promise Chaining in JavaScript

Promise chaining is the process of executing multiple asynchronous tasks
sequentially, where each `.then()` passes its result to the next.

Example:

``` javascript
new Promise((resolve, reject) => {
  resolve(2);
})
.then(result => {
  console.log(result); // 2
  return result * 2;
})
.then(result => {
  console.log(result); // 4
  return result * 3;
})
.then(result => {
  console.log(result); // 12
});
```

------------------------------------------------------------------------

## 5. Difference between px, em, and rem in CSS

-   **px (pixels)** -- Absolute unit, fixed size independent of parent
    or root element.\
-   **em** -- Relative to the **font-size of the parent element**.\
-   **rem (root em)** -- Relative to the **font-size of the root
    `<html>` element**.

Example:

``` css
html { font-size: 16px; }
div { font-size: 2em; }   /* 2 * parent font-size */
p { font-size: 2rem; }   /* 2 * root font-size */
```

------------------------------------------------------------------------

## 6. Why are Closures Helpful in JavaScript?

A **closure** is a function that remembers the scope in which it was
created, even after that scope has finished executing.

Benefits: - **Data privacy** -- Variables remain private inside
closures.\
- **State preservation** -- Functions can "remember" values between
calls.\
- **Function factories** -- Can dynamically create customized functions.

Example:

``` javascript
function counter() {
  let count = 0;
  return function() {
    count++;
    return count;
  };
}

const myCounter = counter();
console.log(myCounter()); // 1
console.log(myCounter()); // 2
```

Closures make JavaScript more powerful by enabling encapsulation and
modular programming.
