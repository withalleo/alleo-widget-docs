[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / OptionalContainerSelectorSupportingSettingsDialogHelper

# ~~Class: OptionalContainerSelectorSupportingSettingsDialogHelper~~

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

- [`ContainerSelectorSupportingSettingsDialogHelper`](ContainerSelectorSupportingSettingsDialogHelper.md)

## Constructors

### Constructor

```ts
new OptionalContainerSelectorSupportingSettingsDialogHelper(settings?: SettingsDialogDefinition, options?: SettingsDialogOptions): OptionalContainerSelectorSupportingSettingsDialogHelper;
```

Constructs a new Settings Dialog.

#### Parameters

| Parameter   | Type                                                                    | Description                      |
| ----------- | ----------------------------------------------------------------------- | -------------------------------- |
| `settings?` | [`SettingsDialogDefinition`](../interfaces/SettingsDialogDefinition.md) | The settings for the dialog.     |
| `options?`  | `SettingsDialogOptions`                                                 | Options for the settings dialog. |

#### Returns

`OptionalContainerSelectorSupportingSettingsDialogHelper`

#### Inherited from

[`ContainerSelectorSupportingSettingsDialogHelper`](ContainerSelectorSupportingSettingsDialogHelper.md).[`constructor`](ContainerSelectorSupportingSettingsDialogHelper.md#constructor)

### Constructor

```ts
new OptionalContainerSelectorSupportingSettingsDialogHelper(
   settings: SettingsDialogDefinition,
   createSettingsButtonOnInit?: boolean,
   callbackOnSettingsDialogClose?: (didAnythingChanged: boolean, changedProperties: string[], ret: false | "" | FormlyDialogModel) => void): OptionalContainerSelectorSupportingSettingsDialogHelper;
```

#### Parameters

| Parameter                        | Type                                                                                                                        | Description                                              |
| -------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------- |
| `settings`                       | [`SettingsDialogDefinition`](../interfaces/SettingsDialogDefinition.md)                                                     | The settings for the dialog.                             |
| `createSettingsButtonOnInit?`    | `boolean`                                                                                                                   | Whether to create the settings button on initialization. |
| `callbackOnSettingsDialogClose?` | (`didAnythingChanged`: `boolean`, `changedProperties`: `string`[], `ret`: `false` \| `""` \| `FormlyDialogModel`) => `void` | Callback function when the settings dialog is closed.    |

#### Returns

`OptionalContainerSelectorSupportingSettingsDialogHelper`

#### Deprecated

Use the constructor with SettingsDialogOptions.

#### Inherited from

[`ContainerSelectorSupportingSettingsDialogHelper`](ContainerSelectorSupportingSettingsDialogHelper.md).[`constructor`](ContainerSelectorSupportingSettingsDialogHelper.md#constructor)

## Properties

### ~~isContainerOptional~~

```ts
protected readonly isContainerOptional: boolean = true;
```

#### Overrides

[`ContainerSelectorSupportingSettingsDialogHelper`](ContainerSelectorSupportingSettingsDialogHelper.md).[`isContainerOptional`](ContainerSelectorSupportingSettingsDialogHelper.md#iscontaineroptional)

---

### ~~optionsCallback~~

```ts
optionsCallback: Function;
```

#### Inherited from

[`ContainerSelectorSupportingSettingsDialogHelper`](ContainerSelectorSupportingSettingsDialogHelper.md).[`optionsCallback`](ContainerSelectorSupportingSettingsDialogHelper.md#optionscallback)

---

### ~~title~~

```ts
readonly title: string = undefined;
```

#### Inherited from

[`ContainerSelectorSupportingSettingsDialogHelper`](ContainerSelectorSupportingSettingsDialogHelper.md).[`title`](ContainerSelectorSupportingSettingsDialogHelper.md#title)

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

[`ContainerSelectorSupportingSettingsDialogHelper`](ContainerSelectorSupportingSettingsDialogHelper.md).[`dialogSettings`](ContainerSelectorSupportingSettingsDialogHelper.md#dialogsettings)

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

[`ContainerSelectorSupportingSettingsDialogHelper`](ContainerSelectorSupportingSettingsDialogHelper.md).[`addSettingsButtonToWidgetContextMenu`](ContainerSelectorSupportingSettingsDialogHelper.md#addsettingsbuttontowidgetcontextmenu)

---

### ~~addSettingsToWidgetObjectSettings()~~

```ts
addSettingsToWidgetObjectSettings(): Promise<void>;
```

Adds settings to the widget object settings (ie. service, or advanced settings)

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`ContainerSelectorSupportingSettingsDialogHelper`](ContainerSelectorSupportingSettingsDialogHelper.md).[`addSettingsToWidgetObjectSettings`](ContainerSelectorSupportingSettingsDialogHelper.md#addsettingstowidgetobjectsettings)

---

### ~~destroy()~~

```ts
destroy(): void;
```

Destroys the settings dialog, removing any settings buttons and custom object settings from the widget.

#### Returns

`void`

#### Inherited from

[`ContainerSelectorSupportingSettingsDialogHelper`](ContainerSelectorSupportingSettingsDialogHelper.md).[`destroy`](ContainerSelectorSupportingSettingsDialogHelper.md#destroy)

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

[`ContainerSelectorSupportingSettingsDialogHelper`](ContainerSelectorSupportingSettingsDialogHelper.md).[`initialSettingsTransformation`](ContainerSelectorSupportingSettingsDialogHelper.md#initialsettingstransformation)

---

### ~~openSettingsDialog()~~

```ts
openSettingsDialog(): Promise<false | void | "" | FormlyDialogModel>;
```

Opens the settings dialog.

#### Returns

`Promise`\<`false` \| `void` \| `""` \| `FormlyDialogModel`\>

#### Inherited from

[`ContainerSelectorSupportingSettingsDialogHelper`](ContainerSelectorSupportingSettingsDialogHelper.md).[`openSettingsDialog`](ContainerSelectorSupportingSettingsDialogHelper.md#opensettingsdialog)

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

[`ContainerSelectorSupportingSettingsDialogHelper`](ContainerSelectorSupportingSettingsDialogHelper.md).[`processFormDialogResult`](ContainerSelectorSupportingSettingsDialogHelper.md#processformdialogresult)

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

#### Inherited from

[`ContainerSelectorSupportingSettingsDialogHelper`](ContainerSelectorSupportingSettingsDialogHelper.md).[`refreshFormData`](ContainerSelectorSupportingSettingsDialogHelper.md#refreshformdata)

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

[`ContainerSelectorSupportingSettingsDialogHelper`](ContainerSelectorSupportingSettingsDialogHelper.md).[`updateDialogUiSettings`](ContainerSelectorSupportingSettingsDialogHelper.md#updatedialoguisettings)

---

### ~~closeAllSettingDialogs()~~

```ts
static closeAllSettingDialogs(): void;
```

#### Returns

`void`

#### Inherited from

[`ContainerSelectorSupportingSettingsDialogHelper`](ContainerSelectorSupportingSettingsDialogHelper.md).[`closeAllSettingDialogs`](ContainerSelectorSupportingSettingsDialogHelper.md#closeallsettingdialogs)

---

### ~~getAllContainersAsFormOptions()~~

```ts
static getAllContainersAsFormOptions(): FormlySelectOption[];
```

#### Returns

`FormlySelectOption`[]

#### Inherited from

[`ContainerSelectorSupportingSettingsDialogHelper`](ContainerSelectorSupportingSettingsDialogHelper.md).[`getAllContainersAsFormOptions`](ContainerSelectorSupportingSettingsDialogHelper.md#getallcontainersasformoptions)

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

[`ContainerSelectorSupportingSettingsDialogHelper`](ContainerSelectorSupportingSettingsDialogHelper.md).[`shouldDisableRequiredParam`](ContainerSelectorSupportingSettingsDialogHelper.md#shoulddisablerequiredparam)
