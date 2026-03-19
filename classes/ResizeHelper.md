[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / ResizeHelper

# Class: ResizeHelper

Enables axis-independent widget resizing with automatic DOM updates and size constraints.

Provides automatic handling of widget resize events, updating CSS variables and triggering
callbacks when the widget's size changes. Supports minimum size constraints and debounced
resize callbacks for performance. Essential for responsive widgets that need to adapt
their layout based on size.

## Example

```typescript
// Basic usage with minimum size
new ResizeHelper({ width: 200, height: 150 });

// With callback for custom resize logic
new ResizeHelper(
  { width: 300, height: 200 },
  {
    callback: ({ width, height }) => {
      console.log(`Widget resized to ${width}x${height}`);
      updateLayout(width, height);
    }
  }
);

// Get current widget size
const size = ResizeHelper.getWidgetSize();
```

## Constructors

### Constructor

> **new ResizeHelper**(`minSize?`, `options?`): `ResizeHelper`

Enables axis-independent resizing with options-based configuration.

#### Parameters

##### minSize?

[`Size`](../type-aliases/Size.md)

Minimum allowed widget dimensions.

##### options?

`ResizeHelperOptions`

Configuration options for resize behavior.

#### Returns

`ResizeHelper`

#### Throws

Throws if widget doesn't have a DOM or container element is not found.

### Constructor

> **new ResizeHelper**(`minSize?`, `callback`, `updateCss?`, `settings?`): `ResizeHelper`

Enables axis-independent resizing with legacy parameter-based configuration.

#### Parameters

##### minSize?

[`Size`](../type-aliases/Size.md)

Minimum allowed widget dimensions.

##### callback

(`__namedParameters`) => `void`

Function called when widget is resized with {width, height} parameter.

##### updateCss?

`boolean`

Whether to update CSS custom properties with size values.

##### settings?

`LimitedResizeHelperOptions`

Additional configuration options.

#### Returns

`ResizeHelper`

#### Throws

Throws if widget doesn't have a DOM or container element is not found.

#### Deprecated

Use the object-based constructor signature instead for better type safety.

## Properties

### callback

> **callback**: (`__namedParameters`) => `void`

#### Parameters

##### \_\_namedParameters

[`Size`](../type-aliases/Size.md)

#### Returns

`void`

***

### updateCss

> **updateCss**: `boolean` = `true`

## Methods

### destroy()

> **destroy**(): `void`

Destroys the ResizeHelper instance, disabling resizing and disconnecting the observer.

#### Returns

`void`

#### Throws

Will throw an error if no DOM is available.

***

### onResize()

> **onResize**(`contentRect`): `void`

Triggers the resize event with the current size of the widget.
This method is called by the ResizeObserver when the widget is resized.
It updates the CSS variables and calls the callback function if provided.
Additionally, it tracks the resize event for analytics purposes.

#### Parameters

##### contentRect

[`Size`](../type-aliases/Size.md)

The content rectangle of the resized element.

#### Returns

`void`

#### Throws

Will throw an error if no DOM is available.

***

### setMinSize()

> `static` **setMinSize**(`minSize`): `void`

Sets the minimum size of the element.

#### Parameters

##### minSize

[`Size`](../type-aliases/Size.md)

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

##### size

[`Size`](../type-aliases/Size.md)

The size to set.

#### Returns

`void`

#### Throws

Will throw an error if no DOM is available.
