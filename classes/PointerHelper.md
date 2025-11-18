[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / PointerHelper

# Class: PointerHelper

Helper class for handling pointer events and click/alt-click logic on an element.

## Constructors

### Constructor

> **new PointerHelper**(`element`): `PointerHelper`

Creates a PointerHelper for the given element.

#### Parameters

##### element

`HTMLElement`

The target HTML element.

#### Returns

`PointerHelper`

## Properties

### altCallbacks

> `protected` **altCallbacks**: (`e`) => `void`[] = `[]`

Registered alt-click callbacks.

#### Parameters

##### e

`PointerEvent`

#### Returns

`void`

***

### callbacks

> `protected` **callbacks**: (`e`) => `void`[] = `[]`

Registered click callbacks.

#### Parameters

##### e

`PointerEvent`

#### Returns

`void`

***

### element

> `protected` **element**: `HTMLElement`

The target HTML element.

## Methods

### onAltClick()

> `protected` **onAltClick**(`e`): `void`

Invokes registered alt-click callbacks.

#### Parameters

##### e

`PointerEvent`

The pointer event.

#### Returns

`void`

***

### onClick()

> `protected` **onClick**(`e`): `void`

Invokes registered click callbacks.

#### Parameters

##### e

`PointerEvent`

The pointer event.

#### Returns

`void`

***

### registerOnAltClick()

> **registerOnAltClick**(`callback`): `void`

Registers a callback for alt-click or long-press events.

#### Parameters

##### callback

(`e`) => `void`

Function to call on alt-click.

#### Returns

`void`

***

### registerOnclick()

> **registerOnclick**(`callback`): `void`

Registers a callback for normal click events.

#### Parameters

##### callback

(`e`) => `void`

Function to call on click.

#### Returns

`void`
