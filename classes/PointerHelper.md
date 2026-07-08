[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / PointerHelper

# Class: PointerHelper

Manages pointer events with support for click, alt-click, and long-press detection.

Provides a unified interface for handling various pointer interactions including normal clicks,
alt/ctrl-modified clicks, and long-press gestures. Automatically filters out invalid clicks
based on pressure and timing. Useful for implementing context menus, alternate actions,
and touch-friendly interactions.

## Example

```typescript
const element = document.querySelector(".interactive-area");
const pointer = new PointerHelper(element);

// Handle normal clicks
pointer.registerOnclick((e) => {
  console.log("Clicked at:", e.clientX, e.clientY);
  performAction();
});

// Handle alt-click or long-press for context menu
pointer.registerOnAltClick((e) => {
  console.log("Alt-click detected");
  showContextMenu(e);
});
```

## Constructors

### Constructor

```ts
new PointerHelper(element: HTMLElement): PointerHelper;
```

Creates a PointerHelper instance for managing pointer interactions on an element.

Attaches pointer event listeners to track down, up, cancel, leave, and out events.
Automatically manages pointer state and distinguishes between different interaction types.

#### Parameters

| Parameter | Type          | Description                                           |
| --------- | ------------- | ----------------------------------------------------- |
| `element` | `HTMLElement` | The HTML element to attach pointer event handlers to. |

#### Returns

`PointerHelper`

## Properties

### altCallbacks

```ts
protected altCallbacks: (e: PointerEvent) => void[] = [];
```

Registered alt-click callbacks.

#### Parameters

| Parameter | Type           |
| --------- | -------------- |
| `e`       | `PointerEvent` |

#### Returns

`void`

---

### callbacks

```ts
protected callbacks: (e: PointerEvent) => void[] = [];
```

Registered click callbacks.

#### Parameters

| Parameter | Type           |
| --------- | -------------- |
| `e`       | `PointerEvent` |

#### Returns

`void`

---

### element

```ts
protected element: HTMLElement;
```

The HTML element to attach pointer event handlers to.

## Methods

### onAltClick()

```ts
protected onAltClick(e: PointerEvent): void;
```

Invokes all registered alt-click callbacks.

#### Parameters

| Parameter | Type           | Description                                     |
| --------- | -------------- | ----------------------------------------------- |
| `e`       | `PointerEvent` | The pointer event that triggered the alt-click. |

#### Returns

`void`

---

### onClick()

```ts
protected onClick(e: PointerEvent): void;
```

Invokes all registered normal click callbacks.

#### Parameters

| Parameter | Type           | Description                                 |
| --------- | -------------- | ------------------------------------------- |
| `e`       | `PointerEvent` | The pointer event that triggered the click. |

#### Returns

`void`

---

### registerOnAltClick()

```ts
registerOnAltClick(callback: (e: PointerEvent) => void): void;
```

Registers a callback function for alt-click or long-press events.

Triggered by clicks with Alt/Ctrl modifiers or by pressing and holding for
more than 700ms. Useful for context menus or alternative actions. Multiple
callbacks can be registered.

#### Parameters

| Parameter  | Type                            | Description                                                  |
| ---------- | ------------------------------- | ------------------------------------------------------------ |
| `callback` | (`e`: `PointerEvent`) => `void` | Function to execute on alt-click, receives the PointerEvent. |

#### Returns

`void`

---

### registerOnclick()

```ts
registerOnclick(callback: (e: PointerEvent) => void): void;
```

Registers a callback function to be invoked on normal click events.

Normal clicks are pointer events that don't have alt/ctrl modifiers and aren't
long-presses. Multiple callbacks can be registered.

#### Parameters

| Parameter  | Type                            | Description                                              |
| ---------- | ------------------------------- | -------------------------------------------------------- |
| `callback` | (`e`: `PointerEvent`) => `void` | Function to execute on click, receives the PointerEvent. |

#### Returns

`void`
