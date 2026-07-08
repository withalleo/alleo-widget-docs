[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / UserNotification

# Class: UserNotification

Manages toast-style notifications displayed to users in the Alleo interface.

Provides a simple API for showing informational messages, alerts, and custom notifications
with configurable timeouts, buttons, and styling. Notifications appear as overlay toasts
in the top-right corner of the interface by default.

## Example

```typescript
// Simple info notification
UserNotification.show("Operation completed successfully");

// Notification with title and image
UserNotification.show({
  title: "Welcome",
  text: "Thanks for using our widget!",
  image: "https://example.com/icon.png",
});

// Never-closing notification with custom button
UserNotification.show("Important message", {
  neverTimeout: true,
  alternativeButton: {
    text: "Learn More",
    onClick: () => window.open("https://example.com"),
  },
});
```

## Extended by

- [`SimpleUserNotification`](SimpleUserNotification.md)

## Constructors

### Constructor

```ts
new UserNotification(notification: Notification, options?: UserNotificationOptions): UserNotification;
```

Creates a new UserNotification instance.

#### Parameters

| Parameter      | Type                                                                    | Description           |
| -------------- | ----------------------------------------------------------------------- | --------------------- |
| `notification` | [`Notification`](../type-aliases/Notification.md)                       | Notification data.    |
| `options`      | [`UserNotificationOptions`](../type-aliases/UserNotificationOptions.md) | Notification options. |

#### Returns

`UserNotification`

## Properties

### notification

```ts
protected notification: Notification;
```

Notification data.

---

### options

```ts
options: UserNotificationOptions = {};
```

Notification options.

---

### DEBUG

```ts
static DEBUG: boolean = true;
```

Enable debug logging.

## Accessors

### isOpen

#### Get Signature

```ts
get isOpen(): boolean;
```

Returns true if the notification is open.

##### Returns

`boolean`

## Methods

### close()

```ts
close(): Promise<void>;
```

Closes the notification and removes it from the UI.

#### Returns

`Promise`\<`void`\>

---

### destroy()

```ts
destroy(): void;
```

Destroys the notification and cleans up resources.

#### Returns

`void`

---

### open()

```ts
open(): Promise<void>;
```

Opens the notification in the UI.

#### Returns

`Promise`\<`void`\>

---

### updateContent()

```ts
updateContent(notification: Notification): Promise<void>;
```

Updates the notification content.

#### Parameters

| Parameter      | Type                                              | Description            |
| -------------- | ------------------------------------------------- | ---------------------- |
| `notification` | [`Notification`](../type-aliases/Notification.md) | New notification data. |

#### Returns

`Promise`\<`void`\>

---

### updateOptions()

```ts
updateOptions(options?: UserNotificationOptions): void;
```

Updates notification options and redraws content.

#### Parameters

| Parameter | Type                                                                    | Default value | Description           |
| --------- | ----------------------------------------------------------------------- | ------------- | --------------------- |
| `options` | [`UserNotificationOptions`](../type-aliases/UserNotificationOptions.md) | `undefined`   | New options to apply. |

#### Returns

`void`

---

### error()

```ts
static error(
   message: string,
   actions?: string[],
   throttle?: boolean): void;
```

Shows an error notification.

#### Parameters

| Parameter  | Type       | Default value | Description                       |
| ---------- | ---------- | ------------- | --------------------------------- |
| `message`  | `string`   | `undefined`   | Message to display.               |
| `actions`  | `string`[] | `[]`          | Optional actions.                 |
| `throttle` | `boolean`  | `true`        | If true, throttles notifications. |

#### Returns

`void`

---

### info()

```ts
static info(
   message: string,
   actions?: string[],
   throttle?: boolean): void;
```

Shows an info notification.

#### Parameters

| Parameter  | Type       | Default value | Description                       |
| ---------- | ---------- | ------------- | --------------------------------- |
| `message`  | `string`   | `undefined`   | Message to display.               |
| `actions`  | `string`[] | `[]`          | Optional actions.                 |
| `throttle` | `boolean`  | `true`        | If true, throttles notifications. |

#### Returns

`void`

---

### warn()

```ts
static warn(
   message: string,
   actions?: string[],
   throttle?: boolean): void;
```

Shows a warning notification.

#### Parameters

| Parameter  | Type       | Default value | Description                       |
| ---------- | ---------- | ------------- | --------------------------------- |
| `message`  | `string`   | `undefined`   | Message to display.               |
| `actions`  | `string`[] | `[]`          | Optional actions.                 |
| `throttle` | `boolean`  | `true`        | If true, throttles notifications. |

#### Returns

`void`
