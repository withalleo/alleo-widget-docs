[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / ColorSwitcherHelper

# Class: ColorSwitcherHelper

A helper class for creating a color switcher (Which is like a color picker, but only changes between two pre-defined colors when clicked)
Extends the ColorPickerHelper class.

## Extends

- [`ColorPickerHelper`](ColorPickerHelper.md)

## Constructors

### new ColorSwitcherHelper()

> **new ColorSwitcherHelper**(`handle`?, `CSSVariable`?, `defaultColor`?, `coloPickerSettings`?, `widgetContainerSelector`?, `callbackOnColorChange`?, `displayColorSwitcherButtonOnInit`?): [`ColorSwitcherHelper`](ColorSwitcherHelper.md)

Creates a Color Switcher

#### Parameters

• **handle?**: `string` = `'fontColor'`

The handle for the color switcher.

• **CSSVariable?**: `string` = `'--widget-font-color'`

The CSS variable for the font color.

• **defaultColor?**: `string` = `DefaultColors.text`

The default color.

• **coloPickerSettings?**: `Partial`\<`object`\> = `...`

The settings for the color picker.

• **widgetContainerSelector?**: `string` = `'.widget-container'`

The CSS selector for the widget container.

• **callbackOnColorChange?** = `undefined`

The callback function to call on color change.

• **displayColorSwitcherButtonOnInit?**: `boolean` = `true`

Whether to display the color switcher button on initialization.

#### Returns

[`ColorSwitcherHelper`](ColorSwitcherHelper.md)

#### Throws

Will throw an error if the DOM is not available.

#### Overrides

[`ColorPickerHelper`](ColorPickerHelper.md).[`constructor`](ColorPickerHelper.md#constructors)

## Properties

### color

> **color**: `string`

The current color.

#### Inherited from

[`ColorPickerHelper`](ColorPickerHelper.md).[`color`](ColorPickerHelper.md#color)

## Methods

### createColorPickerButton()

> **createColorPickerButton**(`button`?, `coloPickerSettings`?): `void`

Creates a color picker button.

#### Parameters

• **button?**: [`ContextMenuColor`](../interfaces/ContextMenuColor.md) = `undefined`

The context menu color button.

• **coloPickerSettings?**: `Partial`\<`object`\>

The settings for the color picker.

#### Returns

`void`

#### Throws

Will throw an error if the DOM is not available.

#### Inherited from

[`ColorPickerHelper`](ColorPickerHelper.md).[`createColorPickerButton`](ColorPickerHelper.md#createcolorpickerbutton)

***

### onUpdate()

> `protected` **onUpdate**(`color`): `void`

Updates the color. (when set)

#### Parameters

• **color**: `string`

The new color.

#### Returns

`void`

#### Inherited from

[`ColorPickerHelper`](ColorPickerHelper.md).[`onUpdate`](ColorPickerHelper.md#onupdate)

***

### setColor()

> **setColor**(`color`): `void`

Sets the color.

#### Parameters

• **color**: `string`

The new color.

#### Returns

`void`

#### Inherited from

[`ColorPickerHelper`](ColorPickerHelper.md).[`setColor`](ColorPickerHelper.md#setcolor)
