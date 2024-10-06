[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / MultiTouchHelperOptions

# Type Alias: MultiTouchHelperOptions

> **MultiTouchHelperOptions**: `object`

Options for configuring the MultiTouchHelper.

## Type declaration

### adjustWidgetSizeAutomatically?

> `optional` **adjustWidgetSizeAutomatically**: `boolean`

If true, the widget size will not be adjusted automatically when the zoom level changes (default: true)

### autoManage?

> `optional` **autoManage**: `boolean`

If true, the MultiTouchHelper will automatically manage the touch interactions (default: true)

### element?

> `optional` **element**: `HTMLElement`

The element that will be manipulated (default: the whole widget)

### enableDblClickToZoom?

> `optional` **enableDblClickToZoom**: `boolean`

Enable to double-click to zoom into the widget (default: false)

### enablePointerOverWidget?

> `optional` **enablePointerOverWidget**: `boolean`

If true, the pointer over widget will be shown (default: false)

### eventList?

> `optional` **eventList**: `string`[]

A list of events that will be disabled when the MultiTouchHelper is enabled

### onScaleAdjustment()?

> `optional` **onScaleAdjustment**: (`scale`) => `void`

A callback function that will be called when the scale is adjusted

#### Parameters

• **scale**: `number`

#### Returns

`void`

### showAdjustSizeButton?

> `optional` **showAdjustSizeButton**: `boolean`

If true, a button will be shown to adjust the widget size manually (default: false)
