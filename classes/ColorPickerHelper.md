[**@withalleo/alleo-widget**](../README.md)

---

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
  "textColor",
  "--text-color",
  "#ffffff",
);

// Color picker with custom palette and callback
const bgColorPicker = new ColorPickerHelper(
  "backgroundColor",
  "--bg-color",
  DefaultColors.background,
  {
    label: "Background Color",
    icon: { icon: "fill-drip", set: "fas" },
    palette: ColorPalette.Background,
    includeTransparent: true,
  },
  ".widget-container",
  (color) => console.log("Color changed to:", color),
);
```

## Extended by

- [`ColorSwitcherHelper`](ColorSwitcherHelper.md)

## Constructors

### Constructor

```ts
new ColorPickerHelper(
   handle?: string,
   CSSVariable?: string,
   defaultColor?: string,
   coloPickerSettings?: Partial<{
  icon: {
     icon: string;
     set: string;
  };
  includeTransparent: boolean;
  label: string;
  palette: ColorPalette;
}>,
   widgetContainerSelector?: string,
   callbackOnColorChange?: (color: string) => void,
   displayColorPickerButtonOnInit?: boolean): ColorPickerHelper;
```

Creates a color picker with toolbar button and automatic color management.

#### Parameters

| Parameter                         | Type                                                                                                                                                | Default value           | Description                                                                  |
| --------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------- | ---------------------------------------------------------------------------- |
| `handle?`                         | `string`                                                                                                                                            | `'color'`               | Shared variable name for storing the selected color.                         |
| `CSSVariable?`                    | `string`                                                                                                                                            | `'--widget-color'`      | CSS custom property name to update with the selected color.                  |
| `defaultColor?`                   | `string`                                                                                                                                            | `DefaultColors.primary` | Default color value when no color is stored.                                 |
| `coloPickerSettings?`             | `Partial`\<\{ `icon`: \{ `icon`: `string`; `set`: `string`; \}; `includeTransparent`: `boolean`; `label`: `string`; `palette`: `ColorPalette`; \}\> | `...`                   | Configuration for the color picker appearance and behavior.                  |
| `widgetContainerSelector?`        | `string`                                                                                                                                            | `'.widget-container'`   | CSS selector for the widget's main container element.                        |
| `callbackOnColorChange?`          | (`color`: `string`) => `void`                                                                                                                       | `...`                   | Callback function invoked when color changes, receives the new color string. |
| `displayColorPickerButtonOnInit?` | `boolean`                                                                                                                                           | `true`                  | Whether to show the color picker button immediately on creation.             |

#### Returns

`ColorPickerHelper`

#### Throws

Throws if the widget doesn't have a DOM (service widgets).

## Properties

### color

```ts
color: string;
```

The current color.

## Methods

### createColorPickerButton()

```ts
createColorPickerButton(button?: ContextMenuColor, coloPickerSettings: Partial<{
  icon: {
     icon: string;
     set: string;
  };
  includeTransparent: boolean;
  label: string;
  palette: ColorPalette;
}>): void;
```

Creates a color picker button.

#### Parameters

| Parameter             | Type                                                                                                                                                | Default value | Description                        |
| --------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | ------------- | ---------------------------------- |
| `button?`             | `ContextMenuColor`                                                                                                                                  | `undefined`   | The context menu color button.     |
| `coloPickerSettings?` | `Partial`\<\{ `icon`: \{ `icon`: `string`; `set`: `string`; \}; `includeTransparent`: `boolean`; `label`: `string`; `palette`: `ColorPalette`; \}\> | `undefined`   | The settings for the color picker. |

#### Returns

`void`

#### Throws

Will throw an error if the DOM is not available.

---

### onUpdate()

```ts
protected onUpdate(color: string): void;
```

Updates the color. (when set)

#### Parameters

| Parameter | Type     | Description    |
| --------- | -------- | -------------- |
| `color`   | `string` | The new color. |

#### Returns

`void`

---

### setColor()

```ts
setColor(color: string): void;
```

Sets the color.

#### Parameters

| Parameter | Type     | Description    |
| --------- | -------- | -------------- |
| `color`   | `string` | The new color. |

#### Returns

`void`
