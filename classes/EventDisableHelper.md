[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / EventDisableHelper

# Class: EventDisableHelper

Manages temporary disabling and re-enabling of DOM events on HTML elements.

Provides fine-grained control over event handling, allowing widgets to selectively disable
events like dragging, scrolling, or pointer interactions. Automatically manages event state
based on widget interactability. Useful for implementing custom interactions that need to
temporarily prevent default browser behaviors. Stores and restores original event listeners.

## Example

```typescript
const element = document.querySelector('.interactive');

// Disable all pointer events
const pointerDisabler = new EventDisableHelper(
  element,
  EventDisableHelper.POINTER_EVENTS
);

// Disable scroll events with auto-management
const scrollDisabler = new EventDisableHelper(
  element,
  EventDisableHelper.SCROLL_EVENTS,
  { autoManage: true }
);

// Manually control event disabling
const customDisabler = new EventDisableHelper(element, ['click', 'dblclick'], {
  autoManage: false,
  callback: (e) => console.log('Event prevented:', e.type)
});
customDisabler.disable();
// ... do work ...
customDisabler.enable();
```

## Constructors

### Constructor

> **new EventDisableHelper**(`element?`, `events?`, `options?`): `EventDisableHelper`

Constructor for EventDisableHelper.

#### Parameters

##### element?

`HTMLElement` \| `Window`

The HTML element or window to which events are attached.

##### events?

`string`[] = `EventDisableHelper.POINTER_EVENTS`

List of events to be managed.

##### options?

[`EventDisableHelperOptions`](../type-aliases/EventDisableHelperOptions.md) = `{}`

Options for the EventDisableHelper.

#### Returns

`EventDisableHelper`

## Properties

### disabled

> **disabled**: `boolean` = `false`

Flag indicating whether events are disabled.

***

### events

> **events**: `string`[]

List of events to be managed.

***

### htmlElement

> `protected` **htmlElement**: `HTMLElement` \| `Window`

The HTML element or window to which events are attached.

***

### ALL\_EVENTS

> `static` **ALL\_EVENTS**: `string`[]

A list of all events.

***

### EXTENDED\_EVENTS

> `static` **EXTENDED\_EVENTS**: `string`[]

A list of all events that have been ever used in Alleo... waaaay overkill usually.

***

### KEYBOARD\_EVENTS

> `static` **KEYBOARD\_EVENTS**: `string`[]

A list of keyboard related events.

***

### MULTI\_TOUCH\_EVENTS

> `static` **MULTI\_TOUCH\_EVENTS**: `string`[]

A list of JavaScript events that are related to multi-touch.

***

### POINTER\_EVENTS

> `static` **POINTER\_EVENTS**: `string`[]

A list of pointer events to enable dragging.

***

### ~~POINTER\_EVENTS\_EXTENDED~~

> `static` **POINTER\_EVENTS\_EXTENDED**: `string`[] = `EventDisableHelper.POINTER_EVENTS_MULTI_TOUCH`

#### Deprecated

Use MULTI_TOUCH_EVENTS instead.

***

### POINTER\_EVENTS\_NO\_UNLOCK

> `static` **POINTER\_EVENTS\_NO\_UNLOCK**: `string`[]

A list of pointer events to enable dragging without unlocking.

***

### SCROLL\_EVENTS

> `static` **SCROLL\_EVENTS**: `string`[]

A list of scrolling related events.

## Methods

### autoManage()

> **autoManage**(): `void`

Automatically manages events based on the interactibility of the widget.

#### Returns

`void`

***

### destroy()

> **destroy**(): `void`

Destroys the EventDisableHelper instance, stopping auto-management and enabling all events.

#### Returns

`void`

***

### disableEvents()

> **disableEvents**(`events?`, `preventDefault?`, `stopPropagation?`, `stopImmediatePropagation?`, `capture?`): `void`

Disables events on the element.

#### Parameters

##### events?

`string`[] = `...`

List of events to be disabled.

##### preventDefault?

`boolean` = `false`

Whether to call preventDefault on the event.

##### stopPropagation?

`boolean` = `true`

Whether to call stopPropagation on the event.

##### stopImmediatePropagation?

`boolean` = `false`

Whether to call stopImmediatePropagation on the event.

##### capture?

`boolean` = `false`

Whether to capture the event.

#### Returns

`void`

***

### enableEvents()

> **enableEvents**(`events?`): `void`

Enables events on the element.

#### Parameters

##### events?

`string`[] = `...`

List of events to be enabled.

#### Returns

`void`

***

### stopAutoManage()

> **stopAutoManage**(): `void`

Stops automatically managing events.

#### Returns

`void`

***

### cancelEvent()

> `static` **cancelEvent**(`e`, `preventDefault?`, `stopPropagation?`, `stopImmediatePropagation?`, `callback?`): `void`

Cancels an event.

#### Parameters

##### e

`Event`

The event to be cancelled.

##### preventDefault?

`boolean` = `true`

Whether to call preventDefault on the event.

##### stopPropagation?

`boolean` = `true`

Whether to call stopPropagation on the event.

##### stopImmediatePropagation?

`boolean` = `true`

Whether to call stopImmediatePropagation on the event.

##### callback?

(`e`) => `void`

A callback to be called when the event is cancelled.

#### Returns

`void`

***

### makeDraggable()

> `static` **makeDraggable**(`element`): `void`

Makes an element draggable.

#### Parameters

##### element

`HTMLElement`

The element to be made draggable.

#### Returns

`void`
