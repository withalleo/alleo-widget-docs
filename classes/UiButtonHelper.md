[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / UiButtonHelper

# Class: UiButtonHelper

Helper class for managing UI buttons for widget services.

## Constructors

### new UiButtonHelper()

> **new UiButtonHelper**(): [`UiButtonHelper`](UiButtonHelper.md)

Constructs a new button.

#### Returns

[`UiButtonHelper`](UiButtonHelper.md)

## Properties

### container

> `readonly` **container**: `HTMLElement`

***

### containerId

> `static` **containerId**: `string` = `'widget-service-ui-helper-main-buttons'`

## Accessors

### buttons

> `get` **buttons**(): `HTMLElement`[]

Gets the list of button elements.

#### Returns

`HTMLElement`[]

The list of button elements.

## Methods

### addButton()

> **addButton**(`html`, `callback`, `settings`): `string`

Adds a new button to the UI.

#### Parameters

• **html**: `string`

The HTML content of the button.

• **callback**

The callback function to execute when the button is clicked.

• **settings** = `{}`

The settings for the button.

• **settings.buttonId?**: `string`

The ID of the button.

• **settings.position?**: `UiButtonPosition`

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

• **buttonId**: `string`

The ID of the button.

#### Returns

`HTMLElement`

The button element.

***

### isVisible()

> **isVisible**(`buttonId`): `boolean`

Checks if a button with the given ID is visible.

#### Parameters

• **buttonId**: `string`

The ID of the button.

#### Returns

`boolean`

True if the button is visible, false otherwise.

***

### removeButton()

> **removeButton**(`buttonId`): `void`

Removes a button with the given ID.

#### Parameters

• **buttonId**: `string`

The ID of the button to remove.

#### Returns

`void`
