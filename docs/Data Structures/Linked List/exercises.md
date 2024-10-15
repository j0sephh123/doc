## **Basic Exercises**

### **Exercise 1: Find Nth Node from End**

**Linked List Type:** Singly Linked List

**Problem:**

Implement a method `findNthFromEnd(n)` that returns the data of the nth node from the end of the singly linked list.

**Assertions:**

```javascript
const assert = require("assert");

// Assume SinglyLinkedList is your implementation
const list = new SinglyLinkedList();

// Populate the list
list.insertAtTail(10);
list.insertAtTail(20);
list.insertAtTail(30);
list.insertAtTail(40);
list.insertAtTail(50);

// Test findNthFromEnd
assert.strictEqual(
  list.findNthFromEnd(1),
  50,
  "1st node from end should be 50"
);
assert.strictEqual(
  list.findNthFromEnd(3),
  30,
  "3rd node from end should be 30"
);
assert.strictEqual(
  list.findNthFromEnd(5),
  10,
  "5th node from end should be 10"
);

// Edge cases
assert.throws(() => list.findNthFromEnd(0), "Should throw error for n = 0");
assert.throws(
  () => list.findNthFromEnd(6),
  "Should throw error for n greater than list length"
);
```

---

### **Exercise 2: Remove Duplicates**

**Linked List Type:** Singly Linked List

**Problem:**

Implement a method `removeDuplicates()` that removes duplicate elements from an unsorted singly linked list.

**Assertions:**

```javascript
const assert = require("assert");

// Assume SinglyLinkedList is your implementation
const list = new SinglyLinkedList();

// Populate the list with duplicates
list.insertAtTail(10);
list.insertAtTail(20);
list.insertAtTail(10);
list.insertAtTail(30);
list.insertAtTail(20);
list.insertAtTail(40);

// Remove duplicates
list.removeDuplicates();

// Test the list content
assert.deepStrictEqual(
  list.toArray(),
  [10, 20, 30, 40],
  "List should be [10, 20, 30, 40] after removing duplicates"
);
```

---

### **Exercise 3: Insert After Given Node**

**Linked List Type:** Doubly Linked List

**Problem:**

Implement a method `insertAfter(nodeData, newData)` that inserts `newData` after the first occurrence of `nodeData` in a doubly linked list.

**Assertions:**

```javascript
const assert = require("assert");

// Assume DoublyLinkedList is your implementation
const list = new DoublyLinkedList();

// Populate the list
list.insertAtTail(10);
list.insertAtTail(20);
list.insertAtTail(30);

// Insert after
list.insertAfter(20, 25);

// Test the list content
assert.deepStrictEqual(
  list.toArray(),
  [10, 20, 25, 30],
  "List should be [10, 20, 25, 30] after insertion"
);

// Edge case: nodeData not found
assert.throws(
  () => list.insertAfter(99, 40),
  "Should throw error when nodeData not found"
);
```

---

### **Exercise 4: Count Nodes in Circular Linked List**

**Linked List Type:** Circular Linked List

**Problem:**

Implement a method `countNodes()` that returns the number of nodes in a circular linked list.

**Assertions:**

```javascript
const assert = require("assert");

// Assume CircularLinkedList is your implementation
const list = new CircularLinkedList();

// Populate the list
list.insertAtTail(10);
list.insertAtTail(20);
list.insertAtTail(30);

// Test countNodes
assert.strictEqual(list.countNodes(), 3, "List should have 3 nodes");

// Empty list
const emptyList = new CircularLinkedList();
assert.strictEqual(emptyList.countNodes(), 0, "Empty list should have 0 nodes");
```

---

### **Exercise 5: Swap Nodes**

**Linked List Type:** Singly Linked List

**Problem:**

Implement a method `swapNodes(data1, data2)` that swaps the nodes containing `data1` and `data2` in a singly linked list.

**Assertions:**

```javascript
const assert = require("assert");

// Assume SinglyLinkedList is your implementation
const list = new SinglyLinkedList();

// Populate the list
list.insertAtTail(10);
list.insertAtTail(20);
list.insertAtTail(30);
list.insertAtTail(40);

// Swap nodes
list.swapNodes(20, 40);

// Test the list content
assert.deepStrictEqual(
  list.toArray(),
  [10, 40, 30, 20],
  "List should be [10, 40, 30, 20] after swapping"
);

// Edge case: One or both nodes not found
assert.throws(
  () => list.swapNodes(50, 60),
  "Should throw error when nodes not found"
);
```

---

## **Intermediate Exercises**

### **Exercise 6: Detect Loop**

**Linked List Type:** Singly Linked List

**Problem:**

Implement a method `hasLoop()` that detects if there is a cycle (loop) in a singly linked list.

**Assertions:**

