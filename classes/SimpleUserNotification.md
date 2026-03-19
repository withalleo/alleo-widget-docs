[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / SimpleUserNotification

# Class: SimpleUserNotification

Simple notification class for displaying info messages.

## Extends

- [`UserNotification`](UserNotification.md)

## Constructors

### Constructor

> **new SimpleUserNotification**(`notificationText`, `options?`): `SimpleUserNotification`

Creates a SimpleUserNotification instance.

#### Parameters

##### notificationText

`string`

The message to display.

##### options?

[`UserNotificationOptions`](../type-aliases/UserNotificationOptions.md) = `undefined`

Notification options.

#### Returns

`SimpleUserNotification`

#### Overrides

[`UserNotification`](UserNotification.md).[`constructor`](UserNotification.md#constructor)

## Properties

### notification

> `protected` **notification**: [`Notification`](../type-aliases/Notification.md)

Notification data.

#### Inherited from

[`UserNotification`](UserNotification.md).[`notification`](UserNotification.md#notification)

***

### notificationText

> `protected` **notificationText**: `string`

The message to display.

***

### options

> **options**: [`UserNotificationOptions`](../type-aliases/UserNotificationOptions.md) = `{}`

Notification options.

#### Inherited from

[`UserNotification`](UserNotification.md).[`options`](UserNotification.md#options)

***

### DEBUG

> `static` **DEBUG**: `boolean` = `true`

Enable debug logging.

#### Inherited from

[`UserNotification`](UserNotification.md).[`DEBUG`](UserNotification.md#debug)

## Accessors

### isOpen

#### Get Signature

> **get** **isOpen**(): `boolean`

Returns true if the notification is open.

##### Returns

`boolean`

#### Inherited from

[`UserNotification`](UserNotification.md).[`isOpen`](UserNotification.md#isopen)

## Methods

### close()

> **close**(): `Promise`\<`void`\>

Closes the notification and removes it from the UI.

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`UserNotification`](UserNotification.md).[`close`](UserNotification.md#close)

***

### destroy()

> **destroy**(): `void`

Destroys the notification and cleans up resources.

#### Returns

`void`

#### Inherited from

[`UserNotification`](UserNotification.md).[`destroy`](UserNotification.md#destroy)

***

### open()

> **open**(): `Promise`\<`void`\>

Opens the notification in the UI.

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`UserNotification`](UserNotification.md).[`open`](UserNotification.md#open)

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

#### Inherited from

[`UserNotification`](UserNotification.md).[`updateContent`](UserNotification.md#updatecontent)

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

#### Inherited from

[`UserNotification`](UserNotification.md).[`updateOptions`](UserNotification.md#updateoptions)

***

### updateText()

> **updateText**(`notificationText`): `void`

Updates the notification text.

#### Parameters

##### notificationText

`string`

New message to display.

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

#### Inherited from

[`UserNotification`](UserNotification.md).[`error`](UserNotification.md#error)

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

#### Inherited from

[`UserNotification`](UserNotification.md).[`info`](UserNotification.md#info)

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

#### Inherited from

[`UserNotification`](UserNotification.md).[`warn`](UserNotification.md#warn)
