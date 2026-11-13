[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / ItemListHelperOptions

# Type Alias: ItemListHelperOptions

```ts
type ItemListHelperOptions = {
    allowDataConnectors?: boolean
    allowImport?: boolean
    allowLocalEdit?: boolean
    allowReordering?: boolean
    dataSourceLabel?: string
    defaultValue?: ListRecord[]
    disableAllEdits?: boolean
    elements?: FormlyFieldConfig<
        FormlyFieldProps & {
            [p: string]: any
        }
    >[]
    importSettings?: Omit<DataImportHelperSettings, 'fields'>
    label?: string
    localListProps?: Record<string, any>
    migrateIdGenerateFunction?: (element: unknown, list: unknown[], index: number) => string
    migrateOldArrayTypeList?: boolean
    newIdGenerateFunction?: () => string
    onListChangeCallback?: (list: ListRecord[]) => void
    readonlyApi?: boolean
}
```

Options for configuring the ItemListHelper.

## Properties

### allowDataConnectors?

```ts
allowDataConnectors?: boolean;
```

---

### allowImport?

```ts
allowImport?: boolean;
```

---

### allowLocalEdit?

```ts
allowLocalEdit?: boolean;
```

---

### allowReordering?

```ts
allowReordering?: boolean;
```

---

### dataSourceLabel?

```ts
dataSourceLabel?: string;
```

---

### defaultValue?

```ts
defaultValue?: ListRecord[];
```

---

### disableAllEdits?

```ts
disableAllEdits?: boolean;
```

---

### elements?

```ts
elements?: FormlyFieldConfig<FormlyFieldProps & {
[p: string]: any;
}>[];
```

---

### importSettings?

```ts
importSettings?: Omit<DataImportHelperSettings, "fields">;
```

---

### label?

```ts
label?: string;
```

---

### localListProps?

```ts
localListProps?: Record<string, any>;
```

---

### migrateIdGenerateFunction?

```ts
migrateIdGenerateFunction?: (element: unknown, list: unknown[], index: number) => string;
```

#### Parameters

| Parameter | Type        |
| --------- | ----------- |
| `element` | `unknown`   |
| `list`    | `unknown`[] |
| `index`   | `number`    |

#### Returns

`string`

---

### migrateOldArrayTypeList?

```ts
migrateOldArrayTypeList?: boolean;
```

---

### newIdGenerateFunction?

```ts
newIdGenerateFunction?: () => string;
```

#### Returns

`string`

---

### onListChangeCallback?

```ts
onListChangeCallback?: (list: ListRecord[]) => void;
```

#### Parameters

| Parameter | Type                            |
| --------- | ------------------------------- |
| `list`    | [`ListRecord`](ListRecord.md)[] |

#### Returns

`void`

---

### readonlyApi?

```ts
readonlyApi?: boolean;
```
