[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / WidgetDetails

# Class: WidgetDetails

Helper class for managing widget label, visibility, and search description.

## Constructors

### Constructor

> **new WidgetDetails**(): `WidgetDetails`

#### Returns

`WidgetDetails`

## Accessors

### hideLabel

#### Get Signature

> **get** `static` **hideLabel**(): `boolean`

Gets whether the widget label is hidden.

##### Returns

`boolean`

#### Set Signature

> **set** `static` **hideLabel**(`hide`): `void`

Sets whether the widget label is hidden.

##### Parameters

###### hide

`boolean`

True to hide the label, false to show.

##### Returns

`void`

***

### label

#### Get Signature

> **get** `static` **label**(): `string`

Gets the widget label (caption text).

##### Returns

`string`

#### Set Signature

> **set** `static` **label**(`title`): `void`

Sets the widget label (caption text).
Truncates to 250 characters if needed.

##### Parameters

###### title

`string`

The label to set.

##### Returns

`void`

***

### searchDescription

#### Set Signature

> **set** `static` **searchDescription**(`description`): `void`

Sets the widget search description. Falls back to hiding label and setting label if not supported.

##### Parameters

###### description

`string`

The search description to set.

##### Returns

`void`
