[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / BoardObjectHelper

# Class: BoardObjectHelper

Utility class for managing and manipulating board objects in Alleo.

Provides methods for working with various board objects including widgets, containers, text elements,
images, and notepads. Handles operations like creation, deletion, selection, positioning, and
container management. Essential for widgets that need to interact with other board objects.

## Example

```typescript
// Get the current widget object
const widget = BoardObjectHelper.thisWidget

// Create a new text object
const textId = await BoardObjectHelper.createTextObject('Hello World', { x: 100, y: 100 })

// Add object to a container
const container = BoardObjectHelper.getBoardObjectById(containerId)
const object = BoardObjectHelper.getBoardObjectById(objectId)
BoardObjectHelper.addObjectToContainer(container, object)

// Delete the current widget
BoardObjectHelper.deleteMe()
```

## Constructors

### Constructor

```ts
new BoardObjectHelper(): BoardObjectHelper;
```

#### Returns

`BoardObjectHelper`

## Accessors

### canEdit

#### Get Signature

```ts
get static canEdit(): boolean;
```

Whether the current user has edit permissions on the board.

##### Returns

`boolean`

True if the current user can edit, false otherwise (also when unknown).

---

### thisWidget

#### Get Signature

```ts
get static thisWidget(): RealIBoardObject;
```

Reference to the current widget's board object instance.

Provides access to the board object representing this widget, allowing manipulation
of its properties, position, size, and other attributes.

##### Example

```typescript
const widget = BoardObjectHelper.thisWidget
console.log(widget.id, widget.type)
const position = widget.getPosition()
```

##### Returns

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object instance for the current widget.

## Methods

### addObjectToContainer()

```ts
static addObjectToContainer(container: RealIBoardObject, elem: RealIBoardObject): void;
```

Adds a board object to a container, establishing a parent-child relationship.

Automatically removes the object from any previous container before adding it to the new one.
Fires appropriate events and updates the container's managed objects list. The container
will control the object's positioning and z-order.

#### Parameters

| Parameter   | Type                                                    | Description                                       |
| ----------- | ------------------------------------------------------- | ------------------------------------------------- |
| `container` | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | The container object (must be of type Container). |
| `elem`      | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | The board object to add to the container.         |

#### Returns

`void`

#### Throws

Throws if container is not a Container type, if objects are invalid, if elem is the container
itself, or if the user does not have edit permissions.

#### Example

```typescript
const container = BoardObjectHelper.getBoardObjectById(containerId)
const textObject = BoardObjectHelper.getBoardObjectById(textId)
BoardObjectHelper.addObjectToContainer(container, textObject)
```

---

### addTags()

```ts
static addTags(
   object: RealIBoardObject,
   tags: string | string[],
   replace?: boolean
): void;
```

Adds tags to a board object. Tags that are already present are skipped.

#### Parameters

| Parameter  | Type                                                    | Default value | Description                           |
| ---------- | ------------------------------------------------------- | ------------- | ------------------------------------- |
| `object`   | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | `undefined`   | The board object.                     |
| `tags`     | `string` \| `string`[]                                  | `undefined`   | The tags to add.                      |
| `replace?` | `boolean`                                               | `false`       | Whether to replace the existing tags. |

#### Returns

`void`

#### Throws

Will throw an error if the user does not have edit permissions.

---

### changeObjectContainerPosition()

```ts
static changeObjectContainerPosition(object: RealIBoardObject, position: number): void;
```

Changes the z-order position of an object within its container's managed objects list.

Reorders objects within a container, affecting their stacking order and layout position.
The position is rounded; negative, too large, or non-finite positions move the object to the end.

#### Parameters

| Parameter  | Type                                                    | Description                                    |
| ---------- | ------------------------------------------------------- | ---------------------------------------------- |
| `object`   | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | The object to reposition within its container. |
| `position` | `number`                                                | The new zero-based index position.             |

#### Returns

`void`

#### Throws

Throws if object is not in a container, is invalid, or if the user does not have edit permissions.

#### Example

```typescript
// Move object to front (position 0)
BoardObjectHelper.changeObjectContainerPosition(object, 0)

// Move object to back
BoardObjectHelper.changeObjectContainerPosition(object, 999)
```

---

### deleteMe()

```ts
static deleteMe(): Promise<void>;
```

Deletes the current widget from the board.

#### Returns

`Promise`\<`void`\>

---

### deleteObject()

```ts
static deleteObject(object: RealIBoardObject): void;
```

Deletes a board object.

#### Parameters

| Parameter | Type                                                    | Description           |
| --------- | ------------------------------------------------------- | --------------------- |
| `object`  | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | The object to delete. |

#### Returns

`void`

#### Throws

Will throw an error if the object is not a proper board object or the user does not have permissions to delete objects.

---

### editStickyNoteContent()

```ts
static editStickyNoteContent(
   stickyNote: RealIBoardObject,
   text: string,
   overwritePermissions?: boolean
): void;
```

Edits the content of a sticky note.

#### Parameters

| Parameter               | Type                                                    | Default value | Description                       |
| ----------------------- | ------------------------------------------------------- | ------------- | --------------------------------- |
| `stickyNote`            | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | `undefined`   | The sticky note object.           |
| `text`                  | `string`                                                | `undefined`   | The new text content.             |
| `overwritePermissions?` | `boolean`                                               | `false`       | Whether to overwrite permissions. |

#### Returns

`void`

#### Throws

Will throw an error if the user does not have permissions to edit sticky notes or the sticky note is not a proper board object.

---

### editTextContent()

```ts
static editTextContent(textObject: RealIBoardObject, text: string): void;
```

Programmatically updates the text content of a text object.

Modifies a text object's content and fires the appropriate events to update
the display and mark the object as modified. Only works on Text-type objects.
Pass the raw template (placeholders are rendered by the object). Line breaks become spaces
on objects that disallow line breaks.

#### Parameters

| Parameter    | Type                                                    | Description                                  |
| ------------ | ------------------------------------------------------- | -------------------------------------------- |
| `textObject` | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | The text object to edit (must be type Text). |
| `text`       | `string`                                                | The new text content to display.             |

#### Returns

`void`

#### Throws

Throws if textObject is not valid, not a text object, or if the user does not have edit permissions.

#### Example

```typescript
const textObj = BoardObjectHelper.getBoardObjectById(textId)
BoardObjectHelper.editTextContent(textObj, 'Updated text content')
```

---

### getActionEffects()

```ts
static getActionEffects(object: RealIBoardObject): {
  id: string;
  label: string;
}[];
```

Retrieves the action effects exposed by a board object.

#### Parameters

| Parameter | Type                                                    | Description       |
| --------- | ------------------------------------------------------- | ----------------- |
| `object`  | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | The board object. |

#### Returns

\{
`id`: `string`;
`label`: `string`;
\}[]

The id and label of each action effect. Empty if the object exposes none.

---

### getBoardObjectById()

```ts
static getBoardObjectById(id: string): RealIBoardObject;
```

Retrieves a board object by its unique identifier.

Searches all board objects and returns the one matching the specified ID.
Returns undefined if no object is found or if an error occurs.

#### Parameters

| Parameter | Type     | Description                                    |
| --------- | -------- | ---------------------------------------------- |
| `id`      | `string` | The unique ID of the board object to retrieve. |

#### Returns

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object, or undefined if not found.

#### Example

```typescript
const object = BoardObjectHelper.getBoardObjectById('abc-123-def')
if (object) {
    console.log(object.type, object.getPosition())
}
```

---

### getContainerIdOfObject()

```ts
static getContainerIdOfObject(object: RealIBoardObject): string;
```

Retrieves the ID of the container that manages a given object.

Returns the parent container's ID if the object is inside a container,
or undefined if the object is not contained.

#### Parameters

| Parameter | Type                                                    | Description                |
| --------- | ------------------------------------------------------- | -------------------------- |
| `object`  | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | The board object to check. |

#### Returns

`string`

The container's ID, or undefined if object is not in a container.

#### Example

```typescript
const containerId = BoardObjectHelper.getContainerIdOfObject(object)
if (containerId) {
    const container = BoardObjectHelper.getBoardObjectById(containerId)
}
```

---

### getContainerIdOfWidget()

```ts
static getContainerIdOfWidget(): string;
```

Retrieves the ID of the container managing the current widget.

#### Returns

`string`

The ID of the container.

---

### getContainerObjectIds()

```ts
static getContainerObjectIds(container: RealIBoardObject): string[];
```

Retrieves the IDs of all objects managed by a container.

Returns an array of board object IDs that are children of the specified container.
Returns an empty array if the container has no managed objects.

#### Parameters

| Parameter   | Type                                                    | Description           |
| ----------- | ------------------------------------------------------- | --------------------- |
| `container` | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | The container object. |

#### Returns

`string`[]

Array of managed object IDs.

#### Example

```typescript
const objectIds = BoardObjectHelper.getContainerObjectIds(container)
console.log(`Container manages ${objectIds.length} objects`)
```

---

### getContainerObjects()

```ts
static getContainerObjects(container: RealIBoardObject): RealIBoardObject[];
```

Retrieves all board objects managed by a container.

Returns the actual board object instances (not just IDs) for all children of the
container. Filters out invalid objects, service widgets, and duplicates. Only returns
objects that genuinely belong to this container.

#### Parameters

| Parameter   | Type                                                    | Description           |
| ----------- | ------------------------------------------------------- | --------------------- |
| `container` | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | The container object. |

#### Returns

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)[]

