[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / SharedVariableLimitError

# Class: SharedVariableLimitError

Thrown by [SharedVariable](SharedVariable.md) writes that would break the server limits or wouldn't survive a reload.
Nothing is written in that case.

## Extends

- `Error`

## Constructors

### Constructor

```ts
new SharedVariableLimitError(
   message: string,
   limit: "type" | "size" | "depth",
   actual?: number,
   max?: number
): SharedVariableLimitError;
```

#### Parameters

| Parameter | Type                              |
| --------- | --------------------------------- |
| `message` | `string`                          |
| `limit`   | `"type"` \| `"size"` \| `"depth"` |
| `actual?` | `number`                          |
| `max?`    | `number`                          |

#### Returns

`SharedVariableLimitError`

#### Overrides

`Error.constructor`

## Properties

### actual?

```ts
readonly actual?: number;
```

The measured depth (levels) or size (bytes); for depth, the first level found over the
limit. `undefined` for `'type'`.

---

### limit

```ts
readonly limit: "type" | "size" | "depth";
```

`'depth'`, `'size'` or `'type'` (a value that can't be stored, see [SharedVariable.set](SharedVariable.md#set)).

---

### max?

```ts
readonly max?: number;
```

The allowed maximum. `undefined` for `'type'`.
