[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / widgetHasDom

# Function: widgetHasDom()

```ts
function widgetHasDom(h?: IWidgetApi | IWidgetServiceApi): h is IWidgetApi;
```

Type guard to determine if the current widget has a DOM presence (is a board object vs. a service).

Alleo widgets can be either board objects (visible on the canvas with DOM) or services
(background processes without visual representation). This function checks which type
the widget is and narrows the TypeScript type accordingly.

## Parameters

| Parameter | Type                                | Default value | Description                       |
| --------- | ----------------------------------- | ------------- | --------------------------------- |
| `h?`      | `IWidgetApi` \| `IWidgetServiceApi` | `haptic`      | The widget API instance to check. |

## Returns

`h is IWidgetApi`

True if the widget has DOM (is a board object), false if it's a service.

## Example

```typescript
if (widgetHasDom(haptic)) {
  // TypeScript knows haptic.rootNode exists
  const container = haptic.rootNode.querySelector(".container");
} else {
  // Widget is a service, no DOM available
  console.log("Running as background service");
}
```
