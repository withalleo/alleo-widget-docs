[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / UserNotificationOptions

# Type Alias: UserNotificationOptions

```ts
type UserNotificationOptions = {
  alternativeButton?: {
    onClick: () => void;
    text: string;
  };
  autoOpen?: boolean;
  hideButton?: boolean;
  neverTimeout?: boolean;
  timeout?: number;
};
```

Configuration options for controlling notification behavior and appearance.

## Properties

### alternativeButton?

```ts
optional alternativeButton?: {
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
text: string;
```

---

### autoOpen?

```ts
optional autoOpen?: boolean;
```

When true, notification opens immediately upon creation.

---

### hideButton?

```ts
optional hideButton?: boolean;
```

When true, hides the default dismiss button.

---

### neverTimeout?

```ts
optional neverTimeout?: boolean;
```

When true, notification stays visible until manually dismissed.

---

### timeout?

```ts
optional timeout?: number;
```

Duration in milliseconds before the notification automatically closes (default varies by type).
