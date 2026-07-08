[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / Notification

# Type Alias: Notification

```ts
type Notification = {
  image?: string;
  text: string;
  title?: string;
  type?: string;
};
```

Configuration object for the content and appearance of a notification.

## Properties

### image?

```ts
optional image?: string;
```

Optional image URL displayed alongside the notification.

---

### text

```ts
text: string;
```

The main notification message (supports HTML content).

---

### title?

```ts
optional title?: string;
```

Optional title displayed above the message text.

---

### type?

```ts
optional type?: string;
```

The notification type determining visual style (e.g., 'info').
