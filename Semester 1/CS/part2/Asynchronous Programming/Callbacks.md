# Understanding Callbacks in TypeScript

A **callback** is a function passed as an argument to another function, allowing it to execute at a specific time, often after completing an operation. Callbacks are fundamental in JavaScript and TypeScript, enabling **asynchronous programming** and **modular code design**.

- [Understanding Callbacks in TypeScript](#understanding-callbacks-in-typescript)
  - [Basic Callback Example](#basic-callback-example)
  - [Syntax](#syntax)
  - [Why Use Callbacks?](#why-use-callbacks)
  - [Key Concepts of Callbacks](#key-concepts-of-callbacks)
  - [Real-Life Examples](#real-life-examples)
    - [1. Loading Images on a Website](#1-loading-images-on-a-website)
    - [2. Handling Form Submissions](#2-handling-form-submissions)
  - [Example: Callback in an Asynchronous Function](#example-callback-in-an-asynchronous-function)
  - [Example: Callback with `Array.forEach()`](#example-callback-with-arrayforeach)
  - [Advantages of Callbacks](#advantages-of-callbacks)

## Basic Callback Example

```typescript
function greet(name: string, callback: () => void) {
    console.log(`Hello, ${name}!`);
    callback();
}

function sayGoodbye() {
    console.log("Goodbye!");
}

greet("GFG", sayGoodbye);
```

**Output:**

```text
Hello, GFG!
Goodbye!
```

## Syntax

```typescript
function mainFunction(param1: string, callbackFunction: () => void) {
    // Perform some tasks
    callbackFunction(); // Invoke the callback
}
```

## Why Use Callbacks?

Callbacks help manage **asynchronous tasks** without blocking execution. Without them, operations like API requests or database queries would freeze the program until completion, causing a sluggish experience.

Using callbacks ensures the program continues running while tasks execute in the background, making applications more **responsive** and **efficient**.

## Key Concepts of Callbacks

**1. Asynchronous Programming**: Callbacks handle the results of asynchronous operations, allowing the program to continue running while waiting for tasks to complete.

**2. Non-Blocking Execution**: Callbacks enable non-blocking programming, improving application performance and responsiveness.

**3. Higher-Order Functions**: A function that takes another function as an argument or returns a function is called a higher-order function. The `mainFunction` example above is one such function.

**4. Anonymous Functions**: Functions without names, often used as callbacks. For example, the function passed to `setTimeout` is an anonymous function.

**5. Closure**: A callback function can access variables from its outer function, even after the outer function has finished execution.

## Real-Life Examples

### 1. Loading Images on a Website

If images loaded synchronously, a webpage would freeze until each image was fully downloaded. Callbacks allow images to load in the background while the rest of the page remains functional.

### 2. Handling Form Submissions

When a user submits a form, data processing takes time. Without callbacks, users would have to wait for the entire process to complete before continuing to interact with the form.

## Example: Callback in an Asynchronous Function

```typescript
function mainFunction(callback: (result: string) => void) {
  console.log("Performing operation...");
  setTimeout(() => {
    callback("Operation complete");
  }, 1000);
}

function callbackFunction(result: string) {
  console.log("Result: " + result);
}

mainFunction(callbackFunction);
```

**Output:**

```text
Performing operation...
Result: Operation complete
```

## Example: Callback with `Array.forEach()`

```typescript
let numbers = [1, 2, 3, 4, 5];
function mainFunction(callback: (num: number) => void) {
  console.log("Processing numbers...");
  numbers.forEach(callback);
}

function callbackFunction(number: number) {
  console.log("Result: " + number);
}

mainFunction(callbackFunction);
```

**Output:**

```text
Processing numbers...
Result: 1
Result: 2
Result: 3
Result: 4
Result: 5
```

## Advantages of Callbacks

- **Asynchronous Execution**: Prevents blocking, ensuring a smooth user experience.
- **Modular Code**: Enhances reusability by allowing functions to accept different callbacks.
- **Event-Driven Approach**: Aligns with JavaScript’s event-driven programming model.

---

Callbacks are a powerful concept in TypeScript that help handle asynchronous operations efficiently. Mastering callbacks lays a strong foundation for understanding **Promises** and **async/await**.
