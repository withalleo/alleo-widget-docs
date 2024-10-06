[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / BoardNotepadHelper

# Class: BoardNotepadHelper

A helper class for handling notepad-related operations on the board.

## Constructors

### new BoardNotepadHelper()

> **new BoardNotepadHelper**(`notepad`): [`BoardNotepadHelper`](BoardNotepadHelper.md)

Creates an instance of BoardNotepadHelper.

#### Parameters

• **notepad**: [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The notepad object.

#### Returns

[`BoardNotepadHelper`](BoardNotepadHelper.md)

#### Throws

Will throw an error if the widget DOM is not available or the notepad is not found.

## Properties

### notepad

> **notepad**: [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The notepad object.

## Methods

### appendContent()

> **appendContent**(`content`, `inputFormat`?): `Promise`\<`void`\>

Appends content to the notepad.

#### Parameters

• **content**: `string` \| `string`[]

The content to append.

• **inputFormat?**: [`TextInputFormat`](../enumerations/TextInputFormat.md) = `TextInputFormat.Text`

The format of the content.

#### Returns

`Promise`\<`void`\>

***

### getContent()

> **getContent**(`inputFormat`?): `Promise`\<`string`\>

Gets the content of the notepad.

#### Parameters

• **inputFormat?**: [`Text`](../enumerations/TextInputFormat.md#text) \| [`Html`](../enumerations/TextInputFormat.md#html) = `TextInputFormat.Text`

The format of the content.

#### Returns

`Promise`\<`string`\>

The content of the notepad.

***

### replaceContent()

> **replaceContent**(`content`, `inputFormat`?): `Promise`\<`void`\>

Replaces the content of the notepad.

#### Parameters

• **content**: `string` \| `string`[]

The new content.

• **inputFormat?**: [`TextInputFormat`](../enumerations/TextInputFormat.md) = `TextInputFormat.Text`

The format of the content.

#### Returns

`Promise`\<`void`\>

***

### getNotepadLabel()

> `static` **getNotepadLabel**(`notepadObject`, `len`?): `string`

Gets the label of the notepad.

#### Parameters

• **notepadObject**: [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The notepad object.

• **len?**: `number` = `30`

The maximum length of the label. (an extra "..." might be added)

#### Returns

`string`

The notepad label.

***

### isNotepad()

> `static` **isNotepad**(`obj`): `boolean`

Checks if the given object is a notepad.

#### Parameters

• **obj**: [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The object to check.

#### Returns

`boolean`

True if the object is a notepad, false otherwise.
