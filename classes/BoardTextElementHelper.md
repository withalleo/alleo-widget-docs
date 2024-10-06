[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / BoardTextElementHelper

# Class: BoardTextElementHelper

A helper class for handling text element-related operations on the board.

## Constructors

### new BoardTextElementHelper()

> **new BoardTextElementHelper**(): [`BoardTextElementHelper`](BoardTextElementHelper.md)

#### Returns

[`BoardTextElementHelper`](BoardTextElementHelper.md)

## Methods

### getTextContent()

> `static` **getTextContent**(`object`, `options`?): `Promise`\<`string`[]\>

Gets the text content of a board object.

#### Parameters

• **object**: [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object.

• **options?**: [`GetTextContentOptions`](../type-aliases/GetTextContentOptions.md) = `{}`

The options for getting text content.

#### Returns

`Promise`\<`string`[]\>

The text content of the board object.

***

### setTextContent()

> `static` **setTextContent**(`object`, `text`, `options`?): `Promise`\<`void`\>

Sets the text content of a board object.

#### Parameters

• **object**: [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object.

• **text**: `string`[]

The text content to set.

• **options?**: [`SetTextContentOptions`](../type-aliases/SetTextContentOptions.md) = `{}`

The options for setting text content.

#### Returns

`Promise`\<`void`\>

#### Throws

Will throw an error if the object type is unsupported for writing text content.
