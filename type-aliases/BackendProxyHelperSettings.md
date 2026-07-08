[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / BackendProxyHelperSettings

# Type Alias: BackendProxyHelperSettings

```ts
type BackendProxyHelperSettings = {
  backendSchema?: Prettify<
    Parameters<IWidgetSecretsProxy["addSecret"]>[1]["configurations"][0]
  >;
  hideStatusHeadline?: boolean;
  onlyWarnOnMissingKey?: boolean;
};
```

## Properties

### backendSchema?

```ts
optional backendSchema?: Prettify<Parameters<IWidgetSecretsProxy["addSecret"]>[1]["configurations"][0]>;
```

---

### hideStatusHeadline?

```ts
optional hideStatusHeadline?: boolean;
```

---

### onlyWarnOnMissingKey?

```ts
optional onlyWarnOnMissingKey?: boolean;
```
