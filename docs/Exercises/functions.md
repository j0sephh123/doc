# Functions

## Basic

### Sum Two Numbers

```js
function sum(a, b) {
  // Your code here
}

assert.strictEqual(sum(2, 3), 5);
assert.strictEqual(sum(-1, 1), 0);
assert.strictEqual(sum(0, 0), 0);
assert.strictEqual(sum(10, 20), 30);
assert.strictEqual(sum(-5, -5), -10);
```

### Multiply All Numbers in an Array

```js
function multiplyArray(arr) {
  // Your code here
}

assert.strictEqual(multiplyArray([1, 2, 3, 4]), 24);
assert.strictEqual(multiplyArray([2, 5]), 10);
assert.strictEqual(multiplyArray([]), 1);
assert.strictEqual(multiplyArray([10]), 10);
assert.strictEqual(multiplyArray([-1, 1, -1]), 1);
```

### Check if a Number is Prime

```js
function isPrime(n) {
  // Your code here
}

assert.strictEqual(isPrime(2), true);
assert.strictEqual(isPrime(4), false);
assert.strictEqual(isPrime(17), true);
assert.strictEqual(isPrime(1), false);
assert.strictEqual(isPrime(0), false);
```

### Generate Fibonacci Sequence up to n

```js
function fibonacci(n) {
  // Your code here
}

assert.deepStrictEqual(fibonacci(5), [0, 1, 1, 2, 3]);
assert.deepStrictEqual(fibonacci(1), [0]);
assert.deepStrictEqual(fibonacci(0), []);
assert.deepStrictEqual(fibonacci(8), [0, 1, 1, 2, 3, 5, 8, 13]);
assert.deepStrictEqual(fibonacci(3), [0, 1, 1]);
```

### Factorial of a Number (Recursion)

```js
function factorial(n) {
  // Your code here
}

assert.strictEqual(factorial(5), 120);
assert.strictEqual(factorial(0), 1);
assert.strictEqual(factorial(1), 1);
assert.strictEqual(factorial(3), 6);
assert.strictEqual(factorial(7), 5040);
```

## Intermediate

### Reverse a String

```js
function reverseString(str) {
  // Your code here
}

assert.strictEqual(reverseString('hello'), 'olleh');
assert.strictEqual(reverseString(''), '');
assert.strictEqual(reverseString('JavaScript'), 'tpircSavaJ');
assert.strictEqual(reverseString('racecar'), 'racecar');
assert.strictEqual(reverseString('12345'), '54321');
```

### Check if a String is a Palindrome

```js
function isPalindrome(str) {
  // Your code here
}

assert.strictEqual(isPalindrome('racecar'), true);
assert.strictEqual(isPalindrome('hello'), false);
assert.strictEqual(isPalindrome('A man a plan a canal Panama'), true);
assert.strictEqual(isPalindrome(''), true);
assert.strictEqual(isPalindrome('12321'), true);
```

### Count Vowels in a String

```js
function countVowels(str) {
  // Your code here
}

assert.strictEqual(countVowels('hello'), 2);
assert.strictEqual(countVowels('xyz'), 0);
assert.strictEqual(countVowels('AEIOUaeiou'), 10);
assert.strictEqual(countVowels(''), 0);
assert.strictEqual(countVowels('bcdfghjklmnpqrstvwxyz'), 0);
```

### Capitalize the First Letter of Each Word

```js
function capitalizeWords(str) {
  // Your code here
}

assert.strictEqual(capitalizeWords('hello world'), 'Hello World');
assert.strictEqual(capitalizeWords('javaScript is fun'), 'JavaScript Is Fun');
assert.strictEqual(capitalizeWords(''), '');
assert.strictEqual(capitalizeWords('a b c'), 'A B C');
assert.strictEqual(capitalizeWords('multiple   spaces'), 'Multiple   Spaces');
```

### Remove Duplicate Elements from an Array

```js
function removeDuplicates(arr) {
  // Your code here
}

assert.deepStrictEqual(removeDuplicates([1, 2, 2, 3, 3, 4]), [1, 2, 3, 4]);
assert.deepStrictEqual(removeDuplicates([]), []);
assert.deepStrictEqual(removeDuplicates([5, 5, 5, 5]), [5]);
assert.deepStrictEqual(removeDuplicates([1, 2, 3, 4]), [1, 2, 3, 4]);
assert.deepStrictEqual(removeDuplicates(['a', 'b', 'a', 'c', 'b']), ['a', 'b', 'c']);
```

## Advanced

### Implement a Function that Returns a Function (Closure)

```js
function createAdder(x) {
  // Your code here
}

const add5 = createAdder(5);
const add10 = createAdder(10);

assert.strictEqual(add5(2), 7);
assert.strictEqual(add5(-5), 0);
assert.strictEqual(add10(5), 15);
assert.strictEqual(add10(0), 10);
assert.strictEqual(createAdder(0)(0), 0);
```

### Memoization Function

```js
function memoize(fn) {
  // Your code here
}

let callCount = 0;
function slowDouble(n) {
  callCount++;
  return n * 2;
}

const fastDouble = memoize(slowDouble);

assert.strictEqual(fastDouble(5), 10);
assert.strictEqual(fastDouble(5), 10);
assert.strictEqual(callCount, 1);
assert.strictEqual(fastDouble(10), 20);
assert.strictEqual(callCount, 2);
```

### Function that Counts Number of Times It Has Been Called

```js
function createCounter() {
  // Your code here
}

const counter1 = createCounter();
const counter2 = createCounter();

assert.strictEqual(counter1(), 1);
assert.strictEqual(counter1(), 2);
assert.strictEqual(counter1(), 3);
assert.strictEqual(counter2(), 1);
assert.strictEqual(counter2(), 2);
```

