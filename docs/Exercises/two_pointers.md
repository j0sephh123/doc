### Numbers that sum to a target

```js
function twoSum(numbers, target) {
  let left = 0;
  let right = numbers.length - 1;

  while (left < right) {
    const leftNumber = numbers[left];
    const rightNumber = numbers[right];
    const sum = leftNumber + rightNumber;

    if (sum === target) {
      return [
        { index: left, number: leftNumber },
        { index: right, number: rightNumber },
      ];
    }

    if (sum < target) {
      left++;
    } else {
      right--;
    }
  }
  return null;
}

console.log(twoSum([2, 3, 4, 5, 6, 7, 8, 9, 10], 5));
// [ { index: 0, number: 2 }, { index: 1, number: 3 } ]
```

### Palindrome

```js
function isPalindrome(s) {
  let left = 0;
  let right = s.length - 1;

  while (left < right) {
    if (s[left] !== s[right]) return false;
    left++;
    right--;
  }
  return true;
}
```
