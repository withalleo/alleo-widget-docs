[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / ContainerSelectorSupportingSettingsDialogHelper

# ~~Class: ContainerSelectorSupportingSettingsDialogHelper~~

Legacy helper for settings dialogs with container selection dropdown.

## Deprecated

Use ObjectSelectorSettingsDialogHelper instead.

## Example

```typescript
// Legacy usage (deprecated)
const settingsHelper = new ContainerSelectorSupportingSettingsDialogHelper(...);

// Use this instead:
// const settingsHelper = new ObjectSelectorSettingsDialogHelper(...);
```

## Extends

- [`SettingsDialogHelper`](SettingsDialogHelper.md)

## Extended by

- [`OptionalContainerSelectorSupportingSettingsDialogHelper`](OptionalContainerSelectorSupportingSettingsDialogHelper.md)

## Constructors

### Constructor

```ts
new ContainerSelectorSupportingSettingsDialogHelper(settings?: SettingsDialogDefinition, options?: SettingsDialogOptions): ContainerSelectorSupportingSettingsDialogHelper;
```

Constructs a new Settings Dialog.

#### Parameters

| Parameter   | Type                                                                    | Description                      |
| ----------- | ----------------------------------------------------------------------- | -------------------------------- |
| `settings?` | [`SettingsDialogDefinition`](../interfaces/SettingsDialogDefinition.md) | The settings for the dialog.     |
| `options?`  | `SettingsDialogOptions`                                                 | Options for the settings dialog. |

#### Returns

`ContainerSelectorSupportingSettingsDialogHelper`

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`constructor`](SettingsDialogHelper.md#constructor)

### Constructor

```ts
new ContainerSelectorSupportingSettingsDialogHelper(
   settings: SettingsDialogDefinition,
   createSettingsButtonOnInit?: boolean,
   callbackOnSettingsDialogClose?: (didAnythingChanged: boolean, changedProperties: string[], ret: false | "" | FormlyDialogModel) => void): ContainerSelectorSupportingSettingsDialogHelper;
```

#### Parameters

| Parameter                        | Type                                                                                                                        | Description                                              |
| -------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------- |
| `settings`                       | [`SettingsDialogDefinition`](../interfaces/SettingsDialogDefinition.md)                                                     | The settings for the dialog.                             |
| `createSettingsButtonOnInit?`    | `boolean`                                                                                                                   | Whether to create the settings button on initialization. |
| `callbackOnSettingsDialogClose?` | (`didAnythingChanged`: `boolean`, `changedProperties`: `string`[], `ret`: `false` \| `""` \| `FormlyDialogModel`) => `void` | Callback function when the settings dialog is closed.    |

#### Returns

`ContainerSelectorSupportingSettingsDialogHelper`

#### Deprecated

Use the constructor with SettingsDialogOptions.

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`constructor`](SettingsDialogHelper.md#constructor)

## Properties

### ~~isContainerOptional~~

```ts
protected readonly isContainerOptional: boolean = false;
```

---

### ~~optionsCallback~~

```ts
optionsCallback: Function;
```

---

### ~~title~~

```ts
readonly title: string = undefined;
```

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`title`](SettingsDialogHelper.md#title)

## Accessors

### ~~dialogSettings~~

#### Get Signature

```ts
get dialogSettings(): SettingsDialogDefinition;
```

The current settings for the dialog.

##### Returns

[`SettingsDialogDefinition`](../interfaces/SettingsDialogDefinition.md)

#### Set Signature

```ts
set dialogSettings(settings: SettingsDialogDefinition): void;
```

Sets the settings for the dialog.

##### Parameters

| Parameter  | Type                                                                    | Description          |
| ---------- | ----------------------------------------------------------------------- | -------------------- |
| `settings` | [`SettingsDialogDefinition`](../interfaces/SettingsDialogDefinition.md) | The settings to set. |

##### Returns

`void`

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`dialogSettings`](SettingsDialogHelper.md#dialogsettings)

## Methods

### ~~addSettingsButtonToWidgetContextMenu()~~

```ts
addSettingsButtonToWidgetContextMenu(button?: ContextMenuButton): void;
```

Creates a settings button on the widget bar.

#### Parameters

| Parameter | Type                | Default value | Description                        |
| --------- | ------------------- | ------------- | ---------------------------------- |
| `button`  | `ContextMenuButton` | `undefined`   | The context menu button to create. |

#### Returns

`void`

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`addSettingsButtonToWidgetContextMenu`](SettingsDialogHelper.md#addsettingsbuttontowidgetcontextmenu)

---

### ~~addSettingsToWidgetObjectSettings()~~

```ts
addSettingsToWidgetObjectSettings(): Promise<void>;
```

Adds settings to the widget object settings (ie. service, or advanced settings)

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`addSettingsToWidgetObjectSettings`](SettingsDialogHelper.md#addsettingstowidgetobjectsettings)

---

### ~~destroy()~~

```ts
destroy(): void;
```

Destroys the settings dialog, removing any settings buttons and custom object settings from the widget.

#### Returns

`void`

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`destroy`](SettingsDialogHelper.md#destroy)

---

### ~~initialSettingsTransformation()~~

```ts
protected initialSettingsTransformation(settings: FormlyDialogSettings): FormlyDialogSettings;
```

Updates the settings with the current options.

#### Parameters

| Parameter  | Type                   | Description             |
| ---------- | ---------------------- | ----------------------- |
| `settings` | `FormlyDialogSettings` | The settings to update. |

#### Returns

`FormlyDialogSettings`

The updated settings.

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`initialSettingsTransformation`](SettingsDialogHelper.md#initialsettingstransformation)

---

### ~~openSettingsDialog()~~

```ts
openSettingsDialog(): Promise<false | void | "" | FormlyDialogModel>;
```

Opens the settings dialog.

#### Returns

`Promise`\<`false` \| `void` \| `""` \| `FormlyDialogModel`\>

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`openSettingsDialog`](SettingsDialogHelper.md#opensettingsdialog)

---

### ~~processFormDialogResult()~~

```ts
protected processFormDialogResult(ret: false | "" | FormlyDialogModel): boolean;
```

Processes the result of the form dialog. (including saving the settings)

#### Parameters

| Parameter | Type                                   | Description                    |
| --------- | -------------------------------------- | ------------------------------ |
| `ret`     | `false` \| `""` \| `FormlyDialogModel` | The result of the form dialog. |

#### Returns

`boolean`

Whether any settings were changed.

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`processFormDialogResult`](SettingsDialogHelper.md#processformdialogresult)

---

### ~~refreshFormData()~~

```ts
protected refreshFormData(settings: FormlyDialogSettings): Promise<FormlyDialogSettings<FormlyDialogModel>>;
```

Refreshes the form data, before opening the dialog
by default it:

- fills the form with the current values before showing the dialog
- adds adjustments to fix issues related to tabs and required fields

#### Parameters

| Parameter  | Type                   | Description              |
| ---------- | ---------------------- | ------------------------ |
| `settings` | `FormlyDialogSettings` | The settings to refresh. |

#### Returns

`Promise`\<`FormlyDialogSettings`\<`FormlyDialogModel`\>\>

The refreshed settings.

#### Overrides

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`refreshFormData`](SettingsDialogHelper.md#refreshformdata)

---

### ~~updateDialogUiSettings()~~

```ts
protected updateDialogUiSettings(settings: FormlyDialogSettings): FormlyDialogSettings;
```

Updates the UI settings of the dialog.

#### Parameters

| Parameter  | Type                   | Description             |
| ---------- | ---------------------- | ----------------------- |
| `settings` | `FormlyDialogSettings` | The settings to update. |

#### Returns

`FormlyDialogSettings`

The updated settings.

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`updateDialogUiSettings`](SettingsDialogHelper.md#updatedialoguisettings)

---

### ~~closeAllSettingDialogs()~~

```ts
static closeAllSettingDialogs(): void;
```

#### Returns

`void`

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`closeAllSettingDialogs`](SettingsDialogHelper.md#closeallsettingdialogs)

---

### ~~getAllContainersAsFormOptions()~~

```ts
static getAllContainersAsFormOptions(): FormlySelectOption[];
```

#### Returns

`FormlySelectOption`[]

---

### ~~shouldDisableRequiredParam()~~

```ts
static shouldDisableRequiredParam(model: FormlyFieldConfig): boolean;
```

Determines whether to disable required parameter for a field. (due to conflicts with being hidden)

#### Parameters

| Parameter | Type                | Description                     |
| --------- | ------------------- | ------------------------------- |
| `model`   | `FormlyFieldConfig` | The Formly form model to check. |

#### Returns

`boolean`

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`shouldDisableRequiredParam`](SettingsDialogHelper.md#shoulddisablerequiredparam)
