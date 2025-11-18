[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / DataConnectorWidget

# Class: DataConnectorWidget\<SharedVariableStructure\>

Base class for widgets that connect to data sources and provide import/export functionality.

## Extends

- [`AlleoWidget`](AlleoWidget.md)\<`SharedVariableStructure`\>

## Type Parameters

### SharedVariableStructure

`SharedVariableStructure`

The structure of shared variables for the widget.

## Constructors

### Constructor

> **new DataConnectorWidget**\<`SharedVariableStructure`\>(`defaultSharedVariables`): `DataConnectorWidget`\<`SharedVariableStructure`\>

Constructs a DataConnectorWidget instance.

#### Parameters

##### defaultSharedVariables

`Partial`\<`SharedVariableStructure`\> = `{}`

Default shared variables for the widget.

#### Returns

`DataConnectorWidget`\<`SharedVariableStructure`\>

#### Overrides

[`AlleoWidget`](AlleoWidget.md).[`constructor`](AlleoWidget.md#constructor)

## Properties

### dom

> `protected` **dom**: `HTMLDivElement`

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`dom`](AlleoWidget.md#dom)

***

### lineLimit

> `protected` **lineLimit**: `number` = `0`

Maximum number of lines allowed for import.

***

### nameHelper

> `protected` **nameHelper**: [`WidgetNameHelper`](WidgetNameHelper.md)

Helper for managing widget name display.

***

### shared

> `protected` **shared**: `Partial`\<`SharedVariableStructure`\>

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`shared`](AlleoWidget.md#shared)

***

### widgetStatus

> `protected` **widgetStatus**: `object`

#### loaded

> **loaded**: `boolean`

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`widgetStatus`](AlleoWidget.md#widgetstatus)

***

### api

> `static` **api**: `IWidgetServiceApi` = `haptic`

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`api`](AlleoWidget.md#api)

***

### widgetNamePrefix

> `readonly` `static` **widgetNamePrefix**: `string` = `'▤ '`

Prefix for widget display name.

## Accessors

### implemented

#### Get Signature

> **get** `protected` **implemented**(): [`DataConnectorActions`](../enumerations/DataConnectorActions.md)[]

Returns the list of actions implemented by the widget.

##### Returns

[`DataConnectorActions`](../enumerations/DataConnectorActions.md)[]

***

### length

#### Get Signature

> **get** `protected` **length**(): `number`

Returns the number of records in the widget's data source.

##### Returns

`number`

***

### settings

#### Get Signature

> **get** `protected` **settings**(): `ExtendedFormlyFieldConfig`[]

Returns the settings fields for the widget.

##### Returns

`ExtendedFormlyFieldConfig`[]

***

### widgetDescription

#### Get Signature

> **get** `protected` **widgetDescription**(): `string`

Returns the description of the widget.

##### Returns

`string`

***

### widgetName

#### Get Signature

> **get** `protected` **widgetName**(): `string`

Returns the display name of the widget.

##### Returns

`string`

## Methods

### append()

> `protected` **append**(`row`): `Promise`\<`boolean`\>

Appends a row to the widget's data source.

#### Parameters

##### row

`string`[]

The row to append.

#### Returns

`Promise`\<`boolean`\>

#### Throws

Error if not implemented.

***

### assertWidgetLoaded()

> `protected` **assertWidgetLoaded**(): `void`

Asserts that the widget is loaded.

#### Returns

`void`

#### Throws

- If the widget has been destroyed.

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`assertWidgetLoaded`](AlleoWidget.md#assertwidgetloaded)

***

### destroy()

> **destroy**(): `void` \| `Promise`\<`void`\>

Called when the widget instance is destroyed (when unloaded, NOT when the widget is deleted from the board).

#### Returns

`void` \| `Promise`\<`void`\>

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`destroy`](AlleoWidget.md#destroy)

***

### domSelect()

> `protected` **domSelect**\<`HTMLElementType`\>(`query`): `HTMLElementType`

Selects a DOM element within the widget container.

#### Type Parameters

##### HTMLElementType

`HTMLElementType` *extends* `HTMLElement` = `HTMLElement`

The type of the HTML element.

#### Parameters

##### query

`string`

The query selector.

#### Returns

`HTMLElementType`

- The selected HTML element.

#### Throws

- If no DOM is available.

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`domSelect`](AlleoWidget.md#domselect)

***

### export()

> `protected` **export**(): `Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

Exports the widget's data as CSV.

#### Returns

`Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

#### Throws

Error if not implemented.

***

### exportProcess()

> **exportProcess**(`name`, `download`): `Promise`\<`void`\>

Handles the export process by exporting data and saving it in board assets.

#### Parameters

##### name

`string` = `'Exported data'`

Name for the exported file.

##### download

`boolean` = `true`

Whether to download the file after export.

#### Returns

`Promise`\<`void`\>

***

### import()

> `protected` **import**(`data`): `Promise`\<`boolean`\>

Imports data into the widget's data source.

#### Parameters

##### data

[`CSVData`](../type-aliases/CSVData.md)

The CSV data to import.

#### Returns

`Promise`\<`boolean`\>

#### Throws

Error if not implemented.

***

### importProcess()

> **importProcess**(): `Promise`\<`void`\>

Handles the import process by opening the import dialog and importing data.

#### Returns

`Promise`\<`void`\>

***

### initialize()

> `protected` **initialize**(): `Promise`\<`void`\>

Initializes the widget (called in constructor).

#### Returns

`Promise`\<`void`\>

***

### reset()

> `protected` **reset**(): `Promise`\<`void`\>

Resets the widget's data source.

#### Returns

`Promise`\<`void`\>

***

### setContainerClass()

> `protected` **setContainerClass**(`className`, `add?`): `void`

Sets an HTML class for the widget container.

#### Parameters

##### className

`string`

The class name to set.

##### add?

`boolean` = `true`

Whether to add or remove the class. (if !add the "not-className" class is added, and the original is removed)

#### Returns

`void`

#### Throws

- If no DOM is available.

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`setContainerClass`](AlleoWidget.md#setcontainerclass)

***

### updateDisplayName()

> `protected` **updateDisplayName**(): `void`

Updates the display name of the widget.

#### Returns

`void`

***

### updateDomStatus()

> `protected` **updateDomStatus**(): `void`

#### Returns

`void`

#### Inherited from

[`AlleoWidget`](AlleoWidget.md).[`updateDomStatus`](AlleoWidget.md#updatedomstatus)

***

### isDataConnector()

> `static` **isDataConnector**(`object`, `actionsRequiredSupport`): `boolean`

Checks if a board object is a DataConnector and supports required actions.

#### Parameters

##### object

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object to check.

##### actionsRequiredSupport

[`DataConnectorActions`](../enumerations/DataConnectorActions.md)[] = `[]`

Actions that must be supported.

#### Returns

`boolean`

True if the object is a DataConnector and supports the required actions.

***

### saveCSVInBoardAssets()

> `static` **saveCSVInBoardAssets**(`file`): `Promise`\<`StorageNodeCreatedResponseDto`\>

Saves a CSV file in board assets and attempts to close the import dialog if open.

#### Parameters

##### file

`File`

The CSV file to upload.

#### Returns

`Promise`\<`StorageNodeCreatedResponseDto`\>

The uploaded file node.
