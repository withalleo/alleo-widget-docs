[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / HelpButtonHelper

# Class: HelpButtonHelper

A helper class for managing the "Help" button in Alleo widgets.

Allows you to open .md files in Help dialogs.

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

Returns the definition of the help button for the context menu.

##### Returns

`ContextMenuButtonDefinition`

The button definition.

***

### helpFileUrl

#### Get Signature

> **get** `protected` **helpFileUrl**(): `string`

##### Returns

`string`

## Methods

### addButton()

> **addButton**(): `void`

Adds the help button to the context menu if conditions are met.

#### Returns

`void`

#### Throws

If the DOM is not available.

***

### getHtmlHelpContent()

> **getHtmlHelpContent**(): `Promise`\<`string`\>

Converts the markdown help content to HTML.

#### Returns

`Promise`\<`string`\>

The HTML content as a string.

***

### getMarkdownHelpContent()

> **getMarkdownHelpContent**(): `Promise`\<`string`\>

Fetches the markdown content for the help file.

#### Returns

`Promise`\<`string`\>

The markdown content as a string.

#### Throws

If the fetch request fails.

***

### getSettingsButton()

> **getSettingsButton**(`label?`, `buttonOptions?`): `FormlyFieldConfig`\<`FormlyFieldProps`\>

Creates a settings button with the provided label and options.

#### Parameters

##### label?

`string` = `'Help'`

The label for the button.

##### buttonOptions?

[`FormButtonHelperSettings`](../type-aliases/FormButtonHelperSettings.md) = `undefined`

Additional options for the button.

#### Returns

`FormlyFieldConfig`\<`FormlyFieldProps`\>

The configuration for the settings button.

***

### showHelp()

> **showHelp**(): `Promise`\<`void`\>

Displays the help dialog with the help content.
Tracks the button click event and shows the dialog with the help content.

#### Returns

`Promise`\<`void`\>

***

### openFormWithoutPrimaryButton()

> `static` **openFormWithoutPrimaryButton**\<`FormlyDialogModel`\>(`settings`): `Promise`\<`false` \| `""` \| `FormlyDialogModel`\>

Opens a form dialog without a primary button.

#### Type Parameters

##### FormlyDialogModel

`FormlyDialogModel` = `Record`\<`string`, `any`\>

#### Parameters

##### settings

`FormlyDialogSettings`\<`FormlyDialogModel`\>

The settings for the dialog.

#### Returns

`Promise`\<`false` \| `""` \| `FormlyDialogModel`\>

The result of the dialog.
