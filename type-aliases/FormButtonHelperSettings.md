[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / FormButtonHelperSettings

# Type Alias: FormButtonHelperSettings

```ts
type FormButtonHelperSettings = {
  align?: "left" | "right" | "center" | "justify" | "start" | "end";
  callbackOnFormOpened?: (button: HTMLElement) => void;
  displayInline?: boolean;
  doNotStartFormTimer?: boolean;
  doNotStartInitialTimer?: boolean;
  formlyKey?: string;
  id?: string;
  interval?: number;
  loadingPlaceholder?: string;
  primary?: boolean;
  singleUse?: boolean;
  timeout?: number;
};
```

Settings for [FormButtonHelper](../classes/FormButtonHelper.md).

Note: this file is TypeScript-first. The canonical shape is the exported
FormButtonHelperSettings type below.

## Properties

### align?

```ts
optional align?: "left" | "right" | "center" | "justify" | "start" | "end";
```

---

### callbackOnFormOpened?

```ts
optional callbackOnFormOpened?: (button: HTMLElement) => void;
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
optional displayInline?: boolean;
```

---

### doNotStartFormTimer?

```ts
optional doNotStartFormTimer?: boolean;
```

---

### doNotStartInitialTimer?

```ts
optional doNotStartInitialTimer?: boolean;
```

---

### formlyKey?

```ts
optional formlyKey?: string;
```

---

### id?

```ts
optional id?: string;
```

---

### interval?

```ts
optional interval?: number;
```

---

### loadingPlaceholder?

```ts
optional loadingPlaceholder?: string;
```

---

### primary?

```ts
optional primary?: boolean;
```

---

### singleUse?

```ts
optional singleUse?: boolean;
```

---

### timeout?

```ts
optional timeout?: number;
```
