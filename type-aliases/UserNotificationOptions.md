[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / UserNotificationOptions

# Type Alias: UserNotificationOptions

> **UserNotificationOptions** = `object`

Options for customizing user notifications.

## Properties

### alternativeButton?

> `optional` **alternativeButton**: `object`

Custom button with text and click handler.

#### onClick()

> **onClick**: () => `void`

##### Returns

`void`

#### text

> **text**: `string`

***

### autoOpen?

> `optional` **autoOpen**: `boolean`

If true, opens notification on creation.

***

### hideButton?

> `optional` **hideButton**: `boolean`

If true, hides the dismiss button.

***

### neverTimeout?

> `optional` **neverTimeout**: `boolean`

If true, notification never auto-closes.

***

### timeout?

> `optional` **timeout**: `number`

Duration before notification auto-closes (ms).
