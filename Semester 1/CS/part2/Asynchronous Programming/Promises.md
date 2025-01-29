# Understanding Promises in JavaScript

A **Promise** in JavaScript is a powerful tool for handling asynchronous operations. It acts as a placeholder for a value that may be available now, in the future, or never. Promises bridge the gap between **producing code** (which takes time) and **consuming code** (which needs the result).

- [Understanding Promises in JavaScript](#understanding-promises-in-javascript)
  - [Promise Constructor](#promise-constructor)
    - [Syntax](#syntax)
    - [Example: Constructor Usage](#example-constructor-usage)
  - [Promise States](#promise-states)
  - [Handling Promises](#handling-promises)
    - [`.then()`](#then)
    - [`.catch()`](#catch)
    - [`.finally()`](#finally)
  - [Chaining Promises](#chaining-promises)
    - [Example: Chaining Promises](#example-chaining-promises)
  - [Error Handling in Promise Chains](#error-handling-in-promise-chains)
    - [Example: Handling Usage](#example-handling-usage)
  - [Converting Callbacks to Promises](#converting-callbacks-to-promises)
    - [Example: Load a script with a Promise](#example-load-a-script-with-a-promise)
  - [Benefits of Promises over Callbacks](#benefits-of-promises-over-callbacks)
  - [Conclusion](#conclusion)

## Promise Constructor

A Promise object is created using the `Promise` constructor, which takes an **executor** function as an argument. The executor function receives two callbacks:

- `resolve(value)`: Called when the operation is successful.
- `reject(error)`: Called when an error occurs.

### Syntax

```javascript
let promise = new Promise(function(resolve, reject) {
  // Executor function
});
```

### Example: Constructor Usage

```javascript
let promise = new Promise(function(resolve, reject) {
  setTimeout(() => resolve("done"), 1000); // Resolves after 1 second
});
```

## Promise States

A Promise has three possible states:

1. **Pending**: Initial state, before completion or failure.
2. **Fulfilled**: Successfully completed with a value.
3. **Rejected**: Failed with an error.

## Handling Promises

To consume the result of a Promise, we use **.then(), .catch(), and .finally()**.

### `.then()`

Used to handle successful completion:

```javascript
promise.then(
  result => console.log(result), // Handles success
  error => console.log(error)  // Handles failure (optional)
);
```

### `.catch()`

Used to handle errors:

```javascript
promise.catch(error => console.log(error));
```

This is equivalent to `.then(null, errorHandler)`, but cleaner.

### `.finally()`

Runs regardless of success or failure:

```javascript
promise.finally(() => console.log("Cleanup"));
```

## Chaining Promises

Since `.then()` returns a new Promise, we can **chain** them to sequence multiple asynchronous operations.

### Example: Chaining Promises

```javascript
new Promise(resolve => setTimeout(() => resolve(1), 1000))
  .then(result => {
    console.log(result); // 1
    return result * 2;
  })
  .then(result => {
    console.log(result); // 2
    return result * 3;
  })
  .then(result => console.log(result)); // 6
```

## Error Handling in Promise Chains

Errors propagate down the chain and can be caught with `.catch()`.

### Example: Handling Usage

```javascript
new Promise((resolve, reject) => {
  throw new Error("Something went wrong");
})
  .then(result => console.log(result))
  .catch(error => console.log("Caught error:", error.message));
```

## Converting Callbacks to Promises

A common use case for Promises is **converting callback-based functions** into Promise-based functions.

### Example: Load a script with a Promise

```javascript
function loadScript(src) {
  return new Promise((resolve, reject) => {
    let script = document.createElement('script');
    script.src = src;
    
    script.onload = () => resolve(script);
    script.onerror = () => reject(new Error(`Script load error for ${src}`));
    
    document.head.append(script);
  });
}

loadScript("https://cdnjs.cloudflare.com/ajax/libs/lodash.js/4.17.11/lodash.js")
  .then(script => console.log("Loaded script:", script.src))
  .catch(error => console.log(error.message));
```

## Benefits of Promises over Callbacks

| Feature | Promises | Callbacks |
|:---------:|:---------:|:----------:|
| Multiple handlers | Yes | No |
| Chaining | Yes | No |
| Error propagation | Yes | No |
| Readability | High | Low |

## Conclusion

Promises improve **code structure, readability, and flexibility** in handling asynchronous operations. By using `.then()`, `.catch()`, and `.finally()`, we can effectively manage success, failure, and cleanup tasks in a clean and predictable way.
