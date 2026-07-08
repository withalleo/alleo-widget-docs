[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / RateLimitUpdateHelper

# Class: RateLimitUpdateHelper\<T\>

Manages rate-limited updates to shared variables to prevent excessive synchronization.

Throttles rapid updates to shared variables by batching changes within a specified time
window. Essential for high-frequency updates like scrolling, dragging, or real-time input
to avoid overwhelming the synchronization system. Automatically coalesces multiple rapid
changes into a single update.

## Example

```typescript
// Rate-limit scroll position updates
const scrollPosition = new RateLimitUpdateHelper<{ x: number; y: number }>(
  "scrollPos",
  200, // Update at most every 200ms
);

// Rapid updates are automatically throttled
element.addEventListener("scroll", () => {
  scrollPosition.set({ x: element.scrollLeft, y: element.scrollTop });
});

// Get latest value
const currentPos = scrollPosition.latest;

// Get stored remote value
const remotePos = scrollPosition.stored;
```

## Type Parameters

| Type Parameter | Default type | Description                           |
| -------------- | ------------ | ------------------------------------- |
| `T`            | `any`        | The type of value being rate-limited. |

## Constructors

### Constructor

```ts
new RateLimitUpdateHelper<T>(key: string, maxDelay?: number): RateLimitUpdateHelper<T>;
```

Creates a RateLimitUpdateHelper for managing rate-limited shared variable updates.

#### Parameters

| Parameter   | Type     | Default value | Description                                                                         |
| ----------- | -------- | ------------- | ----------------------------------------------------------------------------------- |
| `key`       | `string` | `undefined`   | Shared variable name to store the rate-limited value.                               |
| `maxDelay?` | `number` | `250`         | Maximum milliseconds between updates. Rapid changes within this window are batched. |

#### Returns

`RateLimitUpdateHelper`\<`T`\>

## Accessors

### latest

#### Get Signature

```ts
get latest(): T;
```

The most current value, considering both local and remote timing.

Returns the newest local value if updated recently (within maxDelay), otherwise
returns the stored remote value. Useful for getting the authoritative current value.

##### Returns

`T`

The latest value from either local or remote source.

---

### newest

#### Get Signature

```ts
get newest(): T;
```

The most recent value set locally, whether or not it has been synced yet.

Returns the last value passed to `set()`, which may be newer than the stored value
if an update is pending.

##### Returns

`T`

The newest locally set value, or the stored value if no local updates pending.

---

### stored

#### Get Signature

```ts
get stored(): T;
```

The current value stored in the shared variable (remote/synchronized value).

Retrieves the actual value from the shared variable storage, reflecting what
other users or widget instances can see.

##### Returns

`T`

The remotely stored shared variable value.

## Methods

### set()

```ts
set(value: T): void;
```

Sets a new value with automatic rate limiting.

Queues the value for update. If called multiple times within maxDelay window,
only the final value is synced, reducing unnecessary updates.

#### Parameters

| Parameter | Type | Description                               |
| --------- | ---- | ----------------------------------------- |
| `value`   | `T`  | The new value to set and eventually sync. |

#### Returns

`void`

---

### update()

```ts
protected update(): void;
```

Performs the actual update to the shared variable storage.

Only updates if the new value differs from the stored value. Automatically
handles retry logic if the update fails.

#### Returns

`void`
