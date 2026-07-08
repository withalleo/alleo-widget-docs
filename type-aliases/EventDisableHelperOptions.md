[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / EventDisableHelperOptions

# Type Alias: EventDisableHelperOptions

```ts
type EventDisableHelperOptions = {
  autoManage?: boolean;
  callback?: (e: Event) => void;
};
```

Options for the EventDisableHelper.

## Properties

### autoManage?

```ts
optional autoManage?: boolean;
```

If true, the EventDisableHelper will automatically manage the events based on the interactibility of the widget (default: true).

---

### callback?

```ts
optional callback?: (e: Event) => void;
```

A callback that will be called when the event is cancelled. (So it can be used to do something else as well)

#### Parameters

| Parameter | Type    |
| --------- | ------- |
| `e`       | `Event` |

#### Returns

`void`
