# String

## Basic

### Reverse a String

```js
const assert = require("node:assert");

function reverseString(str) {
  let newStr = "";
  for (let index = str.length - 1; index >= 0; index--) {
    newStr += str[index];
  }
  return newStr;
}

assert.strictEqual(reverseString("hello"), "olleh");
assert.strictEqual(reverseString(""), "");
assert.strictEqual(reverseString("a"), "a");
assert.strictEqual(reverseString("racecar"), "racecar");
```

### Check if a String is a Palindrome

```js
const assert = require("node:assert");
// not good
function isPalindrome(str) {
  for (let index = 0; index < str.length; index++) {
    const left = str[index];
    const right = str[str.length - 1 - index];

    if (left !== right) return false;
  }
  return true;
}

assert.strictEqual(isPalindrome("racecar"), true);
assert.strictEqual(isPalindrome("hello"), false);
assert.strictEqual(isPalindrome(""), true);
```

### Count Vowels in a String

```js
const assert = require("node:assert");

function countVowels(str) {
  const vowels = ["a", "e", "i", "o", "u"];
  let counter = 0;

  for (let index = 0; index < str.length; index++) {
    const element = str[index].toLowerCase();
    if (vowels.includes(element)) {
      counter += 1;
    }
  }
  return counter;
}

assert.strictEqual(countVowels("hello"), 2);
assert.strictEqual(countVowels("bcdfghjklmnpqrstvwxyz"), 0);
assert.strictEqual(countVowels("AEIOU"), 5);
assert.strictEqual(countVowels(""), 0);
```

## Intermediate

### Count Occurrences of a Character in a String

```js
const assert = require("node:assert");

function countCharacterOccurrences(str, char) {
  let counter = 0;
  for (let index = 0; index < str.length; index++) {
    const element = str[index].toLowerCase();

    if (element === char) {
      counter += 1;
    }
  }
  return counter;
}

assert.strictEqual(countCharacterOccurrences("hello", "l"), 2);
assert.strictEqual(countCharacterOccurrences("hello", "z"), 0);
assert.strictEqual(countCharacterOccurrences("Mississippi", "s"), 4);
assert.strictEqual(countCharacterOccurrences("", "a"), 0);
```

### Remove Duplicate Characters from a String

```js
const assert = require("node:assert");

function removeDuplicateCharacters(str) {
  const set = new Set();

  for (let index = 0; index < str.length; index++) {
    const element = str[index];
    set.add(element);
  }

  return set.keys().toArray().join("");
}

assert.strictEqual(removeDuplicateCharacters("hello"), "helo");
assert.strictEqual(removeDuplicateCharacters("aaaa"), "a");
assert.strictEqual(removeDuplicateCharacters("abcabc"), "abc");
assert.strictEqual(removeDuplicateCharacters(""), "");
```

### Check if Two Strings are Anagrams

```js
const assert = require("node:assert");

function areAnagrams(str1, str2) {
  const sorted1 = str1
    .split("")
    .filter((s) => s !== " ")
    .sort();
  const sorted2 = str2
    .split("")
    .filter((s) => s !== " ")
    .sort();

  if (sorted1.length !== sorted2.length) return false;

  for (let index = 0; index < sorted1.length; index++) {
    const element1 = sorted1[index];
    const element2 = sorted2[index];

    if (element1 !== element2) return false;
  }

  return true;
}

assert.strictEqual(areAnagrams("listen", "silent"), true);
assert.strictEqual(areAnagrams("hello", "world"), false);
assert.strictEqual(areAnagrams("Dormitory", "Dirty room"), true);
assert.strictEqual(areAnagrams("abc", "def"), false);
assert.strictEqual(areAnagrams("The eyes", "They see"), true);
assert.strictEqual(areAnagrams("abcd", "abcde"), false);
```

### [todo] Find the First Non-Repeating Character in a String

```js
function firstNonRepeatingCharacter(str) {}

assert.strictEqual(firstNonRepeatingCharacter("hello"), "h");
assert.strictEqual(firstNonRepeatingCharacter("aabbcc"), null);
assert.strictEqual(firstNonRepeatingCharacter("aabcbcde"), "d");
assert.strictEqual(firstNonRepeatingCharacter(""), null);
```

### Capitalize the First Letter of Each Word in a String

```js
const assert = require("node:assert");

function capitalizeWords(str) {
  let result = "";
  for (let index = 0; index < str.length; index++) {
    const element = str[index];
    const prev = str[index - 1];

    if (!prev || prev === " ") {
      result += element.toUpperCase();
    } else {
      result += element;
    }
  }
  return result;
}

assert.strictEqual(capitalizeWords("hello world"), "Hello World");
assert.strictEqual(capitalizeWords("javaScript is fun"), "JavaScript Is Fun");
assert.strictEqual(capitalizeWords("a"), "A");
```

### Replace a Substring within a String