```javascript
const assert = require("assert");

// Assume SinglyLinkedList is your implementation
const list = new SinglyLinkedList();

// Populate the list
list.insertAtTail(10);
list.insertAtTail(20);
list.insertAtTail(30);

// Create a loop for testing
list.tail.next = list.head.next; // Loop from node with data 30 to node with data 20

// Test hasLoop
assert.strictEqual(list.hasLoop(), true, "List should have a loop");

// Create a non-looped list
const nonLoopedList = new SinglyLinkedList();
nonLoopedList.insertAtTail(1);
nonLoopedList.insertAtTail(2);
nonLoopedList.insertAtTail(3);

// Test hasLoop
assert.strictEqual(
  nonLoopedList.hasLoop(),
  false,
  "List should not have a loop"
);
```

---

### **Exercise 7: Split Circular Linked List**

**Linked List Type:** Circular Linked List

**Problem:**

Implement a method `splitList()` that splits a circular linked list into two halves. If the total number of nodes is odd, the extra node should go in the first list.

**Assertions:**

```javascript
const assert = require("assert");

// Assume CircularLinkedList is your implementation
const list = new CircularLinkedList();

// Populate the list
list.insertAtTail(10);
list.insertAtTail(20);
list.insertAtTail(30);
list.insertAtTail(40);
list.insertAtTail(50);

// Split the list
const [firstHalf, secondHalf] = list.splitList();

// Test the two halves
assert.deepStrictEqual(
  firstHalf.toArray(),
  [10, 20, 30],
  "First half should be [10, 20, 30]"
);
assert.deepStrictEqual(
  secondHalf.toArray(),
  [40, 50],
  "Second half should be [40, 50]"
);
```

---

### **Exercise 8: Reverse in Groups**

**Linked List Type:** Doubly Linked List

**Problem:**

Implement a method `reverseInGroups(k)` that reverses the doubly linked list in groups of size `k`.

**Assertions:**

```javascript
const assert = require("assert");

// Assume DoublyLinkedList is your implementation
const list = new DoublyLinkedList();

// Populate the list
list.insertAtTail(1);
list.insertAtTail(2);
list.insertAtTail(3);
list.insertAtTail(4);
list.insertAtTail(5);
list.insertAtTail(6);
list.insertAtTail(7);
list.insertAtTail(8);

// Reverse in groups
list.reverseInGroups(3);

// Test the list content
assert.deepStrictEqual(
  list.toArray(),
  [3, 2, 1, 6, 5, 4, 7, 8],
  "List should be [3,2,1,6,5,4,7,8] after reversing in groups of 3"
);
```

---

### **Exercise 9: Delete Nodes with Greater Value on Right**

**Linked List Type:** Singly Linked List

**Problem:**

Implement a method `deleteNodesWithGreaterValueOnRight()` that deletes all nodes which have a greater value node on the right side.

**Assertions:**

```javascript
const assert = require("assert");

// Assume SinglyLinkedList is your implementation
const list = new SinglyLinkedList();

// Populate the list
list.insertAtTail(12);
list.insertAtTail(15);
list.insertAtTail(10);
list.insertAtTail(11);
list.insertAtTail(5);
list.insertAtTail(6);
list.insertAtTail(2);
list.insertAtTail(3);

// Delete nodes
list.deleteNodesWithGreaterValueOnRight();

// Test the list content
assert.deepStrictEqual(
  list.toArray(),
  [15, 11, 6, 3],
  "List should be [15, 11, 6, 3] after deletion"
);
```

---

### **Exercise 10: Pairwise Swap Elements**

**Linked List Type:** Singly Linked List

**Problem:**

Implement a method `pairwiseSwap()` that swaps elements pairwise. For example, `[1,2,3,4]` becomes `[2,1,4,3]`.

**Assertions:**

```javascript
const assert = require("assert");

// Assume SinglyLinkedList is your implementation
const list = new SinglyLinkedList();

// Populate the list
list.insertAtTail(1);
list.insertAtTail(2);
list.insertAtTail(3);
list.insertAtTail(4);
list.insertAtTail(5);

// Perform pairwise swap
list.pairwiseSwap();

// Test the list content
assert.deepStrictEqual(
  list.toArray(),
  [2, 1, 4, 3, 5],
  "List should be [2, 1, 4, 3, 5] after pairwise swap"
);
```

---

## **Advanced Exercises**

### **Exercise 11: Merge Two Sorted Lists**

**Linked List Type:** Singly Linked List

**Problem:**

Implement a method `mergeSorted(otherList)` that merges another sorted singly linked list `otherList` into the current sorted singly linked list to produce a new sorted list.

**Assertions:**

```javascript
const assert = require("assert");

// Assume SinglyLinkedList is your implementation

// First sorted list
const list1 = new SinglyLinkedList();
list1.insertAtTail(1);
list1.insertAtTail(3);
list1.insertAtTail(5);

// Second sorted list
const list2 = new SinglyLinkedList();
list2.insertAtTail(2);
list2.insertAtTail(4);
list2.insertAtTail(6);

// Merge lists
const mergedList = list1.mergeSorted(list2);

// Test the merged list
assert.deepStrictEqual(
  mergedList.toArray(),
  [1, 2, 3, 4, 5, 6],
  "Merged list should be [1,2,3,4,5,6]"
);
```

---

### **Exercise 12: Sort Doubly Linked List**

**Linked List Type:** Doubly Linked List

**Problem:**

