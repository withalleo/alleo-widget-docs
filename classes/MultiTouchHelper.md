[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / MultiTouchHelper

# Class: MultiTouchHelper

Enables advanced touch and zoom interactions for widgets with custom content.

Provides multi-touch gestures (pinch-to-zoom, pan) and mouse-based zooming for widgets
containing complex interactive content like iframes, canvases, or custom visualizations.
Manages event propagation, scale adjustments, and provides UI controls for zooming.
Essential for widgets that need independent zoom/pan controls separate from the board.

## Example

```typescript
// Basic multi-touch support
const multiTouch = new MultiTouchHelper();

// With custom configuration
const customTouch = new MultiTouchHelper({
  enableDblClickToZoom: true,
  showAdjustSizeButton: true,
  adjustWidgetSizeAutomatically: false,
  onScaleAdjustment: (scale) => {
    console.log("Zoom level:", scale);
    updateContent(scale);
  },
});

// For iframe or canvas content
const iframeTouch = new MultiTouchHelper({
  element: document.querySelector("iframe"),
  unlockHelper: true,
  enablePointerOverWidget: true,
});
```

## Constructors

### Constructor

```ts
new MultiTouchHelper(options?: MultiTouchHelperOptions): MultiTouchHelper;
```

Constructor for MultiTouchHelper.

#### Parameters

| Parameter | Type                                                                    | Description                                     |
| --------- | ----------------------------------------------------------------------- | ----------------------------------------------- |
| `options` | [`MultiTouchHelperOptions`](../type-aliases/MultiTouchHelperOptions.md) | Configuration options for the MultiTouchHelper. |

#### Returns

`MultiTouchHelper`

## Properties

### disabled

```ts
protected disabled: boolean = true;
```

---

### enableZoomOutButton

```ts
enableZoomOutButton: boolean = true;
```

Checks if the zoom-out button is enabled for this user (resets to default if not).

---

### eventDisableHelper

```ts
protected eventDisableHelper: EventDisableHelper;
```

---

### eventList

```ts
protected eventList: string[];
```

---

### htmlElement

```ts
readonly htmlElement: HTMLElement;
```

---

### DEBUG

```ts
static DEBUG: boolean = false;
```

## Accessors

### enableZoomOutButtonOption

#### Get Signature

```ts
get enableZoomOutButtonOption(): boolean;
```

Checks if the zoom-out button is enabled in the settings.

##### Returns

`boolean`

#### Set Signature

```ts
set enableZoomOutButtonOption(enable: boolean): void;
```

Sets the zoom-out button option in the settings.

##### Parameters

| Parameter | Type      | Description |
| --------- | --------- | ----------- |
| `enable`  | `boolean` | -           |

##### Returns

`void`

---

### settingsDialogContent

#### Get Signature

```ts
get settingsDialogContent(): FormlyFieldConfig<FormlyFieldProps>[];
```

##### Returns

`FormlyFieldConfig`\<`FormlyFieldProps`\>[]

## Methods

### adjustScaleTransform()

```ts
adjustScaleTransform(): void;
```

Adjusts the scale transform of the widget.

#### Returns

`void`

---

### destroy()

```ts
destroy(): void;
```

Destroys the MultiTouchHelper, stopping all managed interactions and observers.

#### Returns

`void`

---

### hideZoomOut()

```ts
protected hideZoomOut(): void;
```

Hides the zoom-out button.

#### Returns

`void`

---

### showZoomOut()

```ts
protected showZoomOut(): void;
```

Shows the zoom-out button.

#### Returns

`void`

---

### start()

```ts
start(): void;
```

Starts the MultiTouchHelper, enabling managed interactions.

#### Returns

`void`

---

### stop()

```ts
stop(): void;
```

Stops the MultiTouchHelper, disabling managed interactions.

#### Returns

`void`

---

### updateUnlockHelperIcon()

```ts
protected updateUnlockHelperIcon(locked?: boolean): void;
```

Updates the unlock helper icon.

#### Parameters

| Parameter | Type      | Default value | Description                                                                           |
| --------- | --------- | ------------- | ------------------------------------------------------------------------------------- |
| `locked`  | `boolean` | `undefined`   | specifies if the icon should be shown or hidden (undefined means automatic detection) |

#### Returns

`void`

---

### updateZoomOutButtonStatus()

```ts
updateZoomOutButtonStatus(): void;
```

Updates the visibility status of the zoom-out button.

#### Returns

`void`

---

### zoomOutToElement()

```ts
protected zoomOutToElement(): void;
```

Zooms out to the element.

#### Returns

`void`

---

### zoomOutVisible()

```ts
protected zoomOutVisible(): boolean;
```

Checks if the zoom-out button should be visible.

#### Returns

`boolean`

True if the zoom-out button should be visible, false otherwise.

---

### dispatchPointerEvent()

```ts
static dispatchPointerEvent(event: string | PointerEvent): void;
```

Dispatches a pointer event to the widget's root node.

#### Parameters

| Parameter | Type                       | Description            |
| --------- | -------------------------- | ---------------------- |
| `event`   | `string` \| `PointerEvent` | The event to dispatch. |

#### Returns

`void`

---

### resizeObserver()

```ts
static resizeObserver(obj: HTMLElement, callback: ResizeObserverCallback): ResizeObserver;
```

Creates a safe ResizeObserver for the given element.

#### Parameters

| Parameter  | Type                     | Description                                          |
| ---------- | ------------------------ | ---------------------------------------------------- |
| `obj`      | `HTMLElement`            | The element to observe.                              |
| `callback` | `ResizeObserverCallback` | The callback to execute when the element is resized. |

#### Returns

`ResizeObserver`

The created ResizeObserver.
