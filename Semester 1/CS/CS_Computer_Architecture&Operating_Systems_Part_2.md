# Computer Science | Computer Architecture and Operating Systems | Part 2

## Table of Contents

1. [TypeScript](#typescript)
    1. [Why TypeScript?](#why-typescript)
    2. [TypeScript Basics](#typescript-basics)
        1. [Types by Inference](#types-by-inference)
        2. [Defining Types Explicitly](#defining-types-explicitly)
    3. [Advanced TypeScript Features](#advanced-typescript-features)
        1. [Composing Types with Unions](#composing-types-with-unions)
        2. [Generics](#generics)
    4. [TypeScript’s Structural Type System](#typescripts-structural-type-system)
    5. [Key Points](#key-points)
2. [Search Algorithms](#search-algorithms)
    1. [What Are Search Algorithms?](#what-are-search-algorithms)
    2. [Examples of Search Problems](#examples-of-search-problems)
        1. [Timetable Optimization](#timetable-optimization)
        2. [Pathfinding](#pathfinding)
        3. [Integer Factorization](#integer-factorization)
    3. [How Do Search Algorithms Work?](#how-do-search-algorithms-work)
    4. [Search Algorithms You Should Know](#search-algorithms-you-should-know)
        1. [Binary Search](#binary-search)
        2. [Binary Search Pseudocode](#binary-search-pseudocode)
3. [Unit Testing](#unit-testing)
    1. [What Do Unit Tests Look Like?](#what-do-unit-tests-look-like)
    2. [Who Should Create Unit Tests?](#who-should-create-unit-tests)
    3. [How Can You Use Unit Tests?](#how-can-you-use-unit-tests)
        1. [Test-Driven Development (TDD)](#test-driven-development-tdd)
        2. [Checking Your Work](#checking-your-work)
        3. [Code Documentation](#code-documentation)
    4. [When Should You Avoid Unit Testing?](#when-should-you-avoid-unit-testing)
    5. [Common Problems in Unit Testing](#common-problems-in-unit-testing)

## TypeScript

TypeScript is a powerful tool that works alongside JavaScript. It offers all the features of JavaScript while adding an extra layer: **TypeScript's type system**.

### Why TypeScript?

1. **Builds on JavaScript**: Your JavaScript code is valid TypeScript code. TypeScript only adds features on top.
2. **Catches Errors Early**: TypeScript highlights potential errors before you even run your code, reducing bugs.
3. **Improves Developer Experience**: Tools like Visual Studio Code use TypeScript under the hood to provide features like auto-completion.

---

### TypeScript Basics

#### Types by Inference

TypeScript often figures out the type of a variable for you. For example:

```typescript
let helloWorld = "Hello World"; // TypeScript knows this is a string.
```

Here, `helloWorld` is automatically assigned the type `string`. You don’t need to specify it.

#### Defining Types Explicitly

Sometimes, you might want to explicitly define the type of a variable or object. For example:

```typescript
interface User {
  name: string;
  id: number;
}

const user: User = {
  name: "Hayes",
  id: 0,
};
```

If you accidentally assign a property that isn’t in the `User` interface, TypeScript will warn you:

```typescript
const user: User = {
  username: "Hayes", // Error: 'username' does not exist in type 'User'.
  id: 0,
};
```

### Advanced TypeScript Features

#### Composing Types with Unions

A **union** type allows a variable to have multiple possible types. For example:

```typescript
type WindowStates = "open" | "closed" | "minimized";
type LockStates = "locked" | "unlocked";
```

You can use unions to write flexible functions:

```typescript
function getLength(obj: string | string[]) {
  return obj.length;
}
```

#### Generics

Generics allow you to create reusable components with types:

```typescript
interface Backpack<Type> {
  add: (obj: Type) => void;
  get: () => Type;
}

const backpack: Backpack<string> = {
  add: (item) => console.log(item),
  get: () => "item",
};

backpack.add("Book"); // Works fine.
backpack.add(23); // Error: Argument of type 'number' is not assignable to parameter of type 'string'.
```

### TypeScript’s Structural Type System

TypeScript uses **structural typing**, meaning it checks whether objects have the required shape, not necessarily the same type.

Example:

```typescript
interface Point {
  x: number;
  y: number;
}

function logPoint(p: Point) {
  console.log(`${p.x}, ${p.y}`);
}

const point = { x: 12, y: 26 };
logPoint(point); // Works fine.
```

Even though `point` is not explicitly declared as a `Point` type, its structure matches, so it’s valid.

### Key Points

1. **Start Small**: TypeScript can be added incrementally to your JavaScript projects.
2. **Interfaces Over Types**: Prefer `interface` for defining shapes unless you need specific features of `type`.
3. **Error Feedback**: Use TypeScript’s feedback to learn and improve your code.

## Search Algorithms

> 💡 In computer science, **"search"** doesn’t just mean looking for a single item, like the definition of a word or a bus schedule. Instead, it often involves finding an **optimal series of steps** to solve a problem. This makes search algorithms central to many applications, from timetables to route planning.

### What Are Search Algorithms?

> 💡 Search algorithms explore a **defined domain** (or **search space**) to find answers. For example, imagine trying to find someone's phone number in a phone book. The search space includes all the entries in the phone book.

Smart search algorithms reduce the search space, narrowing down millions of possibilities into a manageable subset. In our phone book example, the data is one-dimensional and ordered, making it one of the simplest cases to handle.

Search is closely linked to **sorting algorithms** because the way data is structured heavily influences search efficiency.

### Examples of Search Problems

#### Timetable Optimization

A university has many rooms and classes with constraints like professor availability and student schedules. The combinations are vast, making an exhaustive search impractical. Smart algorithms can optimize the allocation of rooms and schedules efficiently.

#### Pathfinding

Route planning, like finding the best path through a city, is a more complex problem. "Best" might mean fastest, least traffic, or a scenic route. Algorithms convert cities into **graphs** (nodes for locations, edges for paths) to create a searchable structure.

#### Integer Factorization

Breaking an integer into prime factors is a key problem in cryptography. For example, RSA encryption keys are products of two large primes. While multiplying two primes is easy, reversing the process is hard because of the vast search space involved.

### How Do Search Algorithms Work?

> 💡 The simplest method, **brute force**, tries all possible combinations until it finds the solution. For example, in an unordered library, you’d check every book until you find the one you want. While sometimes necessary, brute force is inefficient and impractical for large search spaces.

### Search Algorithms You Should Know

#### Binary Search

Binary search is a simple and effective algorithm that works on **ordered data**.

- **Example**: Finding "Eli" in an alphabetically ordered phone book.
  - Open the book to the middle. If you're at "J," ignore everything after it since "E" comes before "J."
  - Repeat the process by focusing only on the relevant half each time.
  - Continue until you find "Eli."

This method reduces complexity to **O(log n)**. For a phone book with 1,000 entries, binary search takes at most 10 steps.

---

#### Binary Search Pseudocode

Here’s how the binary search algorithm works in pseudocode:

```js
function binarySearch(array, target):
    left = 0
    right = array.length - 1
    
    while left ≤ right:
        mid = floor((left + right) / 2)
        
        if array[mid] == target:
            return mid  // Target found at index mid
        else if array[mid] < target:
            left = mid + 1  // Narrow search to the right half
        else:
            right = mid - 1  // Narrow search to the left half
    
    return -1  // Target not found
```

#### Key Points

- **Input**: A sorted array and the target element to find.
- **Process**: Repeatedly divide the array into halves, comparing the middle element to the target.
- **Output**: The index of the target element, or `-1` if the element is not found.

## Unit Testing

> 💡 Unit testing involves testing the **smallest piece of code** that can be logically isolated, such as a function, method, or property.

The key point is isolation: tests should not rely on external systems like databases or networks. Michael Feathers, in *Working Effectively with Legacy Code*, states:  
> *"If it talks to the database, it talks across the network, it touches the file system, it requires system configuration, or it can't be run at the same time as any other test, it’s not a unit test."*

Unit testing frameworks like **JUnit**, **TestComplete**, and the original **SUnit** (created by Kent Beck) have been pivotal in software development. Despite its long history, unit testing remains essential for building reliable, maintainable software.

### What Do Unit Tests Look Like?

A unit test can focus on:

- A **line of code**
- A **method**
- A **class**

Smaller tests are generally better since they run faster and provide more granular feedback. For example, consider the following simple function:

#### TypeScript Example

```typescript
function divider(a: number, b: number): number {
  return a / b;
}
```

A corresponding unit test written using **Jest** might look like this:

#### Unit Test in TypeScript

```typescript
import { describe, it, expect } from '@jest/globals';

describe("divider function", () => {
  it("should divide two numbers correctly", () => {
    const a = 9;
    const b = 3;
    const result = divider(a, b);
    expect(result).toBe(3);
  });

  it("should throw an error when dividing by zero", () => {
    const a = 9;
    const b = 0;
    expect(() => divider(a, b)).toThrow();
  });
});
```

This test suite ensures the function works correctly and handles edge cases. Notice how it avoids dependencies on external systems, keeping the test focused and efficient.

---

### Who Should Create Unit Tests?

Unit testing is often part of the programming phase, handled by the developer who wrote the code. This approach makes sense because the developer:

- Knows how to access the testable components.
- Can mock objects effectively.

However, unit tests can also be added later to safeguard refactoring or extending the codebase.

### How Can You Use Unit Tests?

#### Test-Driven Development (TDD)

TDD involves writing tests **before** production code:

1. Write a test.
2. Write the code to make the test pass.
3. Refactor the code for clarity or efficiency.

This iterative process ensures clean, well-tested code. While TDD can be challenging to adopt, it fosters better design and confidence in refactoring.

#### Checking Your Work

Writing tests **after** the production code is a more traditional approach but equally valuable. Tests verify that the code works as expected and act as a **change detection system**, alerting you to unintended side effects during development.

#### Code Documentation

Unit tests can serve as **living documentation** by showing how the code is intended to be used. This reduces the need for traditional documentation and helps new developers understand the system.

### When Should You Avoid Unit Testing?

Unit testing is not always the right tool. For example:

- **Integration tests**: Crossing system boundaries (e.g., databases, APIs) can slow test execution. Specialized integration testing frameworks are better suited for this purpose.
- **End-to-end tests**: These require careful setup and dependencies, making them unsuitable for unit testing frameworks.

Using unit testing frameworks for these cases may result in more work than benefit.

### Common Problems in Unit Testing

1. **Cultural Resistance**  
Developers may struggle to adapt to unit testing if they are used to manual testing methods. A team champion who advocates for best practices can help overcome this barrier.

2. **Overtesting**  
More tests don’t always mean better tests. Focus on **smart testing** that delivers meaningful insights quickly.
