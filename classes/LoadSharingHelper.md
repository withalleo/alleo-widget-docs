[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / LoadSharingHelper

# Class: LoadSharingHelper

Coordinates task execution across multiple widget instances using distributed locking.

Implements a leader election system where only one widget instance (across all users)
executes a periodic task, preventing duplicate API calls or processing. Uses shared
variables for lock coordination with automatic takeover if the leader becomes unresponsive.
Essential for widgets that need to fetch data periodically but should only do so once
across all active sessions.

## Example

```typescript
// Only one widget instance will fetch weather data
const weatherUpdater = new LoadSharingHelper(
  (lastUpdateTime) => {
    console.log("I am the leader, fetching weather data");
    fetchWeatherData().then((data) => {
      // Share data via shared variable
      haptic.setDataField("weatherData", data, false);
    });
  },
  60000, // Check every 60 seconds
  70000, // Take over if leader hasn't updated in 70 seconds
  "weatherUpdateLock",
);

// Check if this instance is the leader
if (weatherUpdater.isResponsible) {
  console.log("I am managing updates");
}
```

## Constructors

### Constructor

```ts
new LoadSharingHelper(
   callback: (lastEntryRelativeTime?: number) => void,
   checkInterval?: number,
   takeOverTimeout?: number,
   dataFieldName?: string): LoadSharingHelper;
```

Creates a LoadSharingHelper for coordinated task execution across widget instances.

Sets up periodic checking and automatic leader election. The callback is only invoked
on the instance that holds the lock (the "leader").

#### Parameters

| Parameter          | Type                                           | Default value   | Description                                                                            |
| ------------------ | ---------------------------------------------- | --------------- | -------------------------------------------------------------------------------------- |
| `callback`         | (`lastEntryRelativeTime?`: `number`) => `void` | `undefined`     | Function to execute when this instance is the leader. Receives time since last update. |
| `checkInterval?`   | `number`                                       | `300`           | Milliseconds between lock status checks and callback execution.                        |
| `takeOverTimeout?` | `number`                                       | `...`           | Milliseconds of inactivity before another instance can take over leadership.           |
| `dataFieldName?`   | `string`                                       | `'processLock'` | Shared variable name for storing lock information.                                     |

#### Returns

`LoadSharingHelper`

## Properties

### defaultLock

```ts
static defaultLock: SharedLock;
```

The default shared lock.

## Accessors

### currentLock

#### Get Signature

```ts
get currentLock(): SharedLock;
```

##### Returns

[`SharedLock`](../type-aliases/SharedLock.md)

---

### isMyResponsibility

#### Get Signature

```ts
get isMyResponsibility(): boolean;
```

Indicates whether the current widget instance is the leader responsible for task execution.

##### Returns

`boolean`

True if this instance holds the lock and should execute tasks, false otherwise.

## Methods

### onDestroy()

```ts
onDestroy(): void;
```

Handles the destruction of the widget by stopping the timer.

#### Returns

`void`

---

### restartTimer()

```ts
restartTimer(interval?: number, takeOverTimeOut?: number): void;
```

Restarts the timer with a new interval and takeover timeout.

#### Parameters

| Parameter         | Type     | Default value | Description                                                           |
| ----------------- | -------- | ------------- | --------------------------------------------------------------------- |
| `interval`        | `number` | `undefined`   | The new interval in milliseconds to check the lock status.            |
| `takeOverTimeOut` | `number` | `...`         | The new timeout in milliseconds to take over the lock if not updated. |

#### Returns

`void`

---

### startTimer()

```ts
startTimer(): void;
```

Starts the timer that checks the lock status.

#### Returns

`void`

---

### stopTimer()

```ts
stopTimer(): void;
```

Stops the timer that checks the lock status.

#### Returns

`void`
