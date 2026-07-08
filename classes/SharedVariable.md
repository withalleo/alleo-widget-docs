[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / SharedVariable

# Class: SharedVariable

Static utility for interacting with shared variables.

Use this class when you need direct shared-variable access outside of `this.shared`,
or when you want to observe one or more shared variables with a single callback.

In widgets extending `AlleoWidget`, prefer `this.shared.<key>` for normal read/write
operations because it is typed from your `defaultSharedVariables` and stays in sync
with Alleo data fields.

## Examples

```typescript
class CounterWidget extends AlleoWidget<
  typeof CounterWidget.defaultSharedVariables
> {
  private static defaultSharedVariables = {
    count: 0,
    title: "Counter",
  };

  constructor() {
    super(CounterWidget.defaultSharedVariables);

    // Read and write shared state through this.shared
    this.shared.count = (this.shared.count ?? 0) + 1;
    const currentTitle = this.shared.title;
    console.log(currentTitle, this.shared.count);
  }
}
```

```typescript
class CounterWidget extends AlleoWidget<
  typeof CounterWidget.defaultSharedVariables
> {
  private static defaultSharedVariables = {
    count: 0,
    title: "Counter",
  };

  private counterObserver?: InstanceType<typeof SharedVariable.observer>;

  constructor() {
    super(CounterWidget.defaultSharedVariables);

    // Observe multiple shared keys and react to remote/local updates
    this.counterObserver = new SharedVariable.observer(
      ["count", "title"],
      (data, changed) => {
        console.log("changed:", changed);
        console.log("count:", data.count, "title:", data.title);
      },
      { runOnInit: true },
    );
  }

  public override destroy(): void {
    this.counterObserver?.destroy();
    super.destroy();
  }
}
```

```typescript
// Direct utility usage (without this.shared)
await SharedVariable.set("count", 5);
const count = SharedVariable.get("count");
const values = SharedVariable.getMultiple(["count", "title"]);
console.log(count, values.title);
```

## Constructors

### Constructor

```ts
new SharedVariable(): SharedVariable;
```

#### Returns

`SharedVariable`

## Properties

### observer

```ts
static observer: typeof SharedVariableHelper = SharedVariableHelper;
```

Returns a SharedVariableHelper observer class.

#### Example

```typescript
const observer = new SharedVariable.observer(
  ["count", "title"],
  (data, changed) => {
    console.log("changed:", changed, "values:", data);
  },
  { runOnInit: true },
);

observer.destroy();
```

## Methods

### append()

```ts
static append(variable: string, value: any[]): Promise<any>;
```

Appends values to a shared variable (array).

#### Parameters

| Parameter  | Type     | Description           |
| ---------- | -------- | --------------------- |
| `variable` | `string` | The variable name.    |
| `value`    | `any`[]  | The values to append. |

#### Returns

`Promise`\<`any`\>

#### Example

```typescript
await SharedVariable.append("votes", ["alice", "bob"]);
```

---

### get()

```ts
static get(variable: string): any;
```

Gets the value of a shared variable.

#### Parameters

| Parameter  | Type     | Description        |
| ---------- | -------- | ------------------ |
| `variable` | `string` | The variable name. |

#### Returns

`any`

#### Example

```typescript
const count = SharedVariable.get("count");
console.log(count);
```

---

### getMultiple()

```ts
static getMultiple(variables: string[]): Record<string, any>;
```

Gets multiple shared variable values.

#### Parameters

| Parameter   | Type       | Description              |
| ----------- | ---------- | ------------------------ |
| `variables` | `string`[] | Array of variable names. |

#### Returns

`Record`\<`string`, `any`\>

#### Example

```typescript
const values = SharedVariable.getMultiple(["count", "title"]);
console.log(values.count, values.title);
```

---

### set()

```ts
static set(variable: string, value: any): Promise<any>;
```

Sets the value of a shared variable.

#### Parameters

| Parameter  | Type     | Description        |
| ---------- | -------- | ------------------ |
| `variable` | `string` | The variable name. |
| `value`    | `any`    | The value to set.  |

#### Returns

`Promise`\<`any`\>

#### Example

```typescript
await SharedVariable.set("count", 10);
```

---

### setMultiple()

```ts
static setMultiple(variables: Record<string, any>, delta?: boolean): Promise<any>;
```

Sets multiple shared variable values.

#### Parameters

| Parameter   | Type                        | Default value | Description                              |
| ----------- | --------------------------- | ------------- | ---------------------------------------- |
| `variables` | `Record`\<`string`, `any`\> | `undefined`   | Object mapping variable names to values. |
| `delta`     | `boolean`                   | `false`       | If true, applies changes as a delta.     |

#### Returns

`Promise`\<`any`\>

#### Example

```typescript
await SharedVariable.setMultiple({ count: 3, title: "Ready" }, false);
```
