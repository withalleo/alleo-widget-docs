[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / FontPickerHelper

# Class: FontPickerHelper

Class to create and manage a font picker button on the widget bar.

## Constructors

### new FontPickerHelper()

> **new FontPickerHelper**(`handle`?, `CSSVariable`?, `fontPickerSettings`?): [`FontPickerHelper`](FontPickerHelper.md)

Constructor for FontPickerHelper.

#### Parameters

• **handle?**: `string` = `FontPickerHelper.defaultHandle`

The handle for the font selector.

• **CSSVariable?**: `string` = `FontPickerHelper.defaultCSS`

The CSS variable for the widget font.

• **fontPickerSettings?**: `Partial`\<`object`\> = `...`

The settings for the font picker.

#### Returns

[`FontPickerHelper`](FontPickerHelper.md)

#### Throws

Will throw an error if no DOM is available.

## Properties

### font

> **font**: `string`

***

### defaultCSS

> `readonly` `static` **defaultCSS**: `string` = `'--widget-font'`

Default CSS variable for the widget font.

***

### defaultHandle

> `readonly` `static` **defaultHandle**: `string` = `'font-selector-font'`

Default handle for the font selector.

## Methods

### createFontPickerButton()

> `protected` **createFontPickerButton**(`button`?): `void`

Creates a font picker button on the widget bar.

#### Parameters

• **button?**: [`ContextMenuFont`](../interfaces/ContextMenuFont.md) = `undefined`

The context menu font button.

#### Returns

`void`

#### Throws

Will throw an error if no DOM is available.

***

### onUpdate()

> `protected` **onUpdate**(`font`): `void`

Updates the font in the widget.

#### Parameters

• **font**: `string`

The font to update.

#### Returns

`void`

***

### setFont()

> **setFont**(`font`): `void`

Sets the font for the widget.

#### Parameters

• **font**: `string`

The font to set.

#### Returns

`void`
