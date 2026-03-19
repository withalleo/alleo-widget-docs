[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / DefaultColors

# Class: DefaultColors

Provides theme-aware default colors for consistent widget styling.

Supplies color values that automatically adapt to the Alleo board's theme, with support
for organization-level customization. Colors are derived from the board's theme system
or can be overridden via widget configuration for custom branding.

## Example

```typescript
// Use predefined semantic colors
element.style.color = DefaultColors.text;
element.style.backgroundColor = DefaultColors.background;

// Status colors
errorMsg.style.color = DefaultColors.red;
successMsg.style.color = DefaultColors.green;

// Use multiple colors for charts
const chartColors = DefaultColors.rainbow; // Array of colors

// Theme-aware primary color
button.style.backgroundColor = DefaultColors.primary;
```

## Constructors

### Constructor

> **new DefaultColors**(): `DefaultColors`

#### Returns

`DefaultColors`

## Properties

### background

> `readonly` `static` **background**: `string`

The default background color for widget surfaces.

Automatically adapts to the board's theme. Use for widget backgrounds,
panels, and containers.

***

### green

> `readonly` `static` **green**: `string`

The color representing success, completion, or positive actions.

Typically used for success messages, checkmarks, confirmation indicators,
or any UI element indicating a positive state.

***

### primary

> `readonly` `static` **primary**: `string`

The organization's primary brand color.

Reflects the organization's main brand identity. Use for primary actions,
highlights, and branded UI elements.

***

### rainbow

> `readonly` `static` **rainbow**: `string`[]

Array of distinct colors for visualizations requiring multiple colors.

Provides a palette of 10 visually distinct colors suitable for charts, graphs,
or any UI requiring multiple differentiated color values. Colors are ordered
for maximum visual contrast between adjacent items.

***

### red

> `readonly` `static` **red**: `string`

The color representing errors, warnings, or destructive actions.

Typically used for error messages, validation failures, delete buttons,
or any UI element indicating a problem or danger.

***

### text

> `readonly` `static` **text**: `string`

The default color for text content.

Automatically adapts to the board's theme for proper contrast. Use for
primary text, labels, and readable content.

***

### textContrast

> `readonly` `static` **textContrast**: `string`

High-contrast text color for use on accent-colored backgrounds.

Ensures readability when text is displayed over colored surfaces.

***

### theme

> `protected` `readonly` `static` **theme**: `object`

The board's theme colors object from the Alleo theme system.

***

### toolbarBackground

> `readonly` `static` **toolbarBackground**: `string`

The background color for Alleo UI toolbars and panels.

Matches the color scheme of Alleo's system UI for consistent integration.

***

### toolbarText

> `readonly` `static` **toolbarText**: `string`

The text color for Alleo UI toolbars and panels.

Provides proper contrast for text on toolbar backgrounds.

***

### widgetButton

> `readonly` `static` **widgetButton**: `string`

The default color for widget toolbar buttons and controls.

Used for interactive elements in the widget's control bar.
