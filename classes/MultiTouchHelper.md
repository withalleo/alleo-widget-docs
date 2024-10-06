[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / MultiTouchHelper

# Class: MultiTouchHelper

Class to manage multi-touch and similar advanced interactions for a widget.

## Constructors

### new MultiTouchHelper()

> **new MultiTouchHelper**(`options`): [`MultiTouchHelper`](MultiTouchHelper.md)

Constructor for MultiTouchHelper.

#### Parameters

• **options**: [`MultiTouchHelperOptions`](../type-aliases/MultiTouchHelperOptions.md) = `{}`

Configuration options for the MultiTouchHelper.

#### Returns

[`MultiTouchHelper`](MultiTouchHelper.md)

## Properties

### disabled

> `protected` **disabled**: `boolean` = `true`

***

### eventDisableHelper

> `protected` **eventDisableHelper**: [`EventDisableHelper`](EventDisableHelper.md)

***

### eventList

> `protected` **eventList**: `string`[]

***

### htmlElement

> `readonly` **htmlElement**: `HTMLElement`

## Methods

### adjustScaleTransform()

> **adjustScaleTransform**(): `void`

Adjusts the scale transform of the widget.

#### Returns

`void`

***

### destroy()

> **destroy**(): `void`

Destroys the MultiTouchHelper, stopping all managed interactions and observers.

#### Returns

`void`

***

### hideZoomOut()

> `protected` **hideZoomOut**(): `void`

Hides the zoom-out button.

#### Returns

`void`

***

### showZoomOut()

> `protected` **showZoomOut**(): `void`

Shows the zoom-out button.

#### Returns

`void`

***

### start()

> **start**(): `void`

Starts the MultiTouchHelper, enabling managed interactions.

#### Returns

`void`

***

### stop()

> **stop**(): `void`

Stops the MultiTouchHelper, disabling managed interactions.

#### Returns

`void`

***

### updateZoomOutButtonStatus()

> **updateZoomOutButtonStatus**(): `void`

Updates the visibility status of the zoom-out button.

#### Returns

`void`

***

### zoomOutToElement()

> `protected` **zoomOutToElement**(): `void`

Zooms out to the element.

#### Returns

`void`

***

### zoomOutVisible()

> `protected` **zoomOutVisible**(): `boolean`

Checks if the zoom-out button should be visible.

#### Returns

`boolean`

True if the zoom-out button should be visible, false otherwise.

***

### dispatchPointerEvent()

> `static` **dispatchPointerEvent**(`event`): `void`

Dispatches a pointer event to the widget's root node.

#### Parameters

• **event**: `string` \| `PointerEvent`

The event to dispatch.

#### Returns

`void`

***

### resizeObserver()

> `static` **resizeObserver**(`obj`, `callback`): `ResizeObserver`

Creates a safe ResizeObserver for the given element.

#### Parameters

• **obj**: `HTMLElement`

The element to observe.

• **callback**: `ResizeObserverCallback`

The callback to execute when the element is resized.

#### Returns

`ResizeObserver`

The created ResizeObserver.
