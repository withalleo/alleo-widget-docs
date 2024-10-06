[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / IWidgetEntrypoint

# Interface: IWidgetEntrypoint

## Properties

### apiVersion

> **apiVersion**: [`WidgetApiVersion`](../enumerations/WidgetApiVersion.md)

Alleo API Version to be used

#### Default

```ts
1
```

***

### entrypoint

> **entrypoint**: `string`

Url to html entrypoint

***

### priority?

> `optional` **priority**: `number`

Entrypoint priority, if there are any overlaps in the [ranges](IWidgetEntrypoint.md#range)
you define, the one with the highest priority will be used. If there are
overlaps but there is no priority defined the first match will be selected
using the [entrypoints](IWidgetBaseManifest.md#entrypoints) list order.

***

### range

> **range**: `string`

[Range](../type-aliases/SemverRange.md) where this entrypoint is valid
