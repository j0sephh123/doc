```js
const assert = require('assert');

// Assume DoublyLinkedList is your implementation
const list = new DoublyLinkedList();

// Test isEmpty on empty list
assert.strictEqual(list.isEmpty(), true, 'List should be empty initially');

// Test length on empty list
assert.strictEqual(list.length(), 0, 'Length should be 0 initially');

// Test insertAtHead
list.insertAtHead(10);
assert.strictEqual(list.isEmpty(), false, 'List should not be empty after insertion at head');
assert.strictEqual(list.length(), 1, 'Length should be 1 after one insertion at head');
assert.strictEqual(list.head.data, 10, 'Head data should be 10');
assert.strictEqual(list.tail.data, 10, 'Tail data should be 10');

// Test insertAtTail
list.insertAtTail(20);
assert.strictEqual(list.length(), 2, 'Length should be 2 after insertion at tail');
assert.strictEqual(list.tail.data, 20, 'Tail data should be 20');
assert.strictEqual(list.tail.prev.data, 10, 'Tail prev should be 10');

// Test insertAtPosition
list.insertAtPosition(15, 1);
assert.strictEqual(list.length(), 3, 'Length should be 3 after insertion at position 1');
assert.strictEqual(list.head.next.data, 15, 'Data at position 1 should be 15');
assert.strictEqual(list.head.next.prev.data, 10, 'Prev of node at position 1 should be 10');

// Test toArray
assert.deepStrictEqual(list.toArray(), [10, 15, 20], 'List should be [10, 15, 20]');

// Test search
assert.strictEqual(list.search(15), true, '15 should be found in the list');
assert.strictEqual(list.search(99), false, '99 should not be found in the list');

// Test delete
list.delete(15);
assert.strictEqual(list.length(), 2, 'Length should be 2 after deletion');
assert.deepStrictEqual(list.toArray(), [10, 20], 'List should be [10, 20] after deletion');
assert.strictEqual(list.tail.prev.data, 10, 'Tail prev should be 10 after deletion');

// Test reverse
list.reverse();
assert.deepStrictEqual(list.toArray(), [20, 10], 'List should be reversed to [20, 10]');
assert.strictEqual(list.head.next.prev.data, 20, 'Prev of head.next should be head after reverse');

// Test clear
list.clear();
assert.strictEqual(list.isEmpty(), true, 'List should be empty after clear');
assert.strictEqual(list.length(), 0, 'Length should be 0 after clear');
```