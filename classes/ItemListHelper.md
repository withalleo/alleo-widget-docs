[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / ItemListHelper

# Class: ItemListHelper

Manages dynamic lists of items with import, export, reordering, and editing capabilities.

Provides comprehensive list management including item addition/removal, CSV import/export,
data connector integration, reordering via drag-and-drop, and form-based editing. Stores
data in shared variables with automatic ID generation and change tracking. Essential for
widgets managing collections of user-defined items.

## Example

```typescript
// Create a list of contacts
const contactList = new ItemListHelper("contacts", {
  label: "Contact List",
  allowReordering: true,
  allowImport: true,
  elements: [
    { key: "name", type: "input", props: { label: "Name", required: true } },
    { key: "email", type: "input", props: { label: "Email", type: "email" } },
    { key: "phone", type: "input", props: { label: "Phone" } },
  ],
  importSettings: {
    fields: [
      { name: "name", label: "Name" },
      { name: "email", label: "Email" },
      { name: "phone", label: "Phone" },
    ],
  },
  onListChangeCallback: (list) => {
    console.log("List updated:", list.length, "items");
  },
});

// Get current list
const items = contactList.list;
```

## Constructors

### Constructor

```ts
new ItemListHelper(key: string, options?: ItemListHelperOptions): ItemListHelper;
```

Creates an instance of ItemListHelper.

#### Parameters

| Parameter | Type                                                                | Description                           |
| --------- | ------------------------------------------------------------------- | ------------------------------------- |
| `key`     | `string`                                                            | The key used to store the list data.  |
| `options` | [`ItemListHelperOptions`](../type-aliases/ItemListHelperOptions.md) | Configuration options for the helper. |

#### Returns

`ItemListHelper`

## Properties

### key

```ts
readonly key: string;
```

The key used to store the list data.

## Accessors

### currentLocallyStoredData

#### Get Signature

```ts
get protected currentLocallyStoredData(): any;
```

Gets the locally stored data for the list.

##### Returns

`any`

#### Set Signature

```ts
set protected currentLocallyStoredData(data: any): void;
```

Sets the locally stored data for the list.

##### Throws

Error if edits are disabled.

##### Parameters

| Parameter | Type  |
| --------- | ----- |
| `data`    | `any` |

##### Returns

`void`

---

### data

#### Get Signature

```ts
get data(): ListRecord[];
```

Gets the current list data.

##### Returns

[`ListRecord`](../type-aliases/ListRecord.md)[]

#### Set Signature

```ts
set data(data: ListRecord[]): void;
```

Sets the list data.

##### Throws

Error if the list is read-only.

##### Parameters

| Parameter | Type                                            |
| --------- | ----------------------------------------------- |
| `data`    | [`ListRecord`](../type-aliases/ListRecord.md)[] |

##### Returns

`void`

---

### length

#### Get Signature

```ts
get length(): number;
```

Gets the number of items in the list.

##### Returns

`number`

---

### settingsDialogOptions

#### Get Signature

```ts
get settingsDialogOptions(): FormlyFieldConfig<FormlyFieldProps & {
[p: string]: any;
}>[];
```

Gets the settings dialog options for configuring the list.

##### Returns

`FormlyFieldConfig`\<`FormlyFieldProps` & \{
\[`p`: `string`\]: `any`;
\}\>[]

## Methods

### addItems()

```ts
addItems(items: Partial<ListRecord>[]): void;
```

Adds items to the list.

#### Parameters

| Parameter | Type                                                         | Description            |
| --------- | ------------------------------------------------------------ | ---------------------- |
| `items`   | `Partial`\<[`ListRecord`](../type-aliases/ListRecord.md)\>[] | Array of items to add. |

#### Returns

`void`

#### Throws

Error if the list is read-only.

---

### getFieldList()

```ts
getFieldList<FieldType>(key?: string): FieldType[];
```

Gets a list of field values for a given key.

#### Type Parameters

| Type Parameter | Default type |
| -------------- | ------------ |
| `FieldType`    | `string`     |

#### Parameters

| Parameter | Type     | Description                           |
| --------- | -------- | ------------------------------------- |
| `key`     | `string` | The field key to retrieve values for. |

#### Returns

`FieldType`[]

---

### getFieldListById()

```ts
getFieldListById<FieldType>(key?: string): Record<string, FieldType>;
```

Gets a record of field values by item id for a given key.

#### Type Parameters

| Type Parameter | Default type |
| -------------- | ------------ |
| `FieldType`    | `string`     |

#### Parameters

| Parameter | Type     | Description                           |
| --------- | -------- | ------------------------------------- |
| `key`     | `string` | The field key to retrieve values for. |

#### Returns

`Record`\<`string`, `FieldType`\>

---

### importFromCSV()

```ts
importFromCSV(data: {
[key: string]: string;
}[]): any;
```

Imports items from CSV data.

#### Parameters

| Parameter | Type                                   | Description                             |
| --------- | -------------------------------------- | --------------------------------------- |
| `data`    | \{ \[`key`: `string`\]: `string`; \}[] | Array of objects representing CSV rows. |

#### Returns

`any`

Array of imported items.

#### Throws

Error if no items are found in the CSV file.

---

### openImportDialog()

```ts
openImportDialog(): Promise<void>;
```

Opens the import dialog for importing items.

#### Returns

`Promise`\<`void`\>
