# Objects

### [x] Delete a Property from an Object

```js
function deleteProperty(obj, key) {
  delete obj[key];

  return obj;
}

assert.deepStrictEqual(deleteProperty({ name: "Alice", age: 25 }, "age"), {
  name: "Alice",
});
assert.deepStrictEqual(deleteProperty({ name: "Bob" }, "name"), {});
assert.deepStrictEqual(deleteProperty({}, "name"), {});
assert.deepStrictEqual(deleteProperty({ a: 1, b: 2 }, "a"), { b: 2 });
assert.deepStrictEqual(deleteProperty({ key: "value" }, "nonexistent"), {
  key: "value",
});
```

### [x] Check if Object Has a Property

```js
function hasProperty(obj, key) {
  return key in obj;
}

assert.strictEqual(hasProperty({ name: "Alice" }, "name"), true);
assert.strictEqual(hasProperty({ age: 25 }, "name"), false);
assert.strictEqual(hasProperty({}, "name"), false);
assert.strictEqual(hasProperty({ a: undefined }, "a"), true);
assert.strictEqual(hasProperty({ key: "value" }, "key"), true);
```

### Get Object Keys and Values

```js
function getKeys(obj) {
  // Your code here
}

function getValues(obj) {
  // Your code here
}

assert.deepStrictEqual(getKeys({ a: 1, b: 2 }), ["a", "b"]);
assert.deepStrictEqual(getValues({ a: 1, b: 2 }), [1, 2]);
assert.deepStrictEqual(getKeys({}), []);
assert.deepStrictEqual(getValues({}), []);
assert.deepStrictEqual(getKeys({ name: "Alice", age: 25 }), ["name", "age"]);
assert.deepStrictEqual(getValues({ name: "Alice", age: 25 }), ["Alice", 25]);
assert.deepStrictEqual(getKeys({ x: undefined, y: null }), ["x", "y"]);
assert.deepStrictEqual(getValues({ x: undefined, y: null }), [undefined, null]);
assert.deepStrictEqual(getKeys({ key: "value" }), ["key"]);
assert.deepStrictEqual(getValues({ key: "value" }), ["value"]);
```

### Count Properties in an Object

```js
function countProperties(obj) {
  // Your code here
}

assert.strictEqual(countProperties({ a: 1, b: 2, c: 3 }), 3);
assert.strictEqual(countProperties({}), 0);
assert.strictEqual(countProperties({ name: "Alice" }), 1);
assert.strictEqual(countProperties({ x: 10, y: 20, z: 30, w: 40 }), 4);
assert.strictEqual(
  countProperties({ key: "value", anotherKey: "anotherValue" }),
  2
);
```

### Invert Keys and Values in an Object

```js
function invertObject(obj) {
  // Your code here
}

assert.deepStrictEqual(invertObject({ a: 1, b: 2 }), { 1: "a", 2: "b" });
assert.deepStrictEqual(invertObject({ name: "Alice", age: "25" }), {
  Alice: "name",
  25: "age",
});
assert.deepStrictEqual(invertObject({}), {});
assert.deepStrictEqual(invertObject({ x: "10", y: "20" }), {
  10: "x",
  20: "y",
});
assert.deepStrictEqual(
  invertObject({ key: "value", anotherKey: "anotherValue" }),
  { value: "key", anotherValue: "anotherKey" }
);
```

### Deep Clone an Object

```js
function deepClone(obj) {
  // Your code here
}

const original1 = { a: 1, b: { c: 2 } };
const cloned1 = deepClone(original1);
assert.deepStrictEqual(cloned1, original1);
assert.notStrictEqual(cloned1.b, original1.b);

const original2 = { x: { y: { z: 10 } }, w: 20 };
const cloned2 = deepClone(original2);
assert.deepStrictEqual(cloned2, original2);
assert.notStrictEqual(cloned2.x.y, original2.x.y);

const original3 = {};
const cloned3 = deepClone(original3);
assert.deepStrictEqual(cloned3, original3);
assert.notStrictEqual(cloned3, original3);

const original4 = { arr: [1, 2, 3], obj: { key: "value" } };
const cloned4 = deepClone(original4);
assert.deepStrictEqual(cloned4, original4);
assert.notStrictEqual(cloned4.arr, original4.arr);
assert.notStrictEqual(cloned4.obj, original4.obj);

const original5 = {
  name: "Alice",
  details: { age: 25, hobbies: ["reading", "coding"] },
};
const cloned5 = deepClone(original5);
assert.deepStrictEqual(cloned5, original5);
assert.notStrictEqual(cloned5.details, original5.details);
assert.notStrictEqual(cloned5.details.hobbies, original5.details.hobbies);
```

