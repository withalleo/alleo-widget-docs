[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / DataImportHelper

# Class: DataImportHelper

Helper class for importing data.

## Constructors

### Constructor

> **new DataImportHelper**(`settings`): `DataImportHelper`

Creates an instance of DataImportHelper.

#### Parameters

##### settings

[`DataImportHelperSettings`](../type-aliases/DataImportHelperSettings.md)

The settings for the helper.

#### Returns

`DataImportHelper`

## Properties

### settings

> `protected` **settings**: [`DataImportHelperSettings`](../type-aliases/DataImportHelperSettings.md)

The settings for the helper.

## Methods

### getColumnNames()

> **getColumnNames**(`limit`): `string`[]

Gets the column names.

#### Parameters

##### limit

`number` = `100`

The maximum number of column names to return.

#### Returns

`string`[]

The array of column names.

***

### import()

> **import**(): `Promise`\<\{ `data`: `object`[]; `shouldOverwrite`: `boolean`; `totalCSVLines`: `number`; \}\>

Imports data.

#### Returns

`Promise`\<\{ `data`: `object`[]; `shouldOverwrite`: `boolean`; `totalCSVLines`: `number`; \}\>

An object containing import results.

***

### importToCsv()

> **importToCsv**(`finalStep`): `Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

Imports data from a CSV file.

#### Parameters

##### finalStep

`boolean` = `false`

Indicates if this is the final step of the import.

#### Returns

`Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

The imported CSV data.
