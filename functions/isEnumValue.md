[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / isEnumValue

# Function: isEnumValue()

```ts
function isEnumValue<T>(enumObj: T, value: unknown): value is T[keyof T];
```

Type guard to check if a value is a valid member of a TypeScript enum.

Validates that a runtime value matches one of the enum's defined values,
providing type safety when working with user input or API responses.

## Type Parameters

| Type Parameter                               |
| -------------------------------------------- |
| `T` _extends_ `Record`\<`string`, `string`\> |

## Parameters

| Parameter | Type      | Description                       |
| --------- | --------- | --------------------------------- |
| `enumObj` | `T`       | The enum object to check against. |
| `value`   | `unknown` | The value to validate.            |

## Returns

`value is T[keyof T]`

True if value is a valid enum member, false otherwise.

## Example

```typescript
enum Status {
  Active = "active",
  Inactive = "inactive",
  Pending = "pending",
}

const userInput: unknown = "active";
if (isEnumValue(Status, userInput)) {
  // TypeScript now knows userInput is Status
  const status: Status = userInput;
}

isEnumValue(Status, "active"); // true
isEnumValue(Status, "invalid"); // false
```
