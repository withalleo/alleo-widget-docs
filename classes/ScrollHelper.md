[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / ScrollHelper

# Class: ScrollHelper

A helper class to manage scrolling behavior on an HTML element within a widget.
Including synchronization of scrolling between users.

## Constructors

### Constructor

> **new ScrollHelper**(`element`, `autoEnableScroll`, `syncScrolling`, `syncScrollingLeaderOnly`, `disableUserScrolling`, `sharedVariableName`): `ScrollHelper`

Makes an element scrollable.

#### Parameters

##### element

`HTMLElement`

The HTML element to manage scrolling for.

##### autoEnableScroll

`boolean` = `true`

Whether to automatically enable scrolling.

##### syncScrolling

`boolean` = `true`

Whether to synchronize scrolling.

##### syncScrollingLeaderOnly

`boolean` = `true`

Whether to synchronize scrolling only for the leader.

##### disableUserScrolling

`boolean` = `false`

Whether to disable user scrolling.

##### sharedVariableName

`string` = `'_AlleoWidget_ScrollHelper_coords'`

The name of the shared variable for coordinates.

#### Returns

`ScrollHelper`

## Properties

### coordinates

> **coordinates**: [`Coordinates`](../type-aliases/Coordinates.md)

***

### disableUserScrolling

> **disableUserScrolling**: `boolean`

***

### enabled

> `protected` **enabled**: `boolean` = `false`

***

### eventDisableHelper

> `protected` `readonly` **eventDisableHelper**: [`EventDisableHelper`](EventDisableHelper.md)

***

### htmlElement

> `protected` `readonly` **htmlElement**: `HTMLElement`

***

### sharedVariableName

> `protected` `readonly` **sharedVariableName**: `string`

***

### syncScrolling

> **syncScrolling**: `boolean`

***

### syncScrollingLeaderOnly

> **syncScrollingLeaderOnly**: `boolean`

## Methods

### disableScroll()

> **disableScroll**(): `void`

Disables scrolling on the HTML element.

#### Returns

`void`

***

### enableScroll()

> **enableScroll**(): `void`

Enables scrolling on the HTML element.

#### Returns

`void`

***

### onScroll()

> `protected` **onScroll**(`event`): `void`

Handles the scroll event on the HTML element.

#### Parameters

##### event

`Event`

The scroll event.

#### Returns

`void`

***

### scrollTo()

> **scrollTo**(`coords`, `behavior`): `void`

Scrolls the HTML element to the specified coordinates.

#### Parameters

##### coords

[`Coordinates`](../type-aliases/Coordinates.md)

The coordinates to scroll to.

##### behavior

The scrolling behavior ('auto', 'smooth', or 'instant').

`"auto"` | `"instant"` | `"smooth"`

#### Returns

`void`

***

### scrollToSavedPosition()

> `protected` **scrollToSavedPosition**(): `void`

Scrolls the HTML element to the saved position.

#### Returns

`void`