```js
const assert = require("node:assert");

function replaceSubstring(str, searchValue, replaceValue) {
  let newString = "";
  let index = 0;

  while (newString.length < str.length) {
    const match = searchValue[0] === str[index];
    if (match) {
      for (
        let searchValueIndex = 0;
        searchValueIndex < searchValue.length;
        searchValueIndex++
      ) {
        const replaceElement = replaceValue[searchValueIndex];

        if (replaceElement) {
          newString += replaceValue[searchValueIndex];
        }
      }
      index += searchValue.length;
    } else {
      newString += str[index];
      index++;
    }
  }
  return newString;
}

assert.strictEqual(
  replaceSubstring("hello world", "world", "there"),
  "hello there"
);
assert.strictEqual(
  replaceSubstring("foo bar foo", "foo", "baz"),
  "baz bar baz"
);
assert.strictEqual(replaceSubstring("abcabc", "abc", "def"), "defdef");
assert.strictEqual(replaceSubstring("abc", "d", "e"), "abc");
assert.strictEqual(replaceSubstring("hello", "z", "y"), "hello");
assert.strictEqual(replaceSubstring("abc", "", "x"), "abc");
assert.strictEqual(replaceSubstring("", "abc", "def"), "");
assert.strictEqual(replaceSubstring("aaaaa", "a", "b"), "bbbbb");
assert.strictEqual(replaceSubstring("12345", "2", "8"), "18345");
```

### [todo] Find the Longest Word in a String

```js
function findLongestWord(str) {}

assert.strictEqual(
  findLongestWord("The quick brown fox jumps over the lazy dog"),
  "jumps"
);
assert.strictEqual(findLongestWord("hello world"), "hello");
assert.strictEqual(findLongestWord(""), "");
assert.strictEqual(findLongestWord("a aa aaa"), "aaa");
```

### [todo] Find All Permutations of a String

```js
function permute(str) {}

// Tests
assert.deepStrictEqual(
  permute("abc").sort(),
  ["abc", "acb", "bac", "bca", "cab", "cba"].sort()
);
assert.deepStrictEqual(permute("ab").sort(), ["ab", "ba"].sort());
assert.deepStrictEqual(permute("a"), ["a"]);
assert.deepStrictEqual(permute("").sort(), [""].sort());
```

## Advanced

### Implement a Basic String Compression Algorithm

```js
function compressString(str) {
  let letter = str[0];
  let result = "";
  let counter = 0;

  for (let index = 0; index <= str.length; index++) {
    const element = str[index];

    if (letter === element) {
      counter++;
    } else {
      result += `${str[index - 1]}${counter === 1 ? "" : counter}`;
      counter = 1;
      letter = element;
    }
  }

  return result;
}

assert.strictEqual(compressString("aaabbc"), "a3b2c");
assert.strictEqual(compressString("abcd"), "abcd");
assert.strictEqual(compressString("aabcccccaaa"), "a2bc5a3");
```

### Check if a String Contains Balanced Parentheses

```js
const openingBrackets = ["(", "{", "["];
const closingDict = new Map([
  [")", "("],
  ["}", "{"],
  ["]", "["],
]);

function isBalancedParentheses(str) {
  let lastOpenParanthesis = [];

  for (let i = 0; i < str.length; i++) {
    const el = str[i];
    const isOpening = openingBrackets.includes(el);
    if (isOpening) {
      lastOpenParanthesis.push(el);
    } else {
      // closing
      const match = closingDict.get(el);
      console.log({ match, lastOpenParanthesis });

      if (match !== lastOpenParanthesis.pop()) return false;
    }
  }

  return true;
}

assert.strictEqual(isBalancedParentheses("()"), true);
assert.strictEqual(isBalancedParentheses("([{}])"), true);
assert.strictEqual(isBalancedParentheses("([{]})"), false);
```

### Convert String from snake_case to camelCase

```js
const assert = require("node:assert");

function snakeToCamel(str) {
  let result = "";
  let underscoreIndex = null;
  for (let i = 0; i < str.length; i++) {
    let element = str[i];
    const isUnderscore = element === "_";
    if (isUnderscore) {
      underscoreIndex = i;
    } else {
      if (typeof underscoreIndex === "number") {
        element = element.toUpperCase();
        underscoreIndex = null;
      }
      result += element;
    }
  }
  return result;
}

assert.strictEqual(snakeToCamel("hello_world"), "helloWorld");
assert.strictEqual(snakeToCamel("snake_case_string"), "snakeCaseString");
assert.strictEqual(snakeToCamel("alreadyCamelCase"), "alreadyCamelCase");
assert.strictEqual(snakeToCamel(""), "");
```

### [todo] Find the Longest Palindromic Substring

```js
function longestPalindromicSubstring(s) {}

function expandAroundCenter(s, left, right) {}

assert.strictEqual(longestPalindromicSubstring("babad"), "bab");
assert.strictEqual(longestPalindromicSubstring("cbbd"), "bb");
assert.strictEqual(longestPalindromicSubstring("a"), "a");
assert.strictEqual(longestPalindromicSubstring(""), "");
```

### [todo] Implement Wildcard Pattern Matching with '?' and '\*'

```js
function isMatch(s, p) {}

assert.strictEqual(isMatch("aa", "a"), false);
assert.strictEqual(isMatch("aa", "*"), true);
assert.strictEqual(isMatch("cb", "?a"), false);
assert.strictEqual(isMatch("adceb", "*a*b"), true);
assert.strictEqual(isMatch("acdcb", "a*c?b"), false);
```
