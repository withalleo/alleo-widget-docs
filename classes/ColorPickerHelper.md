[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / ColorPickerHelper

# Class: ColorPickerHelper

Creates and manages an interactive color picker UI for widgets.

Provides a complete color selection interface with predefined palettes, custom colors,
transparent option, and automatic CSS variable updates. Integrates with the widget's
toolbar to display a color picker button. Manages color persistence through shared
variables and provides callbacks for color change events.

## Example

```typescript
// Basic color picker for text color
const textColorPicker = new ColorPickerHelper(
  'textColor',
  '--text-color',
  '#ffffff'
);

// Color picker with custom palette and callback
const bgColorPicker = new ColorPickerHelper(
  'backgroundColor',
  '--bg-color',
  DefaultColors.background,
  {
    label: 'Background Color',
    icon: { icon: 'fill-drip', set: 'fas' },
    palette: ColorPalette.Background,
    includeTransparent: true
  },
  '.widget-container',
  (color) => console.log('Color changed to:', color)
);
```

## Extended by

- [`ColorSwitcherHelper`](ColorSwitcherHelper.md)

## Constructors

### Constructor

> **new ColorPickerHelper**(`handle?`, `CSSVariable?`, `defaultColor?`, `coloPickerSettings?`, `widgetContainerSelector?`, `callbackOnColorChange?`, `displayColorPickerButtonOnInit?`): `ColorPickerHelper`

Creates a color picker with toolbar button and automatic color management.

#### Parameters

##### handle?

`string` = `'color'`

Shared variable name for storing the selected color.

##### CSSVariable?

`string` = `'--widget-color'`

CSS custom property name to update with the selected color.

##### defaultColor?

`string` = `DefaultColors.primary`

Default color value when no color is stored.

##### coloPickerSettings?

`Partial`\<\{ `icon`: \{ `icon`: `string`; `set`: `string`; \}; `includeTransparent`: `boolean`; `label`: `string`; `palette`: `ColorPalette`; \}\> = `...`

Configuration for the color picker appearance and behavior.

##### widgetContainerSelector?

`string` = `'.widget-container'`

CSS selector for the widget's main container element.

##### callbackOnColorChange?

(`color`) => `void`

Callback function invoked when color changes, receives the new color string.

##### displayColorPickerButtonOnInit?

`boolean` = `true`

Whether to show the color picker button immediately on creation.

#### Returns

`ColorPickerHelper`

#### Throws

Throws if the widget doesn't have a DOM (service widgets).

## Properties

### color

> **color**: `string`

The current color.

## Methods

### createColorPickerButton()

> **createColorPickerButton**(`button?`, `coloPickerSettings`): `void`

Creates a color picker button.

#### Parameters

##### button?

`ContextMenuColor` = `undefined`

The context menu color button.

##### coloPickerSettings

`Partial`\<\{ `icon`: \{ `icon`: `string`; `set`: `string`; \}; `includeTransparent`: `boolean`; `label`: `string`; `palette`: `ColorPalette`; \}\>

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

##### color

`string`

The new color.

#### Returns

`void`

***

### setColor()

> **setColor**(`color`): `void`

Sets the color.

#### Parameters

##### color

`string`

The new color.

#### Returns

`void`
