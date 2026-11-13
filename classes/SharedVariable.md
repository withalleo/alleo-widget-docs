[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / SharedVariable

# Class: SharedVariable

Read, write and observe shared variables: the widget data that is saved with the board and synced to every participant.

In widgets extending `AlleoWidget`, prefer `this.shared.<key>` for plain reads and writes: it is typed from your
`defaultSharedVariables`. Use `SharedVariable` for arrays, multi-key writes, untyped keys, and observers.

Things worth knowing:

- **Names are literal keys.** `'settings.color'` is its own variable; it never reads or writes inside `settings`.
  To change a nested value, write the whole object.
- **Reads return the live stored value.** Mutating it changes it locally without notifying anyone, and the change is
  saved silently with the next write of any variable. Copy before changing (`structuredClone` or spread), then write the copy.
- **Writes apply locally right away**, before the returned promise resolves. Other participants get them shortly after.
- **`undefined` deletes a variable, `null` doesn't.** `undefined` (or [SharedVariable.delete](#delete)) removes the key
  from the saved data; `null` is stored as a value and the key stays forever. Deleted and never-written variables
  read `undefined`, `null` ones read `null`. Use `?? default` when reading.
- The platform documents a limit of 10 writes per second; batch related writes with [setMultiple](#setmultiple).
- **Writes over the server limits throw** a [SharedVariableLimitError](SharedVariableLimitError.md) before anything is written: values
  nested deeper than [SharedVariable.limits](#limits)`.maxDepth` levels, or writes larger than `.maxPayloadBytes` as JSON.
  The server rejects deeper values and blocks every later write until the key is cleared, and it closes the
  connection on oversized ones, which reloads the board. `this.shared.<key>` writes are not checked.
- **Only JSON-safe values and `Date`s can be stored**: strings, finite numbers, booleans, `null`, valid `Date`s,
  arrays and plain objects of these. Anything else (`NaN`, `Infinity`, invalid `Date`s, `Map`, `Set`, class
  instances, functions, `bigint`, `symbol`) throws a [SharedVariableLimitError](SharedVariableLimitError.md) with `limit: 'type'`.
  Store dates as epoch ms when you can: a `Date` and a full ISO date-time string both read back as a `Date` after a reload.

## Examples

```typescript
class CounterWidget extends AlleoWidget<typeof CounterWidget.defaultSharedVariables> {
    private static defaultSharedVariables = {
        count: 0,
        title: 'Counter',
    }

    constructor() {
        super(CounterWidget.defaultSharedVariables)

        // Read and write shared state through this.shared
        this.shared.count = (this.shared.count ?? 0) + 1
        const currentTitle = this.shared.title
        console.log(currentTitle, this.shared.count)
    }
}
```

```typescript
// simple values
await SharedVariable.set('title', 'Votes')
SharedVariable.get('title') // 'Votes'

// arrays: append, or replace with a modified copy
await SharedVariable.append('votes', ['alice'])
await SharedVariable.set(
    'votes',
    SharedVariable.get('votes').filter((name) => name !== 'alice'),
)

// objects: write the whole object, never a dotted name
await SharedVariable.set('settings', { ...SharedVariable.get('settings'), color: 'red' })

// several values in one write
await SharedVariable.setMultiple({ title: 'Votes', votes: [] })

// delete
await SharedVariable.delete('title')
```

```typescript
class CounterWidget extends AlleoWidget<typeof CounterWidget.defaultSharedVariables> {
    private static defaultSharedVariables = {
        count: 0,
        title: 'Counter',
    }

    private counterObserver?: InstanceType<typeof SharedVariable.observer>

    constructor() {
        super(CounterWidget.defaultSharedVariables)

        // react to local and remote updates, and render the initial state
        this.counterObserver = new SharedVariable.observer(['count', 'title'], (data) => this.render(data.count, data.title), {
            runOnInit: true,
        })
    }

    private increment(): void {
        this.shared.count = this.shared.count + 1
    }

    public override destroy(): void {
        this.counterObserver?.destroy()
        super.destroy()
    }
}
```

## Constructors

### Constructor

```ts
new SharedVariable(): SharedVariable;
```

#### Returns

`SharedVariable`

## Properties

### limits

```ts
readonly static limits: {
  maxDepth: 25;
  maxPayloadBytes: number;
};
```

Server limits checked before every [set](#set), [append](#append) and [setMultiple](#setmultiple) call.

- `maxDepth`: nesting levels of a value (`{}` / `[]` = 1 level). Measured limit: 27 accepted, 28 rejected. Recommended: `25`
- `maxPayloadBytes`: UTF-8 size of the written value(s) as JSON. The hub drops the connection above 4 MiB per
  message, and the message can carry other payload. Recommended: `3.5 * 1024 * 1024`

#### maxDepth

```ts
readonly maxDepth: 25 = 25;
```

#### maxPayloadBytes

```ts
readonly maxPayloadBytes: number;
```

---

### observer

```ts
static observer: typeof SharedVariableHelper = SharedVariableHelper;
```

The observer class: `new SharedVariable.observer(variables, callback, options?)`.
See SharedVariableHelper for the full behavior.

#### Example

```typescript
const observer = new SharedVariable.observer(['count', 'title'], (data, changed) => {
    console.log('changed:', changed, 'values:', data)
})

observer.destroy()
```

## Methods

### append()

```ts
static append(variable: string, value: unknown[]): Promise<any>;
```

Adds items to the end of a shared array. Concurrent appends from several participants are all kept, which
makes it the right choice for lists like chat messages or votes.

- Duplicates are not removed: appending an existing item adds it again.
- A missing, deleted or `null` variable is created with the given items.
- A single non-array value is appended as one item.
- `null`, `undefined` and `[]` do nothing (no write, no observer callback).
- If the variable holds a non-array value, nothing is written and a `SharedVariableLimitError` (`limit: 'type'`)
  is thrown. Replace it with [set](#set) first.

To remove or reorder items, write the whole array with [set](#set).

#### Parameters

| Parameter  | Type        | Description                                              |
| ---------- | ----------- | -------------------------------------------------------- |
| `variable` | `string`    | The variable name, used as a literal key (no dot paths). |
| `value`    | `unknown`[] | The items to append.                                     |

#### Returns

`Promise`\<`any`\>

A promise that resolves once the write is sent, or right away if there is nothing to append.

#### Throws

If the variable holds a non-array value, a value is nested deeper than `limits.maxDepth`, the write is larger than `limits.maxPayloadBytes`, or it holds an unsupported value (synchronously, nothing is written).

#### Example

```typescript
await SharedVariable.append('votes', ['alice']) // ['alice']
await SharedVariable.append('votes', ['bob', 'carol']) // ['alice', 'bob', 'carol']
await SharedVariable.append('votes', ['alice']) // ['alice', 'bob', 'carol', 'alice']

// objects are appended as items, never merged with existing ones
await SharedVariable.append('messages', [{ id: 1, text: 'Hi' }])

// removing an item: write a filtered copy
await SharedVariable.set(
    'votes',
    SharedVariable.get('votes').filter((name) => name !== 'bob'),
)
```

---

### delete()

```ts
static delete(variableName: string): Promise<any>;
```

Deletes a shared variable: the key is removed from the saved data.

- Afterwards it reads `undefined`, like a never-written variable. Locally the key stays (with the value
  `undefined`) until the board is reloaded.
- Same as [set](#set) with `undefined`. Unlike `null`, which is stored as a value and keeps the key forever.

#### Parameters

| Parameter      | Type     | Description                                              |
| -------------- | -------- | -------------------------------------------------------- |
| `variableName` | `string` | The variable name, used as a literal key (no dot paths). |

#### Returns

`Promise`\<`any`\>

A promise that resolves once the write is sent.

#### Example

```typescript
await SharedVariable.delete('settings')
SharedVariable.get('settings') // undefined
```

---

### get()

```ts
static get(variable: string): any;
```

Reads a shared variable.

Returns the **live stored instance** for arrays and objects. Don't mutate it: observers aren't notified, and the
change is saved silently with the next write of any variable. Copy it first, then write the copy back with [set](#set).

#### Parameters

| Parameter  | Type     | Description                                              |
| ---------- | -------- | -------------------------------------------------------- |
| `variable` | `string` | The variable name, used as a literal key (no dot paths). |

#### Returns

`any`

The stored value; `undefined` if never written or deleted, `null` if set to `null`.

#### Example

```typescript
const count: number = SharedVariable.get('count') ?? 0

// changing an array or object: copy, change, write back
const todos = [...(SharedVariable.get('todos') ?? [])]
todos[0] = { ...todos[0], done: true }
await SharedVariable.set('todos', todos)

// dot paths are NOT resolved
SharedVariable.get('settings.color') // reads a variable literally named 'settings.color'
SharedVariable.get('settings')?.color // reads color inside settings
```

---

### getMultiple()

```ts
static getMultiple(variables: string[]): Record<string, any>;
```

Reads several shared variables at once.

Like [get](#get), arrays and objects are the live stored instances: copy before changing them.

#### Parameters

| Parameter   | Type       | Description                                              |
| ----------- | ---------- | -------------------------------------------------------- |
| `variables` | `string`[] | The variable names, used as literal keys (no dot paths). |

#### Returns

`Record`\<`string`, `any`\>

An object mapping each name to its value (`undefined` for missing or deleted ones, `null` for ones set to `null`).

#### Example

```typescript
const { count, title } = SharedVariable.getMultiple(['count', 'title'])
```

---

### merge()

```ts
static merge(variable: string, value: unknown): Promise<any>;
```

Merges an object into a shared variable. Arrays are appended to, objects are deep merged (keys can be added or changed, but not removed), anything else is replaced.

#### Parameters

| Parameter  | Type      | Description                                                                                                                                                                                                                                         |
| ---------- | --------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `variable` | `string`  | The variable name, used as a literal key (no dot paths).                                                                                                                                                                                            |
| `value`    | `unknown` | The value to merge: a string, finite number, boolean, valid `Date`, or an array or plain object of these (nested `null` is allowed). A top-level `null` or `undefined` is a no-op (nothing is written); use [delete](#delete) to remove a variable. |

#### Returns

`Promise`\<`any`\>

A promise that resolves once the write is sent.

#### Throws

If a value is nested deeper than `limits.maxDepth`, the write is larger than `limits.maxPayloadBytes`, or it holds an unsupported value (synchronously, nothing is written).

#### Example

````typescript
// stored: { count: 1, votes: ['alice'], settings: { color: 'red', size: 2 } }

await SharedVariable.merge('settings', { size: 3, font: 'Arial' })
// stored: { count: 1, votes: ['alice'], settings: { color: 'red', size: 3, font: 'Arial' } }

***

### set()

```ts
static set(variable: string, value: any): Promise<any>;
````

Replaces the value of a shared variable: afterwards it holds exactly `value`.
Arrays are not appended to and objects are not merged (use [append](#append) or [setMultiple](#setmultiple) with `delta` for that).

Behind the scenes it sends the write as a merge (`delta=true`) whenever that gives the same result, so concurrent
changes by other participants (e.g. a new key added meanwhile) are kept instead of overwritten. Otherwise it replaces.

Good to know:

- `undefined` deletes the variable (see [delete](#delete)): the key is removed from the saved data.
- `null` is stored as a value: the variable reads `null` and the key stays, also after a reload.
  Use `undefined` (or [delete](#delete)) to remove a variable for good.
- The new value is readable synchronously; the promise resolves (with `undefined`) once the write is sent.
- Writing back the live instance from [get](#get) after mutating it works, but prefer writing a copy.

#### Parameters

| Parameter  | Type     | Description                                                                                                                       |
| ---------- | -------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `variable` | `string` | The variable name, used as a literal key (no dot paths).                                                                          |
| `value`    | `any`    | The new value: a string, finite number, boolean, `null`, valid `Date`, or an array or plain object of these; `undefined` deletes. |

#### Returns

`Promise`\<`any`\>

A promise that resolves once the write is sent.

#### Throws

If a value is nested deeper than `limits.maxDepth`, the write is larger than `limits.maxPayloadBytes`, or it holds an unsupported value (synchronously, nothing is written).

#### Example

```typescript
await SharedVariable.set('count', 10)
await SharedVariable.set('title', 'Votes')

// arrays: the result is exactly the given array
await SharedVariable.set('votes', ['alice', 'bob'])
await SharedVariable.set('votes', ['bob']) // 'alice' removed

// objects: keys missing from the new object are removed
await SharedVariable.set('settings', { color: 'red', size: 2 })
await SharedVariable.set('settings', { color: 'blue' }) // size removed

// change one property: spread the current value
await SharedVariable.set('settings', { ...SharedVariable.get('settings'), size: 3 })

// delete: the key is removed
await SharedVariable.set('settings', undefined) // same as SharedVariable.delete('settings')

// null is a value: reads null, the key stays
await SharedVariable.set('settings', null)
```

---

### setMultiple()

```ts
static setMultiple(variables: Record<string, any>, delta?: boolean): Promise<any>;
```

Writes several shared variables in one call: one write, one observer callback, one step against the rate limit.
Variables not listed are left untouched.

- `delta = false` (default): each listed variable is **replaced**, like [set](#set) without the merge optimization.
- `delta = true`: each listed variable is **merged**: arrays are appended to, objects are deep merged
  (keys can be added or changed, never removed), anything else is replaced.

With `delta = false`, `undefined` deletes a variable (the key is removed from the saved data) and `null` is
stored as a value (the key stays). With `delta = true`, `undefined` is ignored and `null` is stored, or appended
as an item onto an array; nothing can be deleted.

#### Parameters

| Parameter   | Type                        | Default value | Description                                                                     |
| ----------- | --------------------------- | ------------- | ------------------------------------------------------------------------------- |
| `variables` | `Record`\<`string`, `any`\> | `undefined`   | Object mapping variable names (literal keys, no dot paths) to their new values. |
| `delta?`    | `boolean`                   | `false`       | `false` to replace (default), `true` to merge.                                  |

#### Returns

`Promise`\<`any`\>

A promise that resolves once the write is sent.

#### Throws

If a value is nested deeper than `limits.maxDepth`, the write is larger than `limits.maxPayloadBytes`, or it holds an unsupported value (synchronously, nothing is written).

#### Example

```typescript
// stored: { count: 1, votes: ['alice'], settings: { color: 'red', size: 2 } }

await SharedVariable.setMultiple({ count: 0, votes: [] })
// replace: count 0, votes [], settings unchanged

await SharedVariable.setMultiple({ votes: ['bob'], settings: { size: 3 } }, true)
// merge: votes [..., 'bob'], settings { color: 'red', size: 3 }

await SharedVariable.setMultiple({ title: undefined, settings: undefined })
// delete both (both read undefined)

await SharedVariable.setMultiple({ title: null })
// title reads null, the key stays
```
