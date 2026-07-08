[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / AnalyticsHelper

# Class: AnalyticsHelper

Helper class for tracking analytics events, logging, and debugging widget behavior.

Provides methods for event tracking, structured logging at different severity levels,
and TypeScript decorators for debugging class methods, properties, and parameters.
All log messages are automatically prefixed with the widget name for easy identification.

## Example

```typescript
// Track a user action
AnalyticsHelper.trackEvent("button-clicked", { buttonId: "submit" });

// Log messages at different levels
AnalyticsHelper.debug("Processing data", { count: 10 });
AnalyticsHelper.info("User logged in");
AnalyticsHelper.warn("API rate limit approaching");
AnalyticsHelper.error("Failed to save data", error);

// Use decorators for debugging
class MyWidget {
  @AnalyticsHelper.LogMethod
  processData(data: any) {
    // Method calls will be automatically logged
  }
}
```

## Constructors

### Constructor

```ts
new AnalyticsHelper(): AnalyticsHelper;
```

#### Returns

`AnalyticsHelper`

## Methods

### debug()

```ts
static debug(...params: any[]): void;
```

Logs a debug-level message for development and troubleshooting.

Debug messages are only visible in development mode and are not persisted to logs.
Use for verbose logging during development that would be too noisy in production.

#### Parameters

| Parameter   | Type    | Description                                            |
| ----------- | ------- | ------------------------------------------------------ |
| ...`params` | `any`[] | The values to log (will be prefixed with widget name). |

#### Returns

`void`

---

### error()

```ts
static error(...params: any[]): void;
```

Logs an error-level message for failures and exceptions.

Error messages indicate something went wrong that prevents normal operation.
These messages are always visible and logged, and may trigger error reporting systems.

#### Parameters

| Parameter   | Type    | Description                                            |
| ----------- | ------- | ------------------------------------------------------ |
| ...`params` | `any`[] | The values to log (will be prefixed with widget name). |

#### Returns

`void`

---

### getWidgetName()

```ts
static getWidgetName(): string;
```

Retrieves the unique widget identifier from the configuration or URL.

This identifier is typically the widget's name as defined in its manifest.json file
and is used to categorize analytics events and log messages.

#### Returns

`string`

The widget identifier (e.g., 'hello-world', 'ai-chat'), or undefined if not available.

---

### info()

```ts
static info(...params: any[]): void;
```

Logs an info-level message for notable events that aren't errors.

Info messages are typically hidden in production UI but are persisted to logs.
Use for tracking significant state changes or milestones in widget execution.

#### Parameters

| Parameter   | Type    | Description                                            |
| ----------- | ------- | ------------------------------------------------------ |
| ...`params` | `any`[] | The values to log (will be prefixed with widget name). |

#### Returns

`void`

---

### LogAccessor()

```ts
static LogAccessor(
   target: any,
   propertyKey: any,
   descriptor?: PropertyDescriptor): void;
```

TypeScript decorator that logs getter and setter calls on class properties.

Tracks when properties are read or written, including the values being accessed or set.
Useful for debugging reactive properties or tracking state changes.

#### Parameters

| Parameter     | Type                 | Default value | Description                                         |
| ------------- | -------------------- | ------------- | --------------------------------------------------- |
| `target`      | `any`                | `undefined`   | The prototype of the class containing the accessor. |
| `propertyKey` | `any`                | `undefined`   | The name of the property being decorated.           |
| `descriptor?` | `PropertyDescriptor` | `undefined`   | The property descriptor containing get/set methods. |

#### Returns

`void`

#### Example

```typescript
class MyWidget {
  private _value: number = 0;

  @AnalyticsHelper.LogAccessor
  get value(): number {
    return this._value;
  }
  set value(v: number) {
    this._value = v;
  }
}
// Logs: "Getter Called", "value"
// Logs: "Getter Result", "value", 0
// Logs: "Setter Called", "value", 42
```

---

### LogClass()

```ts
static LogClass<T>(constructor: T): {
(...args: any[]): (Anonymous class)<T>;
  prototype: (Anonymous class)<any>;
} & T;
```

TypeScript decorator that logs class instantiation, including constructor arguments and the created instance.

Useful for tracking when and how classes are instantiated during widget execution.
Logs both the constructor parameters and the final created object.

#### Type Parameters

| Type Parameter                              |
| ------------------------------------------- |
| `T` _extends_ (...`args`: `any`[]) => \{ \} |

#### Parameters

| Parameter     | Type | Description                                     |
| ------------- | ---- | ----------------------------------------------- |
| `constructor` | `T`  | The class constructor function to be decorated. |

#### Returns

\{
(...`args`: `any`[]): `(Anonymous class)`\<`T`\>;
`prototype`: `(Anonymous class)`\<`any`\>;
\} & `T`

A new class that extends the original with logging capabilities.

#### Example

```typescript
@AnalyticsHelper.LogClass
class DataManager {
  constructor(apiKey: string) {
    // ...
  }
}
// Logs: "Class Instantiated", "DataManager", ["abc123"]
// Logs: "Class Created", "DataManager", { ... instance details ... }
```

---

### LogMethod()

```ts
static LogMethod(
   target: any,
   propertyKey: any,
   descriptor?: PropertyDescriptor): void;
```

TypeScript decorator that logs all calls to a method, including arguments and return values.

Useful for debugging method execution flow during development. Logs both the input parameters
and the returned result for each method invocation.

#### Parameters

| Parameter     | Type                 | Default value | Description                                       |
| ------------- | -------------------- | ------------- | ------------------------------------------------- |
| `target`      | `any`                | `undefined`   | The prototype of the class containing the method. |
| `propertyKey` | `any`                | `undefined`   | The name of the method being decorated.           |
| `descriptor?` | `PropertyDescriptor` | `undefined`   | The property descriptor of the method.            |

#### Returns

`void`

#### Example

```typescript
class MyWidget {
  @AnalyticsHelper.LogMethod
  calculateTotal(items: number[]): number {
    return items.reduce((sum, item) => sum + item, 0);
  }
}
// Logs: "Method Called", "calculateTotal", [[1, 2, 3]]
// Logs: "Method Result", "calculateTotal", 6
```

---

### LogParameter()

```ts
static LogParameter(
   target: any,
   propertyKey: any,
   parameterIndex?: number): void;
```

TypeScript parameter decorator that logs when a parameter decorator is applied during class definition.

This decorator fires during class definition time and logs the method name and parameter position.
Useful for debugging parameter metadata and decorator application.

#### Parameters

| Parameter         | Type     | Default value | Description                                                           |
| ----------------- | -------- | ------------- | --------------------------------------------------------------------- |
| `target`          | `any`    | `undefined`   | The prototype of the class containing the method.                     |
| `propertyKey`     | `any`    | `undefined`   | The name of the method whose parameter is being decorated.            |
| `parameterIndex?` | `number` | `undefined`   | The zero-based index of the parameter in the method's parameter list. |

#### Returns

`void`

#### Example

```typescript
class MyWidget {
  processData(@AnalyticsHelper.LogParameter data: any) {
    // ...
  }
}
// Logs: "Parameter Decorator Applied", "processData", "Parameter index: 0"
```

---

### LogProperty()

```ts
static LogProperty(target: any, propertyKey: any): void;
```

TypeScript decorator that logs when a property decorator is applied during class definition.

This decorator fires during class definition time, not during property access.
Primarily useful for debugging decorator application order and property metadata.

#### Parameters

| Parameter     | Type  | Description                                         |
| ------------- | ----- | --------------------------------------------------- |
| `target`      | `any` | The prototype of the class containing the property. |
| `propertyKey` | `any` | The name of the property being decorated.           |

#### Returns

`void`

#### Example

```typescript
class MyWidget {
  @AnalyticsHelper.LogProperty
  username: string;
}
// Logs: "Property Decorator Applied", "username" (at class definition time)
```

---

### trackEvent()

```ts
static trackEvent(action: string, payload?: Record<string, any>): void;
```

Tracks an analytics event for monitoring widget usage and user behavior.

Events are automatically enriched with widget metadata (name, ID, entry point) and sent to
the Alleo analytics system. The event is also forwarded to any analytics tracking widgets
present on the board.

#### Parameters

| Parameter  | Type                        | Description                                                                                     |
| ---------- | --------------------------- | ----------------------------------------------------------------------------------------------- |
| `action`   | `string`                    | The name of the action being tracked (e.g., 'button-clicked', 'data-loaded', 'error-occurred'). |
| `payload?` | `Record`\<`string`, `any`\> | Additional contextual data about the event (e.g., button ID, error message, data size).         |

#### Returns

`void`

#### Example

```typescript
// Track a simple button click
AnalyticsHelper.trackEvent("submit-clicked");

// Track with additional context
AnalyticsHelper.trackEvent("data-exported", {
  format: "csv",
  rowCount: 150,
  timestamp: Date.now(),
});
```

---

### warn()

```ts
static warn(...params: any[]): void;
```

Logs a warning-level message for recoverable issues or potential problems.

Warnings indicate something unexpected happened but the widget can continue operating.
These messages are visible in both development and production.

#### Parameters

| Parameter   | Type    | Description                                            |
| ----------- | ------- | ------------------------------------------------------ |
| ...`params` | `any`[] | The values to log (will be prefixed with widget name). |

#### Returns

`void`
