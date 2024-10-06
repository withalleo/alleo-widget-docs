[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / ResizeHelper

# Class: ResizeHelper

A helper class to enable axis-independent resizing of a widget

## Constructors

### new ResizeHelper()

> **new ResizeHelper**(`minSize`?, `callback`?, `updateCss`?, `widgetContainerSelector`?): [`ResizeHelper`](ResizeHelper.md)

Enable axis-independent resizing.

#### Parameters

• **minSize?**: [`Size`](../type-aliases/Size.md) = `...`

The minimum size of the element.

• **callback?** = `undefined`

A callback function to be called on resize.

• **updateCss?**: `boolean` = `true`

Whether to update CSS properties on resize.

• **widgetContainerSelector?**: `string` = `'.widget-container'`

The CSS selector for the widget container.

#### Returns

[`ResizeHelper`](ResizeHelper.md)

#### Throws

Will throw an error if no DOM is available.

## Properties

### callback()

> **callback**: (`__namedParameters`) => `void` = `undefined`

A callback function to be called on resize.

#### Parameters

• **\_\_namedParameters**

• **\_\_namedParameters.height**: `any`

• **\_\_namedParameters.width**: `any`

#### Returns

`void`

***

### updateCss

> **updateCss**: `boolean` = `true`

Whether to update CSS properties on resize.

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

• **minSize**: [`Size`](../type-aliases/Size.md)

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

• **size**: [`Size`](../type-aliases/Size.md)

The size to set.

#### Returns

`void`

#### Throws

Will throw an error if no DOM is available.
