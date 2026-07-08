[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / ColorSwitcherHelper

# Class: ColorSwitcherHelper

Provides a simplified color picker that toggles between two predefined colors.

A lightweight alternative to ColorPickerHelper that switches between two colors (typically
text and textContrast) with a single click. Extends ColorPickerHelper to inherit core
functionality while simplifying the UI to a toggle button. Ideal for widgets needing
quick theme switching without full color selection UI.

## Example

```typescript
// Basic color switcher for text color
const textSwitcher = new ColorSwitcherHelper(
  "textColor",
  "--text-color",
  DefaultColors.text,
);

// Custom switcher with specific colors and callback
const customSwitcher = new ColorSwitcherHelper(
  "bgColor",
  "--background",
  DefaultColors.background,
  {
    label: "Toggle Background",
    icon: { icon: "moon", set: "fas" },
  },
  ".widget-container",
  (color) => console.log("Switched to:", color),
);
```

## Extends

- [`ColorPickerHelper`](ColorPickerHelper.md)

## Constructors

### Constructor

```ts
new ColorSwitcherHelper(
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
   callbackOnColorChange?: (color: string) => undefined,
   displayColorSwitcherButtonOnInit?: boolean): ColorSwitcherHelper;
```

Creates a color switcher that toggles between two predefined colors.

Initializes a toggle button that switches between text and textContrast colors
(or custom colors via callback). Automatically adds a button to the widget toolbar.

#### Parameters

| Parameter                           | Type                                                                                                                                                | Default value           | Description                                                     |
| ----------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------- | --------------------------------------------------------------- |
| `handle?`                           | `string`                                                                                                                                            | `'fontColor'`           | Shared variable name for storing the current color.             |
| `CSSVariable?`                      | `string`                                                                                                                                            | `'--widget-font-color'` | CSS custom property to update with the color.                   |
| `defaultColor?`                     | `string`                                                                                                                                            | `DefaultColors.text`    | Initial color value.                                            |
| `coloPickerSettings?`               | `Partial`\<\{ `icon`: \{ `icon`: `string`; `set`: `string`; \}; `includeTransparent`: `boolean`; `label`: `string`; `palette`: `ColorPalette`; \}\> | `...`                   | UI configuration for the switcher button.                       |
| `widgetContainerSelector?`          | `string`                                                                                                                                            | `'.widget-container'`   | CSS selector for the widget's container.                        |
| `callbackOnColorChange?`            | (`color`: `string`) => `undefined`                                                                                                                  | `...`                   | Callback invoked when color changes, receives new color string. |
| `displayColorSwitcherButtonOnInit?` | `boolean`                                                                                                                                           | `true`                  | Whether to show the switcher button immediately.                |

#### Returns

`ColorSwitcherHelper`

#### Throws

Throws if widget doesn't have a DOM (service widgets not supported).

#### Overrides

[`ColorPickerHelper`](ColorPickerHelper.md).[`constructor`](ColorPickerHelper.md#constructor)

## Properties

### color

```ts
color: string;
```

The current color.

#### Inherited from

[`ColorPickerHelper`](ColorPickerHelper.md).[`color`](ColorPickerHelper.md#color)

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

#### Inherited from

[`ColorPickerHelper`](ColorPickerHelper.md).[`createColorPickerButton`](ColorPickerHelper.md#createcolorpickerbutton)

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

#### Inherited from

[`ColorPickerHelper`](ColorPickerHelper.md).[`onUpdate`](ColorPickerHelper.md#onupdate)

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

#### Inherited from

[`ColorPickerHelper`](ColorPickerHelper.md).[`setColor`](ColorPickerHelper.md#setcolor)
