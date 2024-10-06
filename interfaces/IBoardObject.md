[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / IBoardObject

# Interface: IBoardObject

## Extended by

- [`RealIBoardObject`](RealIBoardObject.md)

## Properties

### humanTextId

> `readonly` **humanTextId**: `string`

***

### id

> `readonly` **id**: `string`

***

### type

> `readonly` **type**: [`BoardFabricObjectType`](../enumerations/BoardFabricObjectType.md)

## Methods

### getAssetIds()

> **getAssetIds**(): `string`[]

#### Returns

`string`[]

***

### getField()

> **getField**(`fieldName`): `any`

#### Parameters

• **fieldName**: `string`

#### Returns

`any`

***

### moveTo()

> **moveTo**(`pos`): `any`

#### Parameters

• **pos**: [`IPosition`](../type-aliases/IPosition.md)

#### Returns

`any`

***

### moveViewportToObject()

> **moveViewportToObject**(): `Promise`\<`boolean`\>

#### Returns

`Promise`\<`boolean`\>

***

### panViewportToObject()

> **panViewportToObject**(`zoomFactor`?): `Promise`\<`boolean`\>

#### Parameters

• **zoomFactor?**: `number`

#### Returns

`Promise`\<`boolean`\>

***

### setField()

> **setField**(`fieldName`, `value`, `delta`): `void`

#### Parameters

• **fieldName**: `string`

• **value**: `any`

• **delta**: `boolean`

#### Returns

`void`

***

### setScale()

> **setScale**(`scaleX`, `scaleY`): `any`

#### Parameters

• **scaleX**: `number`

• **scaleY**: `number`

#### Returns

`any`

***

### setSize()

> **setSize**(`width`, `height`): `any`

#### Parameters

• **width**: `number`

• **height**: `number`

#### Returns

`any`