Array of managed board objects.

#### Example

```typescript
const objects = BoardObjectHelper.getContainerObjects(container)
objects.forEach((obj) => {
    console.log(obj.type, obj.id)
})
```

---

### getContainerOfObject()

```ts
static getContainerOfObject(object: RealIBoardObject): RealIBoardObject;
```

Retrieves the container managing a given object.

#### Parameters

| Parameter | Type                                                    | Description |
| --------- | ------------------------------------------------------- | ----------- |
| `object`  | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | The object. |

#### Returns

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The container object.

---

### getContainerOfWidget()

```ts
static getContainerOfWidget(): RealIBoardObject;
```

Retrieves the container managing the current widget.

#### Returns

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The container object.

---

### getElementsByTag()

```ts
static getElementsByTag(tag: string): RealIBoardObject[];
```

Retrieves all board objects that have the given tag.

#### Parameters

| Parameter | Type     | Description          |
| --------- | -------- | -------------------- |
| `tag`     | `string` | The tag to look for. |

#### Returns

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)[]

The board objects with the tag.

---

### getElementsByType()

```ts
static getElementsByType(type: ExtendedObjectTypes): FormlySelectOption[];
```

Retrieves elements by their type.

#### Parameters

| Parameter | Type                                                            | Description               |
| --------- | --------------------------------------------------------------- | ------------------------- |
| `type`    | [`ExtendedObjectTypes`](../type-aliases/ExtendedObjectTypes.md) | The type of the elements. |

