[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / BoardObjectHelper

# Class: BoardObjectHelper

A helper class for board objects.

## Constructors

### new BoardObjectHelper()

> **new BoardObjectHelper**(): [`BoardObjectHelper`](BoardObjectHelper.md)

#### Returns

[`BoardObjectHelper`](BoardObjectHelper.md)

## Methods

### addObjectToContainer()

> `static` **addObjectToContainer**(`container`, `elem`): `void`

Adds an object to a container.

#### Parameters

• **container**: [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The container object.

• **elem**: [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The element to add to the container.

#### Returns

`void`

#### Throws

Will throw an error if the container or element is not a proper board object.

***

### changeObjectContainerPosition()

> `static` **changeObjectContainerPosition**(`object`, `position`): `void`

Changes the position of an object within its container.

#### Parameters

• **object**: [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The object to reposition.

• **position**: `number`

The new position of the object.

#### Returns

`void`

#### Throws

Will throw an error if the object is not a board object or not in a container.

***

### deleteObject()

> `static` **deleteObject**(`object`): `void`

Deletes a board object.

#### Parameters

• **object**: [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The object to delete.

#### Returns

`void`

#### Throws

Will throw an error if the object is not a proper board object or the user does not have permissions to delete objects.

***

### editStickyNoteContent()

> `static` **editStickyNoteContent**(`stickyNote`, `text`, `overwritePermissions`?): `void`

Edits the content of a sticky note.

#### Parameters

• **stickyNote**: [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The sticky note object.

• **text**: `string`

The new text content.

• **overwritePermissions?**: `boolean` = `false`

Whether to overwrite permissions.

#### Returns

`void`

#### Throws

Will throw an error if the user does not have permissions to edit sticky notes or the sticky note is not a proper board object.

***

### editTextContent()

> `static` **editTextContent**(`textObject`, `text`): `void`

Edits the text content of a text object.

#### Parameters

• **textObject**: [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The text object to edit.

• **text**: `string`

The new text content.

#### Returns

`void`

#### Throws

Will throw an error if the text object is not a proper board object or not a text object.

***

### getBoardObjectById()

> `static` **getBoardObjectById**(`id`): [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

Retrieves a board object by its ID.

#### Parameters

• **id**: `string`

The ID of the board object.

#### Returns

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object, or undefined if not found.

***

### getContainerIdOfObject()

> `static` **getContainerIdOfObject**(`object`): `string`

Retrieves the ID of the container managing a given object.

#### Parameters

• **object**: [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The object.

#### Returns

`string`

The ID of the container.

***

### getContainerIdOfWidget()

> `static` **getContainerIdOfWidget**(): `string`

Retrieves the ID of the container managing the current widget.

#### Returns

`string`

The ID of the container.

***

### getContainerObjectIds()

> `static` **getContainerObjectIds**(`container`): `string`[]

Retrieves the IDs of objects managed by a container.

#### Parameters

• **container**: [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The container object.

#### Returns

`string`[]

The IDs of the managed objects.

***

### getContainerObjects()

> `static` **getContainerObjects**(`container`): [`RealIBoardObject`](../interfaces/RealIBoardObject.md)[]

Retrieves the objects managed by a container.

#### Parameters

• **container**: [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The container object.

#### Returns

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)[]

The managed objects.

***

### getContainerOfObject()

> `static` **getContainerOfObject**(`object`): [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

Retrieves the container managing a given object.

#### Parameters

• **object**: [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The object.

#### Returns

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The container object.

***

### getContainerOfWidget()

> `static` **getContainerOfWidget**(): [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

Retrieves the container managing the current widget.

#### Returns

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The container object.

***

### getElementsByType()

> `static` **getElementsByType**(`type`): `FormlySelectOption`[]

Retrieves elements by their type.

#### Parameters

• **type**: [`ExtendedObjectTypes`](../type-aliases/ExtendedObjectTypes.md)

The type of the elements.

#### Returns

`FormlySelectOption`[]

The elements of the specified type.

***

### getObjectDisplayName()

> `static` **getObjectDisplayName**(`object`): `string`

Retrieves the display name of a board object.

#### Parameters

• **object**: [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object.

#### Returns

`string`

The display name of the board object.

***

### getObjectTitle()

> `static` **getObjectTitle**(`obj`): `string`

Retrieves the title of a board object.

#### Parameters

• **obj**: [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object.

#### Returns

`string`

The title of the board object.

***

### getStickyNoteContent()

> `static` **getStickyNoteContent**(`stickyNote`): `string`

Retrieves the content of a sticky note.

#### Parameters

• **stickyNote**: [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The sticky note object.

#### Returns

`string`

The content of the sticky note.

***

### isTheSameWidget()

> `static` **isTheSameWidget**(`object`): `boolean`

Checks if a given object is the same as the current widget.

#### Parameters

• **object**: [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The object to check.

#### Returns

`boolean`

True if the object is the same as the current widget, false otherwise.

***

### removeObjectFromContainer()

> `static` **removeObjectFromContainer**(`container`, `elem`): `void`

Removes an object from a container.

#### Parameters

• **container**: [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The container object.

• **elem**: [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The element to remove from the container.

#### Returns

`void`

#### Throws

Will throw an error if the container or element is not a proper board object.
