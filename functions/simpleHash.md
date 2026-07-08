[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / simpleHash

# Function: simpleHash()

```ts
function simpleHash(input: string): string;
```

Creates a case-insensitive, whitespace-normalized hash string from input text.

Generates a comparable hash that treats variations in casing and whitespace as identical.
Useful for comparing user input, detecting duplicates, or creating cache keys where
minor formatting differences should be ignored.

## Parameters

| Parameter | Type     | Description         |
| --------- | -------- | ------------------- |
| `input`   | `string` | The string to hash. |

## Returns

`string`

A base-36 hash string that's consistent for equivalent inputs.

## Example

```typescript
simpleHash("Hello World"); // 'abc123'
simpleHash("hello  world"); // 'abc123' (same hash)
simpleHash("HELLO WORLD"); // 'abc123' (same hash)
simpleHash("Hello World!"); // 'def456' (different due to punctuation)

// Use for deduplication
const seen = new Set();
if (!seen.has(simpleHash(userInput))) {
  seen.add(simpleHash(userInput));
  processInput(userInput);
}
```
