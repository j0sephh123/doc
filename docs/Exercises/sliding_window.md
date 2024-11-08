```js
function maxSubarraySum(arr, k) {
  if (arr.length < k) return null;

  // Initialize window sum with the first `k` elements
  let windowSum = 0;
  for (let i = 0; i < k; i++) {
    windowSum += arr[i];
  }

  // Start with the initial window sum as the max sum
  let maxSum = windowSum;

  // Slide the window across the array
  for (let i = k; i < arr.length; i++) {
    // Slide the window: subtract the element going out and add the element coming in
    windowSum = windowSum - arr[i - k] + arr[i];
    maxSum = Math.max(maxSum, windowSum);
  }

  return maxSum;
}
```
