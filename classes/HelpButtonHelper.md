[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / HelpButtonHelper

# Class: HelpButtonHelper

## Constructors

### Constructor

> **new HelpButtonHelper**(`settings`): `HelpButtonHelper`

#### Parameters

##### settings

`HelpButtonHelperSettings` = `{}`

#### Returns

`HelpButtonHelper`

## Accessors

### button

#### Get Signature

> **get** **button**(): `ContextMenuButtonDefinition`

##### Returns

`ContextMenuButtonDefinition`

***

### helpFileUrl

#### Get Signature

> **get** `protected` **helpFileUrl**(): `string`

##### Returns

`string`

## Methods

### addButton()

> **addButton**(): `void`

#### Returns

`void`

***

### getHtmlHelpContent()

> **getHtmlHelpContent**(): `Promise`\<`string`\>

#### Returns

`Promise`\<`string`\>

***

### getMarkdownHelpContent()

> **getMarkdownHelpContent**(): `Promise`\<`string`\>

#### Returns

`Promise`\<`string`\>

***

### showHelp()

> **showHelp**(): `Promise`\<`void`\>

#### Returns

`Promise`\<`void`\>

***

### openFormWithoutPrimaryButton()

> `static` **openFormWithoutPrimaryButton**\<`FormlyDialogModel`\>(`settings`): `Promise`\<`false` \| `""` \| `FormlyDialogModel`\>

#### Type Parameters

##### FormlyDialogModel

`FormlyDialogModel` = `Record`\<`string`, `any`\>

#### Parameters

##### settings

`FormlyDialogSettings`\<`FormlyDialogModel`\>

#### Returns

`Promise`\<`false` \| `""` \| `FormlyDialogModel`\>
