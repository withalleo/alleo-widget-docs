[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / SettingsDialogHelper

# Class: SettingsDialogHelper

Helper class for managing settings dialogs.

## Extended by

- [`ContainerSelectorSupportingSettingsDialogHelper`](ContainerSelectorSupportingSettingsDialogHelper.md)
- [`OptionalLocationSelectorSupportingSettingsDialogHelper`](OptionalLocationSelectorSupportingSettingsDialogHelper.md)

## Constructors

### Constructor

> **new SettingsDialogHelper**(`settings`?, `options`?): `SettingsDialogHelper`

Constructs a new Settings Dialog.

#### Parameters

##### settings?

`DialogDefinition`

The settings for the dialog.

##### options?

`SettingsDialogOptions`

Options for the settings dialog.

#### Returns

`SettingsDialogHelper`

### Constructor

> **new SettingsDialogHelper**(`settings`, `createSettingsButtonOnInit`?, `callbackOnSettingsDialogClose`?): `SettingsDialogHelper`

#### Parameters

##### settings

`DialogDefinition`

The settings for the dialog.

##### createSettingsButtonOnInit?

`boolean`

Whether to create the settings button on initialization.

##### callbackOnSettingsDialogClose?

(`didAnythingChanged`, `changedProperties`, `ret`) => `void`

Callback function when the settings dialog is closed.

#### Returns

`SettingsDialogHelper`

#### Deprecated

Use the constructor with SettingsDialogOptions.

## Properties

### title

> `readonly` **title**: `string` = `undefined`

## Accessors

### dialogSettings

#### Get Signature

> **get** **dialogSettings**(): `DialogDefinition`

The current settings for the dialog.

##### Returns

`DialogDefinition`

#### Set Signature

> **set** **dialogSettings**(`settings`): `void`

Sets the settings for the dialog.

##### Parameters

###### settings

`DialogDefinition`

The settings to set.

##### Returns

`void`

## Methods

### addSettingsButtonToWidgetContextMenu()

> **addSettingsButtonToWidgetContextMenu**(`button`): `void`

Creates a settings button on the widget bar.

#### Parameters

##### button

`ContextMenuButton` = `undefined`

The context menu button to create.

#### Returns

`void`

***

### addSettingsToWidgetObjectSettings()

> **addSettingsToWidgetObjectSettings**(): `Promise`\<`void`\>

Adds settings to the widget object settings (ie. service, or advanced settings)

#### Returns

`Promise`\<`void`\>

***

### initialSettingsTransformation()

> `protected` **initialSettingsTransformation**(`settings`): `FormlyDialogSettings`

Updates the settings with the current options.

#### Parameters

##### settings

`FormlyDialogSettings`

The settings to update.

#### Returns

`FormlyDialogSettings`

The updated settings.

***

### openSettingsDialog()

> **openSettingsDialog**(): `Promise`\<`void`\>

Opens the settings dialog.

#### Returns

`Promise`\<`void`\>

***

### processFormDialogResult()

> `protected` **processFormDialogResult**(`ret`): `boolean`

Processes the result of the form dialog. (including saving the settings)

#### Parameters

##### ret

The result of the form dialog.

`false` | `""` | `FormlyDialogModel`

#### Returns

`boolean`

Whether any settings were changed.

***

### refreshFormData()

> `protected` **refreshFormData**(`settings`): `FormlyDialogSettings`\<`FormlyDialogModel`\> \| `Promise`\<`FormlyDialogSettings`\<`FormlyDialogModel`\>\>

Refreshes the form data, before opening the dialog
by default it:
- fills the form with the current values before showing the dialog
- adds adjustments to fix issues related to tabs and required fields

#### Parameters

##### settings

`FormlyDialogSettings`

The settings to refresh.

#### Returns

`FormlyDialogSettings`\<`FormlyDialogModel`\> \| `Promise`\<`FormlyDialogSettings`\<`FormlyDialogModel`\>\>

The refreshed settings.

***

### updateDialogUiSettings()

> `protected` **updateDialogUiSettings**(`settings`): `FormlyDialogSettings`

Updates the UI settings of the dialog.

#### Parameters

##### settings

`FormlyDialogSettings`

The settings to update.

#### Returns

`FormlyDialogSettings`

The updated settings.

***

### shouldDisableRequiredParam()

> `static` **shouldDisableRequiredParam**(`model`): `boolean`

Determines whether to disable required parameter for a field. (due to conflicts with being hidden)

#### Parameters

##### model

`FormlyFieldConfig`

The Formly form model to check.

#### Returns

`boolean`
