[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / MultiTouchHelperOptions

# Type Alias: MultiTouchHelperOptions

> **MultiTouchHelperOptions** = `object`

Options for configuring the MultiTouchHelper.

## Properties

### adjustWidgetSizeAutomatically?

> `optional` **adjustWidgetSizeAutomatically?**: `boolean`

If true, the widget size will not be adjusted automatically when the zoom level changes (default: true)

***

### autoManage?

> `optional` **autoManage?**: `boolean`

If true, the MultiTouchHelper will automatically manage the touch interactions (default: true)

***

### element?

> `optional` **element?**: `HTMLElement`

The element that will be manipulated (default: the whole widget)

***

### enableDblClickToZoom?

> `optional` **enableDblClickToZoom?**: `boolean`

Enable to double-click to zoom into the widget (default: false)

***

### enablePointerOverWidget?

> `optional` **enablePointerOverWidget?**: `boolean`

If true, the pointer over widget will be shown (default: false)

***

### eventList?

> `optional` **eventList?**: `string`[]

A list of events that will be disabled when the MultiTouchHelper is enabled

***

### onScaleAdjustment?

> `optional` **onScaleAdjustment?**: (`scale`) => `void`

A callback function that will be called when the scale is adjusted

#### Parameters

##### scale

`number`

#### Returns

`void`

***

### showAdjustSizeButton?

> `optional` **showAdjustSizeButton?**: `boolean`

If true, a button will be shown to adjust the widget size manually (default: false)

***

### unlockHelper?

> `optional` **unlockHelper?**: `boolean`

If true, the widget will display an unlock helper icon for editors. This might be practical when the widget content is not propagating out. (ie. an iframe) (default: false)

***

### zoomOutButtonId?

> `optional` **zoomOutButtonId?**: `string`

the id of the zoom out button data fiueld
