[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / RealIBoardObject

# Interface: RealIBoardObject

Interface extending IBoardObject with allowing the optional properties exposing the object.

## Extends

- [`IBoardObject`](IBoardObject.md)

## Properties

### component?

> `optional` **component**: `Record`\<`string`, `any`\>

***

### humanTextId

> `readonly` **humanTextId**: `string`

#### Inherited from

[`IBoardObject`](IBoardObject.md).[`humanTextId`](IBoardObject.md#humantextid)

***

### id

> `readonly` **id**: `string`

#### Inherited from

[`IBoardObject`](IBoardObject.md).[`id`](IBoardObject.md#id)

***

### obj?

> `optional` **obj**: `Record`\<`string`, `any`\>

***

### type

> `readonly` **type**: [`BoardFabricObjectType`](../enumerations/BoardFabricObjectType.md)

#### Inherited from

[`IBoardObject`](IBoardObject.md).[`type`](IBoardObject.md#type)

## Methods

### getAssetIds()

> **getAssetIds**(): `string`[]

#### Returns

`string`[]

#### Inherited from

[`IBoardObject`](IBoardObject.md).[`getAssetIds`](IBoardObject.md#getassetids)

***

### getField()

> **getField**(`fieldName`): `any`

#### Parameters

• **fieldName**: `string`

#### Returns

`any`

#### Inherited from

[`IBoardObject`](IBoardObject.md).[`getField`](IBoardObject.md#getfield)

***

### moveTo()

> **moveTo**(`pos`): `any`

#### Parameters

• **pos**: [`IPosition`](../type-aliases/IPosition.md)

#### Returns

`any`

#### Inherited from

[`IBoardObject`](IBoardObject.md).[`moveTo`](IBoardObject.md#moveto)

***

### moveViewportToObject()

> **moveViewportToObject**(): `Promise`\<`boolean`\>

#### Returns

`Promise`\<`boolean`\>

#### Inherited from

[`IBoardObject`](IBoardObject.md).[`moveViewportToObject`](IBoardObject.md#moveviewporttoobject)

***

### panViewportToObject()

> **panViewportToObject**(`zoomFactor`?): `Promise`\<`boolean`\>

#### Parameters

• **zoomFactor?**: `number`

#### Returns

`Promise`\<`boolean`\>

#### Inherited from

[`IBoardObject`](IBoardObject.md).[`panViewportToObject`](IBoardObject.md#panviewporttoobject)

***

### setField()

> **setField**(`fieldName`, `value`, `delta`): `void`

#### Parameters

• **fieldName**: `string`

• **value**: `any`

• **delta**: `boolean`

#### Returns

`void`

#### Inherited from

[`IBoardObject`](IBoardObject.md).[`setField`](IBoardObject.md#setfield)

***

### setScale()

> **setScale**(`scaleX`, `scaleY`): `any`

#### Parameters

• **scaleX**: `number`

• **scaleY**: `number`

#### Returns

`any`

#### Inherited from

[`IBoardObject`](IBoardObject.md).[`setScale`](IBoardObject.md#setscale)

***

### setSize()

> **setSize**(`width`, `height`): `any`

#### Parameters

• **width**: `number`

• **height**: `number`

#### Returns

`any`

#### Inherited from

[`IBoardObject`](IBoardObject.md).[`setSize`](IBoardObject.md#setsize)
