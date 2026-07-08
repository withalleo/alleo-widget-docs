[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / DataConnector

# Class: DataConnector

Thin helper wrapper for interacting with a DataConnector widget on the board.

This class calls the exposed connector actions on a specific board object identified by `objectId`.

## Constructors

### Constructor

```ts
new DataConnector(objectId: string): DataConnector;
```

Creates a new helper bound to a specific board object.

#### Parameters

| Parameter  | Type     | Description                                                |
| ---------- | -------- | ---------------------------------------------------------- |
| `objectId` | `string` | ID of the board object (widget instance) to interact with. |

#### Returns

`DataConnector`

## Accessors

### length

#### Get Signature

```ts
get length(): number;
```

Number of records reported by the underlying DataConnector widget.

##### Returns

`number`

---

### supportedActions

#### Get Signature

```ts
get supportedActions(): DataConnectorAction[];
```

Actions that the underlying DataConnector widget reports as supported.

##### Returns

[`DataConnectorAction`](../enumerations/DataConnectorAction.md)[]

## Methods

### append()

```ts
append(row: string[]): Promise<boolean>;
```

Appends a single record to the underlying DataConnector.

#### Parameters

| Parameter | Type       | Description       |
| --------- | ---------- | ----------------- |
| `row`     | `string`[] | Record to append. |

#### Returns

`Promise`\<`boolean`\>

Whatever the widget's `append` implementation returns, typically `true` on success.

---

### deleteLine()

```ts
deleteLine(lineNumber: number): Promise<boolean>;
```

Deletes a specific record from the underlying DataConnector.

#### Parameters

| Parameter    | Type     | Description                               |
| ------------ | -------- | ----------------------------------------- |
| `lineNumber` | `number` | Zero-based index of the record to delete. |

#### Returns

`Promise`\<`boolean`\>

Whatever the widget's `deleteLine` implementation returns.

---

### export()

```ts
export(): Promise<CSVData>;
```

Exports all records from the underlying DataConnector.

#### Returns

`Promise`\<[`CSVData`](../type-aliases/CSVData.md)\>

Exported records as a 2D CSV array.

---

### getLine()

```ts
getLine(lineNumber?: number): Promise<string[]>;
```

Reads a specific record from the underlying DataConnector.

#### Parameters

| Parameter    | Type     | Default value | Description                                               |
| ------------ | -------- | ------------- | --------------------------------------------------------- |
| `lineNumber` | `number` | `0`           | Zero-based index of the record to fetch. Defaults to `0`. |

#### Returns

`Promise`\<`string`[]\>

The requested record as an array of string values.

---

### import()

```ts
import(data: CSVData): Promise<boolean>;
```

Imports data into the underlying DataConnector, replacing its current content.

#### Parameters

| Parameter | Type                                    | Description        |
| --------- | --------------------------------------- | ------------------ |
| `data`    | [`CSVData`](../type-aliases/CSVData.md) | Records to import. |

#### Returns

`Promise`\<`boolean`\>

Whatever the widget's `import` implementation returns, typically `true` on success.

---

### reset()

```ts
reset(): Promise<boolean>;
```

Resets the underlying DataConnector widget.

#### Returns

`Promise`\<`boolean`\>

Whatever the widget's `reset` implementation returns.

---

### setLine()

```ts
setLine(row: string[]): Promise<boolean>;
```

Replaces a specific record in the underlying DataConnector.

#### Parameters

| Parameter | Type       | Description         |
| --------- | ---------- | ------------------- |
| `row`     | `string`[] | New record content. |

#### Returns

`Promise`\<`boolean`\>

Whatever the widget's `setLine` implementation returns.
