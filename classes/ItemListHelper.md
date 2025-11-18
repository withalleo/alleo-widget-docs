[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / ItemListHelper

# Class: ItemListHelper

Helper class for managing a list of items with import, export, and edit capabilities.

## Constructors

### Constructor

> **new ItemListHelper**(`key`, `options`): `ItemListHelper`

Creates an instance of ItemListHelper.

#### Parameters

##### key

`string`

The key used to store the list data.

##### options

[`ItemListHelperOptions`](../type-aliases/ItemListHelperOptions.md) = `{}`

Configuration options for the helper.

#### Returns

`ItemListHelper`

## Properties

### key

> `readonly` **key**: `string`

The key used to store the list data.

## Accessors

### currentLocallyStoredData

#### Get Signature

> **get** `protected` **currentLocallyStoredData**(): `any`

Gets the locally stored data for the list.

##### Returns

`any`

#### Set Signature

> **set** `protected` **currentLocallyStoredData**(`data`): `void`

Sets the locally stored data for the list.

##### Throws

Error if edits are disabled.

##### Parameters

###### data

`any`

##### Returns

`void`

***

### data

#### Get Signature

> **get** **data**(): [`ListRecord`](../type-aliases/ListRecord.md)[]

Gets the current list data.

##### Returns

[`ListRecord`](../type-aliases/ListRecord.md)[]

#### Set Signature

> **set** **data**(`data`): `void`

Sets the list data.

##### Throws

Error if the list is read-only.

##### Parameters

###### data

[`ListRecord`](../type-aliases/ListRecord.md)[]

##### Returns

`void`

***

### length

#### Get Signature

> **get** **length**(): `number`

Gets the number of items in the list.

##### Returns

`number`

***

### settingsDialogOptions

#### Get Signature

> **get** **settingsDialogOptions**(): `FormlyFieldConfig`\<`FormlyFieldProps` & `object`\>[]

Gets the settings dialog options for configuring the list.

##### Returns

`FormlyFieldConfig`\<`FormlyFieldProps` & `object`\>[]

## Methods

### addItems()

> **addItems**(`items`): `void`

Adds items to the list.

#### Parameters

##### items

`Partial`\<[`ListRecord`](../type-aliases/ListRecord.md)\>[]

Array of items to add.

#### Returns

`void`

#### Throws

Error if the list is read-only.

***

### getFieldList()

> **getFieldList**\<`FieldType`\>(`key`): `FieldType`[]

Gets a list of field values for a given key.

#### Type Parameters

##### FieldType

`FieldType` = `string`

#### Parameters

##### key

`string` = `...`

The field key to retrieve values for.

#### Returns

`FieldType`[]

***

### getFieldListById()

> **getFieldListById**\<`FieldType`\>(`key`): `Record`\<`string`, `FieldType`\>

Gets a record of field values by item id for a given key.

#### Type Parameters

##### FieldType

`FieldType` = `string`

#### Parameters

##### key

`string` = `...`

The field key to retrieve values for.

#### Returns

`Record`\<`string`, `FieldType`\>

***

### importFromCSV()

> **importFromCSV**(`data`): `any`

Imports items from CSV data.

#### Parameters

##### data

`object`[]

Array of objects representing CSV rows.

#### Returns

`any`

Array of imported items.

#### Throws

Error if no items are found in the CSV file.

***

### openImportDialog()

> **openImportDialog**(): `Promise`\<`void`\>

Opens the import dialog for importing items.

#### Returns

`Promise`\<`void`\>
