[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / UserNotificationOptions

# Type Alias: UserNotificationOptions

> **UserNotificationOptions** = `object`

Configuration options for controlling notification behavior and appearance.

## Properties

### alternativeButton?

> `optional` **alternativeButton?**: `object`

Custom action button configuration.

#### onClick

> **onClick**: () => `void`

##### Returns

`void`

#### text

> **text**: `string`

***

### autoOpen?

> `optional` **autoOpen?**: `boolean`

When true, notification opens immediately upon creation.

***

### hideButton?

> `optional` **hideButton?**: `boolean`

When true, hides the default dismiss button.

***

### neverTimeout?

> `optional` **neverTimeout?**: `boolean`

When true, notification stays visible until manually dismissed.

***

### timeout?

> `optional` **timeout?**: `number`

Duration in milliseconds before the notification automatically closes (default varies by type).
