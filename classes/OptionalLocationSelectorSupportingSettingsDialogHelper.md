[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / OptionalLocationSelectorSupportingSettingsDialogHelper

# Class: OptionalLocationSelectorSupportingSettingsDialogHelper

Creates and manages interactive settings dialogs for widgets.

Provides a comprehensive system for building widget configuration UIs using Formly forms.
Handles dialog display, form validation, value persistence to shared variables, change
tracking, and toolbar button integration. Supports complex form layouts including tabs,
sections, and custom field types. Essential for widgets requiring user configuration.

## Example

```typescript
// Define settings fields
const settings = new SettingsDialogHelper(
  {
    fields: [
      {
        key: "apiKey",
        type: "input",
        props: { label: "API Key", required: true },
      },
      {
        key: "refreshInterval",
        type: "input",
        props: { label: "Refresh (seconds)", type: "number", min: 1 },
      },
    ],
  },
  {
    title: "Widget Configuration",
    createSettingsButtonOnInit: true,
    callbackOnSettingsDialogClose: (changed, keys, values) => {
      if (changed) {
        console.log("Settings changed:", keys);
        applyNewSettings(values);
      }
    },
  },
);

// Programmatically show dialog
settings.showSettingsDialog();
```

## Extends

- [`SettingsDialogHelper`](SettingsDialogHelper.md)

## Constructors

### Constructor

```ts
new OptionalLocationSelectorSupportingSettingsDialogHelper(settings?: SettingsDialogDefinition, options?: SettingsDialogOptions): OptionalLocationSelectorSupportingSettingsDialogHelper;
```

Constructs a new Settings Dialog.

#### Parameters

| Parameter   | Type                                                                    | Description                      |
| ----------- | ----------------------------------------------------------------------- | -------------------------------- |
| `settings?` | [`SettingsDialogDefinition`](../interfaces/SettingsDialogDefinition.md) | The settings for the dialog.     |
| `options?`  | `SettingsDialogOptions`                                                 | Options for the settings dialog. |

#### Returns

`OptionalLocationSelectorSupportingSettingsDialogHelper`

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`constructor`](SettingsDialogHelper.md#constructor)

### Constructor

```ts
new OptionalLocationSelectorSupportingSettingsDialogHelper(
   settings: SettingsDialogDefinition,
   createSettingsButtonOnInit?: boolean,
   callbackOnSettingsDialogClose?: (didAnythingChanged: boolean, changedProperties: string[], ret: false | "" | FormlyDialogModel) => void): OptionalLocationSelectorSupportingSettingsDialogHelper;
```

#### Parameters

| Parameter                        | Type                                                                                                                        | Description                                              |
| -------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------- |
| `settings`                       | [`SettingsDialogDefinition`](../interfaces/SettingsDialogDefinition.md)                                                     | The settings for the dialog.                             |
| `createSettingsButtonOnInit?`    | `boolean`                                                                                                                   | Whether to create the settings button on initialization. |
| `callbackOnSettingsDialogClose?` | (`didAnythingChanged`: `boolean`, `changedProperties`: `string`[], `ret`: `false` \| `""` \| `FormlyDialogModel`) => `void` | Callback function when the settings dialog is closed.    |

#### Returns

`OptionalLocationSelectorSupportingSettingsDialogHelper`

#### Deprecated

Use the constructor with SettingsDialogOptions.

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`constructor`](SettingsDialogHelper.md#constructor)

## Properties

### optionsCallback

```ts
optionsCallback: Function;
```

---

### title

```ts
readonly title: string = undefined;
```

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`title`](SettingsDialogHelper.md#title)

## Accessors

### dialogSettings

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

### addSettingsButtonToWidgetContextMenu()

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

### addSettingsToWidgetObjectSettings()

```ts
addSettingsToWidgetObjectSettings(): Promise<void>;
```

Adds settings to the widget object settings (ie. service, or advanced settings)

#### Returns

`Promise`\<`void`\>

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`addSettingsToWidgetObjectSettings`](SettingsDialogHelper.md#addsettingstowidgetobjectsettings)

---

### destroy()

```ts
destroy(): void;
```

Destroys the settings dialog, removing any settings buttons and custom object settings from the widget.

#### Returns

`void`

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`destroy`](SettingsDialogHelper.md#destroy)

---

### initialSettingsTransformation()

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

### openSettingsDialog()

```ts
openSettingsDialog(): Promise<false | void | "" | FormlyDialogModel>;
```

Opens the settings dialog.

#### Returns

`Promise`\<`false` \| `void` \| `""` \| `FormlyDialogModel`\>

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`openSettingsDialog`](SettingsDialogHelper.md#opensettingsdialog)

---

### processFormDialogResult()

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

### refreshFormData()

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

### updateDialogUiSettings()

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

### closeAllSettingDialogs()

```ts
static closeAllSettingDialogs(): void;
```

#### Returns

`void`

#### Inherited from

[`SettingsDialogHelper`](SettingsDialogHelper.md).[`closeAllSettingDialogs`](SettingsDialogHelper.md#closeallsettingdialogs)

---

### getAllLocationsAsFormOptions()

```ts
static getAllLocationsAsFormOptions(): FormlySelectOption[];
```

#### Returns

`FormlySelectOption`[]

---

### shouldDisableRequiredParam()

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