#### Returns

`FormlySelectOption`[]

The elements of the specified type.

---

### getObjectDisplayName()

```ts
static getObjectDisplayName(object: RealIBoardObject, addTypeName?: boolean): string;
```

Retrieves the display name of a board object.

#### Parameters

| Parameter      | Type                                                    | Default value | Description                                                                    |
| -------------- | ------------------------------------------------------- | ------------- | ------------------------------------------------------------------------------ |
| `object`       | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | `undefined`   | The board object.                                                              |
| `addTypeName?` | `boolean`                                               | `true`        | Whether to include the type name in the display name. (eg. "Sticky Note: XXX") |

#### Returns

`string`

The display name of the board object.

---

### getObjectTitle()

```ts
static getObjectTitle(obj: RealIBoardObject): string;
```

Retrieves the display title/caption of a board object.

Returns the object's caption text if available (e.g., widget titles, text object content).
Returns undefined if the object has no caption.

#### Parameters

| Parameter | Type                                                    | Description       |
| --------- | ------------------------------------------------------- | ----------------- |
| `obj`     | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | The board object. |

#### Returns

`string`

The title/caption text, or undefined if not available.

#### Example

```typescript
const title = BoardObjectHelper.getObjectTitle(widget)
console.log(`Widget title: ${title}`)
```

---

### getStickyNoteContent()

```ts
static getStickyNoteContent(stickyNote: RealIBoardObject): string;
```

Retrieves the content of a sticky note.

#### Parameters

| Parameter    | Type                                                    | Description             |
| ------------ | ------------------------------------------------------- | ----------------------- |
| `stickyNote` | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | The sticky note object. |

#### Returns

`string`

The content of the sticky note.

---

### getTags()

```ts
static getTags(object: RealIBoardObject): string[];
```

Retrieves the tags of a board object.

#### Parameters

| Parameter | Type                                                    | Description       |
| --------- | ------------------------------------------------------- | ----------------- |
| `object`  | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | The board object. |

#### Returns

`string`[]

The tags of the board object.

---

### getTypeNameOfObject()

```ts
static getTypeNameOfObject(object: IBoardObject): string;
```

