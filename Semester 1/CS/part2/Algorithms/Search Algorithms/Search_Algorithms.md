# Search Algorithms

- [Search Algorithms](#search-algorithms)
  - [What Are Search Algorithms?](#what-are-search-algorithms)
    - [Examples of Search Problems](#examples-of-search-problems)
      - [Timetable Optimization](#timetable-optimization)
      - [Pathfinding](#pathfinding)
      - [Integer Factorization](#integer-factorization)
      - [How Do Search Algorithms Work?](#how-do-search-algorithms-work)

> 💡 In computer science, **"search"** doesn’t just mean looking for a single item, like the definition of a word or a bus schedule. Instead, it often involves finding an **optimal series of steps** to solve a problem. This makes search algorithms central to many applications, from timetables to route planning.

## What Are Search Algorithms?

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

#### How Do Search Algorithms Work?

> 💡 The simplest method, **brute force**, tries all possible combinations until it finds the solution. For example, in an unordered library, you’d check every book until you find the one you want. While sometimes necessary, brute force is inefficient and impractical for large search spaces.
