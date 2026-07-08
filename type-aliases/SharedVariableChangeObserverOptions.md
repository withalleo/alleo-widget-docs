[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / SharedVariableChangeObserverOptions

# Type Alias: SharedVariableChangeObserverOptions

```ts
type SharedVariableChangeObserverOptions = {
  runOnInit?: boolean;
  startSuspended?: boolean;
};
```

Configuration options for shared variable change observers.

## Properties

### runOnInit?

```ts
optional runOnInit?: boolean;
```

When true, executes the callback immediately with current value upon initialization.

---

### startSuspended?

```ts
optional startSuspended?: boolean;
```

When true, observer starts in suspended state and won't trigger callbacks until resumed.