Retrieves the type name of a board object.

#### Parameters

| Parameter | Type           | Description       |
| --------- | -------------- | ----------------- |
| `object`  | `IBoardObject` | The board object. |

#### Returns

`string`

The name of the board object type. (eg. Sticky Note, Notepad, Widget, Image, etc.)

---

### getWidgetFlags()

```ts
static getWidgetFlags(object: RealIBoardObject): Record<WidgetFlag, boolean>;
```

Retrieves the widget flags of a board object.

#### Parameters

| Parameter | Type                                                    | Description |
| --------- | ------------------------------------------------------- | ----------- |
| `object`  | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | -           |

#### Returns

`Record`\<[`WidgetFlag`](../type-aliases/WidgetFlag.md), `boolean`\>

A record of widget flags and their boolean values.

---

### isTheSameWidget()

```ts
static isTheSameWidget(object: RealIBoardObject): boolean;
```

Checks if a given object is the same as the current widget.

#### Parameters

| Parameter | Type                                                    | Description          |
| --------- | ------------------------------------------------------- | -------------------- |
| `object`  | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | The object to check. |

#### Returns

`boolean`

True if the object is the same as the current widget, false otherwise.

---

### moveObject()

```ts
static moveObject(object: RealIBoardObject, position: IPosition): void;
```

Moves a board object to a new position based on coordinates.

#### Parameters

| Parameter  | Type                                                    | Description                     |
| ---------- | ------------------------------------------------------- | ------------------------------- |
| `object`   | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | The board object to move.       |
| `position` | `IPosition`                                             | The new position of the object. |

#### Returns

`void`

#### Throws

Will throw an error if the user does not have edit permissions.

---

### moveObjectCenterToCoordinate()

```ts
static moveObjectCenterToCoordinate(object: RealIBoardObject, position: Position): void;
```

Moves a board object so that its center is at the given coordinate. Takes the object's origin and rotation into account.

#### Parameters

| Parameter  | Type                                                    | Description                                            |
| ---------- | ------------------------------------------------------- | ------------------------------------------------------ |
| `object`   | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | The board object to move.                              |
| `position` | `Position`                                              | The coordinate the object's center should be moved to. |

#### Returns

`void`

#### Throws

Will throw an error if the user does not have edit permissions.

---

### reloadMe()

```ts
static reloadMe(): void;
```

Reloads the current widget

#### Returns

`void`

---

### removeObjectFromContainer()

```ts
static removeObjectFromContainer(container: RealIBoardObject, elem: RealIBoardObject): void;
```

Removes a board object from its container, breaking the parent-child relationship.

The object becomes independent after removal. Fires appropriate events and updates
the container's managed objects list. Does nothing if the object is not in the container.

#### Parameters

| Parameter   | Type                                                    | Description                                    |
| ----------- | ------------------------------------------------------- | ---------------------------------------------- |
| `container` | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | The container object.                          |
| `elem`      | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | The board object to remove from the container. |

#### Returns

`void`

#### Throws

Throws if container or elem are not valid board objects, or if the user does not have edit permissions.

#### Example

```typescript
const container = BoardObjectHelper.getBoardObjectById(containerId)
const textObject = BoardObjectHelper.getBoardObjectById(textId)
BoardObjectHelper.removeObjectFromContainer(container, textObject)
```

---

### removeTags()

```ts
static removeTags(object: RealIBoardObject, tags: string | string[]): void;
```

Removes tags from a board object.

#### Parameters

| Parameter | Type                                                    | Description        |
| --------- | ------------------------------------------------------- | ------------------ |
| `object`  | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | The board object.  |
| `tags`    | `string` \| `string`[]                                  | The tags to remove |

#### Returns

`void`

#### Throws

Will throw an error if the user does not have edit permissions.

---

### triggerActionEffect()

```ts
static triggerActionEffect(object: RealIBoardObject, effectId: string): Promise<void>;
```

Triggers an action effect of a board object.

#### Parameters

| Parameter  | Type                                                    | Description                             |
| ---------- | ------------------------------------------------------- | --------------------------------------- |
| `object`   | [`RealIBoardObject`](../interfaces/RealIBoardObject.md) | The board object.                       |
| `effectId` | `string`                                                | The id of the action effect to trigger. |

#### Returns

`Promise`\<`void`\>

#### Throws

Will throw an error if the action effect is not found, or if the effect's callback throws.
