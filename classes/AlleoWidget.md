[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / AlleoWidget

# Class: AlleoWidget\<SharedVariableStructure\>

Base class for creating Alleo Widgets with shared variable management and lifecycle handling.

This class provides a foundation for building widgets that can store and synchronize data across
multiple widget instances, handle DOM interactions, and manage widget lifecycle events. It includes
automatic handling of interactability states, design mode visualization, and proper cleanup on destruction.

## Example

```typescript
class CounterWidget extends AlleoWidget<
  typeof CounterWidget.defaultSharedVariables
> {
  // "shared variables" are synchronized automatically. you can set the defaults here when a new widget is added.
  // typescript type is also defined here.
  private static defaultSharedVariables = {
    count: <number>0,
  };

  // The constructor will be called when the widget loads.
  constructor() {
    super(CounterWidget.defaultSharedVariables);
    console.log("Widget loaded");

    // let's render the UI for our fake widget
    this.render();

    // the [SharedVariable] class has a lot of tools to deal with synchronized data
    // including an observer, that triggers a callback when any user on any device changes this variable.
    new SharedVariable.observer(["count"], () => this.render());

    this.domSelect("button").onclick = () => {
      // otherwise you can use this as a normal variable.
      this.shared.count = this.shared.count + 1;

      // Note: the observer will trigger immediately.
      // eg. this.render() will run, before the console.log() in the next line
      console.log(this.shared.count);
    };
  }

  // destroy is called when the widget unloads
  // (eg. the user closes the browser, the display is turned off, the user navigates to an other board,
  // or just randomly when offscreen for performance reasons.)
  public override destroy() {
    super.destroy();
    console.log("Widget destroyed");
  }

  // let's do some fake UI updates
  private render() {
    // the value for this.shared.count is always synced between instances.
    // if you change it, it will change on other devices "live" as well.
    // See [ShareVariableHelper] for more
    const displayString = this.shared.count.toString();
    this.domSelect(".counter-container").innerText = displayString;
  }
}

new CounterWidget();
```

## Extended by

- [`DataConnectorWidget`](DataConnectorWidget.md)

## Type Parameters

| Type Parameter                                                  | Default type                | Description                                                             |
| --------------------------------------------------------------- | --------------------------- | ----------------------------------------------------------------------- |
| `SharedVariableStructure` _extends_ `Record`\<`string`, `any`\> | `Record`\<`string`, `any`\> | The structure of the shared variables (an object with key-value pairs). |

## Constructors

### Constructor

```ts
new AlleoWidget<SharedVariableStructure>(defaultSharedVariables?: Partial<SharedVariableStructure>, settings?: WidgetInitSettings): AlleoWidget<SharedVariableStructure>;
```

Creates an instance of AlleoWidget and initializes shared variables, DOM references, and lifecycle handlers.

The constructor sets up a proxy for shared variables to automatically sync with Alleo's data fields,
configures DOM interaction handlers, and registers the widget with the Alleo platform.

#### Parameters

| Parameter                 | Type                                   | Description                                                                                                                                |
| ------------------------- | -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| `defaultSharedVariables?` | `Partial`\<`SharedVariableStructure`\> | Default values for shared variables. These values are used when the widget is first created or when a shared variable hasn't been set yet. |
| `settings?`               | `WidgetInitSettings`                   | Configuration options for widget initialization.                                                                                           |

#### Returns

`AlleoWidget`\<`SharedVariableStructure`\>

## Properties

### dom

```ts
protected dom: HTMLDivElement = null;
```

---

### shared

```ts
protected shared: Partial<SharedVariableStructure>;
```

---

### widgetStatus

```ts
protected widgetStatus: {
  loaded: boolean;
};
```

#### loaded

```ts
loaded: boolean;
```

---

### api

```ts
static api: IWidgetServiceApi = haptic;
```

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

This method is invoked when the widget is unloaded from memory (e.g., when navigating away from the board
or when the widget needs to be reloaded). This is NOT called when the widget object is deleted from the board.
Override this method to perform cleanup tasks such as unsubscribing from observables, clearing timers,
or releasing resources.

#### Returns

`void` \| `Promise`\<`void`\>

Can return a Promise for async cleanup operations.

---

### domSelect()

```ts
protected domSelect<HTMLElementType>(query: string): HTMLElementType;
```

Queries for a DOM element within the widget container using a CSS selector.

This is a convenience method that automatically scopes the query to within the widget's container,
preventing accidental selection of elements outside the widget.

#### Type Parameters

| Type Parameter                            | Default type  | Description                                                                 |
| ----------------------------------------- | ------------- | --------------------------------------------------------------------------- |
| `HTMLElementType` _extends_ `HTMLElement` | `HTMLElement` | The expected HTML element type (e.g., HTMLButtonElement, HTMLInputElement). |

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
const button = this.domSelect<HTMLButtonElement>(".my-button");
button.addEventListener("click", () => console.log("Clicked!"));
```

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
this.setContainerClass("active", true); // Adds 'active' class, removes 'not-active'
this.setContainerClass("active", false); // Removes 'active' class, adds 'not-active'
```

---

### updateDomStatus()

```ts
protected updateDomStatus(): void;
```

#### Returns

`void`
