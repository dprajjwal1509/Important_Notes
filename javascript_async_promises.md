# JavaScript Execution, Asynchronous Programming & Promises -- Technical Paper

## 1. How JavaScript Executes Code

-   JavaScript is **single-threaded** and executes code line by line in
    a synchronous manner.\
-   It uses a **Call Stack** to track execution.\
-   Long-running tasks (e.g., network requests, timers) are offloaded to
    **Web APIs** and results are pushed to the **callback queue**.\
-   The **Event Loop** constantly checks if the Call Stack is empty and
    then pushes callbacks into execution.

------------------------------------------------------------------------

## 2. Sync vs Async

-   **Synchronous (Sync):**
    -   Executes line by line.
    -   Each task must complete before the next begins.
    -   Example: simple math operations.
-   **Asynchronous (Async):**
    -   Tasks can be delegated to external APIs and executed later.
    -   Example: `setTimeout`, network requests.

------------------------------------------------------------------------

## 3. Ways to Make Code Asynchronous

-   `setTimeout`, `setInterval`\
-   Web APIs (DOM events, fetch, XMLHttpRequest)\
-   Promises\
-   `async/await`

------------------------------------------------------------------------

## 4. Web Browser APIs

-   Built-in APIs provided by browsers.\
-   Examples: `DOM API`, `setTimeout`, `fetch`, `localStorage`,
    `Geolocation`, `Canvas API`.

------------------------------------------------------------------------

## 5. Event Loop

-   Coordinates execution of code, handling of events, and execution of
    queued tasks.\
-   Steps:
    1.  Executes synchronous code from the Call Stack.\
    2.  Moves completed async tasks from Callback Queue to Call Stack.\
    3.  Repeats infinitely.

------------------------------------------------------------------------

## 6. Callback Hell

-   Nested callbacks that make code unreadable and difficult to
    maintain.

``` js
doTask1(function(result1) {
  doTask2(result1, function(result2) {
    doTask3(result2, function(result3) {
      console.log(result3);
    });
  });
});
```

------------------------------------------------------------------------

## 7. Inversion of Control in Callbacks

-   Callback-based async programming hands over control of execution to
    another function.\
-   This can lead to bugs if the external function misuses or ignores
    the callback.

------------------------------------------------------------------------

# Promises

## 8. What is a Promise?

-   A promise represents the eventual result of an asynchronous
    operation.\
-   It acts as a placeholder for a value that will be available later.

------------------------------------------------------------------------

## 9. Creating a New Promise

``` js
const myPromise = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve("Success!");
  }, 1000);
});
```

------------------------------------------------------------------------

## 10. Promise States

-   **Pending** → initial state.\
-   **Fulfilled** → operation completed successfully.\
-   **Rejected** → operation failed.

------------------------------------------------------------------------

## 11. Consuming a Promise

``` js
myPromise
  .then(value => console.log(value))
  .catch(error => console.error(error));
```

------------------------------------------------------------------------

# Promise Chaining

## 12. Chaining Promises with `.then`

``` js
fetchData()
  .then(data => process(data))
  .then(result => display(result));
```

------------------------------------------------------------------------

## 13. Handling Errors with `.catch`

``` js
fetchData()
  .then(data => process(data))
  .catch(error => console.error("Error:", error));
```

------------------------------------------------------------------------

## 14. finally Block in Promise Chain

``` js
fetchData()
  .then(data => process(data))
  .catch(error => console.error(error))
  .finally(() => console.log("Execution completed"));
```

------------------------------------------------------------------------

## 15. Errors Inside `.then`

-   If error is thrown inside `.then`:
    -   With `.catch`: error is caught.\
    -   Without `.catch`: error goes unhandled.

------------------------------------------------------------------------

## 16. Why `.catch` Must Be at the End?

-   To ensure any error in the chain is caught.\
-   Acts as a safety net for unhandled errors.

------------------------------------------------------------------------

## 17. Consuming Multiple Promises

### By Chaining

``` js
doTask1()
  .then(doTask2)
  .then(doTask3)
  .catch(console.error);
```

### By `Promise.all`

``` js
Promise.all([task1(), task2(), task3()])
  .then(results => console.log(results))
  .catch(error => console.error(error));
```

------------------------------------------------------------------------

## 18. Error Handling with Promises

-   Errors must be caught with `.catch`.\
-   Avoids unhandled promise rejections.\
-   Ensures program stability.

------------------------------------------------------------------------

## 19. Why Error Handling is Important?

-   Prevents crashes.\
-   Makes debugging easier.\
-   Ensures fallback logic is executed.

------------------------------------------------------------------------

## 20. Promisifying Callback-based Functions

``` js
function delay(ms) {
  return new Promise(resolve => setTimeout(resolve, ms));
}

delay(1000).then(() => console.log("1 second passed"));
```

------------------------------------------------------------------------

# Promise Utility Methods

## 21. `Promise.resolve`

Creates a resolved promise.

``` js
Promise.resolve(42).then(console.log);
```

## 22. `Promise.reject`

Creates a rejected promise.

``` js
Promise.reject("Error!").catch(console.error);
```

## 23. `Promise.all`

Runs all promises in parallel, fails fast on first rejection.

``` js
Promise.all([p1, p2, p3])
  .then(values => console.log(values))
  .catch(err => console.error(err));
```

## 24. `Promise.allSettled`

Waits for all promises, regardless of success or failure.

``` js
Promise.allSettled([p1, p2, p3]).then(console.log);
```

## 25. `Promise.any`

Returns first fulfilled promise, ignores rejections.

``` js
Promise.any([p1, p2, p3])
  .then(value => console.log(value))
  .catch(err => console.error("All failed"));
```

## 26. `Promise.race`

Returns first settled promise (success or failure).

``` js
Promise.race([p1, p2, p3]).then(console.log).catch(console.error);
```

------------------------------------------------------------------------

# ✅ Conclusion

-   JavaScript is synchronous by default, but async programming makes it
    powerful.\
-   Promises solve callback hell and inversion of control.\
-   Mastery of promise chaining, error handling, and utility methods is
    essential for real-world JavaScript development.