## Advanced

### Compare Two Objects for Equality

```js
function isEqual(obj1, obj2) {
  // Your code here
}

assert.strictEqual(isEqual({ a: 1, b: 2 }, { a: 1, b: 2 }), true);
assert.strictEqual(isEqual({ a: 1 }, { a: 1, b: 2 }), false);
assert.strictEqual(isEqual({}, {}), true);
assert.strictEqual(isEqual({ x: { y: 10 } }, { x: { y: 10 } }), true);
assert.strictEqual(isEqual({ a: 1, b: 2 }, { b: 2, a: 1 }), true);
```

### Get Nested Property Value

```js
function getNestedProperty(obj, path) {
  // Your code here
}

const data = { a: { b: { c: 42 } } };
assert.strictEqual(getNestedProperty(data, "a.b.c"), 42);
assert.strictEqual(getNestedProperty(data, "a.b.d"), undefined);
assert.strictEqual(getNestedProperty({}, "a.b"), undefined);
assert.strictEqual(getNestedProperty({ x: { y: { z: 10 } } }, "x.y.z"), 10);
assert.strictEqual(
  getNestedProperty({ key: { nestedKey: "value" } }, "key.nestedKey"),
  "value"
);
```

### Flatten a Nested Object

```js
function flattenObject(obj) {
  // Your code here
}

const nestedObj1 = { a: { b: { c: 1 } }, d: 2 };
assert.deepStrictEqual(flattenObject(nestedObj1), { "a.b.c": 1, d: 2 });

const nestedObj2 = { x: { y: { z: 10 } }, w: 20 };
assert.deepStrictEqual(flattenObject(nestedObj2), { "x.y.z": 10, w: 20 });

const nestedObj3 = {};
assert.deepStrictEqual(flattenObject(nestedObj3), {});

const nestedObj4 = { key: { nestedKey: { innerKey: "value" } } };
assert.deepStrictEqual(flattenObject(nestedObj4), {
  "key.nestedKey.innerKey": "value",
});

const nestedObj5 = { a: 1, b: { c: 2, d: { e: 3 } } };
assert.deepStrictEqual(flattenObject(nestedObj5), {
  a: 1,
  "b.c": 2,
  "b.d.e": 3,
});
```

### Unflatten an Object

```js
function unflattenObject(data) {
  // Your code here
}

const flatObj1 = { "a.b.c": 1, d: 2 };
assert.deepStrictEqual(unflattenObject(flatObj1), { a: { b: { c: 1 } }, d: 2 });

const flatObj2 = { "x.y.z": 10, w: 20 };
assert.deepStrictEqual(unflattenObject(flatObj2), {
  x: { y: { z: 10 } },
  w: 20,
});

const flatObj3 = {};
assert.deepStrictEqual(unflattenObject(flatObj3), {});

const flatObj4 = { "key.nestedKey.innerKey": "value" };
assert.deepStrictEqual(unflattenObject(flatObj4), {
  key: { nestedKey: { innerKey: "value" } },
});

const flatObj5 = { a: 1, "b.c": 2, "b.d.e": 3 };
assert.deepStrictEqual(unflattenObject(flatObj5), {
  a: 1,
  b: { c: 2, d: { e: 3 } },
});
```

### Deep Freeze an Object

```js
function deepFreeze(obj) {
  // Your code here
}

const obj1 = { a: 1, b: { c: 2 } };
deepFreeze(obj1);
assert.throws(() => {
  obj1.b.c = 3;
}, TypeError);
assert.strictEqual(obj1.b.c, 2);

const obj2 = { x: { y: { z: 10 } }, w: 20 };
deepFreeze(obj2);
assert.throws(() => {
  obj2.x.y.z = 15;
}, TypeError);
assert.strictEqual(obj2.x.y.z, 10);

const obj3 = {};
deepFreeze(obj3);
assert.throws(() => {
  obj3.newProp = "test";
}, TypeError);
assert.deepStrictEqual(obj3, {});

const obj4 = { arr: [1, 2, 3], obj: { key: "value" } };
deepFreeze(obj4);
assert.throws(() => {
  obj4.arr.push(4);
}, TypeError);
assert.deepStrictEqual(obj4.arr, [1, 2, 3]);

const obj5 = {
  name: "Alice",
  details: { age: 25, hobbies: ["reading", "coding"] },
};
deepFreeze(obj5);
assert.throws(() => {
  obj5.details.hobbies[0] = "traveling";
}, TypeError);
assert.deepStrictEqual(obj5.details.hobbies, ["reading", "coding"]);
```

### Create an Object from Two Arrays

