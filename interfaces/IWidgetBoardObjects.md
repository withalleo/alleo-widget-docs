[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / IWidgetBoardObjects

# Interface: IWidgetBoardObjects

## Methods

### create()

#### create(type, object)

> **create**(`type`, `object`): `Promise`\<[`IBoardObject`](IBoardObject.md)\>

Create a new object, note that not all objects are supported

##### Parameters

• **type**: [`ScreenShare`](../enumerations/BoardFabricObjectType.md#screenshare)

• **object**: [`IScreenShareCreateData`](IScreenShareCreateData.md)

##### Returns

`Promise`\<[`IBoardObject`](IBoardObject.md)\>

#### create(type, object)

> **create**(`type`, `object`): `Promise`\<[`IBoardObject`](IBoardObject.md)\>

##### Parameters

• **type**: [`LiveVideo`](../enumerations/BoardFabricObjectType.md#livevideo)

• **object**: [`ILiveVideoCreateData`](ILiveVideoCreateData.md)

##### Returns

`Promise`\<[`IBoardObject`](IBoardObject.md)\>

#### create(type, object)

> **create**(`type`, `object`): `Promise`\<[`IBoardObject`](IBoardObject.md)\>

##### Parameters

• **type**: [`StickyNote`](../enumerations/BoardFabricObjectType.md#stickynote)

• **object**: [`IStickyNoteCreateData`](IStickyNoteCreateData.md)

##### Returns

`Promise`\<[`IBoardObject`](IBoardObject.md)\>

#### create(type, object)

> **create**(`type`, `object`): `Promise`\<[`IBoardObject`](IBoardObject.md)\>

##### Parameters

• **type**: [`Text`](../enumerations/BoardFabricObjectType.md#text)

• **object**: [`ITextCreateData`](ITextCreateData.md)

##### Returns

`Promise`\<[`IBoardObject`](IBoardObject.md)\>

#### create(type, object)

> **create**(`type`, `object`): `Promise`\<[`IBoardObject`](IBoardObject.md)\>

##### Parameters

• **type**: [`Container`](../enumerations/BoardFabricObjectType.md#container)

• **object**: [`IContainerCreateData`](IContainerCreateData.md)

##### Returns

`Promise`\<[`IBoardObject`](IBoardObject.md)\>

#### create(type, object)

> **create**(`type`, `object`): `Promise`\<[`IBoardObject`](IBoardObject.md)\>

##### Parameters

• **type**: [`Video`](../enumerations/BoardFabricObjectType.md#video)

• **object**: [`IVideoCreateData`](IVideoCreateData.md)

##### Returns

`Promise`\<[`IBoardObject`](IBoardObject.md)\>

#### create(type, object)

> **create**(`type`, `object`): `Promise`\<[`IBoardObject`](IBoardObject.md)\>

##### Parameters

• **type**: [`Image`](../enumerations/BoardFabricObjectType.md#image)

• **object**: [`IImageCreateData`](IImageCreateData.md)

##### Returns

`Promise`\<[`IBoardObject`](IBoardObject.md)\>

#### create(type, object)

> **create**(`type`, `object`): `Promise`\<[`IBoardObject`](IBoardObject.md)\>

##### Parameters

• **type**: [`Slide`](../enumerations/BoardFabricObjectType.md#slide)

• **object**: [`ISlideCreateData`](ISlideCreateData.md)

##### Returns

`Promise`\<[`IBoardObject`](IBoardObject.md)\>

#### create(type, object)

> **create**(`type`, `object`): `Promise`\<[`IBoardObject`](IBoardObject.md)\>

##### Parameters

• **type**: [`Document`](../enumerations/BoardFabricObjectType.md#document)

• **object**: [`IDocumentCreateData`](IDocumentCreateData.md)

##### Returns

`Promise`\<[`IBoardObject`](IBoardObject.md)\>

#### create(type, object)

> **create**(`type`, `object`): `Promise`\<[`IBoardObject`](IBoardObject.md)\>

##### Parameters

• **type**: [`Widget`](../enumerations/BoardFabricObjectType.md#widget)

• **object**: [`IWidgetCreateData`](../type-aliases/IWidgetCreateData.md)

##### Returns

`Promise`\<[`IBoardObject`](IBoardObject.md)\>

***

### getAll()

> **getAll**(): [`IBoardObject`](IBoardObject.md)[]

Get all objects on canvas

#### Returns

[`IBoardObject`](IBoardObject.md)[]

***

### getByType()

> **getByType**(`type`): [`IBoardObject`](IBoardObject.md)[]

Get all objects of a given type

#### Parameters

• **type**: [`BoardFabricObjectType`](../enumerations/BoardFabricObjectType.md)

#### Returns

[`IBoardObject`](IBoardObject.md)[]

***

### moveTo()

> **moveTo**(`object`): `Promise`\<`boolean`\>

Move to given object immediately

#### Parameters

• **object**: [`IBoardObject`](IBoardObject.md)

#### Returns

`Promise`\<`boolean`\>

***

### panTo()

> **panTo**(`object`, `zoomFactor`?): `Promise`\<`boolean`\>

Pan to a given object using default animation, by default this will zoom into the object to
until the object fills the viewport or the zoom limit is reached

#### Parameters

• **object**: [`IBoardObject`](IBoardObject.md)

• **zoomFactor?**: `number`

used to control the zoom level, defaults to 1 so can be omitted - lower values will zoom out

#### Returns

`Promise`\<`boolean`\>