Implement a method `sort()` that sorts a doubly linked list using insertion sort.

**Assertions:**

```javascript
const assert = require("assert");

// Assume DoublyLinkedList is your implementation
const list = new DoublyLinkedList();

// Populate the list
list.insertAtTail(9);
list.insertAtTail(3);
list.insertAtTail(5);
list.insertAtTail(2);
list.insertAtTail(8);

// Sort the list
list.sort();

// Test the sorted list
assert.deepStrictEqual(
  list.toArray(),
  [2, 3, 5, 8, 9],
  "List should be sorted to [2,3,5,8,9]"
);
```

---

### **Exercise 13: Check Palindrome**

**Linked List Type:** Doubly Circular Linked List

**Problem:**

Implement a method `isPalindrome()` that checks whether a doubly circular linked list is a palindrome.

**Assertions:**

```javascript
const assert = require("assert");

// Assume DoublyCircularLinkedList is your implementation

// Palindrome list
const palindromeList = new DoublyCircularLinkedList();
palindromeList.insertAtTail("r");
palindromeList.insertAtTail("a");
palindromeList.insertAtTail("d");
palindromeList.insertAtTail("a");
palindromeList.insertAtTail("r");

// Check palindrome
assert.strictEqual(
  palindromeList.isPalindrome(),
  true,
  "List should be a palindrome"
);

// Non-palindrome list
const nonPalindromeList = new DoublyCircularLinkedList();
nonPalindromeList.insertAtTail("n");
nonPalindromeList.insertAtTail("o");
nonPalindromeList.insertAtTail("t");

// Check palindrome
assert.strictEqual(
  nonPalindromeList.isPalindrome(),
  false,
  "List should not be a palindrome"
);
```

---

### **Exercise 14: Flatten Multilevel Linked List**

**Linked List Type:** Singly Linked List with Child Pointers

**Problem:**

Extend the singly linked list to include a `child` pointer for each node, which may point to a separate linked list. Implement a method `flatten()` that flattens the multilevel linked list into a single-level singly linked list.

**Note:** This requires modifying your singly linked list to support a `child` pointer.

**Assertions:**

```javascript
const assert = require("assert");

// Assume SinglyLinkedListNode is your node implementation with 'data', 'next', and 'child' pointers

// Create nodes
const node1 = new SinglyLinkedListNode(1);
const node2 = new SinglyLinkedListNode(2);
const node3 = new SinglyLinkedListNode(3);
const node4 = new SinglyLinkedListNode(4);
const node5 = new SinglyLinkedListNode(5);
const node6 = new SinglyLinkedListNode(6);
const node7 = new SinglyLinkedListNode(7);

// Connect main list
node1.next = node2;
node2.next = node3;
node3.next = node4;

// Create child lists
node2.child = node5;
node5.next = node6;
node6.child = node7;

// Flatten the list
const list = new SinglyLinkedList();
list.head = node1;
list.flatten();

// Test the flattened list
assert.deepStrictEqual(
  list.toArray(),
  [1, 2, 5, 6, 7, 3, 4],
  "Flattened list should be [1,2,5,6,7,3,4]"
);
```

---

### **Exercise 15: Clone a Linked List with Random Pointers**

**Linked List Type:** Singly Linked List with Random Pointers

**Problem:**

Each node in the singly linked list has an additional `random` pointer that can point to any node in the list. Implement a method `clone()` that creates a deep copy of the list.

**Note:** This requires modifying your singly linked list to support a `random` pointer.

**Assertions:**

```javascript
const assert = require("assert");

// Assume SinglyLinkedListNode is your node implementation with 'data', 'next', and 'random' pointers

// Create nodes
const nodeA = new SinglyLinkedListNode("A");
const nodeB = new SinglyLinkedListNode("B");
const nodeC = new SinglyLinkedListNode("C");

// Connect nodes
nodeA.next = nodeB;
nodeB.next = nodeC;

// Set random pointers
nodeA.random = nodeC;
nodeB.random = nodeA;
nodeC.random = nodeB;

// Original list
const originalList = new SinglyLinkedList();
originalList.head = nodeA;

// Clone the list
const clonedList = originalList.clone();

// Test the cloned list
assert.notStrictEqual(
  clonedList.head,
  originalList.head,
  "Cloned list should have different nodes"
);
assert.strictEqual(clonedList.head.data, "A", "Head data should be A");
assert.strictEqual(
  clonedList.head.random.data,
  "C",
  "Head random should point to node with data C"
);
assert.strictEqual(
  clonedList.head.next.random.data,
  "A",
  "Second node random should point to node with data A"
);
```

---

**Note for All Exercises:**

- Replace `SinglyLinkedList`, `DoublyLinkedList`, `CircularLinkedList`, and `DoublyCircularLinkedList` with your own class implementations.
- Ensure that your linked list classes support the methods required for each exercise.
- The `toArray` method should return an array representation of your list, which is helpful for testing.
- Handle edge cases such as empty lists, single-node lists, and invalid input within your implementations.
- For exercises involving extensions (Exercises 14 and 15), you may need to modify your node class to include additional pointers like `child` or `random`.