```js
function createObject(keys, values) {
  // Your code here
}

assert.deepStrictEqual(createObject(["a", "b", "c"], [1, 2, 3]), {
  a: 1,
  b: 2,
  c: 3,
});
assert.deepStrictEqual(createObject(["name", "age"], ["Alice", 25]), {
  name: "Alice",
  age: 25,
});
assert.deepStrictEqual(createObject([], []), {});
assert.deepStrictEqual(createObject(["key"], ["value"]), { key: "value" });
assert.deepStrictEqual(createObject(["x", "y", "z"], [10, 20]), {
  x: 10,
  y: 20,
});
```

### Convert Object to Array of Key-Value Pairs

```js
function objectToPairs(obj) {
  // Your code here
}

assert.deepStrictEqual(objectToPairs({ a: 1, b: 2 }), [
  ["a", 1],
  ["b", 2],
]);
assert.deepStrictEqual(objectToPairs({}), []);
assert.deepStrictEqual(objectToPairs({ key: "value" }), [["key", "value"]]);
assert.deepStrictEqual(objectToPairs({ name: "Alice", age: 25 }), [
  ["name", "Alice"],
  ["age", 25],
]);
assert.deepStrictEqual(objectToPairs({ x: 10, y: undefined }), [
  ["x", 10],
  ["y", undefined],
]);
```

### Count Occurrences in an Array and Return an Object

```js
function countOccurrences(arr) {
  // Your code here
}

assert.deepStrictEqual(countOccurrences(["a", "b", "a", "c", "b", "a"]), {
  a: 3,
  b: 2,
  c: 1,
});
assert.deepStrictEqual(countOccurrences([]), {});
assert.deepStrictEqual(countOccurrences([1, 1, 1, 1]), { 1: 4 });
assert.deepStrictEqual(countOccurrences(["apple", "banana", "apple"]), {
  apple: 2,
  banana: 1,
});
assert.deepStrictEqual(countOccurrences(["x", "y", "z"]), { x: 1, y: 1, z: 1 });
```

### Update Nested Object Properties

```js
function updateNestedProperty(obj, path, value) {
  // Your code here
}

const obj1 = { a: { b: { c: 1 } } };
updateNestedProperty(obj1, "a.b.c", 42);
assert.strictEqual(obj1.a.b.c, 42);

const obj2 = { x: { y: { z: 10 } } };
updateNestedProperty(obj2, "x.y.z", 20);
assert.strictEqual(obj2.x.y.z, 20);

const obj3 = {};
updateNestedProperty(obj3, "a.b", 5);
assert.deepStrictEqual(obj3, { a: { b: 5 } });

const obj4 = { key: { nestedKey: "value" } };
updateNestedProperty(obj4, "key.nestedKey", "newValue");
assert.strictEqual(obj4.key.nestedKey, "newValue");

const obj5 = { arr: [{ val: 1 }] };
updateNestedProperty(obj5, "arr.0.val", 100);
assert.strictEqual(obj5.arr[0].val, 100);
```

### Filter Object Properties by Condition

```js
function filterObject(obj, predicate) {
  // Your code here
}

const obj1 = { a: 1, b: 2, c: 3 };
assert.deepStrictEqual(
  filterObject(obj1, (key, value) => value > 1),
  { b: 2, c: 3 }
);

const obj2 = { name: "Alice", age: 25, active: true };
assert.deepStrictEqual(
  filterObject(obj2, (key, value) => typeof value === "string"),
  { name: "Alice" }
);

const obj3 = {};
assert.deepStrictEqual(
  filterObject(obj3, () => true),
  {}
);

const obj4 = { x: undefined, y: null, z: 0 };
assert.deepStrictEqual(
  filterObject(obj4, (key, value) => value != null),
  { z: 0 }
);

const obj5 = { key1: "value1", key2: "value2", key3: "value3" };
assert.deepStrictEqual(
  filterObject(obj5, (key) => key.endsWith("2")),
  { key2: "value2" }
);
```

### Convert Array of Objects to a Single Object

```js
function arrayToObject(arr, keyField) {
  // Your code here
}

const arr1 = [
  { id: 1, value: "a" },
  { id: 2, value: "b" },
];
assert.deepStrictEqual(arrayToObject(arr1, "id"), {
  1: { id: 1, value: "a" },
  2: { id: 2, value: "b" },
});

const arr2 = [];
assert.deepStrictEqual(arrayToObject(arr2, "id"), {});

const arr3 = [
  { key: "x", val: 10 },
  { key: "y", val: 20 },
];
assert.deepStrictEqual(arrayToObject(arr3, "key"), {
  x: { key: "x", val: 10 },
  y: { key: "y", val: 20 },
});

const arr4 = [{ name: "Alice" }, { name: "Bob" }];
assert.deepStrictEqual(arrayToObject(arr4, "name"), {
  Alice: { name: "Alice" },
  Bob: { name: "Bob" },
});

const arr5 = [{ id: 1 }, { id: 1 }];
assert.deepStrictEqual(arrayToObject(arr5, "id"), { 1: { id: 1 } });
```

