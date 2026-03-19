[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / ViewportSizeHelper

# Class: ViewportSizeHelper

Monitors viewport dimensions and element positioning for responsive layouts.

Provides real-time tracking of viewport size changes, including the main canvas and
document body dimensions. Automatically detects resize events and triggers callbacks
with updated size information. Essential for implementing responsive UI that adapts
to browser window resizing, canvas changes, or layout updates. Uses ResizeObserver
for efficient change detection.

## Example

```typescript
// Monitor viewport changes for responsive layout
const viewportHelper = new ViewportSizeHelper((canvas, body) => {
  console.log('Canvas size:', canvas.width, canvas.height);
  console.log('Body size:', body.width, body.height);
  updateLayout(canvas, body);
});

// With custom settings
const customHelper = new ViewportSizeHelper(
  (canvas, body) => adjustUI(canvas),
  {
    triggerOnBodyResize: true,
    triggerOnCanvasResize: true,
    triggerOnInit: false // Don't trigger immediately
  }
);
```

## Constructors

### Constructor

> **new ViewportSizeHelper**(`callback?`, `settings?`): `ViewportSizeHelper`

Creates a ViewportSizeHelper instance to monitor viewport dimension changes.

Sets up ResizeObserver to watch for changes to the main canvas and document body.
Automatically cleans up observers when the widget is destroyed.

#### Parameters

##### callback?

(`canvas`, `body`) => `unknown`

Function called when viewport size changes. Receives canvas and body ViewportSize objects.

##### settings?

`ViewportSizeHelperSettings` = `{}`

Configuration options.

#### Returns

`ViewportSizeHelper`

#### Throws

Throws if the mainCanvas element is not found in the document.

## Properties

### callback

> `readonly` **callback**: (`canvas`, `body`) => `unknown` = `undefined`

Function called when viewport size changes. Receives canvas and body ViewportSize objects.

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

> **triggerChange**(`force?`): `void`

#### Parameters

##### force?

`boolean` = `false`

#### Returns

`void`
