[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / SettingsDialogHelper

# Class: SettingsDialogHelper

Helper class for managing settings dialogs.

## Constructors

### new SettingsDialogHelper()

> **new SettingsDialogHelper**(`settings`, `createSettingsButtonOnInit`?, `callbackOnSettingsDialogClose`?): [`SettingsDialogHelper`](SettingsDialogHelper.md)

#### Parameters

• **settings**: `FormlyDialogSettings`\<`FormlyDialogModel`\>

The settings for the dialog.

• **createSettingsButtonOnInit?**: `boolean`

Whether to create the settings button on initialization.

• **callbackOnSettingsDialogClose?**

Callback function when the settings dialog is closed.

#### Returns

[`SettingsDialogHelper`](SettingsDialogHelper.md)

#### Deprecated

Use the constructor with SettingsDialogOptions.

### new SettingsDialogHelper()

> **new SettingsDialogHelper**(`settings`, `options`?): [`SettingsDialogHelper`](SettingsDialogHelper.md)

Constructs a new Settings Dialog.

#### Parameters

• **settings**: `FormlyDialogSettings`\<`FormlyDialogModel`\>

The settings for the dialog.

• **options?**: `SettingsDialogOptions`

Options for the settings dialog.

#### Returns

[`SettingsDialogHelper`](SettingsDialogHelper.md)

## Properties

### settings

> **settings**: `FormlyDialogSettings`\<`FormlyDialogModel`\>

***

### title

> `readonly` **title**: `string` = `undefined`

## Methods

### addSettingsToWidgetObjectSettings()

> **addSettingsToWidgetObjectSettings**(): `Promise`\<`void`\>

Adds settings to the widget object settings (ie. service, or advanced settings)

#### Returns

`Promise`\<`void`\>

***

### createSettingsButton()

> **createSettingsButton**(`button`): `void`

Creates a settings button on the widget bar.

#### Parameters

• **button**: `ContextMenuButton` = `undefined`

The context menu button to create.

#### Returns

`void`

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

• **ret**: `false` \| `""` \| `FormlyDialogModel`

The result of the form dialog.

#### Returns

`boolean`

Whether any settings were changed.

***

### refreshFormData()

> `protected` **refreshFormData**(`settings`): `FormlyDialogSettings`\<`FormlyDialogModel`\> \| `Promise`\<`FormlyDialogSettings`\<`FormlyDialogModel`\>\>

Refreshes the form data with the current settings.

#### Parameters

• **settings**: `FormlyDialogSettings`\<`FormlyDialogModel`\>

The settings to refresh.

#### Returns

`FormlyDialogSettings`\<`FormlyDialogModel`\> \| `Promise`\<`FormlyDialogSettings`\<`FormlyDialogModel`\>\>

The refreshed settings.

***

### updateDialogUiSettings()

> `protected` **updateDialogUiSettings**(`settings`): `FormlyDialogSettings`\<`FormlyDialogModel`\>

Updates the UI settings of the dialog.

#### Parameters

• **settings**: `FormlyDialogSettings`\<`FormlyDialogModel`\>

The settings to update.

#### Returns

`FormlyDialogSettings`\<`FormlyDialogModel`\>

The updated settings.

***

### updateSettings()

> `protected` **updateSettings**(`settings`): `FormlyDialogSettings`\<`FormlyDialogModel`\>

Updates the settings with the current options.

#### Parameters

• **settings**: `FormlyDialogSettings`\<`FormlyDialogModel`\>

The settings to update.

#### Returns

`FormlyDialogSettings`\<`FormlyDialogModel`\>

The updated settings.
