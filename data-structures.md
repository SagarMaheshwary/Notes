# DATA STRUCTURES

### COMMON

- Array
- String
- Stack
- Queue
- Circular Queue
- Linked List
- Circular Linked List
- Doubly Linked List
- Hash Table
- Tree/Binary Search Tree
- Graph

### HASH TABLE

- A hash table, also known as a hash map, is a data structure that provides efficient data retrieval based on a key. It uses a hash function to map keys to indices in an array, where associated values are stored. Hash tables are widely used in computer science and software development for their O(1) average time complexity for common operations such as insertion, deletion, and retrieval.
- Object in JavaScript is a special type of HashTable implementation. (as it has some predefined keys)
- Hash collision occurs when has of multiple keys map to the same index.
- Handling of collisions can be done in two ways:

  - Separate Chaining with Linked Lists:
    - In separate chaining, you use an array of buckets, and each bucket contains a linked list of key-value pairs that map to the same hash value. When a collision occurs, the new key-value pair is added to the linked list in the corresponding bucket.
    - Advantages:
    - Easy to implement.
    - Efficient for handling multiple collisions, especially in situations where collisions are frequent.
    - Supports an arbitrary number of collisions for each bucket.
    - Trade-offs:
    - Slightly less memory-efficient than open addressing, as it requires additional memory for linked lists.
    - Search operations may have a slightly higher time complexity in the worst case when multiple collisions occur (O(n), where n is the number of elements in the linked list).
  - Open Addressing with Arrays:
    - In open addressing, when a collision occurs, the algorithm probes for the next available slot in the hash table. There are various probing methods, such as linear probing, quadratic probing, and double hashing, that determine the sequence of slots to check.
    - Advantages:
    - More memory-efficient than separate chaining since it doesn't require additional memory for linked lists.
    - Can be faster for simple hash functions with infrequent collisions, as there's no need to traverse a linked list.
    - Trade-offs:
    - Less efficient when multiple collisions occur, especially with a high load factor, as probing for available slots can become more time-consuming.
    - Handling a large number of collisions can be more complex and less predictable than using linked lists.

#### IMPLEMETATION

```typescript
//Using arrays for handling hash collision

class HashTable {
  items: any[];

  constructor(private size: number) {
    this.items = Array(size);
  }

  hash(key: string) {
    let total = 0;
    for (let i = 0; i < key.length; i++) {
      total += key.charCodeAt(i);
    }

    return total % this.size;
  }

  set(key: string, value: any) {
    const hash = this.hash(key);

    const bucket: any[] = this.items[hash];

    if (bucket !== undefined) {
      const itemIndex = bucket.findIndex((item) => item[0] === key);

      if (itemIndex > -1) {
        bucket[itemIndex] = [key, value];
      } else {
        bucket.push([key, value]);
      }

      this.items[hash] = bucket;
    } else {
      this.items[hash] = [[key, value]];
    }
  }

  get(key: string) {
    const bucket = this.items[this.hash(key)];

    if (bucket !== undefined) {
      const item = bucket.find((item) => item[0] === key);

      if (item !== undefined) {
        return item[1];
      }
    }

    return undefined;
  }

  delete(key: string) {
    const hash = this.hash(key);
    const bucket: any[] = this.items[hash];

    if (bucket !== undefined) {
      this.items[hash] = bucket.filter((item) => item[0] !== key);
    }
  }

  print() {
    for (let i = 0; i < this.size; i++) {
      if (this.items[i] !== undefined) {
        console.log(i, this.items[i]);
      }
    }
  }
}
```

### TREE

- A tree is a hierarchical data structure that consists of nodes connected by edges. Each tree has a root node that serves as the starting point for the tree, and from the root, branches of nodes extend outward. Trees are commonly used in computer science and data structures to represent hierarchical structures and relationships, such as directory structures, family trees, and the structure of web pages.
- A leaf node is a node with no children
  - Binary Tree:
  - A binary tree is a tree that have maximum of 2 children per node.
  - There could be less than 2 children per node but not more than that.
  - Only one root node
  - Has only one path from root to any node
  - The Depth First Search algorithm starts at the root node and explores as far as possible along each branch before backtracking.
  - Breadth-first search (BFS) is an algorithm for searching a tree data structure for a node that satisfies a given property. It starts at the tree root and explores all nodes at the present depth prior to moving on to the nodes at the next depth level. Extra memory, usually a queue, is needed to keep track of the child nodes that were encountered but not yet explored.

#### IMPLEMENTATION

```typescript
class TreeNode {
  public value: string;
  public left: TreeNode = null;
  public right: TreeNode = null;

  constructor(value: string) {
    this.value = value;
  }

  setLeft(node: TreeNode) {
    this.left = node;
  }

  setRight(node: TreeNode) {
    this.right = node;
  }
}

const nodeA = new TreeNode("A");
const nodeB = new TreeNode("B");
const nodeC = new TreeNode("C");
const nodeD = new TreeNode("D");
const nodeE = new TreeNode("E");
const nodeF = new TreeNode("F");

nodeA.setLeft(nodeB);
nodeA.setRight(nodeC);
nodeB.setLeft(nodeD);
nodeB.setRight(nodeE);
nodeC.setRight(nodeF);

//  VISUALIZED TREE
//       A
//      / \
//     B   C
//    / \   \
//   D   E   F
```
