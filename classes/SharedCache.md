[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / SharedCache

# Class: SharedCache\<T\>

Provides a key-value cache stored in shared variables for cross-session data persistence.

Enables widgets to cache data that persists across widget reloads and is shared among
all users viewing the widget. Supports delayed writes for performance optimization when
making multiple updates. Ideal for caching API responses, computed results, or user
preferences that should be shared across sessions.

## Example

```typescript
// Create a cache for API responses
const apiCache = new SharedCache<{ data: any; timestamp: number }>("apiCache");

// Store data
apiCache.set("user-123", { data: userData, timestamp: Date.now() });

// Retrieve data
const cached = apiCache.get("user-123");
if (cached && Date.now() - cached.timestamp < 3600000) {
  // Use cached data if less than 1 hour old
  console.log(cached.data);
}

// Use delayed write mode for bulk updates
const bulkCache = new SharedCache("bulkData", true);
bulkCache.set("key1", "value1");
bulkCache.set("key2", "value2");
bulkCache.flush(); // Write all at once
```

## Type Parameters

| Type Parameter | Default type | Description                                               |
| -------------- | ------------ | --------------------------------------------------------- |
| `T`            | `any`        | The type of values stored in the cache (defaults to any). |

## Constructors

### Constructor

```ts
new SharedCache<T>(databaseId?: string, delayedWrite?: boolean): SharedCache<T>;
```

Creates a SharedCache instance for storing key-value pairs in shared variables.

#### Parameters

| Parameter       | Type      | Default value | Description                                                                        |
| --------------- | --------- | ------------- | ---------------------------------------------------------------------------------- |
| `databaseId?`   | `string`  | `'cache'`     | Unique identifier for the cache's shared variable storage.                         |
| `delayedWrite?` | `boolean` | `false`       | When true, writes are batched and must be flushed manually for better performance. |

#### Returns

`SharedCache`\<`T`\>

## Properties

### debug

```ts
static debug: boolean = false;
```

Indicates whether debugging is enabled.

## Methods

### deploy()

```ts
deploy(): void;
```

Deploys the delayed writes to the cache.

#### Returns

`void`

---

### get()

```ts
get(key: string): T;
```

Retrieves a value from the cache by key.

Checks delayed writes first (if enabled), then falls back to persisted cache.

#### Parameters

| Parameter | Type     | Description                |
| --------- | -------- | -------------------------- |
| `key`     | `string` | The cache key to retrieve. |

#### Returns

`T`

The cached value, or undefined if key doesn't exist.

---

### set()

```ts
set(key: string, value: T): void;
```

Stores a value in the cache under the specified key.

If delayed write mode is enabled, the value is queued and not immediately persisted.
Call flush() to persist delayed writes.

#### Parameters

| Parameter | Type     | Description                             |
| --------- | -------- | --------------------------------------- |
| `key`     | `string` | The cache key to store the value under. |
| `value`   | `T`      | The value to cache.                     |

#### Returns

`void`
