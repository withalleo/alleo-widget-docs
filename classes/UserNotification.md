[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / UserNotification

# Class: UserNotification

Manages toast-style notifications displayed to users in the Alleo interface.

Provides a simple API for showing informational messages, alerts, and custom notifications
with configurable timeouts, buttons, and styling. Notifications appear as overlay toasts
in the top-right corner of the interface by default.

## Example

```typescript
// Simple info notification
UserNotification.show('Operation completed successfully');

// Notification with title and image
UserNotification.show({
  title: 'Welcome',
  text: 'Thanks for using our widget!',
  image: 'https://example.com/icon.png'
});

// Never-closing notification with custom button
UserNotification.show('Important message', {
  neverTimeout: true,
  alternativeButton: {
    text: 'Learn More',
    onClick: () => window.open('https://example.com')
  }
});
```

## Extended by

- [`SimpleUserNotification`](SimpleUserNotification.md)

## Constructors

### Constructor

> **new UserNotification**(`notification`, `options?`): `UserNotification`

Creates a new UserNotification instance.

#### Parameters

##### notification

[`Notification`](../type-aliases/Notification.md)

Notification data.

##### options?

[`UserNotificationOptions`](../type-aliases/UserNotificationOptions.md) = `{}`

Notification options.

#### Returns

`UserNotification`

## Properties

### notification

> `protected` **notification**: [`Notification`](../type-aliases/Notification.md)

Notification data.

***

### options

> **options**: [`UserNotificationOptions`](../type-aliases/UserNotificationOptions.md) = `{}`

Notification options.

***

### DEBUG

> `static` **DEBUG**: `boolean` = `true`

Enable debug logging.

## Accessors

### isOpen

#### Get Signature

> **get** **isOpen**(): `boolean`

Returns true if the notification is open.

##### Returns

`boolean`

## Methods

### close()

> **close**(): `Promise`\<`void`\>

Closes the notification and removes it from the UI.

#### Returns

`Promise`\<`void`\>

***

### destroy()

> **destroy**(): `void`

Destroys the notification and cleans up resources.

#### Returns

`void`

***

### open()

> **open**(): `Promise`\<`void`\>

Opens the notification in the UI.

#### Returns

`Promise`\<`void`\>

***

### updateContent()

> **updateContent**(`notification`): `Promise`\<`void`\>

Updates the notification content.

#### Parameters

##### notification

[`Notification`](../type-aliases/Notification.md)

New notification data.

#### Returns

`Promise`\<`void`\>

***

### updateOptions()

> **updateOptions**(`options?`): `void`

Updates notification options and redraws content.

#### Parameters

##### options?

[`UserNotificationOptions`](../type-aliases/UserNotificationOptions.md) = `undefined`

New options to apply.

#### Returns

`void`

***

### error()

> `static` **error**(`message`, `actions?`, `throttle?`): `void`

Shows an error notification.

#### Parameters

##### message

`string`

Message to display.

##### actions?

`string`[] = `[]`

Optional actions.

##### throttle?

`boolean` = `true`

If true, throttles notifications.

#### Returns

`void`

***

### info()

> `static` **info**(`message`, `actions?`, `throttle?`): `void`

Shows an info notification.

#### Parameters

##### message

`string`

Message to display.

##### actions?

`string`[] = `[]`

Optional actions.

##### throttle?

`boolean` = `true`

If true, throttles notifications.

#### Returns

`void`

***

### warn()

> `static` **warn**(`message`, `actions?`, `throttle?`): `void`

Shows a warning notification.

#### Parameters

##### message

`string`

Message to display.

##### actions?

`string`[] = `[]`

Optional actions.

##### throttle?

`boolean` = `true`

If true, throttles notifications.

#### Returns

`void`
