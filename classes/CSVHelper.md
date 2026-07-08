[**@withalleo/alleo-widget**](../README.md)

---

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
const csvString = "Name,Age\nJohn,30\nJane,25";
const data = CSVHelper.csvToArray(csvString);
console.log(data); // [['Name', 'Age'], ['John', '30'], ['Jane', '25']]

// Convert array to CSV
const arrayData = [
  ["Name", "Age"],
  ["John", "30"],
];
const csv = CSVHelper.arrayToCsv(arrayData);

// Download CSV file
CSVHelper.downloadCsv(data, "export.csv");

// Copy to clipboard
CSVHelper.copyToClipboard(data);

// Make a deep copy
const copy = CSVHelper.hardCopy(data);
```

## Constructors

### Constructor

```ts
new CSVHelper(): CSVHelper;
```

#### Returns

`CSVHelper`

## Properties

### lineSeparators

```ts
static lineSeparators: {
  label: string;
  value: string;
}[];
```

#### label

```ts
label: string = "Detect automatically";
```

#### value

```ts
value: string = "";
```

---

### recordSeparators

```ts
static recordSeparators: {
  label: string;
  value: string;
}[];
```

#### label

```ts
label: string = "Detect automatically";
```

#### value

```ts
value: string = "";
```

## Methods

### loadCSV()

```ts
loadCSV(): Promise<CSVData>;
```

Loads a CSV from the user's computer.
Is shows a file selector dialog to select a file.

#### Returns

`Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

---

### loadCSVFromAssetFile()

```ts
loadCSVFromAssetFile(
   fileId: string,
   recordSeparator?: string,
lineSeparator?: string): Promise<CSVData>;
```

Loads a CSV from an asset file.

#### Parameters

| Parameter         | Type     | Default value | Description               |
| ----------------- | -------- | ------------- | ------------------------- |
| `fileId`          | `string` | `undefined`   | The ID of the asset file. |
| `recordSeparator` | `string` | `','`         | -                         |
| `lineSeparator`   | `string` | '\n'          | -                         |

#### Returns

`Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

---

### loadCSVFromText()

```ts
loadCSVFromText(
   text: string,
   recordSeparator?: string,
lineSeparator?: string): Promise<CSVData>;
```

Loads a CSV from a string.

#### Parameters

| Parameter         | Type     | Default value | Description        |
| ----------------- | -------- | ------------- | ------------------ |
| `text`            | `string` | `undefined`   | The CSV as string. |
| `recordSeparator` | `string` | `','`         | -                  |
| `lineSeparator`   | `string` | '\n'          | -                  |

#### Returns

`Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

---

### parseCSVFromString()

```ts
protected parseCSVFromString(
   text: string,
   recordSeparator?: string,
lineSeparator?: string): Promise<CSVData>;
```

Parses a CSV string.

#### Parameters

| Parameter         | Type     | Default value | Description |
| ----------------- | -------- | ------------- | ----------- |
| `text`            | `string` | `undefined`   | -           |
| `recordSeparator` | `string` | `','`         | -           |
| `lineSeparator`   | `string` | '\n'          | -           |

#### Returns

`Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

---

### arrayToCsv()

```ts
static arrayToCsv(
   contentBlocks: (string | number)[] | (string | number)[][],
   recordSeparator?: string,
   lineSeparator?: string): string;
```

#### Parameters

| Parameter         | Type                                                   | Default value |
| ----------------- | ------------------------------------------------------ | ------------- |
| `contentBlocks`   | (`string` \| `number`)[] \| (`string` \| `number`)[][] | `undefined`   |
| `recordSeparator` | `string`                                               | `','`         |
| `lineSeparator`   | `string`                                               | '\n'          |

#### Returns

`string`

---

### csvToArray()

```ts
static csvToArray(
   csv: string,
   recordSeparator?: string,
   lineSeparator?: string): CSVData;
```

#### Parameters

| Parameter         | Type     | Default value |
| ----------------- | -------- | ------------- |
| `csv`             | `string` | `undefined`   |
| `recordSeparator` | `string` | `','`         |
| `lineSeparator`   | `string` | '\n'          |

#### Returns

[`CSVData`](../type-aliases/CSVData.md)

---

### hardCopy()

```ts
static hardCopy(data: CSVData): CSVData;
```

#### Parameters

| Parameter | Type                                    |
| --------- | --------------------------------------- |
| `data`    | [`CSVData`](../type-aliases/CSVData.md) |

#### Returns

[`CSVData`](../type-aliases/CSVData.md)

---

### loadCSVFromSpreadsheetAssetFile()

```ts
static loadCSVFromSpreadsheetAssetFile(fileId: string, sheetNumber?: number): Promise<CSVData>;
```

#### Parameters

| Parameter     | Type     | Default value |
| ------------- | -------- | ------------- |
| `fileId`      | `string` | `undefined`   |
| `sheetNumber` | `number` | `0`           |

#### Returns

`Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>
