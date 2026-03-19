[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / FormButtonHelperSettings

# Type Alias: FormButtonHelperSettings

> **FormButtonHelperSettings** = `object`

## Properties

### align?

> `optional` **align?**: `"left"` \| `"right"` \| `"center"` \| `"justify"` \| `"start"` \| `"end"`

***

### callbackOnFormOpened?

> `optional` **callbackOnFormOpened?**: (`button`) => `void`

Callback function to be called when the form is opened.

#### Parameters

##### button

`HTMLElement`

#### Returns

`void`

***

### displayInline?

> `optional` **displayInline?**: `boolean`

Flag to indicate if the button should be displayed inline.

***

### doNotStartFormTimer?

> `optional` **doNotStartFormTimer?**: `boolean`

***

### doNotStartTimer?

> `optional` **doNotStartTimer?**: `boolean`

Flag to indicate if the timer should not start.

***

### formlyKey?

> `optional` **formlyKey?**: `string`

Key for the Formly field configuration.

***

### id?

> `optional` **id?**: `string`

ID of the form button.

***

### interval?

> `optional` **interval?**: `number`

Interval for the timer in milliseconds.

***

### loadingPlaceholder?

> `optional` **loadingPlaceholder?**: `string`

Placeholder text to display while loading.

***

### primary?

> `optional` **primary?**: `boolean`

***

### singleUse?

> `optional` **singleUse?**: `boolean`

Flag to indicate if the button should be single-use.

***

### timeout?

> `optional` **timeout?**: `number`

Timeout in milliseconds after which the button should be destroyed.
