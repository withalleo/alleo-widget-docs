[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / DataConnector

# Class: DataConnector

Helper class for interacting with DataConnector widgets on the board.

## Constructors

### Constructor

> **new DataConnector**(`objectId`): `DataConnector`

#### Parameters

##### objectId

`string`

The ID of the board object to interact with.

#### Returns

`DataConnector`

## Accessors

### length

#### Get Signature

> **get** **length**(): `number`

Returns the number of records in the DataConnector widget.

##### Returns

`number`

***

### supportedActions

#### Get Signature

> **get** **supportedActions**(): [`DataConnectorActions`](../enumerations/DataConnectorActions.md)[]

Returns the actions supported by the DataConnector widget.

##### Returns

[`DataConnectorActions`](../enumerations/DataConnectorActions.md)[]

## Methods

### append()

> **append**(`row`): `Promise`\<`boolean`\>

Appends a row to the DataConnector widget.

#### Parameters

##### row

`string`[]

The row to append.

#### Returns

`Promise`\<`boolean`\>

***

### export()

> **export**(): `Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

Exports the data from the DataConnector widget.

#### Returns

`Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

The exported CSV data.

***

### import()

> **import**(`data`): `Promise`\<`boolean`\>

Imports data into the DataConnector widget.

#### Parameters

##### data

[`CSVData`](../type-aliases/CSVData.md)

The CSV data to import.

#### Returns

`Promise`\<`boolean`\>
