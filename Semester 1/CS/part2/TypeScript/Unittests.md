# Unit Testing

- [Unit Testing](#unit-testing)
  - [What Do Unit Tests Look Like?](#what-do-unit-tests-look-like)
    - [TypeScript Example](#typescript-example)
    - [Unit Test in TypeScript](#unit-test-in-typescript)
  - [Who Should Create Unit Tests?](#who-should-create-unit-tests)
  - [How Can You Use Unit Tests?](#how-can-you-use-unit-tests)
    - [Test-Driven Development (TDD)](#test-driven-development-tdd)
    - [Checking Your Work](#checking-your-work)
    - [Code Documentation](#code-documentation)
  - [When Should You Avoid Unit Testing?](#when-should-you-avoid-unit-testing)
  - [Common Problems in Unit Testing](#common-problems-in-unit-testing)

> 💡 Unit testing involves testing the **smallest piece of code** that can be logically isolated, such as a function, method, or property.

The key point is isolation: tests should not rely on external systems like databases or networks. Michael Feathers, in *Working Effectively with Legacy Code*, states:  
> *"If it talks to the database, it talks across the network, it touches the file system, it requires system configuration, or it can't be run at the same time as any other test, it’s not a unit test."*

Unit testing frameworks like **JUnit**, **TestComplete**, and the original **SUnit** (created by Kent Beck) have been pivotal in software development. Despite its long history, unit testing remains essential for building reliable, maintainable software.

## What Do Unit Tests Look Like?

A unit test can focus on:

- A **line of code**
- A **method**
- A **class**

Smaller tests are generally better since they run faster and provide more granular feedback. For example, consider the following simple function:

### TypeScript Example

```typescript
function divider(a: number, b: number): number {
  return a / b;
}
```

A corresponding unit test written using **Jest** might look like this:

### Unit Test in TypeScript

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

## Who Should Create Unit Tests?

Unit testing is often part of the programming phase, handled by the developer who wrote the code. This approach makes sense because the developer:

- Knows how to access the testable components.
- Can mock objects effectively.

However, unit tests can also be added later to safeguard refactoring or extending the codebase.

## How Can You Use Unit Tests?

### Test-Driven Development (TDD)

TDD involves writing tests **before** production code:

1. Write a test.
2. Write the code to make the test pass.
3. Refactor the code for clarity or efficiency.

This iterative process ensures clean, well-tested code. While TDD can be challenging to adopt, it fosters better design and confidence in refactoring.

### Checking Your Work

Writing tests **after** the production code is a more traditional approach but equally valuable. Tests verify that the code works as expected and act as a **change detection system**, alerting you to unintended side effects during development.

### Code Documentation

Unit tests can serve as **living documentation** by showing how the code is intended to be used. This reduces the need for traditional documentation and helps new developers understand the system.

## When Should You Avoid Unit Testing?

Unit testing is not always the right tool. For example:

- **Integration tests**: Crossing system boundaries (e.g., databases, APIs) can slow test execution. Specialized integration testing frameworks are better suited for this purpose.
- **End-to-end tests**: These require careful setup and dependencies, making them unsuitable for unit testing frameworks.

Using unit testing frameworks for these cases may result in more work than benefit.

## Common Problems in Unit Testing

1. **Cultural Resistance**  
Developers may struggle to adapt to unit testing if they are used to manual testing methods. A team champion who advocates for best practices can help overcome this barrier.

2. **Overtesting**  
More tests don’t always mean better tests. Focus on **smart testing** that delivers meaningful insights quickly.
