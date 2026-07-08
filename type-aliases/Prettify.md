[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / Prettify

# Type Alias: Prettify\<T\>

```ts
type Prettify<T> = { [K in keyof T]: T[K] } & {};
```

Prettifies a TypeScript type by flattening its structure for better readability.

## Type Parameters

| Type Parameter |
| -------------- |
| `T`            |
