[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / CSVHelper

# Class: CSVHelper

Helper class for CSV operations.

## Constructors

### Constructor

> **new CSVHelper**(): `CSVHelper`

#### Returns

`CSVHelper`

## Properties

### lineSeparators

> `static` **lineSeparators**: `object`[]

#### label

> **label**: `string` = `'Detect automatically'`

#### value

> **value**: `string` = `''`

***

### recordSeparators

> `static` **recordSeparators**: `object`[]

#### label

> **label**: `string` = `'Detect automatically'`

#### value

> **value**: `string` = `''`

## Methods

### loadCSV()

> **loadCSV**(): `Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

Loads a CSV from the user's computer.
 Is shows a file selector dialog to select a file.

#### Returns

`Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

***

### loadCSVFromAssetFile()

> **loadCSVFromAssetFile**(`fileId`, `recordSeparator`, `lineSeparator`): `Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

Loads a CSV from an asset file.

#### Parameters

##### fileId

`string`

The ID of the asset file.

##### recordSeparator

`string` = `','`

##### lineSeparator

`string` = '\n'

#### Returns

`Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

***

### loadCSVFromText()

> **loadCSVFromText**(`text`, `recordSeparator`, `lineSeparator`): `Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

Loads a CSV from a string.

#### Parameters

##### text

`string`

The CSV as string.

##### recordSeparator

`string` = `','`

##### lineSeparator

`string` = '\n'

#### Returns

`Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

***

### parseCSVFromString()

> `protected` **parseCSVFromString**(`text`, `recordSeparator`, `lineSeparator`): `Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

Parses a CSV string.

#### Parameters

##### text

`string`

##### recordSeparator

`string` = `','`

##### lineSeparator

`string` = '\n'

#### Returns

`Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

***

### arrayToCsv()

> `static` **arrayToCsv**(`contentBlocks`, `recordSeparator`, `lineSeparator`): `string`

#### Parameters

##### contentBlocks

(`string` \| `number`)[] | (`string` \| `number`)[][]

##### recordSeparator

`string` = `','`

##### lineSeparator

`string` = '\n'

#### Returns

`string`

***

### csvToArray()

> `static` **csvToArray**(`csv`, `recordSeparator`, `lineSeparator`): [`CSVData`](../type-aliases/CSVData.md)

#### Parameters

##### csv

`string`

##### recordSeparator

`string` = `','`

##### lineSeparator

`string` = '\n'

#### Returns

[`CSVData`](../type-aliases/CSVData.md)

***

### hardCopy()

> `static` **hardCopy**(`data`): [`CSVData`](../type-aliases/CSVData.md)

#### Parameters

##### data

[`CSVData`](../type-aliases/CSVData.md)

#### Returns

[`CSVData`](../type-aliases/CSVData.md)

***

### loadCSVFromSpreadsheetAssetFile()

> `static` **loadCSVFromSpreadsheetAssetFile**(`fileId`, `sheetNumber`): `Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

#### Parameters

##### fileId

`string`

##### sheetNumber

`number` = `0`

#### Returns

`Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>
