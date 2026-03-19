[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / BoardObjectHelper

# Class: BoardObjectHelper

Utility class for managing and manipulating board objects in Alleo.

Provides methods for working with various board objects including widgets, containers, text elements,
images, and notepads. Handles operations like creation, deletion, selection, positioning, and
container management. Essential for widgets that need to interact with other board objects.

## Example

```typescript
// Get the current widget object
const widget = BoardObjectHelper.thisWidget;

// Create a new text object
const textId = await BoardObjectHelper.createTextObject('Hello World', { x: 100, y: 100 });

// Add object to a container
const container = BoardObjectHelper.getBoardObjectById(containerId);
const object = BoardObjectHelper.getBoardObjectById(objectId);
BoardObjectHelper.addObjectToContainer(container, object);

// Delete the current widget
BoardObjectHelper.deleteMe();
```

## Constructors

### Constructor

> **new BoardObjectHelper**(): `BoardObjectHelper`

#### Returns

`BoardObjectHelper`

## Accessors

### thisWidget

#### Get Signature

> **get** `static` **thisWidget**(): [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

Reference to the current widget's board object instance.

Provides access to the board object representing this widget, allowing manipulation
of its properties, position, size, and other attributes.

##### Example

```typescript
const widget = BoardObjectHelper.thisWidget;
console.log(widget.id, widget.type);
const position = widget.getPosition();
```

##### Returns

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object instance for the current widget.

## Methods

### addObjectToContainer()

> `static` **addObjectToContainer**(`container`, `elem`): `void`

Adds a board object to a container, establishing a parent-child relationship.

Automatically removes the object from any previous container before adding it to the new one.
Fires appropriate events and updates the container's managed objects list. The container
will control the object's positioning and z-order.

#### Parameters

##### container

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The container object (must be of type Container).

##### elem

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object to add to the container.

#### Returns

`void`

#### Throws

Throws if container is not a Container type or if objects are invalid.

#### Example

```typescript
const container = BoardObjectHelper.getBoardObjectById(containerId);
const textObject = BoardObjectHelper.getBoardObjectById(textId);
BoardObjectHelper.addObjectToContainer(container, textObject);
```

***

### addTags()

> `static` **addTags**(`object`, `tags`, `replace?`): `void`

Adds tags to a board object.

#### Parameters

##### object

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object.

##### tags

`string` \| `string`[]

The tags to add.

##### replace?

`boolean` = `false`

Whether to replace the existing tags.

#### Returns

`void`

***

### changeObjectContainerPosition()

> `static` **changeObjectContainerPosition**(`object`, `position`): `void`

Changes the z-order position of an object within its container's managed objects list.

Reorders objects within a container, affecting their stacking order and layout position.
The position is clamped to valid indices (0 to container length).

#### Parameters

##### object

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The object to reposition within its container.

##### position

`number`

The new zero-based index position (will be rounded and clamped).

#### Returns

`void`

#### Throws

Throws if object is not in a container or is invalid.

#### Example

```typescript
// Move object to front (position 0)
BoardObjectHelper.changeObjectContainerPosition(object, 0);

// Move object to back
BoardObjectHelper.changeObjectContainerPosition(object, 999);
```

***

### deleteMe()

> `static` **deleteMe**(): `Promise`\<`void`\>

Deletes the current widget from the board.

#### Returns

`Promise`\<`void`\>

***

### deleteObject()

> `static` **deleteObject**(`object`): `void`

Deletes a board object.

#### Parameters

##### object

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The object to delete.

#### Returns

`void`

#### Throws

Will throw an error if the object is not a proper board object or the user does not have permissions to delete objects.

***

### editStickyNoteContent()

> `static` **editStickyNoteContent**(`stickyNote`, `text`, `overwritePermissions?`): `void`

Edits the content of a sticky note.

#### Parameters

##### stickyNote

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The sticky note object.

##### text

`string`

The new text content.

##### overwritePermissions?

`boolean` = `false`

Whether to overwrite permissions.

#### Returns

`void`

#### Throws

Will throw an error if the user does not have permissions to edit sticky notes or the sticky note is not a proper board object.

***

### editTextContent()

> `static` **editTextContent**(`textObject`, `text`): `void`

Programmatically updates the text content of a text object.

Modifies a text object's content and fires the appropriate events to update
the display and mark the object as modified. Only works on Text-type objects.

#### Parameters

##### textObject

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The text object to edit (must be type Text).

##### text

`string`

The new text content to display.

#### Returns

`void`

#### Throws

Throws if textObject is not valid or not a text object.

#### Example

```typescript
const textObj = BoardObjectHelper.getBoardObjectById(textId);
BoardObjectHelper.editTextContent(textObj, 'Updated text content');
```

***

### getActionEffects()

> `static` **getActionEffects**(`object`): `object`[]

#### Parameters

##### object

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

#### Returns

`object`[]

***

### getBoardObjectById()

> `static` **getBoardObjectById**(`id`): [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

Retrieves a board object by its unique identifier.

Searches all board objects and returns the one matching the specified ID.
Returns undefined if no object is found or if an error occurs.

#### Parameters

##### id

`string`

The unique ID of the board object to retrieve.

#### Returns

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object, or undefined if not found.

#### Example

```typescript
const object = BoardObjectHelper.getBoardObjectById('abc-123-def');
if (object) {
  console.log(object.type, object.getPosition());
}
```

***

### getContainerIdOfObject()

> `static` **getContainerIdOfObject**(`object`): `string`

Retrieves the ID of the container that manages a given object.

Returns the parent container's ID if the object is inside a container,
or undefined if the object is not contained.

#### Parameters

##### object

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object to check.

#### Returns

`string`

The container's ID, or undefined if object is not in a container.

#### Example

```typescript
const containerId = BoardObjectHelper.getContainerIdOfObject(object);
if (containerId) {
  const container = BoardObjectHelper.getBoardObjectById(containerId);
}
```

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

Retrieves the IDs of all objects managed by a container.

Returns an array of board object IDs that are children of the specified container.
Returns an empty array if the container has no managed objects.

#### Parameters

##### container

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The container object.

#### Returns

`string`[]

Array of managed object IDs.

#### Example

```typescript
const objectIds = BoardObjectHelper.getContainerObjectIds(container);
console.log(`Container manages ${objectIds.length} objects`);
```

***

### getContainerObjects()

> `static` **getContainerObjects**(`container`): [`RealIBoardObject`](../interfaces/RealIBoardObject.md)[]

Retrieves all board objects managed by a container.

Returns the actual board object instances (not just IDs) for all children of the
container. Filters out invalid objects, service widgets, and duplicates. Only returns
objects that genuinely belong to this container.

#### Parameters

##### container

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The container object.

#### Returns

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)[]

Array of managed board objects.

#### Example

```typescript
const objects = BoardObjectHelper.getContainerObjects(container);
objects.forEach(obj => {
  console.log(obj.type, obj.id);
});
```

***

### getContainerOfObject()

> `static` **getContainerOfObject**(`object`): [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

Retrieves the container managing a given object.

#### Parameters

##### object

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

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

### getElementsByTag()

> `static` **getElementsByTag**(`tag`): [`RealIBoardObject`](../interfaces/RealIBoardObject.md)[]

Retrieves the current widget's container.

#### Parameters

##### tag

`string`

#### Returns

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)[]

The container object.

***

### getElementsByType()

> `static` **getElementsByType**(`type`): `FormlySelectOption`[]

Retrieves elements by their type.

#### Parameters

##### type

[`ExtendedObjectTypes`](../type-aliases/ExtendedObjectTypes.md)

The type of the elements.

#### Returns

`FormlySelectOption`[]

The elements of the specified type.

***

### getObjectDisplayName()

> `static` **getObjectDisplayName**(`object`, `addTypeName?`): `string`

Retrieves the display name of a board object.

#### Parameters

##### object

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object.

##### addTypeName?

`boolean` = `true`

Whether to include the type name in the display name. (eg. "Sticky Note: XXX")

#### Returns

`string`

The display name of the board object.

***

### getObjectTitle()

> `static` **getObjectTitle**(`obj`): `string`

Retrieves the display title/caption of a board object.

Returns the object's caption text if available (e.g., widget titles, text object content).
Returns undefined if the object has no caption.

#### Parameters

##### obj

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object.

#### Returns

`string`

The title/caption text, or undefined if not available.

#### Example

```typescript
const title = BoardObjectHelper.getObjectTitle(widget);
console.log(`Widget title: ${title}`);
```

***

### getStickyNoteContent()

> `static` **getStickyNoteContent**(`stickyNote`): `string`

Retrieves the content of a sticky note.

#### Parameters

##### stickyNote

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The sticky note object.

#### Returns

`string`

The content of the sticky note.

***

### getTags()

> `static` **getTags**(`object`): `string`[]

Retrieves the tags of a board object.

#### Parameters

##### object

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object.

#### Returns

`string`[]

The tags of the board object.

***

### getTypeNameOfObject()

> `static` **getTypeNameOfObject**(`object`): `string`

Retrieves the type name of a board object.

#### Parameters

##### object

`IBoardObject`

The board object.

#### Returns

`string`

The name of the board object type. (eg. Sticky Note, Notepad, Widget, Image, etc.)

***

### isTheSameWidget()

> `static` **isTheSameWidget**(`object`): `boolean`

Checks if a given object is the same as the current widget.

#### Parameters

##### object

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The object to check.

#### Returns

`boolean`

True if the object is the same as the current widget, false otherwise.

***

### moveObject()

> `static` **moveObject**(`object`, `position`): `void`

Moves a board object to a new position based on coordinates.

#### Parameters

##### object

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object to move.

##### position

`IPosition`

The new position of the object.

#### Returns

`void`

***

### moveObjectCenterToCoordinate()

> `static` **moveObjectCenterToCoordinate**(`object`, `position`): `void`

#### Parameters

##### object

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

##### position

`Position`

#### Returns

`void`

***

### reloadMe()

> `static` **reloadMe**(): `void`

Reloads the current widget

#### Returns

`void`

***

### removeObjectFromContainer()

> `static` **removeObjectFromContainer**(`container`, `elem`): `void`

Removes a board object from its container, breaking the parent-child relationship.

The object becomes independent after removal. Fires appropriate events and updates
the container's managed objects list. Does nothing if the object is not in the container.

#### Parameters

##### container

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The container object.

##### elem

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object to remove from the container.

#### Returns

`void`

#### Throws

Throws if container or elem are not valid board objects.

#### Example

```typescript
const container = BoardObjectHelper.getBoardObjectById(containerId);
const textObject = BoardObjectHelper.getBoardObjectById(textId);
BoardObjectHelper.removeObjectFromContainer(container, textObject);
```

***

### removeTags()

> `static` **removeTags**(`object`, `tags`): `void`

Removes tags from a board object.

#### Parameters

##### object

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object.

##### tags

`string` \| `string`[]

The tags to remove

#### Returns

`void`

***

### triggerActionEffect()

> `static` **triggerActionEffect**(`object`, `effectId`): `Promise`\<`void`\>

#### Parameters

##### object

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

##### effectId

`string`

#### Returns

`Promise`\<`void`\>
