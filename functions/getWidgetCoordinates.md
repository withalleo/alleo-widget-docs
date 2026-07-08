[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / getWidgetCoordinates

# Function: getWidgetCoordinates()

```ts
function getWidgetCoordinates(
  event:
    | PointerEvent
    | MouseEvent
    | Touch
    | {
        clientX: number;
        clientY: number;
      },
): Coordinates;
```

Converts browser viewport coordinates from a pointer event to widget-relative coordinates.

Takes a mouse/touch event and calculates the position within the widget's coordinate system,
accounting for widget scaling, rotation, and viewport position. Essential for accurate
pointer tracking in interactive widgets.

## Parameters

| Parameter | Type                                                                                            | Description                                                        |
| --------- | ----------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| `event`   | \| `PointerEvent` \| `MouseEvent` \| `Touch` \| \{ `clientX`: `number`; `clientY`: `number`; \} | The pointer/mouse event or object with clientX/clientY properties. |

## Returns

`Coordinates`

Object with x and y coordinates relative to the widget's top-left corner.

## Throws

Throws if the widget doesn't have a DOM (service widgets).

## Example

```typescript
element.addEventListener("click", (event) => {
  const coords = getWidgetCoordinates(event);
  console.log(`Clicked at widget position: ${coords.x}, ${coords.y}`);
  drawCircle(coords.x, coords.y);
});
```
