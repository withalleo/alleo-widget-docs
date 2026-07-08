[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / isEqual

# Function: isEqual()

```ts
function isEqual<T>(a: T, b: T): boolean;
```

Performs deep equality comparison between two values of any type.

Recursively compares objects and arrays by value rather than reference. Supports
primitives, arrays, objects, null, and undefined. Useful for detecting actual
data changes rather than reference changes.

## Type Parameters

| Type Parameter |
| -------------- |
| `T`            |

## Parameters

| Parameter | Type | Description                  |
| --------- | ---- | ---------------------------- |
| `a`       | `T`  | The first value to compare.  |
| `b`       | `T`  | The second value to compare. |

## Returns

`boolean`

True if values are deeply equal, false otherwise.

## Example

```typescript
// Primitives
isEqual(5, 5); // true
isEqual("hello", "hello"); // true

// Objects (different references, same content)
isEqual({ x: 1 }, { x: 1 }); // true
isEqual({ x: 1 }, { x: 2 }); // false

// Arrays
isEqual([1, 2, 3], [1, 2, 3]); // true
isEqual([1, 2], [1, 2, 3]); // false

// Nested structures
isEqual(
  { user: { name: "John", age: 30 } },
  { user: { name: "John", age: 30 } },
); // true
```
