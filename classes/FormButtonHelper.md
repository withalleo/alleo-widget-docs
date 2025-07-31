[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / FormButtonHelper

# Class: FormButtonHelper

Class helping to add buttons to a form or dialog.

## Constructors

### Constructor

> **new FormButtonHelper**(`label`, `callback?`, `settings?`): `FormButtonHelper`

Creates an instance of FormButtonHelper.

#### Parameters

##### label

`string`

The label of the button.

##### callback?

(`field`) => `void`

The callback function to be called when the button is clicked.

##### settings?

[`FormButtonHelperSettings`](../type-aliases/FormButtonHelperSettings.md) = `{}`

The settings for the form button helper.

#### Returns

`FormButtonHelper`

## Properties

### callback()

> **callback**: (`field`) => `void`

#### Parameters

##### field

`FormlyFieldConfig`\<`FormlyFieldProps`\>

#### Returns

`void`

***

### label

> `readonly` **label**: `string`

***

### settings

> `readonly` **settings**: [`FormButtonHelperSettings`](../type-aliases/FormButtonHelperSettings.md)

***

### widgetId

> `readonly` **widgetId**: `string`

***

### defaultTimerInterval

> `protected` `readonly` `static` **defaultTimerInterval**: `number` = `2500`

## Accessors

### button

#### Get Signature

> **get** **button**(): `FormlyFieldConfig`\<`FormlyFieldProps`\>

Gets the Formly field configuration for the button.

##### Returns

`FormlyFieldConfig`\<`FormlyFieldProps`\>

The Formly field configuration.

***

### isTimerRunning

#### Get Signature

> **get** **isTimerRunning**(): `boolean`

Checks if the timer is running.

##### Returns

`boolean`

True if the timer is running, false otherwise.

## Methods

### destroy()

> **destroy**(): `void`

Destroys the form button helper.

#### Returns

`void`

***

### onTimerTick()

> `protected` **onTimerTick**(): `Promise`\<`void`\>

Handles the timer tick event.

#### Returns

`Promise`\<`void`\>

***

### startTimer()

> **startTimer**(`interval`): `void`

Starts the timer.

#### Parameters

##### interval

`number` = `undefined`

#### Returns

`void`

***

### stopTimer()

> **stopTimer**(): `void`

Stops the timer.

#### Returns

`void`

***

### updateButtonUI()

> **updateButtonUI**(): `Promise`\<`void`\>

#### Returns

`Promise`\<`void`\>
