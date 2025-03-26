[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / UserNotification

# Class: UserNotification

## Extended by

- [`SimpleUserNotification`](SimpleUserNotification.md)

## Constructors

### Constructor

> **new UserNotification**(`notification`, `options`): `UserNotification`

#### Parameters

##### notification

[`Notification`](../type-aliases/Notification.md)

##### options

[`UserNotificationOptions`](../type-aliases/UserNotificationOptions.md) = `{}`

#### Returns

`UserNotification`

## Properties

### notification

> `protected` **notification**: [`Notification`](../type-aliases/Notification.md)

***

### options

> `protected` **options**: [`UserNotificationOptions`](../type-aliases/UserNotificationOptions.md) = `{}`

## Accessors

### isOpen

#### Get Signature

> **get** **isOpen**(): `boolean`

##### Returns

`boolean`

## Methods

### close()

> **close**(): `void`

#### Returns

`void`

***

### destroy()

> **destroy**(): `void`

#### Returns

`void`

***

### open()

> **open**(): `Promise`\<`void`\>

#### Returns

`Promise`\<`void`\>

***

### updateContent()

> **updateContent**(`notification`): `void`

#### Parameters

##### notification

[`Notification`](../type-aliases/Notification.md)

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
