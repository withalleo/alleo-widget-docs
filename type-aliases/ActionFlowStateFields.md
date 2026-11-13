[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / ActionFlowStateFields

# Type Alias: ActionFlowStateFields

```ts
type ActionFlowStateFields = ActionSocketDataConfig & {
    id?: string
    label: string
    valueFunction: () => unknown | Promise<unknown>
}
```

Describes a single state field exposed to the action flow system,
combining the socket data type with the function that provides its current value.

## Type Declaration

### id?

```ts
id?: string;
```

Stable key of the field. When omitted, a hash of ActionFlowStateFields.label is used.

### label

```ts
label: string
```

Human-readable name shown for this field in the action flow editor.

### valueFunction

```ts
valueFunction: () => unknown | (Promise<unknown>)
```

Returns the current value of the field, called every time the action flow reads the widget state.
Maybe asynchronous; the returned promise is awaited before the state is published.

#### Returns

`unknown` \| `Promise`\<`unknown`\>
