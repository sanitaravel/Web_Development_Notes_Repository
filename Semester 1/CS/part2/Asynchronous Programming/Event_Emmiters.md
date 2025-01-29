# Event Emitters in TypeScript

**Event emitters** allow different parts of an application to communicate by **emitting** and **listening** for events. This pattern is widely used in Node.js, front-end frameworks, and other TypeScript-based applications to enable a **decoupled, modular architecture**.

- [Event Emitters in TypeScript](#event-emitters-in-typescript)
  - [What Are Event Emitters?](#what-are-event-emitters)
    - [Real-World Analogy](#real-world-analogy)
  - [Using Event Emitters in TypeScript](#using-event-emitters-in-typescript)
    - [Importing and Creating an EventEmitter](#importing-and-creating-an-eventemitter)
    - [Emitting Events](#emitting-events)
    - [Listening for Events](#listening-for-events)
    - [One-Time Listeners](#one-time-listeners)
    - [Removing Event Listeners](#removing-event-listeners)
  - [Event Emitters in a Class](#event-emitters-in-a-class)
  - [Summary](#summary)

## What Are Event Emitters?

Imagine you're hosting a big party, and you hire a DJ to play music. Throughout the night, different things happen: guests arrive, someone makes a speech, or a surprise guest appears. You want to notify the DJ to change the music accordingly.

Instead of constantly checking if something has happened, the DJ listens for specific events. When an event occurs, the DJ reacts automatically. This is exactly how event emitters work in TypeScript.

### Real-World Analogy

- **Event Emitter**: The party host who announces events (e.g., "The guest of honor has arrived!").
- **Event Listeners**: The DJ and guests who listen for announcements and react accordingly.
- **Events**: Specific occurrences (e.g., "play upbeat music" when a VIP arrives).

## Using Event Emitters in TypeScript

### Importing and Creating an EventEmitter

In TypeScript (or Node.js), we can use the built-in `EventEmitter` class from the `events` module:

```typescript
import { EventEmitter } from 'events';

class MyEmitter extends EventEmitter {}

const myEmitter = new MyEmitter();
```

### Emitting Events

To trigger an event, we use `.emit(eventName, ...args)`. This notifies all listeners registered for that event.

```typescript
myEmitter.emit('greet', 'Hello, TypeScript!');
```

If there are no listeners, emitting the event does nothing.

### Listening for Events

To respond to an event, we use `.on(eventName, listener)`. The listener function runs whenever the event is emitted.

```typescript
myEmitter.on('greet', (message: string) => {
  console.log(`Received message: ${message}`);
});
```

Now, if we emit `greet`, the listener executes:

```typescript
myEmitter.emit('greet', 'Hello, TypeScript!');
// Output: Received message: Hello, TypeScript!
```

### One-Time Listeners

If we want an event to be handled only once, we use `.once(eventName, listener)`. The listener is removed after the first execution.

```typescript
myEmitter.once('greetOnce', (message: string) => {
  console.log(`This will run only once: ${message}`);
});

myEmitter.emit('greetOnce', 'First call');
myEmitter.emit('greetOnce', 'Second call');
// Output: This will run only once: First call
```

### Removing Event Listeners

We can remove event listeners using `.off(eventName, listener)` or `.removeListener(eventName, listener)`. To remove all listeners for a specific event, use `.removeAllListeners(eventName)`.

```typescript
const listener = (message: string) => console.log(message);

myEmitter.on('event', listener);
myEmitter.off('event', listener);
```

## Event Emitters in a Class

Using event emitters within a class can make an application more modular and scalable.

```typescript
class MessageBus extends EventEmitter {
  sendMessage(message: string) {
    console.log(`Sending message: ${message}`);
    this.emit('message', message);
  }
}

const bus = new MessageBus();

bus.on('message', (msg) => console.log(`Received: ${msg}`));

bus.sendMessage('Hello from MessageBus!');
```

## Summary

- **Event emitters** allow components to communicate asynchronously.
- **Listeners** subscribe to events using `.on()` or `.once()`.
- **Events** are triggered using `.emit()`.
- **Listeners can be removed** using `.off()` or `.removeListener()`.
- **Typed event emitters** help enforce type safety in TypeScript.

Event emitters are powerful tools for handling asynchronous communication in a modular and efficient way. Mastering them will help you write cleaner and more scalable TypeScript applications!
