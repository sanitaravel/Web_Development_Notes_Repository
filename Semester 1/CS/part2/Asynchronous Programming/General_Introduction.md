# Introduction to Asynchronous Code in TypeScript

When writing code, we often need to perform tasks that take time to complete, such as reading files, fetching data from a server, or waiting for user input. If we handled these tasks in a normal, step-by-step manner (**synchronous execution**), our program could freeze while waiting for each task to finish. To prevent this, we use **asynchronous programming**.

- [Introduction to Asynchronous Code in TypeScript](#introduction-to-asynchronous-code-in-typescript)
  - [Why Asynchronous Code?](#why-asynchronous-code)
  - [How Asynchronous Code Works](#how-asynchronous-code-works)
    - [1. Callbacks](#1-callbacks)
    - [2. Promises](#2-promises)
    - [3. Event Emitters](#3-event-emitters)
  - [Summary](#summary)

## Why Asynchronous Code?

Asynchronous code allows tasks to run in the background **without blocking** the main execution of the program. This means your application remains **responsive and efficient**.

> Imagine if a webpage froze every time it fetched data. Asynchronous programming prevents such issues and keeps applications smooth.

## How Asynchronous Code Works

Instead of executing one line after another in order, **asynchronous code schedules tasks** to be completed later. TypeScript (and JavaScript) uses an **event loop** to manage these tasks.

Some common ways to handle asynchronous code include:

### 1. Callbacks

A **callback** is a function passed as an argument to another function, to be executed later when an operation completes.

```typescript
function fetchData(callback: (data: string) => void) {
    setTimeout(() => {
        callback("Data loaded");
    }, 2000);
}

fetchData((result) => {
    console.log(result);
});
```

> Callbacks are useful but can lead to **callback hell** if nested too deeply.

### 2. Promises

A **Promise** is an object that represents a value that may be available now, in the future, or never.

```typescript
function fetchData(): Promise<string> {
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve("Data loaded");
        }, 2000);
    });
}

fetchData().then((result) => console.log(result));
```

> Promises help avoid callback hell and make code **more readable**.

### 3. Event Emitters

**Event emitters** are used to handle multiple asynchronous events, such as user interactions or real-time data updates.

```typescript
import { EventEmitter } from "events";

const emitter = new EventEmitter();

emitter.on("dataReceived", (data) => {
    console.log("Received:", data);
});

setTimeout(() => {
    emitter.emit("dataReceived", "Some data");
}, 2000);
```

> Event emitters are powerful for **handling multiple events dynamically**.

## Summary

- **Asynchronous code** helps keep applications **responsive**.
- The **event loop** manages asynchronous tasks.
- Common methods to handle async code include **callbacks, promises, and event emitters**.

> Each of these methods has its own **advantages and use cases**, which we will explore in separate notes.
