[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / UiButtonHelper

# Class: UiButtonHelper

Manages floating action buttons for service widgets in the Alleo UI.

Creates and positions custom buttons in the bottom-right corner of the interface,
alongside system buttons like Intercom or help. Handles responsive positioning,
button lifecycle, and ensures buttons are properly displayed and accessible.
Primarily used by service widgets that don't have a board presence.

## Example

```typescript
const buttonHelper = new UiButtonHelper();

// Add a simple button
buttonHelper.add({
  id: 'my-action',
  label: 'Click Me',
  onClick: () => console.log('Button clicked!')
});

// Add button with icon
buttonHelper.add({
  id: 'settings',
  icon: 'settings',
  label: 'Settings',
  onClick: () => openSettings()
});

// Remove a button
buttonHelper.remove('my-action');
```

## Constructors

### Constructor

> **new UiButtonHelper**(): `UiButtonHelper`

Creates a new UiButtonHelper instance and initializes the button container.

Sets up a fixed-position container in the bottom-right corner for floating action buttons.
Automatically manages positioning relative to other UI elements like Intercom and help buttons.
Cleans up automatically when the widget is destroyed.

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

The background color used for buttons, automatically matching the UI theme.

Returns the primary color if Intercom is present (for consistency with Intercom button),
otherwise returns the toolbar background color.

##### Returns

`string`

CSS color value for button backgrounds.

***

### buttons

#### Get Signature

> **get** **buttons**(): `HTMLElement`[]

Array of all button HTML elements managed by this helper.

##### Returns

`HTMLElement`[]

Array of button elements currently displayed.

## Methods

### addButton()

> **addButton**(`html`, `callback`, `settings?`): `string`

Adds a new button to the UI.

#### Parameters

##### html

`string`

The HTML content of the button.

##### callback

(`e`) => `void`

The callback function to execute when the button is clicked.

##### settings?

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

Retrieves the HTML element for a button by its ID.

#### Parameters

##### buttonId

`string`

The unique identifier of the button to retrieve.

#### Returns

`HTMLElement`

The button element, or undefined if not found.

***

### isVisible()

> **isVisible**(`buttonId`): `boolean`

Checks whether a button with the specified ID is currently visible.

#### Parameters

##### buttonId

`string`

The unique identifier of the button to check.

#### Returns

`boolean`

True if a button with this ID exists and is displayed, false otherwise.

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
