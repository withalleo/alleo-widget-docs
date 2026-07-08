[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / DataImportHelper

# Class: DataImportHelper

Facilitates importing data from spreadsheet files and data connectors.

Provides UI workflows for selecting files, choosing spreadsheet sheets, mapping columns
to fields, and importing data as CSV. Supports Excel files, Google Sheets, and integration
with data connector widgets. Includes line limits, overwrite confirmation, and field
mapping validation. Essential for widgets that need to import structured data.

## Example

```typescript
// Configure import with field mapping
const importHelper = new DataImportHelper({
  fields: [
    { name: "name", label: "Full Name" },
    { name: "email", label: "Email Address" },
    { name: "phone", label: "Phone Number" },
  ],
  allowImportFromDataConnector: true,
  label: "Import Contacts",
  askAboutOverwrite: true,
  lineLimit: 500,
  warningMessage: "Large imports may take time",
});

// Import data from file
const csvData = await importHelper.importToCsv(true);
console.log("Imported rows:", csvData.length);

// Process imported data
csvData.forEach((row) => {
  processContact(row);
});
```

## Constructors

### Constructor

```ts
new DataImportHelper(settings: DataImportHelperSettings): DataImportHelper;
```

Creates a DataImportHelper instance configured for data import workflows.

#### Parameters

| Parameter  | Type                                                                      | Description                           |
| ---------- | ------------------------------------------------------------------------- | ------------------------------------- |
| `settings` | [`DataImportHelperSettings`](../type-aliases/DataImportHelperSettings.md) | Configuration for the import process. |

#### Returns

`DataImportHelper`

## Properties

### settings

```ts
protected settings: DataImportHelperSettings;
```

Configuration for the import process.

## Methods

### getColumnNames()

```ts
getColumnNames(limit?: number): string[];
```

Generates column names in spreadsheet format (A, B, C... Z, AA, AB...).

Creates Excel-style column labels for use in column mapping interfaces.

#### Parameters

| Parameter | Type     | Default value | Description                         |
| --------- | -------- | ------------- | ----------------------------------- |
| `limit?`  | `number` | `100`         | Number of column names to generate. |

#### Returns

`string`[]

Array of column names (e.g., ['A', 'B', 'C'...]).

---

### import()

```ts
import(): Promise<{
  data: {
   [p: string]: string;
  }[];
  shouldOverwrite: boolean;
  totalCSVLines: number;
}>;
```

Imports data.

#### Returns

`Promise`\<\{
`data`: \{
\[`p`: `string`\]: `string`;
\}[];
`shouldOverwrite`: `boolean`;
`totalCSVLines`: `number`;
\}\>

An object containing import results.

---

### importToCsv()

```ts
importToCsv(finalStep?: boolean): Promise<CSVData>;
```

Imports data from a spreadsheet file with interactive dialogs.

Guides the user through selecting a file, choosing a sheet (if multiple),
mapping columns to fields, and importing the data as CSV format.

#### Parameters

| Parameter    | Type      | Default value | Description                                             |
| ------------ | --------- | ------------- | ------------------------------------------------------- |
| `finalStep?` | `boolean` | `false`       | Whether this is the final step in a multi-step process. |

#### Returns

`Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

The imported data as a 2D array (rows and columns).
