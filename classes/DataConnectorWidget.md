[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / DataConnectorWidget

# Class: DataConnectorWidget\<SharedVariableStructure\>

Base class for widgets that provide data import/export and act as data sources for other widgets.

Extends `AlleoWidget` and wires up common data-connector behavior such as CSV import/export,
exposed actions for other widgets, settings UI, and a preview dialog.
Concrete widgets typically override the protected data methods (`export`, `import`, `append`, etc.)
and the metadata getters (`implemented`, `length`, `widgetName`, `widgetDescription`, `settings`).

## Extends

- [`AlleoWidget`](AlleoWidget.md)\<`SharedVariableStructure`\>

## Type Parameters

| Type Parameter            | Description                                                     |
| ------------------------- | --------------------------------------------------------------- |
| `SharedVariableStructure` | Structure of the widget's shared variables stored on the board. |

## Constructors

### Constructor

```ts
new DataConnectorWidget<SharedVariableStructure>(defaultSharedVariables?: Partial<SharedVariableStructure>): DataConnectorWidget<SharedVariableStructure>;
```

Creates a data connector widget.

The constructor:

- sets up the settings dialog (including Import/Export/Preview buttons when supported),
- exposes standard data connector actions and
- initializes the widget name and action effects.

#### Parameters

| Parameter                | Type                                   | Description                                                |
| ------------------------ | -------------------------------------- | ---------------------------------------------------------- |
| `defaultSharedVariables` | `Partial`\<`SharedVariableStructure`\> | Optional initial values for the widget's shared variables. |

#### Returns

`DataConnectorWidget`\<`SharedVariableStructure`\>

#### Overrides

[`AlleoWidget`](AlleoWidget.md).[`constructor`](AlleoWidget.md#constructor)

## Properties

### dom

```ts
protected dom: HTMLDivElement = null;
```

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`dom`](AlleoWidget.md#dom)

---

### lineLimit

```ts
protected lineLimit: number = 0;
```

Maximum number of records allowed for import; `0` means "no explicit limit".

---

### nameHelper

```ts
protected nameHelper: WidgetNameHelper;
```

Helper responsible for keeping the visible widget name in sync.

---

### onChangeCallbacks

```ts
onChangeCallbacks: () => void[] = [];
```

Optional callbacks that run when the widget's data changes.

#### Returns

`void`

---

### shared

```ts
protected shared: Partial<SharedVariableStructure>;
```

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`shared`](AlleoWidget.md#shared)

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

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`widgetStatus`](AlleoWidget.md#widgetstatus)

---

### api

```ts
static api: IWidgetServiceApi = haptic;
```

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`api`](AlleoWidget.md#api)

---

### widgetNamePrefix

```ts
readonly static widgetNamePrefix: string = '▤ ';
```

Prefix used when showing the widget name on the board.

## Accessors

### displayName

#### Get Signature

```ts
get displayName(): string;
```

Resolved display name of the widget as shown on the board.

Uses the custom `displayName` shared variable when present, otherwise falls back to `widgetName`.

##### Returns

`string`

---

### implemented

#### Get Signature

```ts
get implemented(): DataConnectorAction[];
```

List of data connector actions that this concrete widget actually implements.

Subclasses should override this to advertise their supported features.

##### Returns

[`DataConnectorAction`](../enumerations/DataConnectorAction.md)[]

---

### length

#### Get Signature

```ts
get length(): number;
```

Number of records currently stored by the widget, when known.

Subclasses can override this to expose their own length; `undefined` means "not reported".

##### Returns

`number`

---

### settings

#### Get Signature

```ts
get protected settings(): ExtendedFormlyFieldConfig[];
```

Additional settings fields contributed by the concrete widget.

These are injected into the shared settings dialog for the data connector instance.

##### Returns

[`ExtendedFormlyFieldConfig`](../interfaces/ExtendedFormlyFieldConfig.md)[]

---

### widgetDescription

#### Get Signature

```ts
get widgetDescription(): string;
```

Short description of what this data connector does.

Used in the settings dialog footer.

##### Returns

`string`

---

### widgetName

#### Get Signature

```ts
get widgetName(): string;
```

Human friendly base name of the widget (without the connector prefix).

Subclasses should override this to provide a more specific name.

##### Returns

`string`

## Methods

### append()

```ts
protected append(newRecord: string[]): Promise<boolean>;
```

Appends a new record to the widget's data source.

The base implementation only emits an action trigger and returns `false`.
Most widgets should override this to update their internal data and return `true` on success.

#### Parameters

| Parameter   | Type       | Description       |
| ----------- | ---------- | ----------------- |
| `newRecord` | `string`[] | Record to append. |

#### Returns

`Promise`\<`boolean`\>

`true` when the record was added; `false` in the base implementation.

---

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

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`assertWidgetLoaded`](AlleoWidget.md#assertwidgetloaded)

---

### deleteLine()

```ts
protected deleteLine(recordNumber: number): Promise<boolean>;
```

Deletes a single record from the widget's data source.

The base implementation only emits an action trigger and returns `false`.

#### Parameters

| Parameter      | Type     | Description                               |
| -------------- | -------- | ----------------------------------------- |
| `recordNumber` | `number` | Zero-based index of the record to delete. |

#### Returns

`Promise`\<`boolean`\>

`true` when the record was deleted; `false` in the base implementation.

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

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`destroy`](AlleoWidget.md#destroy)

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

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`domSelect`](AlleoWidget.md#domselect)

---

### export()

```ts
protected export(): Promise<CSVData>;
```

Exports the widget's data as a 2D CSV array.

Subclasses must override this to return their current data.

#### Returns

`Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

All records currently stored by this data connector.

#### Throws

Always throws in the base class; concrete implementations must provide a working version.

---

### exportProcess()

```ts
exportProcess(name?: string, download?: boolean): Promise<void>;
```

Exports data from the connector and uploads it as a CSV file to board assets.

Optionally triggers a download for the current user.

#### Parameters

| Parameter  | Type      | Default value     | Description                                                 |
| ---------- | --------- | ----------------- | ----------------------------------------------------------- |
| `name`     | `string`  | `'Exported data'` | Base name to use for the exported file (without extension). |
| `download` | `boolean` | `true`            | When `true`, also downloads the file to the local machine.  |

#### Returns

`Promise`\<`void`\>

#### Throws

When the uploaded file has no public URL.

---

### getLine()

```ts
protected getLine(recordNumber?: number): Promise<string[]>;
```

Reads a single record from the widget's data source by index.

This method relies on `export` and enforces `lineLimit` when it is greater than 0.

#### Parameters

| Parameter      | Type     | Default value | Description                                              |
| -------------- | -------- | ------------- | -------------------------------------------------------- |
| `recordNumber` | `number` | `0`           | Zero-based index of the record to read. Defaults to `0`. |

#### Returns

`Promise`\<`string`[]\>

The requested record as an array of string cell values.

#### Throws

When export or get support is missing, the index is negative, exceeds `lineLimit`, or is out of bounds.

---

### import()

```ts
protected import(newRecords: CSVData): Promise<boolean>;
```

Replaces all records in the widget's data source with the given CSV content.

The base implementation only emits an action trigger and returns `false`.
Most widgets should override this to update their internal data and return `true` on success.

#### Parameters

| Parameter    | Type                                    | Description                        |
| ------------ | --------------------------------------- | ---------------------------------- |
| `newRecords` | [`CSVData`](../type-aliases/CSVData.md) | Complete set of records to import. |

#### Returns

`Promise`\<`boolean`\>

`true` when the data was imported; `false` in the base implementation.

---

### importProcess()

```ts
importProcess(): Promise<void>;
```

Opens the generic data import dialog and pushes the imported CSV into the connector.

Shows a toast about the result and does not throw on failure.

#### Returns

`Promise`\<`void`\>

---

### initialize()

```ts
protected initialize(): Promise<void>;
```

Performs common initialization steps for a connector instance.

Subclasses can override this to hook into the lifecycle, but should usually call `super.initialize()`.

#### Returns

`Promise`\<`void`\>

---

### reset()

```ts
protected reset(): Promise<boolean>;
```

Clears the widget's data source.

The base implementation only emits an action trigger and returns `false`.

#### Returns

`Promise`\<`boolean`\>

`true` when the data was reset; `false` in the base implementation.

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

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`setContainerClass`](AlleoWidget.md#setcontainerclass)

---

### setLine()

```ts
protected setLine(record: string[], recordNumber: number): Promise<boolean>;
```

Replaces a single record in the widget's data source.

The base implementation only emits an action trigger and returns `false`.
Most widgets should override this to update their internal data and return `true` on success.

#### Parameters

| Parameter      | Type       | Description                                |
| -------------- | ---------- | ------------------------------------------ |
| `record`       | `string`[] | New record content.                        |
| `recordNumber` | `number`   | Zero-based index of the record to replace. |

#### Returns

`Promise`\<`boolean`\>

`true` when the record was updated; `false` in the base implementation.

---

### updateActions()

```ts
protected updateActions(): void;
```

Registers action effects and triggers for the data connector based on the implemented actions.

This wires the widget into the haptic action system so other widgets and flows can
call into this connector and listen to its events.

#### Returns

`void`

---

### updateDomStatus()

```ts
protected updateDomStatus(): void;
```

#### Returns

`void`

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`updateDomStatus`](AlleoWidget.md#updatedomstatus)

---

### isDataConnector()

```ts
static isDataConnector(object: RealIBoardObject, actionsRequiredSupport?: DataConnectorAction[]): boolean;
```

Checks if a board object represents a DataConnector widget and, optionally, if it supports given actions.

#### Parameters

| Parameter                | Type                                                              | Default value | Description                                               |
| ------------------------ | ----------------------------------------------------------------- | ------------- | --------------------------------------------------------- |
| `object`                 | [`RealIBoardObject`](../interfaces/RealIBoardObject.md)           | `undefined`   | Board object to check.                                    |
| `actionsRequiredSupport` | [`DataConnectorAction`](../enumerations/DataConnectorAction.md)[] | `[]`          | Actions that must be supported for the object to qualify. |

#### Returns

`boolean`

`true` when the object is marked as a data connector and supports at least one of the requested actions.

---

### saveCSVInBoardAssets()

```ts
static saveCSVInBoardAssets(file: File): Promise<StorageNodeCreatedResponseDto>;
```

Saves a CSV file into the board assets area and quietly confirms the import dialog if it is open.

This is mostly used by widgets when exporting data for the user.

#### Parameters

| Parameter | Type   | Description                          |
| --------- | ------ | ------------------------------------ |
| `file`    | `File` | CSV file to upload as a board asset. |

#### Returns

`Promise`\<`StorageNodeCreatedResponseDto`\>

The uploaded file node returned by the board service.
