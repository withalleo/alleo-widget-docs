[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / WidgetNameHelper

# Class: WidgetNameHelper

Helper class for managing widget names.

## Constructors

### Constructor

> **new WidgetNameHelper**(`preferredName`, `currentNote`): `WidgetNameHelper`

Sets up the name of the widget.

#### Parameters

##### preferredName

`string` = `undefined`

The preferred name for the widget.

##### currentNote

`string` = `undefined`

The current note of the widget.

#### Returns

`WidgetNameHelper`

## Accessors

### name

#### Get Signature

> **get** **name**(): `string`

Gets the name of the widget.

##### Returns

`string`

The name of the widget.

#### Set Signature

> **set** **name**(`name`): `void`

Sets the name of the widget.

##### Parameters

###### name

`string`

The new name of the widget.

##### Returns

`void`

***

### note

#### Get Signature

> **get** **note**(): `string`

Gets the note associated with the widget.

##### Returns

`string`

The note associated with the widget.

#### Set Signature

> **set** **note**(`note`): `void`

Sets the note associated with the widget.

##### Parameters

###### note

`string`

The new note for the widget.

##### Returns

`void`

***

### displayName

#### Get Signature

> **get** `static` **displayName**(): `string`

Gets the display name of the widget.

##### Returns

`string`

The display name of the widget.

***

### manifest

#### Get Signature

> **get** `static` **manifest**(): `Record`\<`string`, `any`\>

Gets the manifest of the widget.

##### Returns

`Record`\<`string`, `any`\>

The manifest of the widget.

***

### widgetId

#### Get Signature

> **get** `static` **widgetId**(): `string`

Gets the display name of the widget.

##### Returns

`string`

The display name of the widget.

## Methods

### getFullName()

> `protected` **getFullName**(): `string`

Gets the full name of the widget, including the note.

#### Returns

`string`

The full name of the widget.

***

### updateWidgetName()

> `protected` **updateWidgetName**(): `void`

Updates the widget name.

#### Returns

`void`

***

### setOnlyNote()

> `static` **setOnlyNote**(`note?`): `void`

Sets the note for the widget.

#### Parameters

##### note?

`string`

The note to set.

#### Returns

`void`
