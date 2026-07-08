[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / EventDisableHelper

# Class: EventDisableHelper

Manages temporary disabling and re-enabling of DOM events on HTML elements.

Provides fine-grained control over event handling, allowing widgets to selectively disable
events like dragging, scrolling, or pointer interactions. Automatically manages event state
based on widget interactability. Useful for implementing custom interactions that need to
temporarily prevent default browser behaviors. Stores and restores original event listeners.

## Example

```typescript
const element = document.querySelector(".interactive");

// Disable all pointer events
const pointerDisabler = new EventDisableHelper(
  element,
  EventDisableHelper.POINTER_EVENTS,
);

// Disable scroll events with auto-management
const scrollDisabler = new EventDisableHelper(
  element,
  EventDisableHelper.SCROLL_EVENTS,
  { autoManage: true },
);

// Manually control event disabling
const customDisabler = new EventDisableHelper(element, ["click", "dblclick"], {
  autoManage: false,
  callback: (e) => console.log("Event prevented:", e.type),
});
customDisabler.disable();
// ... do work ...
customDisabler.enable();
```

## Constructors

### Constructor

```ts
new EventDisableHelper(
   element?: HTMLElement | Window,
   events?: string[],
   options?: EventDisableHelperOptions): EventDisableHelper;
```

Constructor for EventDisableHelper.

#### Parameters

| Parameter | Type                                                                        | Default value                       | Description                                              |
| --------- | --------------------------------------------------------------------------- | ----------------------------------- | -------------------------------------------------------- |
| `element` | `HTMLElement` \| `Window`                                                   | `...`                               | The HTML element or window to which events are attached. |
| `events`  | `string`[]                                                                  | `EventDisableHelper.POINTER_EVENTS` | List of events to be managed.                            |
| `options` | [`EventDisableHelperOptions`](../type-aliases/EventDisableHelperOptions.md) | `{}`                                | Options for the EventDisableHelper.                      |

#### Returns

`EventDisableHelper`

## Properties

### disabled

```ts
disabled: boolean = false;
```

Flag indicating whether events are disabled.

---

### events

```ts
events: string[];
```

List of events to be managed.

---

### htmlElement

```ts
protected htmlElement: HTMLElement | Window;
```

The HTML element or window to which events are attached.

---

### ALL\_EVENTS

```ts
static ALL_EVENTS: string[];
```

A list of all events.

---

### EXTENDED\_EVENTS

```ts
static EXTENDED_EVENTS: string[];
```

A list of all events that have been ever used in Alleo... waaaay overkill usually.

---

### KEYBOARD\_EVENTS

```ts
static KEYBOARD_EVENTS: string[];
```

A list of keyboard related events.

---

### MULTI\_TOUCH\_EVENTS

```ts
static MULTI_TOUCH_EVENTS: string[];
```

A list of JavaScript events that are related to multi-touch.

---

### POINTER\_EVENTS

```ts
static POINTER_EVENTS: string[];
```

A list of pointer events to enable dragging.

---

### ~~POINTER\_EVENTS\_EXTENDED~~

```ts
static POINTER_EVENTS_EXTENDED: string[] = EventDisableHelper.POINTER_EVENTS_MULTI_TOUCH;
```

#### Deprecated

Use MULTI_TOUCH_EVENTS instead.

---

### POINTER\_EVENTS\_NO\_UNLOCK

```ts
static POINTER_EVENTS_NO_UNLOCK: string[];
```

A list of pointer events to enable dragging without unlocking.

---

### SCROLL\_EVENTS

```ts
static SCROLL_EVENTS: string[];
```

A list of scrolling related events.

## Methods

### autoManage()

```ts
autoManage(): void;
```

Automatically manages events based on the interactibility of the widget.

#### Returns

`void`

---

### destroy()

```ts
destroy(): void;
```

Destroys the EventDisableHelper instance, stopping auto-management and enabling all events.

#### Returns

`void`

---

### disableEvents()

```ts
disableEvents(
   events?: string[],
   preventDefault?: boolean,
   stopPropagation?: boolean,
   stopImmediatePropagation?: boolean,
   capture?: boolean): void;
```

Disables events on the element.

#### Parameters

| Parameter                  | Type       | Default value | Description                                            |
| -------------------------- | ---------- | ------------- | ------------------------------------------------------ |
| `events`                   | `string`[] | `...`         | List of events to be disabled.                         |
| `preventDefault`           | `boolean`  | `false`       | Whether to call preventDefault on the event.           |
| `stopPropagation`          | `boolean`  | `true`        | Whether to call stopPropagation on the event.          |
| `stopImmediatePropagation` | `boolean`  | `false`       | Whether to call stopImmediatePropagation on the event. |
| `capture`                  | `boolean`  | `false`       | Whether to capture the event.                          |

#### Returns

`void`

---

### enableEvents()

```ts
enableEvents(events?: string[]): void;
```

Enables events on the element.

#### Parameters

| Parameter | Type       | Description                   |
| --------- | ---------- | ----------------------------- |
| `events`  | `string`[] | List of events to be enabled. |

#### Returns

`void`

---

### stopAutoManage()

```ts
stopAutoManage(): void;
```

Stops automatically managing events.

#### Returns

`void`

---

### cancelEvent()

```ts
static cancelEvent(
   e: Event,
   preventDefault?: boolean,
   stopPropagation?: boolean,
   stopImmediatePropagation?: boolean,
   callback?: (e: Event) => void): void;
```

Cancels an event.

#### Parameters

| Parameter                  | Type                     | Default value | Description                                            |
| -------------------------- | ------------------------ | ------------- | ------------------------------------------------------ |
| `e`                        | `Event`                  | `undefined`   | The event to be cancelled.                             |
| `preventDefault`           | `boolean`                | `true`        | Whether to call preventDefault on the event.           |
| `stopPropagation`          | `boolean`                | `true`        | Whether to call stopPropagation on the event.          |
| `stopImmediatePropagation` | `boolean`                | `true`        | Whether to call stopImmediatePropagation on the event. |
| `callback`                 | (`e`: `Event`) => `void` | `undefined`   | A callback to be called when the event is cancelled.   |

#### Returns

`void`

---

### makeDraggable()

```ts
static makeDraggable(element: HTMLElement): void;
```

Makes an element draggable.

#### Parameters

| Parameter | Type          | Description                       |
| --------- | ------------- | --------------------------------- |
| `element` | `HTMLElement` | The element to be made draggable. |

#### Returns

`void`
