[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / ItemListHelper

# Class: ItemListHelper

## Constructors

### Constructor

> **new ItemListHelper**(`key`, `options`): `ItemListHelper`

#### Parameters

##### key

`string`

##### options

[`ItemListHelperOptions`](../type-aliases/ItemListHelperOptions.md) = `{}`

#### Returns

`ItemListHelper`

## Properties

### key

> `readonly` **key**: `string`

## Accessors

### currentLocallyStoredData

#### Get Signature

> **get** `protected` **currentLocallyStoredData**(): `any`

##### Returns

`any`

#### Set Signature

> **set** `protected` **currentLocallyStoredData**(`data`): `void`

##### Parameters

###### data

`any`

##### Returns

`void`

***

### data

#### Get Signature

> **get** **data**(): [`ListRecord`](../type-aliases/ListRecord.md)[]

##### Returns

[`ListRecord`](../type-aliases/ListRecord.md)[]

#### Set Signature

> **set** **data**(`data`): `void`

##### Parameters

###### data

[`ListRecord`](../type-aliases/ListRecord.md)[]

##### Returns

`void`

***

### length

#### Get Signature

> **get** **length**(): `number`

##### Returns

`number`

***

### settingsDialogOptions

#### Get Signature

> **get** **settingsDialogOptions**(): `FormlyFieldConfig`\<`FormlyFieldProps` & `object`\>[]

##### Returns

`FormlyFieldConfig`\<`FormlyFieldProps` & `object`\>[]

## Methods

### addItems()

> **addItems**(`items`): `void`

#### Parameters

##### items

`Partial`\<[`ListRecord`](../type-aliases/ListRecord.md)\>[]

#### Returns

`void`

***

### getFieldList()

> **getFieldList**\<`FieldType`\>(`key`): `FieldType`[]

#### Type Parameters

##### FieldType

`FieldType` = `string`

#### Parameters

##### key

`string` = `...`

#### Returns

`FieldType`[]

***

### getFieldListById()

> **getFieldListById**\<`FieldType`\>(`key`): `Record`\<`string`, `FieldType`\>

#### Type Parameters

##### FieldType

`FieldType` = `string`

#### Parameters

##### key

`string` = `...`

#### Returns

`Record`\<`string`, `FieldType`\>

***

### importFromCSV()

> **importFromCSV**(`data`): `any`

#### Parameters

##### data

`object`[]

#### Returns

`any`

***

### openImportDialog()

> **openImportDialog**(): `Promise`\<`void`\>

#### Returns

`Promise`\<`void`\>
