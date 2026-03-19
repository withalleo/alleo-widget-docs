[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / FormButtonHelper

# Class: FormButtonHelper

Creates interactive buttons for Formly forms and dialogs with timer and state management.

Provides utilities for adding action buttons to settings forms with features like periodic
refresh timers, single-use restrictions, loading states, and automatic cleanup. Integrates
seamlessly with Formly forms and handles button lifecycle, permissions, and visibility.
Essential for creating interactive form controls and action buttons.

## Example

```typescript
// Create a refresh button with timer
const refreshButton = new FormButtonHelper(
  'Refresh Data',
  () => {
    console.log('Refreshing...');
    loadData();
  },
  {
    interval: 5000, // Refresh every 5 seconds
    primary: true,
    loadingPlaceholder: 'Loading...'
  }
);

// Single-use action button
const importButton = new FormButtonHelper(
  'Import Data',
  () => importData(),
  {
    singleUse: true,
    primary: false
  }
);

// Get Formly field config
const fieldConfig = refreshButton.field;
```

## Constructors

### Constructor

> **new FormButtonHelper**(`label`, `callback?`, `settings?`): `FormButtonHelper`

Creates a FormButtonHelper instance for managing interactive form buttons.

Initializes button with label, click handler, and optional timer for periodic execution.
Automatically handles cleanup when widget is destroyed and respects user edit permissions.

#### Parameters

##### label

`string`

Text displayed on the button.

##### callback?

(`field`) => `void`

Function invoked when button is clicked, receives the field configuration.

##### settings?

[`FormButtonHelperSettings`](../type-aliases/FormButtonHelperSettings.md) = `{}`

Configuration options.

#### Returns

`FormButtonHelper`

## Properties

### callback

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

> **startTimer**(`interval?`): `void`

Starts the timer.

#### Parameters

##### interval?

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
