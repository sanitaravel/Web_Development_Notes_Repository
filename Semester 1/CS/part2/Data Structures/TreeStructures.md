# Tree Structures

- [Tree Structures](#tree-structures)
  - [Common Tree Terminology](#common-tree-terminology)
  - [Searching Nodes in Trees](#searching-nodes-in-trees)
    - [Breadth-First Search (BFS)](#breadth-first-search-bfs)
    - [Depth-First Search (DFS)](#depth-first-search-dfs)
  - [Creating Trees in TypeScript](#creating-trees-in-typescript)
    - [TypeScript Implementation](#typescript-implementation)
    - [Example Usage](#example-usage)
    - [Benefits of Tree Structures](#benefits-of-tree-structures)

>A **tree** organizes data in a **parent-child relationship**, resembling a family tree or a company org chart. Each element (called a **node**) can have many children but must have exactly one parent, except for the topmost node (the **root**), which has no parent. This creates a hierarchical, branching structure that looks like an upside-down tree.

Trees are widely used in real-world scenarios, including file systems, organizational charts, XML documents, and game decision-making systems. Their hierarchical nature makes them efficient for searching and organizing data, as seen in **DOM trees** that power web browsers' rendering engines. Trees also play a crucial role in algorithms and applications, from database indexing to artificial intelligence decision-making.

## Common Tree Terminology

- **Root**: The topmost node in a tree. It serves as the starting point and has no parent.
- **Node**: Any element in the tree that contains data and can connect to other nodes. A node can be a parent, child, or both.
- **Edge**: A connection between two nodes that defines their relationship. Edges establish the hierarchical structure of the tree.
- **Leaf**: A node at the bottom of the tree with no children. Leaves mark the endpoints of branches.

## Searching Nodes in Trees

Tree traversal often uses two primary methods: **Breadth-First Search (BFS)** and **Depth-First Search (DFS)**.

### Breadth-First Search (BFS)

- **Approach**: Explores the tree level by level, examining all nodes at the current depth before moving deeper.
- **Best For**: Finding the shortest path or closest matches.
- **Data Structure**: Uses a queue to track nodes to be visited.

### Depth-First Search (DFS)

- **Approach**: Explores one complete branch before backtracking to try other branches.
- **Best For**: Finding complete paths or exploring deeply nested structures.
- **Data Structure**: Uses a stack (or recursion) to track traversal.

The choice between BFS and DFS depends on the specific task and the tree's structure.

## Creating Trees in TypeScript

Tree structures can be implemented in TypeScript using **classes** to define the blueprint for each node. A typical implementation includes:

1. A property to store data (e.g., a value).
2. An array to reference child nodes.
3. A method to add new children and establish parent-child relationships.

Here is a simple example:

### TypeScript Implementation

```typescript
class TreeNode {
  value: string;
  children: TreeNode[] = [];

  constructor(value: string) {
    this.value = value;
  }

  addChild(value: string): TreeNode {
    const child = new TreeNode(value);
    this.children.push(child);
    return child;
  }
}
```

### Example Usage

```typescript
const root = new TreeNode("Root");
const child1 = root.addChild("Child 1");
const child2 = root.addChild("Child 2");

child1.addChild("Child 1.1");
child2.addChild("Child 2.1");

console.log(root);
```

This example defines a **TreeNode** class with a `value` for data storage, a `children` array for child node references, and an `addChild` method to expand the tree dynamically.

---

### Benefits of Tree Structures

- **Efficient Searching**: Their hierarchical nature speeds up data lookup and traversal.
- **Versatile Applications**: Useful in AI decision-making, database indexing, file systems, and more.
- **Scalable Design**: Nodes can easily expand without affecting the rest of the tree.
