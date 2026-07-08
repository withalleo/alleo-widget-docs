[**@withalleo/alleo-widget**](../README.md)

---

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
  console.log("Notepad content:", text);

  // Write content
  await notepadHelper.setText("New content", TextInputFormat.Markdown);

  // Get notepad label
  const label = BoardNotepadHelper.getNotepadLabel(notepadObj);
}
```

## Constructors

### Constructor

```ts
new BoardNotepadHelper(notepad: RealIBoardObject): BoardNotepadHelper;
```

Creates a BoardNotepadHelper instance for manipulating a specific notepad.

Initializes the helper with references to the notepad's collaborative editing
infrastructure. Requires a widget with DOM access.

#### Parameters

| Parameter | Type                                                    | Description                                              |
| --------- | ------------------------------------------------------- | -------------------------------------------------------- |
| `notepad` | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | The board object representing the collaborative notepad. |

#### Returns

`BoardNotepadHelper`

#### Throws

Throws if widget doesn't have DOM or notepad object is invalid.

## Properties

### notepad

```ts
notepad: RealIBoardObject;
```

The board object representing the collaborative notepad.

## Methods

### appendContent()

```ts
appendContent(content: string | string[], inputFormat?: TextInputFormat): Promise<void>;
```

Appends content to the notepad.

#### Parameters

| Parameter      | Type                                                    | Default value          | Description                |
| -------------- | ------------------------------------------------------- | ---------------------- | -------------------------- |
| `content`      | `string` \| `string`[]                                  | `undefined`            | The content to append.     |
| `inputFormat?` | [`TextInputFormat`](../enumerations/TextInputFormat.md) | `TextInputFormat.Text` | The format of the content. |

#### Returns

`Promise`\<`void`\>

---

### getContent()

```ts
getContent(inputFormat?: TextInputFormat): Promise<string>;
```

Gets the content of the notepad.

#### Parameters

| Parameter      | Type                                                    | Default value          | Description                |
| -------------- | ------------------------------------------------------- | ---------------------- | -------------------------- |
| `inputFormat?` | [`TextInputFormat`](../enumerations/TextInputFormat.md) | `TextInputFormat.Text` | The format of the content. |

#### Returns

`Promise`\<`string`\>

The content of the notepad.

---

### replaceContent()

```ts
replaceContent(content: string | string[], inputFormat?: TextInputFormat): Promise<void>;
```

Replaces the content of the notepad.

#### Parameters

| Parameter      | Type                                                    | Default value          | Description                |
| -------------- | ------------------------------------------------------- | ---------------------- | -------------------------- |
| `content`      | `string` \| `string`[]                                  | `undefined`            | The new content.           |
| `inputFormat?` | [`TextInputFormat`](../enumerations/TextInputFormat.md) | `TextInputFormat.Text` | The format of the content. |

#### Returns

`Promise`\<`void`\>

---

### getNotepadLabel()

```ts
static getNotepadLabel(notepadObject: RealIBoardObject, len?: number): string;
```

Retrieves a display label for a notepad object.

Returns the notepad's caption/title if available, otherwise returns a preview
of the content. Automatically truncates long text and adds ellipsis.

#### Parameters

| Parameter       | Type                                                    | Default value | Description                                                                |
| --------------- | ------------------------------------------------------- | ------------- | -------------------------------------------------------------------------- |
| `notepadObject` | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | `undefined`   | The notepad board object.                                                  |
| `len?`          | `number`                                                | `30`          | Maximum length of the returned label. Longer text is truncated with '...'. |

#### Returns

`string`

The notepad label (title or content preview).

#### Static

---

### isNotepad()

```ts
static isNotepad(obj: RealIBoardObject): boolean;
```

Determines if a board object is a collaborative notepad.

Checks the object's type and data properties to identify notepad objects.

#### Parameters

| Parameter | Type                                                    | Description                |
| --------- | ------------------------------------------------------- | -------------------------- |
| `obj`     | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | The board object to check. |

#### Returns

`boolean`

True if the object is a notepad, false otherwise.

#### Static
