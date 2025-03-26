[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / SimpleUserNotification

# Class: SimpleUserNotification

## Extends

- [`UserNotification`](UserNotification.md)

## Constructors

### Constructor

> **new SimpleUserNotification**(`notificationText`, `options`): `SimpleUserNotification`

#### Parameters

##### notificationText

`string`

##### options

[`UserNotificationOptions`](../type-aliases/UserNotificationOptions.md) = `undefined`

#### Returns

`SimpleUserNotification`

#### Overrides

[`UserNotification`](UserNotification.md).[`constructor`](UserNotification.md#constructor)

## Properties

### notification

> `protected` **notification**: [`Notification`](../type-aliases/Notification.md)

#### Inherited from

[`UserNotification`](UserNotification.md).[`notification`](UserNotification.md#notification)

***

### notificationText

> `protected` **notificationText**: `string`

***

### options

> `protected` **options**: [`UserNotificationOptions`](../type-aliases/UserNotificationOptions.md) = `{}`

#### Inherited from

[`UserNotification`](UserNotification.md).[`options`](UserNotification.md#options)

## Accessors

### isOpen

#### Get Signature

> **get** **isOpen**(): `boolean`

##### Returns

`boolean`

#### Inherited from

[`UserNotification`](UserNotification.md).[`isOpen`](UserNotification.md#isopen)

## Methods

### close()

> **close**(): `void`

#### Returns

`void`

#### Inherited from

[`UserNotification`](UserNotification.md).[`close`](UserNotification.md#close)

***

### destroy()

> **destroy**(): `void`

#### Returns

`void`

#### Inherited from

[`UserNotification`](UserNotification.md).[`destroy`](UserNotification.md#destroy)

***

### open()

> **open**(): `Promise`\<`void`\>

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`UserNotification`](UserNotification.md).[`open`](UserNotification.md#open)

***

### updateContent()

> **updateContent**(`notification`): `void`

#### Parameters

##### notification

[`Notification`](../type-aliases/Notification.md)

#### Returns

`void`

#### Inherited from

[`UserNotification`](UserNotification.md).[`updateContent`](UserNotification.md#updatecontent)

***

### updateText()

> **updateText**(`notificationText`): `void`

#### Parameters

##### notificationText

`string`

#### Returns

`void`

***

### error()

> `static` **error**(`message`, `actions`, `throttle`): `any`

#### Parameters

##### message

`string`

##### actions

`string`[] = `[]`

##### throttle

`boolean` = `true`

#### Returns

`any`

#### Inherited from

[`UserNotification`](UserNotification.md).[`error`](UserNotification.md#error)

***

### info()

> `static` **info**(`message`, `actions`, `throttle`): `any`

#### Parameters

##### message

`string`

##### actions

`string`[] = `[]`

##### throttle

`boolean` = `true`

#### Returns

`any`

#### Inherited from

[`UserNotification`](UserNotification.md).[`info`](UserNotification.md#info)

***

### warn()

> `static` **warn**(`message`, `actions`, `throttle`): `any`

#### Parameters

##### message

`string`

##### actions

`string`[] = `[]`

##### throttle

`boolean` = `true`

#### Returns

`any`

#### Inherited from

[`UserNotification`](UserNotification.md).[`warn`](UserNotification.md#warn)
