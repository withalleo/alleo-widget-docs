[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / BoardTextElementHelper

# Class: BoardTextElementHelper

Provides utilities for reading and writing text content from various board objects.

Handles text extraction and manipulation across multiple object types including containers,
sticky notes, notepads, text labels, and text-based widgets. Supports multiple formats
(plain text, HTML, Markdown) and provides consistent APIs for heterogeneous object types.
Essential for widgets that need to process or generate text content from board objects.

## Example

```typescript
// Check if object supports text operations
const obj = BoardObjectHelper.getBoardObjectById(objectId);
if (BoardTextElementHelper.isSupported(obj)) {
  // Get text content
  const texts = await BoardTextElementHelper.getTextContent(obj, {
    format: TextInputFormat.Text
  });
  console.log('Text:', texts.join('\n'));

  // Set text content
  await BoardTextElementHelper.setTextContent(obj, ['New content'], {
    format: TextInputFormat.Text,
    append: false
  });
}

// Extract text from container and all children
const containerText = await BoardTextElementHelper.getTextContent(containerObj);
```

## Constructors

### Constructor

> **new BoardTextElementHelper**(): `BoardTextElementHelper`

#### Returns

`BoardTextElementHelper`

## Methods

### getTextContent()

> `static` **getTextContent**(`object`, `options?`): `Promise`\<`string`[]\>

Extracts text content from a board object in the specified format.

Recursively extracts text from containers (including child objects), retrieves
content from notepads, sticky notes, text labels, and text-based widgets.
Returns an array of text strings, one per object or content section.

#### Parameters

##### object

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object to extract text from.

##### options?

[`GetTextContentOptions`](../type-aliases/GetTextContentOptions.md) = `{}`

Configuration for text extraction.

#### Returns

`Promise`\<`string`[]\>

Array of text strings extracted from the object and its children.

#### Static

***

### isSupported()

> `static` **isSupported**(`object`): `boolean`

Determines if a board object supports text content operations.

Checks if the object is one of the supported types: Container, StickyNote, Text label,
Notepad, or text-based widgets (string, number, boolean). Use this before attempting
text operations to ensure compatibility.

#### Parameters

##### object

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object to check for text support.

#### Returns

`boolean`

True if text operations are supported, false otherwise.

#### Static

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
