[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / FormButtonHelper

# Class: FormButtonHelper

Creates interactive buttons for Formly forms and dialogs with timer and state management.

Provides utilities for adding action buttons to settings forms with features like periodic
refresh timers, single-use restrictions, loading states, and automatic cleanup. Integrates
seamlessly with Formly forms and handles button lifecycle, permissions, and visibility.
Essential for creating interactive form controls and action buttons.

## Example

```typescript
// Create a refresh button with timer
const refreshButton = new FormButtonHelper(
  "Refresh Data",
  () => {
    console.log("Refreshing...");
    loadData();
  },
  {
    primary: true,
    loadingPlaceholder: "Loading...",
  },
);

// Single-use action button
const importButton = new FormButtonHelper("Import Data", () => importData(), {
  primary: false,
});

// Get Formly field config
const fieldConfig = refreshButton.field;
```

## Constructors

### Constructor

```ts
new FormButtonHelper(
   label: string,
   callback?: (field: FormlyFieldConfig<FormlyFieldProps>) => void,
   settings?: FormButtonHelperSettings): FormButtonHelper;
```

Creates a FormButtonHelper instance for managing interactive form buttons.

Initializes button with label, click handler, and optional timer for periodic execution.
Automatically handles cleanup when widget is destroyed and respects user edit permissions.

#### Parameters

| Parameter   | Type                                                                      | Default value | Description                         |
| ----------- | ------------------------------------------------------------------------- | ------------- | ----------------------------------- |
| `label`     | `string`                                                                  | `undefined`   | Text displayed on the button.       |
| `callback?` | (`field`: `FormlyFieldConfig`\<`FormlyFieldProps`\>) => `void`            | `undefined`   | Invoked when the button is clicked. |
| `settings?` | [`FormButtonHelperSettings`](../type-aliases/FormButtonHelperSettings.md) | `{}`          | Configuration options.              |

#### Returns

`FormButtonHelper`

## Properties

### callback

```ts
callback: (field: FormlyFieldConfig<FormlyFieldProps>) => void;
```

#### Parameters

| Parameter | Type                                      |
| --------- | ----------------------------------------- |
| `field`   | `FormlyFieldConfig`\<`FormlyFieldProps`\> |

#### Returns

`void`

---

### label

```ts
readonly label: string;
```

---

### settings

```ts
readonly settings: FormButtonHelperSettings;
```

---

### widgetId

```ts
readonly widgetId: string;
```

---

### DEBUG

```ts
static DEBUG: boolean = false;
```

---

### defaultTimerInterval

```ts
protected readonly static defaultTimerInterval: number = 500;
```

## Accessors

### button

#### Get Signature

```ts
get button(): FormlyFieldConfig<FormlyFieldProps>;
```

Gets the Formly field configuration for the button.

##### Returns

`FormlyFieldConfig`\<`FormlyFieldProps`\>

The Formly field configuration.

---

### isAnyDialogOpen

#### Get Signature

```ts
get isAnyDialogOpen(): boolean;
```

##### Returns

`boolean`

---

### isTimerRunning

#### Get Signature

```ts
get isTimerRunning(): boolean;
```

Checks if the timer is running.

##### Returns

`boolean`

True if the timer is running, false otherwise.

## Methods

### destroy()

```ts
destroy(): void;
```

Destroys the form button helper.

#### Returns

`void`

---

### onTimerTick()

```ts
protected onTimerTick(): Promise<void>;
```

Handles the timer tick event.

#### Returns

`Promise`\<`void`\>

---

### startTimer()

```ts
startTimer(interval?: number): void;
```

Starts the timer.

#### Parameters

| Parameter  | Type     | Default value |
| ---------- | -------- | ------------- |
| `interval` | `number` | `undefined`   |

#### Returns

`void`

---

### stopTimer()

```ts
stopTimer(): void;
```

Stops the timer.

#### Returns

`void`

---

### updateButtonUI()

```ts
updateButtonUI(): Promise<void>;
```

#### Returns

`Promise`\<`void`\>
