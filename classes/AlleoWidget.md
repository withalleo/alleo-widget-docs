[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / AlleoWidget

# Class: AlleoWidget\<SharedVariableStructure _extends_ `Record`\<`string`, `any`\> = `Record`\<`string`, `any`\>\>

Base class for creating Alleo Widgets with shared variable management and lifecycle handling.

This class provides a foundation for building widgets that can store and synchronize data across
multiple widget instances, handle DOM interactions, and manage widget lifecycle events. It includes
automatic handling of interactability states, design mode visualization, and proper cleanup on destruction.

## Example

```typescript
class CounterWidget extends AlleoWidget<typeof CounterWidget.defaultSharedVariables> {
    // "shared variables" are synchronized automatically. you can set the defaults here when a new widget is added.
    // typescript type is also defined here.
    private static defaultSharedVariables = {
        'count': <number>0,
    }

    // The constructor will be called when the widget loads.
    constructor() {
        super(CounterWidget.defaultSharedVariables)
        console.log('Widget loaded')

        // let's render the UI for our fake widget
        this.render()

        // the [SharedVariable] class has a lot of tools to deal with synchronized data
        // including an observer, that triggers a callback when any user on any device changes this variable.
        new SharedVariable.observer(['count'], () => this.render())

        this.domSelect('button').onclick = () => {
            // otherwise you can use this as a normal variable.
            this.shared.count = this.shared.count + 1

            // Note: the observer will trigger immediately.
            // eg. this.render() will run, before the console.log() in the next line
            console.log(this.shared.count)
        }
    }

    // destroy is called when the widget unloads
    // (eg. the user closes the browser, the display is turned off, the user navigates to an other board,
    // or just randomly when offscreen for performance reasons.)
    public override destroy() {
        super.destroy()
        console.log('Widget destroyed')
    }

    // let's do some fake UI updates
    private render() {
        // the value for this.shared.count is always synced between instances.
        // if you change it, it will change on other devices "live" as well.
        // See [SharedVariable] for more
        const displayString = this.shared.count.toString()
        this.domSelect('.counter-container').innerText = displayString
    }
}

new CounterWidget()
```

## Extended by

- [`DataConnectorWidget`](DataConnectorWidget.md)

## Type Parameters

| Type Parameter                                                                                                      | Default type                | Description                                                             |
| ------------------------------------------------------------------------------------------------------------------- | --------------------------- | ----------------------------------------------------------------------- |
| <a id="type-parameter-sharedvariablestructure"></a> `SharedVariableStructure` _extends_ `Record`\<`string`, `any`\> | `Record`\<`string`, `any`\> | The structure of the shared variables (an object with key-value pairs). |

## Constructors

### Constructor

```ts
new AlleoWidget<SharedVariableStructure extends Record<string, any> = Record<string, any>>(defaultSharedVariables?: Partial<SharedVariableStructure>, settings?: WidgetInitSettings): AlleoWidget<SharedVariableStructure>;
```

Creates an instance of AlleoWidget and initializes shared variables, DOM references, and lifecycle handlers.

The constructor sets up a proxy for shared variables to automatically sync with Alleo's data fields,
configures DOM interaction handlers, and registers the widget with the Alleo platform.
On creation it schedules `justCreated()` and `justCreatedOptionalUI()`. On unload it calls `destroy()`
and, during the creation phase, sets the `WidgetInitiallyConfigured` flag, which ends the creation phase.
Closing any `SettingsDialogHelper` dialog (saved or cancelled) ends the creation phase too.

#### Parameters

| Parameter                 | Type                                                          | Description                                                                                                                                |
| ------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| `defaultSharedVariables?` | `Partial`\<`SharedVariableStructure`\>                        | Default values for shared variables. These values are used when the widget is first created or when a shared variable hasn't been set yet. |
| `settings?`               | [`WidgetInitSettings`](../type-aliases/WidgetInitSettings.md) | Configuration options for widget initialization.                                                                                           |

#### Returns

`AlleoWidget`\<`SharedVariableStructure`\>

## Properties

### dom

```ts
readonly dom: HTMLDivElement = null;
```

The widget container element, or null for service widgets.

---

### shared

```ts
readonly shared: Partial<SharedVariableStructure>;
```

Shared variables, synced across all instances. Falls back to the defaults for unset values.

---

### widgetContainerSelector

```ts
readonly widgetContainerSelector: string;
```

CSS selector of the widget container, or undefined for service widgets.

---

### widgetStatus

```ts
protected widgetStatus: {
  creation: boolean;
  loaded: boolean;
};
```

#### creation

```ts
creation: boolean
```

#### loaded

```ts
loaded: boolean
```

---

### api

```ts
static api: IWidgetApi | IWidgetServiceApi = haptic;
```

The global `haptic` widget API.

---

### widgetFlagCollectionFieldName

```ts
readonly static widgetFlagCollectionFieldName: string = 'WidgetFlags';
```

Name of the data field that stores the widget flags.

## Accessors

### creation

#### Get Signature

```ts
get static creation(): boolean;
```

Indicates whether the widget is being created and loaded for the first time.

Only true on the client that created the widget, and only until the widget is unloaded for the first time
or any of its settings dialogs is closed (saved or cancelled).

Cancellable by the widget or other widgets to skip configuration.

##### Returns

`boolean`

True during the creation phase, false otherwise.

---

### widgetFlags

#### Get Signature

```ts
get static widgetFlags(): Record<WidgetFlag, boolean>;
```

Returns a copy of the current widget's flags.

##### Returns

`Record`\<[`WidgetFlag`](../type-aliases/WidgetFlag.md), `boolean`\>

A copy of the flags object, mapping each flag to its value.

## Methods

### assertWidgetLoaded()

```ts
protected assertWidgetLoaded(): void;
```

Validates that the widget is still loaded and has not been destroyed.

Use this method in async operations or callbacks to ensure the widget instance is still valid
before performing operations. This prevents errors when a widget is destroyed while an async
operation is still in progress.

#### Returns

`void`

#### Throws

Throws an error with message "assertWidgetLoaded - Widget was destroyed" if the widget has been destroyed.

#### Example

```typescript
async loadData() {
  const data = await fetchDataFromAPI();
  this.assertWidgetLoaded(); // Ensure widget wasn't destroyed during fetch
  this.displayData(data);
}
```

---

### destroy()

```ts
destroy(): void | Promise<void>;
```

Lifecycle method called when the widget instance is being destroyed.

This method is invoked every time the widget is unloaded from memory (e.g., when navigating away from the board,
when the widget is reloaded or unloaded off-screen), not just when the widget object is deleted from the board.
Override this method to perform cleanup tasks such as unsubscribing from observables, clearing timers,
or releasing resources.

#### Returns

`void` \| `Promise`\<`void`\>

Can return a Promise for async cleanup operations.

---

### domSelect()

```ts
protected domSelect<HTMLElementType extends HTMLElement = HTMLElement>(query: string): HTMLElementType;
```

Queries for a DOM element within the widget container using a CSS selector.

This is a convenience method that automatically scopes the query to within the widget's container,
preventing accidental selection of elements outside the widget.

#### Type Parameters

| Type Parameter                                                                        | Default type  | Description                                                                 |
| ------------------------------------------------------------------------------------- | ------------- | --------------------------------------------------------------------------- |
| <a id="type-parameter-htmlelementtype"></a> `HTMLElementType` _extends_ `HTMLElement` | `HTMLElement` | The expected HTML element type (e.g., HTMLButtonElement, HTMLInputElement). |

#### Parameters

| Parameter | Type     | Description                                                         |
| --------- | -------- | ------------------------------------------------------------------- |
| `query`   | `string` | CSS selector string (will be prefixed with the container selector). |

#### Returns

`HTMLElementType`

The first matching HTML element, or null if not found.

#### Throws

Throws if the widget doesn't have a DOM.

#### Example

```typescript
const button = this.domSelect<HTMLButtonElement>('.my-button')
button.addEventListener('click', () => console.log('Clicked!'))
```

---

### justCreated()

```ts
justCreated(): void | Promise<void>;
```

One-time setup on creation, on the creating client only.

Runs after the widget constructor has finished.

For optional UI (eg. settings dialog) use `justCreatedOptionalUI()`.

#### Returns

`void` \| `Promise`\<`void`\>

Can return a Promise for async initialization operations.

---

### justCreatedOptionalUI()

```ts
justCreatedOptionalUI(): void | Promise<void>;
```

Shows optional UI (e.g. the settings dialog) about 1 s after creation, on the creating client only.

Skipped if

- the widget was unloaded or deleted
- the widget already has the "widget-initially-configured" flag (e.g. a settings dialog was closed,
  or another widget set it to skip configuration)

Never put required setup here; use `justCreated()` instead.
Errors are caught and logged.

#### Returns

`void` \| `Promise`\<`void`\>

Can return a Promise for async UI operations.

---

### setContainerClass()

```ts
protected setContainerClass(className: string, add?: boolean): void;
```

Adds or removes CSS classes from the widget container for styling purposes.

When adding a class, it removes the "not-{className}" variant. When removing a class,
it adds the "not-{className}" variant instead. This pattern helps with CSS targeting.

#### Parameters

| Parameter   | Type      | Default value | Description                                                                          |
| ----------- | --------- | ------------- | ------------------------------------------------------------------------------------ |
| `className` | `string`  | `undefined`   | The CSS class name to add or remove.                                                 |
| `add?`      | `boolean` | `true`        | When true, adds the class. When false, removes the class and adds "not-{className}". |

#### Returns

`void`

#### Throws

Throws if the widget doesn't have a DOM (e.g., when used in a service context).

#### Example

```typescript
this.setContainerClass('active', true) // Adds 'active' class, removes 'not-active'
this.setContainerClass('active', false) // Removes 'active' class, adds 'not-active'
```

---

### updateDomStatus()

```ts
protected updateDomStatus(): void;
```

Syncs the container's pointer events and design-mode styling with the current interactibility and design mode.

#### Returns

`void`

---

### isWidgetFlagSet()

```ts
static isWidgetFlagSet(flag: WidgetFlag): boolean;
```

Checks if a specific widget flag is set.

#### Parameters

| Parameter | Type                                          | Description               |
| --------- | --------------------------------------------- | ------------------------- |
| `flag`    | [`WidgetFlag`](../type-aliases/WidgetFlag.md) | The widget flag to check. |

#### Returns

`boolean`

True if the flag is set, false otherwise.

---

### setWidgetFlag()

```ts
static setWidgetFlag(flag: WidgetFlag, flagValue?: boolean): void;
```

Sets a widget flag. If the flag is already set to the desired value, no action is taken.

#### Parameters

| Parameter    | Type                                          | Default value | Description                                                                        |
| ------------ | --------------------------------------------- | ------------- | ---------------------------------------------------------------------------------- |
| `flag`       | [`WidgetFlag`](../type-aliases/WidgetFlag.md) | `undefined`   | The widget flag to set.                                                            |
| `flagValue?` | `boolean`                                     | `true`        | The value to set the flag to. Defaults to true. False can be used to unset a flag. |

#### Returns

`void`
