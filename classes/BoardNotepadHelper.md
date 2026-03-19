[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / BoardNotepadHelper

# Class: BoardNotepadHelper

Provides utilities for interacting with collaborative notepad objects on the board.

Enables widgets to read, write, and manipulate content in Alleo's collaborative notepads.
Supports multiple input/output formats (plain text, Markdown, HTML) and handles the
underlying collaborative editing infrastructure. Essential for widgets that need to
integrate with or manipulate notepad content programmatically.

## Example

```typescript
// Get notepad from board
const notepadObj = BoardObjectHelper.getBoardObjectById(notepadId);

// Check if object is a notepad
if (BoardNotepadHelper.isNotepad(notepadObj)) {
  const notepadHelper = new BoardNotepadHelper(notepadObj);

  // Read content
  const text = await notepadHelper.getText();
  console.log('Notepad content:', text);

  // Write content
  await notepadHelper.setText('New content', TextInputFormat.Markdown);

  // Get notepad label
  const label = BoardNotepadHelper.getNotepadLabel(notepadObj);
}
```

## Constructors

### Constructor

> **new BoardNotepadHelper**(`notepad`): `BoardNotepadHelper`

Creates a BoardNotepadHelper instance for manipulating a specific notepad.

Initializes the helper with references to the notepad's collaborative editing
infrastructure. Requires a widget with DOM access.

#### Parameters

##### notepad

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object representing the collaborative notepad.

#### Returns

`BoardNotepadHelper`

#### Throws

Throws if widget doesn't have DOM or notepad object is invalid.

## Properties

### notepad

> **notepad**: [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object representing the collaborative notepad.

## Methods

### appendContent()

> **appendContent**(`content`, `inputFormat?`): `Promise`\<`void`\>

Appends content to the notepad.

#### Parameters

##### content

`string` \| `string`[]

The content to append.

##### inputFormat?

[`TextInputFormat`](../enumerations/TextInputFormat.md) = `TextInputFormat.Text`

The format of the content.

#### Returns

`Promise`\<`void`\>

***

### getContent()

> **getContent**(`inputFormat?`): `Promise`\<`string`\>

Gets the content of the notepad.

#### Parameters

##### inputFormat?

[`TextInputFormat`](../enumerations/TextInputFormat.md) = `TextInputFormat.Text`

The format of the content.

#### Returns

`Promise`\<`string`\>

The content of the notepad.

***

### replaceContent()

> **replaceContent**(`content`, `inputFormat?`): `Promise`\<`void`\>

Replaces the content of the notepad.

#### Parameters

##### content

`string` \| `string`[]

The new content.

##### inputFormat?

[`TextInputFormat`](../enumerations/TextInputFormat.md) = `TextInputFormat.Text`

The format of the content.

#### Returns

`Promise`\<`void`\>

***

### getNotepadLabel()

> `static` **getNotepadLabel**(`notepadObject`, `len?`): `string`

Retrieves a display label for a notepad object.

Returns the notepad's caption/title if available, otherwise returns a preview
of the content. Automatically truncates long text and adds ellipsis.

#### Parameters

##### notepadObject

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The notepad board object.

##### len?

`number` = `30`

Maximum length of the returned label. Longer text is truncated with '...'.

#### Returns

`string`

The notepad label (title or content preview).

#### Static

***

### isNotepad()

> `static` **isNotepad**(`obj`): `boolean`

Determines if a board object is a collaborative notepad.

Checks the object's type and data properties to identify notepad objects.

#### Parameters

##### obj

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object to check.

#### Returns

`boolean`

True if the object is a notepad, false otherwise.

#### Static
