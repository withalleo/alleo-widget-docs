[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / DataConnector

# Class: DataConnector

Thin helper wrapper for interacting with a DataConnector widget on the board.

This class calls the exposed connector actions on a specific board object identified by `objectId`.

## Constructors

### Constructor

> **new DataConnector**(`objectId`): `DataConnector`

Creates a new helper bound to a specific board object.

#### Parameters

##### objectId

`string`

ID of the board object (widget instance) to interact with.

#### Returns

`DataConnector`

## Accessors

### length

#### Get Signature

> **get** **length**(): `number`

Number of records reported by the underlying DataConnector widget.

##### Returns

`number`

***

### supportedActions

#### Get Signature

> **get** **supportedActions**(): [`DataConnectorAction`](../enumerations/DataConnectorAction.md)[]

Actions that the underlying DataConnector widget reports as supported.

##### Returns

[`DataConnectorAction`](../enumerations/DataConnectorAction.md)[]

## Methods

### append()

> **append**(`row`): `Promise`\<`boolean`\>

Appends a single record to the underlying DataConnector.

#### Parameters

##### row

`string`[]

Record to append.

#### Returns

`Promise`\<`boolean`\>

Whatever the widget's `append` implementation returns, typically `true` on success.

***

### deleteLine()

> **deleteLine**(`lineNumber`): `Promise`\<`boolean`\>

Deletes a specific record from the underlying DataConnector.

#### Parameters

##### lineNumber

`number`

Zero-based index of the record to delete.

#### Returns

`Promise`\<`boolean`\>

Whatever the widget's `deleteLine` implementation returns.

***

### export()

> **export**(): `Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

Exports all records from the underlying DataConnector.

#### Returns

`Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

Exported records as a 2D CSV array.

***

### getLine()

> **getLine**(`lineNumber?`): `Promise`\<`string`[]\>

Reads a specific record from the underlying DataConnector.

#### Parameters

##### lineNumber?

`number` = `0`

Zero-based index of the record to fetch. Defaults to `0`.

#### Returns

`Promise`\<`string`[]\>

The requested record as an array of string values.

***

### import()

> **import**(`data`): `Promise`\<`boolean`\>

Imports data into the underlying DataConnector, replacing its current content.

#### Parameters

##### data

[`CSVData`](../type-aliases/CSVData.md)

Records to import.

#### Returns

`Promise`\<`boolean`\>

Whatever the widget's `import` implementation returns, typically `true` on success.

***

### reset()

> **reset**(): `Promise`\<`boolean`\>

Resets the underlying DataConnector widget.

#### Returns

`Promise`\<`boolean`\>

Whatever the widget's `reset` implementation returns.

***

### setLine()

> **setLine**(`row`): `Promise`\<`boolean`\>

Replaces a specific record in the underlying DataConnector.

#### Parameters

##### row

`string`[]

New record content.

#### Returns

`Promise`\<`boolean`\>

Whatever the widget's `setLine` implementation returns.
