[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / getWidgetCoordinates

# Function: getWidgetCoordinates()

> **getWidgetCoordinates**(`event`): `Coordinates`

Retrieves the coordinates of a pointer event within the widget.

## Parameters

### event

The event to get coordinates from.

`PointerEvent` | `MouseEvent` | `Touch` | \{ `clientX`: `number`; `clientY`: `number`; \}

## Returns

`Coordinates`

The coordinates of the widget.

## Throws

Will throw an error if the widget does not have a DOM.
