[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / FormButtonHelperSettings

# Type Alias: FormButtonHelperSettings

```ts
type FormButtonHelperSettings = {
    align?: 'left' | 'right' | 'center' | 'justify' | 'start' | 'end'
    callbackOnFormOpened?: (button: HTMLElement) => void
    displayInline?: boolean
    doNotStartFormTimer?: boolean
    doNotStartInitialTimer?: boolean
    formlyKey?: string
    id?: string
    interval?: number
    loadingPlaceholder?: string
    primary?: boolean
    singleUse?: boolean
    timeout?: number
}
```

Settings for [FormButtonHelper](../classes/FormButtonHelper.md).

Note: this file is TypeScript-first. The canonical shape is the exported
FormButtonHelperSettings type below.

## Properties

### align?

```ts
align?: "left" | "right" | "center" | "justify" | "start" | "end";
```

---

### callbackOnFormOpened?

```ts
callbackOnFormOpened?: (button: HTMLElement) => void;
```

#### Parameters

| Parameter | Type          |
| --------- | ------------- |
| `button`  | `HTMLElement` |

#### Returns

`void`

---

### displayInline?

```ts
displayInline?: boolean;
```

---

### doNotStartFormTimer?

```ts
doNotStartFormTimer?: boolean;
```

---

### doNotStartInitialTimer?

```ts
doNotStartInitialTimer?: boolean;
```

---

### formlyKey?

```ts
formlyKey?: string;
```

---

### id?

```ts
id?: string;
```

---

### interval?

```ts
interval?: number;
```

---

### loadingPlaceholder?

```ts
loadingPlaceholder?: string;
```

---

### primary?

```ts
primary?: boolean;
```

---

### singleUse?

```ts
singleUse?: boolean;
```

---

### timeout?

```ts
timeout?: number;
```
