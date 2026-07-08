[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / MultiTouchHelperOptions

# Type Alias: MultiTouchHelperOptions

```ts
type MultiTouchHelperOptions = {
  adjustWidgetSizeAutomatically?: boolean;
  autoManage?: boolean;
  element?: HTMLElement;
  enableDblClickToZoom?: boolean;
  enablePointerOverWidget?: boolean;
  eventList?: string[];
  onScaleAdjustment?: (scale: number) => void;
  showAdjustSizeButton?: boolean;
  unlockHelper?: boolean;
  zoomOutButtonId?: string;
};
```

Options for configuring the MultiTouchHelper.

## Properties

### adjustWidgetSizeAutomatically?

```ts
optional adjustWidgetSizeAutomatically?: boolean;
```

If true, the widget size will not be adjusted automatically when the zoom level changes (default: true)

---

### autoManage?

```ts
optional autoManage?: boolean;
```

If true, the MultiTouchHelper will automatically manage the touch interactions (default: true)

---

### element?

```ts
optional element?: HTMLElement;
```

The element that will be manipulated (default: the whole widget)

---

### enableDblClickToZoom?

```ts
optional enableDblClickToZoom?: boolean;
```

Enable to double-click to zoom into the widget (default: false)

---

### enablePointerOverWidget?

```ts
optional enablePointerOverWidget?: boolean;
```

If true, the pointer over widget will be shown (default: false)

---

### eventList?

```ts
optional eventList?: string[];
```

A list of events that will be disabled when the MultiTouchHelper is enabled

---

### onScaleAdjustment?

```ts
optional onScaleAdjustment?: (scale: number) => void;
```

A callback function that will be called when the scale is adjusted

#### Parameters

| Parameter | Type     |
| --------- | -------- |
| `scale`   | `number` |

#### Returns

`void`

---

### showAdjustSizeButton?

```ts
optional showAdjustSizeButton?: boolean;
```

If true, a button will be shown to adjust the widget size manually (default: false)

---

### unlockHelper?

```ts
optional unlockHelper?: boolean;
```

If true, the widget will display an unlock helper icon for editors. This might be practical when the widget content is not propagating out. (ie. an iframe) (default: false)

---

### zoomOutButtonId?

```ts
optional zoomOutButtonId?: string;
```

the id of the zoom out button data fiueld
