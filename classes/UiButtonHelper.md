[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / UiButtonHelper

# Class: UiButtonHelper

Helper class for managing UI buttons for widget services.

## Constructors

### Constructor

> **new UiButtonHelper**(): `UiButtonHelper`

Constructs a new button.

#### Returns

`UiButtonHelper`

## Properties

### container

> `readonly` **container**: `HTMLElement`

***

### containerId

> `static` **containerId**: `string` = `'widget-service-ui-helper-main-buttons'`

## Accessors

### backgroundColor

#### Get Signature

> **get** **backgroundColor**(): `string`

Gets the background color of the buttons.

##### Returns

`string`

The background color of the buttons.

***

### buttons

#### Get Signature

> **get** **buttons**(): `HTMLElement`[]

Gets the list of button elements.

##### Returns

`HTMLElement`[]

The list of button elements.

## Methods

### addButton()

> **addButton**(`html`, `callback`, `settings`): `string`

Adds a new button to the UI.

#### Parameters

##### html

`string`

The HTML content of the button.

##### callback

(`e`) => `void`

The callback function to execute when the button is clicked.

##### settings

The settings for the button.

###### backgroundColor?

`string`

###### buttonId?

`string`

The ID of the button.

###### callbackAltClick?

(`e`) => `void`

###### callbackPointerDown?

(`e`) => `void`

###### callbackPointerUp?

(`e`) => `void`

###### color?

`string`

###### position?

`number` \| [`UiButtonPosition`](../enumerations/UiButtonPosition.md)

The position of the button.

#### Returns

`string`

The ID of the newly added button.

***

### destroy()

> **destroy**(): `void`

Destroys all buttons managed by this helper.

#### Returns

`void`

***

### getButton()

> **getButton**(`buttonId`): `HTMLElement`

Gets the button element with the given ID.

#### Parameters

##### buttonId

`string`

The ID of the button.

#### Returns

`HTMLElement`

The button element.

***

### isVisible()

> **isVisible**(`buttonId`): `boolean`

Checks if a button with the given ID is visible.

#### Parameters

##### buttonId

`string`

The ID of the button.

#### Returns

`boolean`

True if the button is visible, false otherwise.

***

### removeButton()

> **removeButton**(`buttonId`): `void`

Removes a button with the given ID.

#### Parameters

##### buttonId

`string`

The ID of the button to remove.

#### Returns

`void`

***

### reOrderButtons()

> `protected` **reOrderButtons**(): `void`

#### Returns

`void`
