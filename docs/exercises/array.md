# Array
https://chatgpt.com/share/67097d8e-1d40-8007-a6bb-e7611065a576

## Basic
### Sum of All Elements
```js
const sumArray = (arr) => arr.reduce((acc, el) => acc + el, 0);

assert.strictEqual(sumArray([1, 2, 3, 4]), 10);
assert.strictEqual(sumArray([0, -1, -2, 3]), 0);
assert.strictEqual(sumArray([]), 0);
```
### Find the Maximum Element
```js
function findMax(arr) {
  let max = -Infinity;

  arr.forEach(el=>{
    if(el > max) {
      max = el;
    }
  });

  return max;
}

assert.strictEqual(findMax([1, 2, 3, 4]), 4);
assert.strictEqual(findMax([-1, -5, -3]), -1);
assert.strictEqual(findMax([100, 23, 57, 1]), 100);
```
### Reverse an Array
```js
function reverseArray(arr) {
  const newArray = [];

  arr.forEach(el=>{
    newArray.unshift(el);
  });

  return newArray
}

assert.deepStrictEqual(reverseArray([1, 2, 3, 4]), [4, 3, 2, 1]);
assert.deepStrictEqual(reverseArray([5, 6, 7]), [7, 6, 5]);
assert.deepStrictEqual(reverseArray([]), []);
```
### Remove Duplicates
```js
function removeDuplicates(arr) {
  return new Set(arr).values().toArray();
}

assert.deepStrictEqual(removeDuplicates([1, 2, 2, 3, 3, 4]), [1, 2, 3, 4]);
assert.deepStrictEqual(removeDuplicates([5, 5, 5]), [5]);
assert.deepStrictEqual(removeDuplicates([]), []);
```
### Find an Element's Index
```js
function findIndex(arr, value) {
  for (let index = 0; index < arr.length; index++) {
    if (arr[index] === value) {
      return index;
    }
  }
  return -1;
}

assert.strictEqual(findIndex([1, 2, 3, 4], 3), 2);
assert.strictEqual(findIndex([1, 2, 3, 4], 5), -1);
assert.strictEqual(findIndex([], 1), -1);
```
### Count Occurrences of a Value
```js
function countOccurrences(array, value) {
  const map = new Map();
  for (let index = 0; index < array.length; index++) {
    const element = array[index];
    if (!map.has(element)) {
      map.set(element, 1);
    } else {
      map.set(element, map.get(element) + 1);
    }
  }
  return map.get(value) ?? 0;
}

assert.strictEqual(countOccurrences([1, 2, 2, 3, 2], 2), 3);
assert.strictEqual(countOccurrences([4, 4, 4, 4], 4), 4);
assert.strictEqual(countOccurrences([1, 2, 3], 5), 0);
```
### Filter Even Numbers
```js
function filterEven(arr) {
  const isEven = (el) => el % 2 === 0;
  return arr.filter(isEven);
}

assert.deepStrictEqual(filterEven([1, 2, 3, 4]), [2, 4]);
assert.deepStrictEqual(filterEven([5, 7, 9]), []);
assert.deepStrictEqual(filterEven([10, 12, 15]), [10, 12]);
```


