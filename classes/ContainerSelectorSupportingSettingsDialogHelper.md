[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / ContainerSelectorSupportingSettingsDialogHelper

# Class: ContainerSelectorSupportingSettingsDialogHelper

Helper class for managing settings dialogs.

## Extends

- [`SettingsDialogHelper`](SettingsDialogHelper.md)

## Extended by

- [`OptionalContainerSelectorSupportingSettingsDialogHelper`](OptionalContainerSelectorSupportingSettingsDialogHelper.md)

## Constructors

### Constructor

> **new ContainerSelectorSupportingSettingsDialogHelper**(`settings`?, `options`?): `ContainerSelectorSupportingSettingsDialogHelper`

Constructs a new Settings Dialog.

#### Parameters

##### settings?

`DialogDefinition`

The settings for the dialog.

##### options?

`SettingsDialogOptions`

Options for the settings dialog.

#### Returns

`ContainerSelectorSupportingSettingsDialogHelper`

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`constructor`](SettingsDialogHelper.md#constructor)

### Constructor

> **new ContainerSelectorSupportingSettingsDialogHelper**(`settings`, `createSettingsButtonOnInit`?, `callbackOnSettingsDialogClose`?): `ContainerSelectorSupportingSettingsDialogHelper`

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

`ContainerSelectorSupportingSettingsDialogHelper`

#### Deprecated

Use the constructor with SettingsDialogOptions.

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`constructor`](SettingsDialogHelper.md#constructor)

## Properties

### isContainerOptional

> `protected` `readonly` **isContainerOptional**: `boolean` = `false`

***

### optionsCallback

> **optionsCallback**: `Function`

***

### title

> `readonly` **title**: `string` = `undefined`

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`title`](SettingsDialogHelper.md#title)

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

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`dialogSettings`](SettingsDialogHelper.md#dialogsettings)

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

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`addSettingsButtonToWidgetContextMenu`](SettingsDialogHelper.md#addsettingsbuttontowidgetcontextmenu)

***

### addSettingsToWidgetObjectSettings()

> **addSettingsToWidgetObjectSettings**(): `Promise`\<`void`\>

Adds settings to the widget object settings (ie. service, or advanced settings)

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`addSettingsToWidgetObjectSettings`](SettingsDialogHelper.md#addsettingstowidgetobjectsettings)

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

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`initialSettingsTransformation`](SettingsDialogHelper.md#initialsettingstransformation)

***

### openSettingsDialog()

> **openSettingsDialog**(): `Promise`\<`void`\>

Opens the settings dialog.

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`openSettingsDialog`](SettingsDialogHelper.md#opensettingsdialog)

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

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`processFormDialogResult`](SettingsDialogHelper.md#processformdialogresult)

***

### refreshFormData()

> `protected` **refreshFormData**(`settings`): `Promise`\<`FormlyDialogSettings`\<`FormlyDialogModel`\>\>

Refreshes the form data, before opening the dialog
by default it:
- fills the form with the current values before showing the dialog
- adds adjustments to fix issues related to tabs and required fields

#### Parameters

##### settings

`FormlyDialogSettings`

The settings to refresh.

#### Returns

`Promise`\<`FormlyDialogSettings`\<`FormlyDialogModel`\>\>

The refreshed settings.

#### Overrides

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`refreshFormData`](SettingsDialogHelper.md#refreshformdata)

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

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`updateDialogUiSettings`](SettingsDialogHelper.md#updatedialoguisettings)

***

### getAllContainersAsFormOptions()

> `static` **getAllContainersAsFormOptions**(): `FormlySelectOption`[]

#### Returns

`FormlySelectOption`[]

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

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`shouldDisableRequiredParam`](SettingsDialogHelper.md#shoulddisablerequiredparam)
