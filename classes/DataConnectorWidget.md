[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / DataConnectorWidget

# Class: DataConnectorWidget\<SharedVariableStructure\>

Class representing an Alleo Widget.

Provides access to shared variables, a constructor, and a destroy method.

## Extends

- [`AlleoWidget`](AlleoWidget.md)\<`SharedVariableStructure`\>

## Type Parameters

### SharedVariableStructure

`SharedVariableStructure`

The structure of the shared variables.

## Constructors

### Constructor

> **new DataConnectorWidget**\<`SharedVariableStructure`\>(`defaultSharedVariables`): `DataConnectorWidget`\<`SharedVariableStructure`\>

#### Parameters

##### defaultSharedVariables

`Partial`\<`SharedVariableStructure`\> = `{}`

#### Returns

`DataConnectorWidget`\<`SharedVariableStructure`\>

#### Overrides

[`AlleoWidget`](AlleoWidget.md).[`constructor`](AlleoWidget.md#constructor)

## Properties

### dom

> `protected` **dom**: `HTMLDivElement`

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`dom`](AlleoWidget.md#dom)

***

### lineLimit

> `protected` **lineLimit**: `number` = `0`

***

### nameHelper

> `protected` **nameHelper**: [`WidgetNameHelper`](WidgetNameHelper.md)

***

### shared

> `protected` **shared**: `Partial`\<`SharedVariableStructure`\>

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`shared`](AlleoWidget.md#shared)

***

### widgetStatus

> `protected` **widgetStatus**: `object`

#### loaded

> **loaded**: `boolean`

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`widgetStatus`](AlleoWidget.md#widgetstatus)

***

### widgetNamePrefix

> `readonly` `static` **widgetNamePrefix**: `string` = `'▤ '`

## Accessors

### implemented

#### Get Signature

> **get** `protected` **implemented**(): [`DataConnectorActions`](../enumerations/DataConnectorActions.md)[]

##### Returns

[`DataConnectorActions`](../enumerations/DataConnectorActions.md)[]

***

### length

#### Get Signature

> **get** `protected` **length**(): `number`

##### Returns

`number`

***

### widgetName

#### Get Signature

> **get** `protected` **widgetName**(): `string`

##### Returns

`string`

## Methods

### append()

> `protected` **append**(`row`): `Promise`\<`boolean`\>

#### Parameters

##### row

`string`[]

#### Returns

`Promise`\<`boolean`\>

***

### assertWidgetLoaded()

> `protected` **assertWidgetLoaded**(): `void`

Asserts that the widget is loaded.

#### Returns

`void`

#### Throws

- If the widget has been destroyed.

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`assertWidgetLoaded`](AlleoWidget.md#assertwidgetloaded)

***

### destroy()

> **destroy**(): `void` \| `Promise`\<`void`\>

Called when the widget instance is destroyed (when unloaded, NOT when the widget is deleted from the board).

#### Returns

`void` \| `Promise`\<`void`\>

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`destroy`](AlleoWidget.md#destroy)

***

### domSelect()

> `protected` **domSelect**\<`HTMLElementType`\>(`query`): `HTMLElementType`

Selects a DOM element within the widget container.

#### Type Parameters

##### HTMLElementType

`HTMLElementType` *extends* `HTMLElement` = `HTMLElement`

The type of the HTML element.

#### Parameters

##### query

`string`

The query selector.

#### Returns

`HTMLElementType`

- The selected HTML element.

#### Throws

- If no DOM is available.

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`domSelect`](AlleoWidget.md#domselect)

***

### export()

> `protected` **export**(): `Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

#### Returns

`Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

***

### exportProcess()

> **exportProcess**(`name`, `download`): `Promise`\<`void`\>

#### Parameters

##### name

`string` = `'Exported data'`

##### download

`boolean` = `true`

#### Returns

`Promise`\<`void`\>

***

### import()

> `protected` **import**(`data`): `Promise`\<`boolean`\>

#### Parameters

##### data

[`CSVData`](../type-aliases/CSVData.md)

#### Returns

`Promise`\<`boolean`\>

***

### importProcess()

> **importProcess**(): `Promise`\<`void`\>

#### Returns

`Promise`\<`void`\>

***

### initialize()

> `protected` **initialize**(): `Promise`\<`void`\>

#### Returns

`Promise`\<`void`\>

***

### setContainerClass()

> `protected` **setContainerClass**(`className`, `add`?): `void`

Sets an HTML class for the widget container.

#### Parameters

##### className

`string`

The class name to set.

##### add?

`boolean` = `true`

Whether to add or remove the class. (if !add the "not-className" class is added, and the original is removed)

#### Returns

`void`

#### Throws

- If no DOM is available.

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`setContainerClass`](AlleoWidget.md#setcontainerclass)

***

### updateDisplayName()

> `protected` **updateDisplayName**(): `void`

#### Returns

`void`

***

### isDataConnector()

> `static` **isDataConnector**(`object`, `actionsRequiredSupport`): `boolean`

#### Parameters

##### object

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

##### actionsRequiredSupport

[`DataConnectorActions`](../enumerations/DataConnectorActions.md)[] = `[]`

#### Returns

`boolean`

***

### saveCSVInBoardAssets()

> `static` **saveCSVInBoardAssets**(`file`): `Promise`\<`StorageNodeCreatedResponseDto`\>

#### Parameters

##### file

`File`

#### Returns

`Promise`\<`StorageNodeCreatedResponseDto`\>
