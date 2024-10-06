[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / ColorPickerHelper

# Class: ColorPickerHelper

A helper class for creating a color picker

## Extended by

- [`ColorSwitcherHelper`](ColorSwitcherHelper.md)

## Constructors

### new ColorPickerHelper()

> **new ColorPickerHelper**(`handle`?, `CSSVariable`?, `defaultColor`?, `coloPickerSettings`?, `widgetContainerSelector`?, `callbackOnColorChange`?, `displayColorPickerButtonOnInit`?): [`ColorPickerHelper`](ColorPickerHelper.md)

Creates a Color Picker

#### Parameters

• **handle?**: `string` = `'color'`

The handle for the color picker. (the shared variable)

• **CSSVariable?**: `string` = `'--widget-color'`

The CSS variable for the color.

• **defaultColor?**: `string` = `DefaultColors.primary`

The default color.

• **coloPickerSettings?**: `Partial`\<`object`\> = `...`

The settings for the color picker.

• **widgetContainerSelector?**: `string` = `'.widget-container'`

The CSS selector for the widget container.

• **callbackOnColorChange?** = `undefined`

The callback function to call on color change.

• **displayColorPickerButtonOnInit?**: `boolean` = `true`

Whether to display the color picker button on initialization.

#### Returns

[`ColorPickerHelper`](ColorPickerHelper.md)

#### Throws

Will throw an error if the DOM is not available.

## Properties

### color

> **color**: `string`

The current color.

## Methods

### createColorPickerButton()

> **createColorPickerButton**(`button`?, `coloPickerSettings`?): `void`

Creates a color picker button.

#### Parameters

• **button?**: `ContextMenuColor` = `undefined`

The context menu color button.

• **coloPickerSettings?**: `Partial`\<`object`\>

The settings for the color picker.

#### Returns

`void`

#### Throws

Will throw an error if the DOM is not available.

***

### onUpdate()

> `protected` **onUpdate**(`color`): `void`

Updates the color. (when set)

#### Parameters

• **color**: `string`

The new color.

#### Returns

`void`

***

### setColor()

> **setColor**(`color`): `void`

Sets the color.

#### Parameters

• **color**: `string`

The new color.

#### Returns

`void`
