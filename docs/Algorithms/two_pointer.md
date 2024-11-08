# Two-Pointer

The **two-pointer technique** is an efficient algorithmic strategy typically used to solve problems involving arrays or linked lists. In this approach, two pointers are used to traverse the data structure, often moving towards each other from opposite ends (or in the same direction with varying speeds). This helps in reducing the time complexity of a solution, particularly when compared to brute-force solutions.

Two pointers are useful when:

1. You need to check pairs or triplets of elements in an array.
2. The array is sorted or can be sorted to make pointer movement logical.
3. The problem involves finding pairs that satisfy a certain condition (e.g., summing to a target value).

## Example Scenario:

If you are given a sorted array, the two-pointer technique can help in finding two numbers whose sum matches a target. One pointer starts from the beginning (left) and the other from the end (right). Depending on whether their sum is too low or too high, you move one pointer.

## Exercises:

### Find the Sum of Two Elements

- **Problem**: Given a sorted array, find two numbers that add up to a target sum. Return their indices.
- **Example**:

  ```javascript
  function twoSum(nums, target) {
    let left = 0;
    let right = nums.length - 1;

    while (left < right) {
      const sum = nums[left] + nums[right];

      if (sum === target) {
        return [left, right]; // Return the indices
      }

      if (sum < target) {
        left++; // Move left pointer to increase the sum
      } else {
        right--; // Move right pointer to decrease the sum
      }
    }

    return []; // Return an empty array if no solution is found
  }
  console.log(twoSum([1, 2, 3, 4, 6], 6)); // [1, 3]
  console.log(twoSum([2, 3, 4], 6)); // [0, 2]
  ```

### [todo] Remove Duplicates from a Sorted Array

- **Problem**: Given a sorted array, remove the duplicates in-place so that each element appears only once and return the new length.
- **Example**:

```javascript
function removeDuplicates(nums) {
  // Implement two-pointer solution here
}

console.log(removeDuplicates([1, 1, 2])); // 2, because the array becomes [1, 2]
console.log(removeDuplicates([0, 0, 1, 1, 1, 2, 2, 3, 3, 4])); // 5, because the array becomes [0, 1, 2, 3, 4]
```

- **Hint**: Use two pointers where one pointer tracks unique elements, and the other moves through the array.

### [todo] Reverse a String

- **Problem**: Write a function to reverse a string using the two-pointer technique.
- **Example**:

  ```javascript
  function reverseString(s) {
    // Implement two-pointer solution here
  }

  console.log(reverseString(["h", "e", "l", "l", "o"])); // ['o', 'l', 'l', 'e', 'h']
  ```

- **Hint**: Start with two pointers at the ends of the array and swap the elements until they meet in the middle.

### [todo] Container with Most Water

- **Problem**: Given an array where each element represents the height of a line on the x-axis, find two lines such that they together with the x-axis form a container that can hold the most water.
- **Example**:

  ```javascript
  function maxArea(height) {
    // Implement two-pointer solution here
  }

  console.log(maxArea([1, 8, 6, 2, 5, 4, 8, 3, 7])); // 49
  ```

- **Hint**: Use two pointers, one at the beginning and one at the end. Move the pointer pointing to the smaller height, as this is the limiting factor in the area calculation.

### [todo] 3Sum (Advanced)

- **Problem**: Given an array of integers, return all unique triplets that sum up to zero.
- **Example**:

  ```javascript
  function threeSum(nums) {
    // Implement two-pointer solution here
  }

  console.log(threeSum([-1, 0, 1, 2, -1, -4])); // [[-1, -1, 2], [-1, 0, 1]]
  ```

- **Hint**: After sorting the array, loop through each element and for each element, use the two-pointer technique to find pairs that sum to the negative of the current element.

### [todo] Palindrome

### [todo] Partitioning Around a Pivot

### [todo] Sorting Colors (Dutch National Flag Problem)

### [todo] Smallest Subarray with a Given Sum
