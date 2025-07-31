[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / BoardTextElementHelper

# Class: BoardTextElementHelper

A helper class for handling text element-related operations on the board.

## Constructors

### Constructor

> **new BoardTextElementHelper**(): `BoardTextElementHelper`

#### Returns

`BoardTextElementHelper`

## Methods

### getTextContent()

> `static` **getTextContent**(`object`, `options?`): `Promise`\<`string`[]\>

Gets the text content of a board object.

#### Parameters

##### object

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object.

##### options?

[`GetTextContentOptions`](../type-aliases/GetTextContentOptions.md) = `{}`

The options for getting text content.

#### Returns

`Promise`\<`string`[]\>

The text content of the board object.

***

### isSupported()

> `static` **isSupported**(`object`): `boolean`

Checks if the given board object is a supported object type for text content operations.
Supported types include Container, StickyNote, Notepad, Label (Text) and certain Widgets.

#### Parameters

##### object

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object to check.

#### Returns

`boolean`

True if the object is supported, false otherwise.

***

### setTextContent()

> `static` **setTextContent**(`object`, `text`, `options?`): `Promise`\<`void`\>

Sets the text content of a board object.

#### Parameters

##### object

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object.

##### text

`string`[]

The text content to set.

##### options?

[`SetTextContentOptions`](../type-aliases/SetTextContentOptions.md) = `{}`

The options for setting text content.

#### Returns

`Promise`\<`void`\>

#### Throws

Will throw an error if the object type is unsupported for writing text content.
