[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / CSVHelper

# Class: CSVHelper

Provides utilities for parsing, manipulating, and generating CSV data.

Handles CSV parsing with automatic delimiter detection, proper quote handling,
and support for various line ending formats. Includes methods for converting
between CSV strings and 2D arrays, downloading CSV files, and copying data to
clipboard. Essential for widgets working with tabular data import/export.

## Example

```typescript
// Parse CSV string to array
const csvString = 'Name,Age\nJohn,30\nJane,25';
const data = CSVHelper.csvToArray(csvString);
console.log(data); // [['Name', 'Age'], ['John', '30'], ['Jane', '25']]

// Convert array to CSV
const arrayData = [['Name', 'Age'], ['John', '30']];
const csv = CSVHelper.arrayToCsv(arrayData);

// Download CSV file
CSVHelper.downloadCsv(data, 'export.csv');

// Copy to clipboard
CSVHelper.copyToClipboard(data);

// Make a deep copy
const copy = CSVHelper.hardCopy(data);
```

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

> **loadCSVFromAssetFile**(`fileId`, `recordSeparator?`, `lineSeparator?`): `Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

Loads a CSV from an asset file.

#### Parameters

##### fileId

`string`

The ID of the asset file.

##### recordSeparator?

`string` = `','`

##### lineSeparator?

`string` = '\n'

#### Returns

`Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

***

### loadCSVFromText()

> **loadCSVFromText**(`text`, `recordSeparator?`, `lineSeparator?`): `Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

Loads a CSV from a string.

#### Parameters

##### text

`string`

The CSV as string.

##### recordSeparator?

`string` = `','`

##### lineSeparator?

`string` = '\n'

#### Returns

`Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

***

### parseCSVFromString()

> `protected` **parseCSVFromString**(`text`, `recordSeparator?`, `lineSeparator?`): `Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

Parses a CSV string.

#### Parameters

##### text

`string`

##### recordSeparator?

`string` = `','`

##### lineSeparator?

`string` = '\n'

#### Returns

`Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

***

### arrayToCsv()

> `static` **arrayToCsv**(`contentBlocks`, `recordSeparator?`, `lineSeparator?`): `string`

#### Parameters

##### contentBlocks

(`string` \| `number`)[] \| (`string` \| `number`)[][]

##### recordSeparator?

`string` = `','`

##### lineSeparator?

`string` = '\n'

#### Returns

`string`

***

### csvToArray()

> `static` **csvToArray**(`csv`, `recordSeparator?`, `lineSeparator?`): [`CSVData`](../type-aliases/CSVData.md)

#### Parameters

##### csv

`string`

##### recordSeparator?

`string` = `','`

##### lineSeparator?

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

> `static` **loadCSVFromSpreadsheetAssetFile**(`fileId`, `sheetNumber?`): `Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

#### Parameters

##### fileId

`string`

##### sheetNumber?

`number` = `0`

#### Returns

`Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>
