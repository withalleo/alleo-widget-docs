[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / DataImportHelper

# Class: DataImportHelper

## Constructors

### Constructor

> **new DataImportHelper**(`settings`): `DataImportHelper`

#### Parameters

##### settings

[`DataImportHelperSettings`](../type-aliases/DataImportHelperSettings.md)

#### Returns

`DataImportHelper`

## Properties

### settings

> `protected` **settings**: [`DataImportHelperSettings`](../type-aliases/DataImportHelperSettings.md)

## Methods

### getColumnNames()

> **getColumnNames**(`limit`): `string`[]

#### Parameters

##### limit

`number` = `100`

#### Returns

`string`[]

***

### import()

> **import**(): `Promise`\<\{ `data`: `object`[]; `shouldOverwrite`: `boolean`; `totalCSVLines`: `number`; \}\>

#### Returns

`Promise`\<\{ `data`: `object`[]; `shouldOverwrite`: `boolean`; `totalCSVLines`: `number`; \}\>

***

### importToCsv()

> **importToCsv**(): `Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

#### Returns

`Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>
