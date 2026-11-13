[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / ActionFlowState

# Class: ActionFlowState

Helper for registering the state fields a widget exposes to the action flow system.

You can register one or multiple fields for a widget that is published with the value calculated when
the action flow reads the widget state.

## Constructors

### Constructor

```ts
new ActionFlowState(): ActionFlowState;
```

#### Returns

`ActionFlowState`

## Methods

### get()

```ts
static get(): ActionFlowStateFields[];
```

Returns the current state of the action flow, including all registered fields.

#### Returns

[`ActionFlowStateFields`](../type-aliases/ActionFlowStateFields.md)[]

An object mapping field IDs to their current values. *

---

### isSupported()

```ts
static isSupported(): boolean;
```

#### Returns

`boolean`

---

### set()

```ts
static set(settings: ActionFlowStateFields[]): void;
```

Registers the given fields as the widget's action flow state.

Replaces `haptic.actionFlowStateFields` and `haptic.getActionFlowState` with values derived
from `settings`, so every call to `getActionFlowState` re-evaluates the provided value functions.
Value functions may be asynchronous; they are evaluated in parallel and awaited.

#### Parameters

| Parameter  | Type                                                                  | Description                                                                   |
| ---------- | --------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| `settings` | [`ActionFlowStateFields`](../type-aliases/ActionFlowStateFields.md)[] | Fields to expose. Entries without an `id` get one derived from their `label`. |

#### Returns

`void`
