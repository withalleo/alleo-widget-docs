[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / randomInt

# Function: randomInt()

```ts
function randomInt(min: number, max: number): number;
```

Generates a cryptographically secure random integer within a specified range (inclusive).

Uses the Web Crypto API for secure random number generation, making it suitable for
security-sensitive applications. Both min and max values are inclusive in the range.

## Parameters

| Parameter | Type     | Description                                                     |
| --------- | -------- | --------------------------------------------------------------- |
| `min`     | `number` | The minimum value (inclusive, must be non-negative).            |
| `max`     | `number` | The maximum value (inclusive, must be non-negative and >= min). |

## Returns

`number`

A random integer between min and max (inclusive).

## Throws

Throws if min > max, if either is negative, or if range exceeds 2^32.

## Example

```typescript
randomInt(1, 6); // Random dice roll: 1, 2, 3, 4, 5, or 6
randomInt(0, 100); // Random percentage: 0 to 100
randomInt(10, 10); // Always returns 10
```
