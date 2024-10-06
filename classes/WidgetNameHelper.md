[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / WidgetNameHelper

# Class: WidgetNameHelper

Helper class for managing widget names.

## Constructors

### new WidgetNameHelper()

> **new WidgetNameHelper**(`preferredName`, `currentNote`): [`WidgetNameHelper`](WidgetNameHelper.md)

Sets up the name of the widget.

#### Parameters

• **preferredName**: `string` = `undefined`

The preferred name for the widget.

• **currentNote**: `string` = `undefined`

The current note of the widget.

#### Returns

[`WidgetNameHelper`](WidgetNameHelper.md)

## Accessors

### name

> `get` **name**(): `string`

Gets the name of the widget.

> `set` **name**(`name`): `void`

Sets the name of the widget.

#### Parameters

• **name**: `string`

The new name of the widget.

#### Returns

`string`

The name of the widget.

***

### note

> `get` **note**(): `string`

Gets the note associated with the widget.

> `set` **note**(`note`): `void`

Sets the note associated with the widget.

#### Parameters

• **note**: `string`

The new note for the widget.

#### Returns

`string`

The note associated with the widget.

***

### displayName

> `get` `static` **displayName**(): `string`

Gets the display name of the widget.

#### Returns

`string`

The display name of the widget.

***

### manifest

> `get` `static` **manifest**(): `Record`\<`string`, `any`\>

Gets the manifest of the widget.

#### Returns

`Record`\<`string`, `any`\>

The manifest of the widget.

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

> `static` **setOnlyNote**(`note`?): `void`

Sets the note for the widget.

#### Parameters

• **note?**: `string`

The note to set.

#### Returns

`void`