### Curry a Function

```js
function curry(fn) {
  // Your code here
}

function add(a, b, c) {
  return a + b + c;
}

const curriedAdd = curry(add);

assert.strictEqual(curriedAdd(1)(2)(3), 6);
assert.strictEqual(curriedAdd(1, 2)(3), 6);
assert.strictEqual(curriedAdd(1)(2, 3), 6);
assert.strictEqual(curriedAdd(1, 2, 3), 6);
assert.strictEqual(curriedAdd()(1)(2)(3), 6);
```

### Implement a Debounce Function

```js
function debounce(fn, delay) {
  // Your code here
}

let count = 0;
function increment() {
  count++;
}

const debouncedIncrement = debounce(increment, 100);

debouncedIncrement();
debouncedIncrement();
debouncedIncrement();

setTimeout(() => {
  assert.strictEqual(count, 1);
}, 150);

setTimeout(() => {
  debouncedIncrement();
  setTimeout(() => {
    assert.strictEqual(count, 2);
  }, 150);
}, 200);
```

### Implement a Function that Composes Two Functions

```js
function compose(f, g) {
  // Your code here
}

function double(n) {
  return n * 2;
}

function square(n) {
  return n * n;
}

const doubleThenSquare = compose(square, double);
const squareThenDouble = compose(double, square);

assert.strictEqual(doubleThenSquare(5), 100);
assert.strictEqual(squareThenDouble(5), 50);
assert.strictEqual(doubleThenSquare(2), 16);
assert.strictEqual(squareThenDouble(2), 8);
assert.strictEqual(doubleThenSquare(0), 0);
```

### Partial Application Function

```js
function partial(fn, ...fixedArgs) {
  // Your code here
}

function multiply(a, b, c) {
  return a * b * c;
}

const multiplyByTwo = partial(multiply, 2);

assert.strictEqual(multiplyByTwo(3, 4), 24);
assert.strictEqual(multiplyByTwo(5, 5), 50);
assert.strictEqual(multiplyByTwo(1, 1), 2);
assert.strictEqual(multiplyByTwo(0, 10), 0);
assert.strictEqual(multiplyByTwo(-1, 3), -6);
```

### Implement a Function that Flattens Nested Arrays

```js
function flattenArray(arr) {
  // Your code here
}

assert.deepStrictEqual(flattenArray([1, [2, [3, [4]], 5]]), [1, 2, 3, 4, 5]);
assert.deepStrictEqual(flattenArray([1, [2, 3], 4, 5]), [1, 2, 3, 4, 5]);
assert.deepStrictEqual(flattenArray([1, [2, [3, [4, [5]]]]]), [1, 2, 3, 4, 5]);
assert.deepStrictEqual(flattenArray([]), []);
assert.deepStrictEqual(flattenArray([[[[[]]]]]), []);
```

### Implement a Function that Filters Out Falsy Values

```js
function filterFalsy(arr) {
  // Your code here
}

assert.deepStrictEqual(filterFalsy([0, 1, false, 2, '', 3]), [1, 2, 3]);
assert.deepStrictEqual(filterFalsy([null, undefined, NaN, '', false, 0]), []);
assert.deepStrictEqual(filterFalsy(['a', 'b', 'c']), ['a', 'b', 'c']);
assert.deepStrictEqual(filterFalsy([true, false, true]), [true, true]);
assert.deepStrictEqual(filterFalsy([]), []);
```

### Implement a Function that Finds the Intersection of Two Arrays

```js
function intersection(arr1, arr2) {
  // Your code here
}

assert.deepStrictEqual(intersection([1, 2, 3], [2, 3, 4]), [2, 3]);
assert.deepStrictEqual(intersection([5, 6, 7], [7, 8, 9]), [7]);
assert.deepStrictEqual(intersection([1, 1, 2, 2], [2, 2, 3, 3]), [2]);
assert.deepStrictEqual(intersection([], [1, 2, 3]), []);
assert.deepStrictEqual(intersection([1, 2, 3], []), []);
```

### Implement a Function that Validates an Email Address

```js
function isValidEmail(email) {
  // Your code here
}

assert.strictEqual(isValidEmail('test@example.com'), true);
assert.strictEqual(isValidEmail('invalid-email'), false);
assert.strictEqual(isValidEmail('user.name+tag+sorting@example.com'), true);
assert.strictEqual(isValidEmail('user@.com'), false);
assert.strictEqual(isValidEmail('user@site@domain.com'), false);
```

### Implement a Function that Checks if All Elements in an Array Pass a Test

```js
function all(arr, test) {
  // Your code here
}

assert.strictEqual(all([2, 4, 6], n => n % 2 === 0), true);
assert.strictEqual(all([1, 2, 3], n => n < 5), true);
assert.strictEqual(all([1, 2, 3], n => n > 2), false);
assert.strictEqual(all([], n => n > 0), true);
assert.strictEqual(all([true, true, true], x => x === true), true);
```

### Implement a Function that Chains Function Calls

```js
function chainFunctions(funcs) {
  // Your code here
}

function add2(n) {
  return n + 2;
}

function multiply3(n) {
  return n * 3;
}

function subtract1(n) {
  return n - 1;
}

const chainedFunction = chainFunctions([add2, multiply3, subtract1]);

assert.strictEqual(chainedFunction(5), (5 + 2) * 3 - 1);
assert.strictEqual(chainedFunction(0), (0 + 2) * 3 - 1);
assert.strictEqual(chainedFunction(-2), (-2 + 2) * 3 - 1);
assert.strictEqual(chainedFunction(1), (1 + 2) * 3 - 1);
assert.strictEqual(chainedFunction(10), (10 + 2) * 3 - 1);
```
