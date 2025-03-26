[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / ResizeHelper

# Class: ResizeHelper

A helper class to enable axis-independent resizing of a widget

## Constructors

### Constructor

> **new ResizeHelper**(`minSize`?, `options`?): `ResizeHelper`

Enable axis-independent resizing.

#### Parameters

##### minSize?

[`Size`](../type-aliases/Size.md)

The minimum size of the element.

##### options?

`ResizeHelperOptions`

The options to use.

#### Returns

`ResizeHelper`

#### Throws

Will throw an error if no DOM is available.

### Constructor

> **new ResizeHelper**(`minSize`?, `callback`?, `updateCss`?, `settings`?): `ResizeHelper`

Enable axis-independent resizing.

#### Parameters

##### minSize?

[`Size`](../type-aliases/Size.md)

The minimum size of the element.

##### callback?

(`__namedParameters`) => `void`

The callback to call when the element is resized.

##### updateCss?

`boolean`

Whether to update the CSS variables.

##### settings?

`LimitedResizeHelperOptions`

The options to use.

#### Returns

`ResizeHelper`

#### Throws

Will throw an error if no DOM is available.

#### Deprecated

Use the object-based constructor instead.

## Properties

### callback()

> **callback**: (`__namedParameters`) => `void`

#### Parameters

##### \_\_namedParameters

###### height

`any`

###### width

`any`

#### Returns

`void`

***

### updateCss

> **updateCss**: `boolean` = `true`

## Methods

### destroy()

> **destroy**(): `void`

Destroys the ResizeHelper instance, disabling resizing and disconnecting the observer.

#### Returns

`void`

#### Throws

Will throw an error if no DOM is available.

***

### setMinSize()

> `static` **setMinSize**(`minSize`): `void`

Sets the minimum size of the element.

#### Parameters

##### minSize

[`Size`](../type-aliases/Size.md)

The minimum size to set.

#### Returns

`void`

#### Throws

Will throw an error if no DOM is available.

***

### setSize()

> `static` **setSize**(`size`): `void`

Sets the size of the element.

#### Parameters

##### size

[`Size`](../type-aliases/Size.md)

The size to set.

#### Returns

`void`

#### Throws

Will throw an error if no DOM is available.
