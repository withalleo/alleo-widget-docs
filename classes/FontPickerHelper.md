[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / FontPickerHelper

# Class: FontPickerHelper

Creates and manages a font picker button for widget text styling.

Provides an interactive font selection UI that appears in the widget toolbar, allowing
users to choose from available system fonts. Automatically updates CSS custom properties
and persists selections via shared variables. Essential for widgets with customizable
text styling needs.

## Example

```typescript
// Basic font picker with defaults
const fontPicker = new FontPickerHelper();

// Custom font picker with callback
const customFontPicker = new FontPickerHelper(
  'myFontHandle',
  '--custom-font',
  {
    label: 'Choose Font',
    defaultFont: 'Arial, sans-serif',
    widgetContainerSelector: '.content',
    callbackOnFontChange: (font) => {
      console.log('Font changed to:', font);
      updateTextElements(font);
    },
    displayFontPickerButtonOnInit: true
  }
);

// Access current font
console.log('Current font:', fontPicker.font);
```

## Constructors

### Constructor

> **new FontPickerHelper**(`handle?`, `CSSVariable?`, `fontPickerSettings?`): `FontPickerHelper`

Creates a FontPickerHelper instance with font selection UI.

Initializes the font picker, sets up event handlers for font changes, and optionally
displays a font selection button in the widget toolbar.

#### Parameters

##### handle?

`string` = `FontPickerHelper.defaultHandle`

Shared variable name for storing the selected font.

##### CSSVariable?

`string` = `FontPickerHelper.defaultCSS`

CSS custom property name to update with the font value.

##### fontPickerSettings?

[`FontPickerSettings`](../type-aliases/FontPickerSettings.md) = `...`

Configuration options for the font picker.

#### Returns

`FontPickerHelper`

#### Throws

Throws if widget doesn't have a DOM (service widgets not supported).

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

> `protected` **createFontPickerButton**(`button?`): `void`

Creates a font picker button on the widget bar.

#### Parameters

##### button?

`ContextMenuFont` = `undefined`

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

##### font

`string`

The font to update.

#### Returns

`void`

***

### setFont()

> **setFont**(`font`): `void`

Sets the font for the widget.

#### Parameters

##### font

`string`

The font to set.

#### Returns

`void`
