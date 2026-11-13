[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / BackendProxyHelperSettings

# Type Alias: BackendProxyHelperSettings

```ts
type BackendProxyHelperSettings = {
    backendSchema?: Prettify<Parameters<IWidgetSecretsProxy['addSecret']>[1]['configurations'][0]>
    backendSchemas?: Prettify<Parameters<IWidgetSecretsProxy['addSecret']>[1]['configurations']>
    externalSecretProvider?: Prettify<Parameters<IWidgetSecretsProxy['addSecret']>[1]['externalSecretProvider']>
    hideStatusHeadline?: boolean
    onlyWarnOnMissingKey?: boolean
}
```

## Properties

### backendSchema?

```ts
backendSchema?: Prettify<Parameters<IWidgetSecretsProxy["addSecret"]>[1]["configurations"][0]>;
```

---

### backendSchemas?

```ts
backendSchemas?: Prettify<Parameters<IWidgetSecretsProxy["addSecret"]>[1]["configurations"]>;
```

---

### externalSecretProvider?

```ts
externalSecretProvider?: Prettify<Parameters<IWidgetSecretsProxy["addSecret"]>[1]["externalSecretProvider"]>;
```

---

### hideStatusHeadline?

```ts
hideStatusHeadline?: boolean;
```

---

### onlyWarnOnMissingKey?

```ts
onlyWarnOnMissingKey?: boolean;
```
