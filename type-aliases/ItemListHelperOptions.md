[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / ItemListHelperOptions

# Type Alias: ItemListHelperOptions

> **ItemListHelperOptions** = `object`

Options for configuring the ItemListHelper.

## Properties

### allowDataConnectors?

> `optional` **allowDataConnectors**: `boolean`

***

### allowImport?

> `optional` **allowImport**: `boolean`

***

### allowLocalEdit?

> `optional` **allowLocalEdit**: `boolean`

***

### allowReordering?

> `optional` **allowReordering**: `boolean`

***

### dataSourceLabel?

> `optional` **dataSourceLabel**: `string`

***

### defaultValue?

> `optional` **defaultValue**: [`ListRecord`](ListRecord.md)[]

***

### disableAllEdits?

> `optional` **disableAllEdits**: `boolean`

***

### elements?

> `optional` **elements**: `FormlyFieldConfig`\<`FormlyFieldProps` & `object`\>[]

***

### importSettings?

> `optional` **importSettings**: `Omit`\<[`DataImportHelperSettings`](DataImportHelperSettings.md), `"fields"`\>

***

### label?

> `optional` **label**: `string`

***

### localListProps?

> `optional` **localListProps**: `Record`\<`string`, `any`\>

***

### migrateIdGenerateFunction()?

> `optional` **migrateIdGenerateFunction**: (`element`, `list`, `index`) => `string`

#### Parameters

##### element

`unknown`

##### list

`unknown`[]

##### index

`number`

#### Returns

`string`

***

### migrateOldArrayTypeList?

> `optional` **migrateOldArrayTypeList**: `boolean`

***

### newIdGenerateFunction()?

> `optional` **newIdGenerateFunction**: () => `string`

#### Returns

`string`

***

### onListChangeCallback()?

> `optional` **onListChangeCallback**: (`list`) => `void`

#### Parameters

##### list

[`ListRecord`](ListRecord.md)[]

#### Returns

`void`

***

### readonlyApi?

> `optional` **readonlyApi**: `boolean`