## Intermediate
### Array Insertion
```js
function insertAtPosition(arr, value, index) {
  arr.splice(index, 0, value);
  return arr;
}

assert.deepStrictEqual(insertAtPosition([1, 2, 3], 4, 2), [1, 2, 4, 3]);
assert.deepStrictEqual(insertAtPosition([5, 6], 7, 0), [7, 5, 6]);
assert.deepStrictEqual(insertAtPosition([], 1, 0), [1]);
```
### Merge Two Arrays
```js
function mergeArrays(arr1, arr2) {
  return [...arr1,...arr2]
}

assert.deepStrictEqual(mergeArrays([1, 2], [3, 4]), [1, 2, 3, 4]);
assert.deepStrictEqual(mergeArrays([], [1]), [1]);
assert.deepStrictEqual(mergeArrays([], []), []);
```
### Check if an Array is Sorted
```js
function isSorted(array) {
  for (let index = 0; index < array.length; index++) {
    const element = array[index];
    const next = array[index + 1];

    if (element > next) {
      return false;
    }
  }
  return true;
}

assert.strictEqual(isSorted([1, 2, 3, 4]), true);
assert.strictEqual(isSorted([4, 3, 2, 1]), false);
assert.strictEqual(isSorted([]), true);
```
### Rotate Array to the Left
```js
function rotateLeft(array, positions) {
  return [...array.slice(positions), ...array.slice(0, positions)];
}

assert.deepStrictEqual(rotateLeft([1, 2, 3, 4], 2), [3, 4, 1, 2]);
assert.deepStrictEqual(rotateLeft([1, 2, 3], 1), [2, 3, 1]);
assert.deepStrictEqual(rotateLeft([], 1), []);
```
### Sum of Array Elements Until a Condition
```js
function sumUntil(array) {
  let sum = 0;
  for (let index = 0; index < array.length; index++) {
    const element = array[index];
    if (element < 0) {
      return sum;
    }

    sum += element;
  }
  return sum;
}

assert.strictEqual(sumUntil([1, 2, 3, -1, 4]), 6);
assert.strictEqual(sumUntil([5, 6, 7]), 18);
assert.strictEqual(sumUntil([-1, 1, 2]), 0);
```
### Partition an Array
```js
function partitionArray(array, pivot) {
  const less = [];
  const more = [];

  for (let index = 0; index < array.length; index++) {
    const element = array[index];

    if (element < pivot) {
      less.push(element);
    } else {
      more.push(element);
    }
  }
  return [less, more];
}

assert.deepStrictEqual(partitionArray([1, 4, 3, 2, 5], 3), [
  [1, 2],
  [4, 3, 5],
]);
assert.deepStrictEqual(partitionArray([7, 8, 6], 7), [[6], [7, 8]]);
assert.deepStrictEqual(partitionArray([], 1), [[], []]);
assert.deepStrictEqual(partitionArray([10, 3, 5, 6, 1], 5), [
  [3, 1],
  [10, 5, 6],
]);
assert.deepStrictEqual(partitionArray([9, 8, 7], 10), [[9, 8, 7], []]);
assert.deepStrictEqual(partitionArray([11, 15, 13], 10), [[], [11, 15, 13]]);
assert.deepStrictEqual(partitionArray([5, 5, 5], 5), [[], [5, 5, 5]]);
assert.deepStrictEqual(partitionArray([2, 2, 3, 4, 2], 3), [
  [2, 2, 2],
  [3, 4],
]);
```
### Find the Intersection of Two Arrays
```js
function findIntersection(array1, array2) {
  const intersection = new Set();
  const common = new Set();
  for (let index = 0; index < array1.length; index++) {
    const element = array1[index];
    common.add(element);
  }

  for (let index = 0; index < array2.length; index++) {
    const element = array2[index];
    const found = common.has(element);
    if (found) {
      intersection.add(element);
    }
  }

  return intersection.values().toArray();
}

assert.deepStrictEqual(findIntersection([1, 2, 3], [2, 3, 4]), [2, 3]);
assert.deepStrictEqual(findIntersection([1, 1, 2], [2, 2, 3]), [2]);
assert.deepStrictEqual(findIntersection([5, 6], [1, 2]), []);
assert.deepStrictEqual(findIntersection([1, 2, 3], []), []);
assert.deepStrictEqual(findIntersection([], [1, 2, 3]), []);
assert.deepStrictEqual(findIntersection([1, 2, 3], [1, 2, 3]), [1, 2, 3]);
assert.deepStrictEqual(findIntersection([7, 8, 9], [10, 11, 12]), []);
assert.deepStrictEqual(findIntersection([1, 2, 2, 3], [2, 3, 3]), [2, 3]);
assert.deepStrictEqual(findIntersection([1, 2, 2, 3], [2, 3, 4, 2]), [2, 3]);
assert.deepStrictEqual(findIntersection([-1, 0, 1, 2], [0, 2, 3]), [0, 2]);
assert.deepStrictEqual(findIntersection([10, 20, 30], [30, 40, 50]), [30]);
assert.deepStrictEqual(findIntersection([5, 5, 5], [5, 5, 5]), [5]);
assert.deepStrictEqual(findIntersection([1, 2, 3, 4, 5, 6], [2, 4]), [2, 4]);
```
### Find the Union of Two Arrays
```js
function findUnion(arr1, arr2) {
  const union = new Set();
  for (const element of arr1) {
    union.add(element);
  }
  for (const element of arr2) {
    union.add(element);
  }
  return union.values().toArray();
}

assert.deepStrictEqual(findUnion([1, 2, 3], [2, 3, 4]), [1, 2, 3, 4]);
assert.deepStrictEqual(findUnion([1, 1, 2], [2, 2, 3]), [1, 2, 3]);
assert.deepStrictEqual(findUnion([], [1, 2]), [1, 2]);
assert.deepStrictEqual(findUnion([], []), []);
assert.deepStrictEqual(findUnion([1, 2], [1, 2, 3, 4]), [1, 2, 3, 4]);
assert.deepStrictEqual(findUnion([5, 6], [7, 8]), [5, 6, 7, 8]);
assert.deepStrictEqual(findUnion([1, 1, 1], [1, 1]), [1]);
assert.deepStrictEqual(findUnion([1, "2", 3], [2, "2", 4]), [1, "2", 3, 2, 4]);
assert.deepStrictEqual(findUnion([-1, 0, 1], [0, 1, 2]), [-1, 0, 1, 2]);
assert.deepStrictEqual(findUnion([4, 3, 2], [2, 3, 4, 5]), [4, 3, 2, 5]);
const largeArray1 = Array.from({ length: 1000 }, (_, i) => i);
const largeArray2 = Array.from({ length: 1000 }, (_, i) => i + 500);
assert.deepStrictEqual(
  findUnion(largeArray1, largeArray2),
  Array.from(new Set([...largeArray1, ...largeArray2]))
);
assert.deepStrictEqual(findUnion([1], [1]), [1]);
assert.deepStrictEqual(findUnion([1], [2]), [1, 2]);
```
### Chunk an Array
```js
function chunkArray(array, size) {
  const end = [];
  for (let index = 0; index < array.length; index += size) {
    const tempArray = [];
    for (let inner = index; inner < index + size; inner++) {
      const innerElement = array[inner];
      if (innerElement) {
        tempArray.push(innerElement);
      }
    }
    end.push(tempArray);
  }

  return end;
}

assert.deepStrictEqual(chunkArray([1, 2, 3, 4], 2), [
  [1, 2],
  [3, 4],
]);
assert.deepStrictEqual(chunkArray([1, 2, 3, 4, 5], 2), [[1, 2], [3, 4], [5]]);
assert.deepStrictEqual(chunkArray([1, 2], 3), [[1, 2]]);
assert.deepStrictEqual(chunkArray([1, 2, 3, 4], 1), [[1], [2], [3], [4]]);
assert.deepStrictEqual(chunkArray([1, 2, 3], 5), [[1, 2, 3]]);
assert.deepStrictEqual(chunkArray([], 3), []);
assert.deepStrictEqual(chunkArray([1], 2), [[1]]);
```
### Move All Zeroes to the End
```js
function moveZeroes(array) {
  let zeroCounter = 0;
  const arr = [];
  for (let index = 0; index < array.length; index++) {
    const element = array[index];
    if (element !== 0) {
      arr.push(element);
    } else {
      zeroCounter += 1;
    }
  }

  for (let i = 0; i < zeroCounter; i++) {
    arr.push(0);
  }

  return arr;
}

assert.deepStrictEqual(moveZeroes([0, 1, 0, 3, 12]), [1, 3, 12, 0, 0]);
assert.deepStrictEqual(moveZeroes([0, 0, 1]), [1, 0, 0]);
assert.deepStrictEqual(moveZeroes([1, 2, 3]), [1, 2, 3]);
```
### Find Missing Number


## Advanced
### Flatten a Multidimensional Array
### Find All Pairs that Sum to a Target
### Find the Longest Increasing Subsequence
### Three Sum
### Subarray Sum Equals K
### Longest Consecutive Sequence
### Product of Array Except Self
### Find the Majority Element 
Problem: Write a function findMajorityElement that finds the element that appears more than half the time in an array.