### Implement Simple Object.assign

```js
function simpleAssign(target, ...sources) {
  // Your code here
}

const target1 = {};
simpleAssign(target1, { a: 1 }, { b: 2 });
assert.deepStrictEqual(target1, { a: 1, b: 2 });

const target2 = { a: 1 };
simpleAssign(target2, { a: 2, b: 3 });
assert.deepStrictEqual(target2, { a: 2, b: 3 });

const target3 = {};
simpleAssign(target3);
assert.deepStrictEqual(target3, {});

const target4 = { x: 10 };
simpleAssign(target4, { y: 20 }, { z: 30 }, { x: 40 });
assert.deepStrictEqual(target4, { x: 40, y: 20, z: 30 });

const target5 = {};
simpleAssign(target5, { key: "value" });
assert.deepStrictEqual(target5, { key: "value" });
```

### Check if Two Objects Have the Same Keys

```js
function haveSameKeys(obj1, obj2) {
  // Your code here
}

assert.strictEqual(haveSameKeys({ a: 1, b: 2 }, { a: 3, b: 4 }), true);
assert.strictEqual(haveSameKeys({ a: 1 }, { a: 1, b: 2 }), false);
assert.strictEqual(haveSameKeys({}, {}), true);
assert.strictEqual(haveSameKeys({ x: 10, y: 20 }, { y: 30, x: 40 }), true);
assert.strictEqual(
  haveSameKeys({ key: "value" }, { anotherKey: "value" }),
  false
);
```

### Group Array of Objects by Property

```js
function groupBy(arr, key) {
  // Your code here
}

const arr1 = [
  { type: "fruit", name: "apple" },
  { type: "vegetable", name: "carrot" },
  { type: "fruit", name: "banana" },
];
assert.deepStrictEqual(groupBy(arr1, "type"), {
  fruit: [
    { type: "fruit", name: "apple" },
    { type: "fruit", name: "banana" },
  ],
  vegetable: [{ type: "vegetable", name: "carrot" }],
});

const arr2 = [];
assert.deepStrictEqual(groupBy(arr2, "key"), {});

const arr3 = [
  { category: "A", value: 1 },
  { category: "B", value: 2 },
  { category: "A", value: 3 },
];
assert.deepStrictEqual(groupBy(arr3, "category"), {
  A: [
    { category: "A", value: 1 },
    { category: "A", value: 3 },
  ],
  B: [{ category: "B", value: 2 }],
});

const arr4 = [{ id: 1 }, { id: 2 }, { id: 1 }];
assert.deepStrictEqual(groupBy(arr4, "id"), {
  1: [{ id: 1 }, { id: 1 }],
  2: [{ id: 2 }],
});

const arr5 = [{ key: undefined }, { key: null }, { key: undefined }];
assert.deepStrictEqual(groupBy(arr5, "key"), {
  undefined: [{ key: undefined }, { key: undefined }],
  null: [{ key: null }],
});
```

### Get Keys of Object with Values of a Certain Type

```js
function keysOfType(obj, type) {
  // Your code here
}

const obj1 = { a: 1, b: "2", c: true, d: null };
assert.deepStrictEqual(keysOfType(obj1, "number"), ["a"]);
assert.deepStrictEqual(keysOfType(obj1, "string"), ["b"]);
assert.deepStrictEqual(keysOfType(obj1, "boolean"), ["c"]);
assert.deepStrictEqual(keysOfType(obj1, "object"), ["d"]);

const obj2 = { x: [1, 2], y: { z: 3 }, w: function () {} };
assert.deepStrictEqual(keysOfType(obj2, "object"), ["x", "y"]);
assert.deepStrictEqual(keysOfType(obj2, "function"), ["w"]);

const obj3 = {};
assert.deepStrictEqual(keysOfType(obj3, "number"), []);

const obj4 = { key: "value", anotherKey: 42 };
assert.deepStrictEqual(keysOfType(obj4, "string"), ["key"]);
assert.deepStrictEqual(keysOfType(obj4, "number"), ["anotherKey"]);

const obj5 = { a: undefined, b: null, c: NaN };
assert.deepStrictEqual(keysOfType(obj5, "undefined"), ["a"]);
assert.deepStrictEqual(keysOfType(obj5, "object"), ["b"]);
assert.deepStrictEqual(keysOfType(obj5, "number"), ["c"]);
```
