[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / DataConnector

# Class: DataConnector

## Constructors

### Constructor

> **new DataConnector**(`objectId`): `DataConnector`

#### Parameters

##### objectId

`string`

#### Returns

`DataConnector`

## Accessors

### length

#### Get Signature

> **get** **length**(): `number`

##### Returns

`number`

***

### supportedActions

#### Get Signature

> **get** **supportedActions**(): [`DataConnectorActions`](../enumerations/DataConnectorActions.md)[]

##### Returns

[`DataConnectorActions`](../enumerations/DataConnectorActions.md)[]

## Methods

### append()

> **append**(`row`): `Promise`\<`boolean`\>

#### Parameters

##### row

`string`[]

#### Returns

`Promise`\<`boolean`\>

***

### export()

> **export**(): `Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

#### Returns

`Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

***

### import()

> **import**(`data`): `Promise`\<`boolean`\>

#### Parameters

##### data

[`CSVData`](../type-aliases/CSVData.md)

#### Returns

`Promise`\<`boolean`\>
