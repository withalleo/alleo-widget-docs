[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / EventDisableHelper

# Class: EventDisableHelper

Helper class to manage and disable events on HTML elements.

ie. to prevent dragging, scrolling, etc.

## Constructors

### new EventDisableHelper()

> **new EventDisableHelper**(`element`, `events`, `options`): [`EventDisableHelper`](EventDisableHelper.md)

Constructor for EventDisableHelper.

#### Parameters

• **element**: `HTMLElement` \| `Window` = `...`

The HTML element or window to which events are attached.

• **events**: `string`[] = `EventDisableHelper.POINTER_EVENTS`

List of events to be managed.

• **options**: [`EventDisableHelperOptions`](../type-aliases/EventDisableHelperOptions.md) = `{}`

Options for the EventDisableHelper.

#### Returns

[`EventDisableHelper`](EventDisableHelper.md)

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

> **disableEvents**(`events`, `preventDefault`, `stopPropagation`, `stopImmediatePropagation`, `capture`): `void`

Disables events on the element.

#### Parameters

• **events**: `string`[] = `...`

List of events to be disabled.

• **preventDefault**: `boolean` = `false`

Whether to call preventDefault on the event.

• **stopPropagation**: `boolean` = `true`

Whether to call stopPropagation on the event.

• **stopImmediatePropagation**: `boolean` = `false`

Whether to call stopImmediatePropagation on the event.

• **capture**: `boolean` = `false`

Whether to capture the event.

#### Returns

`void`

***

### enableEvents()

> **enableEvents**(`events`): `void`

Enables events on the element.

#### Parameters

• **events**: `string`[] = `...`

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

> `static` **cancelEvent**(`e`, `preventDefault`, `stopPropagation`, `stopImmediatePropagation`, `callback`): `void`

Cancels an event.

#### Parameters

• **e**: `Event`

The event to be cancelled.

• **preventDefault**: `boolean` = `true`

Whether to call preventDefault on the event.

• **stopPropagation**: `boolean` = `true`

Whether to call stopPropagation on the event.

• **stopImmediatePropagation**: `boolean` = `true`

Whether to call stopImmediatePropagation on the event.

• **callback** = `undefined`

A callback to be called when the event is cancelled.

#### Returns

`void`

***

### makeDraggable()

> `static` **makeDraggable**(`element`): `void`

Makes an element draggable.

#### Parameters

• **element**: `HTMLElement`

The element to be made draggable.

#### Returns

`void`
