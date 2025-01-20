# TypeScript

> TypeScript is a powerful tool that works alongside JavaScript. It offers all the features of JavaScript while adding an extra layer: **TypeScript's type system**.

- [TypeScript](#typescript)
  - [Why TypeScript?](#why-typescript)
  - [TypeScript Basics](#typescript-basics)
    - [Types by Inference](#types-by-inference)
    - [Defining Types Explicitly](#defining-types-explicitly)
  - [Advanced TypeScript Features](#advanced-typescript-features)
    - [Composing Types with Unions](#composing-types-with-unions)
    - [Generics](#generics)
  - [TypeScript’s Structural Type System](#typescripts-structural-type-system)
  - [Key Points](#key-points)

## Why TypeScript?

1. **Builds on JavaScript**: Your JavaScript code is valid TypeScript code. TypeScript only adds features on top.
2. **Catches Errors Early**: TypeScript highlights potential errors before you even run your code, reducing bugs.
3. **Improves Developer Experience**: Tools like Visual Studio Code use TypeScript under the hood to provide features like auto-completion.

---

## TypeScript Basics

### Types by Inference

TypeScript often figures out the type of a variable for you. For example:

```typescript
let helloWorld = "Hello World"; // TypeScript knows this is a string.
```

Here, `helloWorld` is automatically assigned the type `string`. You don’t need to specify it.

### Defining Types Explicitly

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

## Advanced TypeScript Features

### Composing Types with Unions

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

### Generics

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

## TypeScript’s Structural Type System

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

## Key Points

1. **Start Small**: TypeScript can be added incrementally to your JavaScript projects.
2. **Interfaces Over Types**: Prefer `interface` for defining shapes unless you need specific features of `type`.
3. **Error Feedback**: Use TypeScript’s feedback to learn and improve your code.
