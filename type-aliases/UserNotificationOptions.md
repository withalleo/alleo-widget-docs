[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / UserNotificationOptions

# Type Alias: UserNotificationOptions

```ts
type UserNotificationOptions = {
    alternativeButton?: {
        onClick: () => void
        text: string
    }
    autoOpen?: boolean
    hideButton?: boolean
    neverTimeout?: boolean
    timeout?: number
}
```

Configuration options for controlling notification behavior and appearance.

## Properties

### alternativeButton?

```ts
alternativeButton?: {
  onClick: () => void;
  text: string;
};
```

Custom action button configuration.

#### onClick

```ts
onClick: () => void;
```

##### Returns

`void`

#### text

```ts
text: string
```

---

### autoOpen?

```ts
autoOpen?: boolean;
```

When true, notification opens immediately upon creation.

---

### hideButton?

```ts
hideButton?: boolean;
```

When true, hides the default dismiss button.

---

### neverTimeout?

```ts
neverTimeout?: boolean;
```

When true, notification stays visible until manually dismissed.

---

### timeout?

```ts
timeout?: number;
```

Duration in milliseconds before the notification automatically closes (default varies by type).
