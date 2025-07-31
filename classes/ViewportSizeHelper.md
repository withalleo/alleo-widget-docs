[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / ViewportSizeHelper

# Class: ViewportSizeHelper

A helper class for managing viewport size changes and providing size information
for specific elements in the Alleo whiteboard application.

## Constructors

### Constructor

> **new ViewportSizeHelper**(`callback`, `settings`): `ViewportSizeHelper`

Creates an instance of ViewportSizeHelper.

#### Parameters

##### callback

(`canvas`, `body`) => `unknown`

A function to be called when the viewport size changes.

##### settings

`ViewportSizeHelperSettings` = `{}`

Optional settings to configure the behavior of the helper.

#### Returns

`ViewportSizeHelper`

## Properties

### callback()

> `readonly` **callback**: (`canvas`, `body`) => `unknown` = `undefined`

A function to be called when the viewport size changes.

#### Parameters

##### canvas

[`ViewportSize`](../type-aliases/ViewportSize.md)

##### body

[`ViewportSize`](../type-aliases/ViewportSize.md)

#### Returns

`unknown`

## Accessors

### body

#### Get Signature

> **get** `static` **body**(): [`ViewportSize`](../type-aliases/ViewportSize.md)

Static method to get the current size of the body element.

##### Returns

[`ViewportSize`](../type-aliases/ViewportSize.md)

The size of the body.

***

### canvas

#### Get Signature

> **get** `static` **canvas**(): [`ViewportSize`](../type-aliases/ViewportSize.md)

Static method to get the current size and position (compared to the body) of the Alleo canvas.

The canvas does not include the top / bottom / left / right menus and locked toolbars.
The returned size is rounded to the nearest pixels.

##### Returns

[`ViewportSize`](../type-aliases/ViewportSize.md)

The size and position of the canvas.

## Methods

### destroy()

> **destroy**(): `void`

#### Returns

`void`

***

### onChange()

> `protected` **onChange**(`canvasSize`, `bodySize`): `void`

#### Parameters

##### canvasSize

[`ViewportSize`](../type-aliases/ViewportSize.md)

##### bodySize

[`ViewportSize`](../type-aliases/ViewportSize.md)

#### Returns

`void`

***

### triggerChange()

> **triggerChange**(`force`): `void`

#### Parameters

##### force

`boolean` = `false`

#### Returns

`void`
