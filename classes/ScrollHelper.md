[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / ScrollHelper

# Class: ScrollHelper

Manages scrolling behavior with optional cross-user synchronization.

Provides controlled scrolling for HTML elements within widgets, with support for
synchronizing scroll positions across multiple users viewing the same widget.
Can be configured to follow a leader's scrolling or allow independent scrolling.
Includes rate-limiting to prevent excessive updates during rapid scrolling.

## Example

```typescript
const scrollContainer = document.querySelector('.scrollable-content');

// Basic scroll management with synchronization
const scrollHelper = new ScrollHelper(scrollContainer);

// Scroll with custom settings
const customScroll = new ScrollHelper(
  scrollContainer,
  true,  // auto-enable
  true,  // sync scrolling
  false, // allow all users to control scroll
  false, // allow user scrolling
  'myScrollPosition'
);

// Programmatically scroll to position
scrollHelper.scrollTo({ x: 0, y: 100 });
```

## Constructors

### Constructor

> **new ScrollHelper**(`element`, `autoEnableScroll?`, `syncScrolling?`, `syncScrollingLeaderOnly?`, `disableUserScrolling?`, `sharedVariableName?`): `ScrollHelper`

Creates a ScrollHelper to manage scrolling behavior on an HTML element.

Sets up scroll event handling, synchronization listeners, and rate-limited
coordinate updates. Automatically enables scrolling unless specified otherwise.

#### Parameters

##### element

`HTMLElement`

The HTML element to make scrollable and manage.

##### autoEnableScroll?

`boolean` = `true`

Whether to enable scrolling immediately upon creation.

##### syncScrolling?

`boolean` = `true`

Whether to synchronize scroll position across users.

##### syncScrollingLeaderOnly?

`boolean` = `true`

When true, only the session leader can control scrolling. When false, any user can control it.

##### disableUserScrolling?

`boolean` = `false`

When true, prevents users from manually scrolling (programmatic scrolling still works).

##### sharedVariableName?

`string` = `'_AlleoWidget_ScrollHelper_coords'`

Shared variable name for storing scroll coordinates.

#### Returns

`ScrollHelper`

## Properties

### coordinates

> **coordinates**: [`Coordinates`](../type-aliases/Coordinates.md)

***

### disableUserScrolling

> **disableUserScrolling**: `boolean`

***

### enabled

> `protected` **enabled**: `boolean` = `false`

***

### eventDisableHelper

> `protected` `readonly` **eventDisableHelper**: [`EventDisableHelper`](EventDisableHelper.md)

***

### htmlElement

> `protected` `readonly` **htmlElement**: `HTMLElement`

***

### sharedVariableName

> `protected` `readonly` **sharedVariableName**: `string`

***

### syncScrolling

> **syncScrolling**: `boolean`

***

### syncScrollingLeaderOnly

> **syncScrollingLeaderOnly**: `boolean`

## Methods

### disableScroll()

> **disableScroll**(): `void`

Disables scrolling on the HTML element.

#### Returns

`void`

***

### enableScroll()

> **enableScroll**(): `void`

Enables scrolling on the HTML element.

#### Returns

`void`

***

### onScroll()

> `protected` **onScroll**(`event`): `void`

Handles the scroll event on the HTML element.

#### Parameters

##### event

`Event`

The scroll event.

#### Returns

`void`

***

### scrollTo()

> **scrollTo**(`coords`, `behavior?`): `void`

Scrolls the HTML element to the specified coordinates.

#### Parameters

##### coords

[`Coordinates`](../type-aliases/Coordinates.md)

The coordinates to scroll to.

##### behavior?

`"auto"` \| `"instant"` \| `"smooth"`

The scrolling behavior ('auto', 'smooth', or 'instant').

#### Returns

`void`

***

### scrollToSavedPosition()

> `protected` **scrollToSavedPosition**(): `void`

Scrolls the HTML element to the saved position.

#### Returns

`void`
