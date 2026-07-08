[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / SimpleUserNotification

# Class: SimpleUserNotification

Simple notification class for displaying info messages.

## Extends

- [`UserNotification`](UserNotification.md)

## Constructors

### Constructor

```ts
new SimpleUserNotification(notificationText: string, options?: UserNotificationOptions): SimpleUserNotification;
```

Creates a SimpleUserNotification instance.

#### Parameters

| Parameter          | Type                                                                    | Default value | Description             |
| ------------------ | ----------------------------------------------------------------------- | ------------- | ----------------------- |
| `notificationText` | `string`                                                                | `undefined`   | The message to display. |
| `options`          | [`UserNotificationOptions`](../type-aliases/UserNotificationOptions.md) | `undefined`   | Notification options.   |

#### Returns

`SimpleUserNotification`

#### Overrides

[`UserNotification`](UserNotification.md).[`constructor`](UserNotification.md#constructor)

## Properties

### notification

```ts
protected notification: Notification;
```

Notification data.

#### Inherited from

[`UserNotification`](UserNotification.md).[`notification`](UserNotification.md#notification)

---

### notificationText

```ts
protected notificationText: string;
```

The message to display.

---

### options

```ts
options: UserNotificationOptions = {};
```

Notification options.

#### Inherited from

[`UserNotification`](UserNotification.md).[`options`](UserNotification.md#options)

---

### DEBUG

```ts
static DEBUG: boolean = true;
```

Enable debug logging.

#### Inherited from

[`UserNotification`](UserNotification.md).[`DEBUG`](UserNotification.md#debug)

## Accessors

### isOpen

#### Get Signature

```ts
get isOpen(): boolean;
```

Returns true if the notification is open.

##### Returns

`boolean`

#### Inherited from

[`UserNotification`](UserNotification.md).[`isOpen`](UserNotification.md#isopen)

## Methods

### close()

```ts
close(): Promise<void>;
```

Closes the notification and removes it from the UI.

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`UserNotification`](UserNotification.md).[`close`](UserNotification.md#close)

---

### destroy()

```ts
destroy(): void;
```

Destroys the notification and cleans up resources.

#### Returns

`void`

#### Inherited from

[`UserNotification`](UserNotification.md).[`destroy`](UserNotification.md#destroy)

---

### open()

```ts
open(): Promise<void>;
```

Opens the notification in the UI.

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`UserNotification`](UserNotification.md).[`open`](UserNotification.md#open)

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

#### Inherited from

[`UserNotification`](UserNotification.md).[`updateContent`](UserNotification.md#updatecontent)

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

#### Inherited from

[`UserNotification`](UserNotification.md).[`updateOptions`](UserNotification.md#updateoptions)

---

### updateText()

```ts
updateText(notificationText: string): void;
```

Updates the notification text.

#### Parameters

| Parameter          | Type     | Description             |
| ------------------ | -------- | ----------------------- |
| `notificationText` | `string` | New message to display. |

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

#### Inherited from

[`UserNotification`](UserNotification.md).[`error`](UserNotification.md#error)

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

#### Inherited from

[`UserNotification`](UserNotification.md).[`info`](UserNotification.md#info)

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

#### Inherited from

[`UserNotification`](UserNotification.md).[`warn`](UserNotification.md#warn)
