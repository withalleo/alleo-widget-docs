[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / isEqual

# Function: isEqual()

```ts
function isEqual<T>(a: T, b: T): boolean
```

Performs deep equality comparison between two values of any type.

Useful for detecting actual data changes rather than reference changes. Rules:

- Primitives: strict equality, except `NaN` equals `NaN`. Functions are compared by reference.
- Dates: compared by timestamp; invalid Dates equal each other.
- Arrays: same length and deeply equal items in order. `undefined` items are not skipped.
- Maps: same size, keys matched like `Map.has`, values compared deeply.
- Sets: same size, items matched like `Set.has` (objects by reference, not deeply).
- Objects: own enumerable string keys compared deeply. Keys with an `undefined` value
  count as missing, like in JSON, so `{ x: undefined }` equals `{}`. Prototypes and symbol keys are ignored.
- Cyclic structures are not supported.

## Type Parameters

| Type Parameter                    |
| --------------------------------- |
| <a id="type-parameter-t"></a> `T` |

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
isEqual(5, 5) // true
isEqual('hello', 'hello') // true
isEqual(NaN, NaN) // true

// Objects (different references, same content)
isEqual({ x: 1 }, { x: 1 }) // true
isEqual({ x: 1 }, { x: 2 }) // false
isEqual({ x: undefined }, {}) // true
isEqual({ x: undefined }, { x: null }) // false

// Arrays
isEqual([1, 2, 3], [1, 2, 3]) // true
isEqual([1, 2], [1, 2, 3]) // false

// Nested structures
isEqual({ user: { name: 'John', age: 30 } }, { user: { name: 'John', age: 30 } }) // true
```
