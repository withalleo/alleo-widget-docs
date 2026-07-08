[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / ItemListHelperOptions

# Type Alias: ItemListHelperOptions

```ts
type ItemListHelperOptions = {
  allowDataConnectors?: boolean;
  allowImport?: boolean;
  allowLocalEdit?: boolean;
  allowReordering?: boolean;
  dataSourceLabel?: string;
  defaultValue?: ListRecord[];
  disableAllEdits?: boolean;
  elements?: FormlyFieldConfig<
    FormlyFieldProps & {
      [p: string]: any;
    }
  >[];
  importSettings?: Omit<DataImportHelperSettings, "fields">;
  label?: string;
  localListProps?: Record<string, any>;
  migrateIdGenerateFunction?: (
    element: unknown,
    list: unknown[],
    index: number,
  ) => string;
  migrateOldArrayTypeList?: boolean;
  newIdGenerateFunction?: () => string;
  onListChangeCallback?: (list: ListRecord[]) => void;
  readonlyApi?: boolean;
};
```

Options for configuring the ItemListHelper.

## Properties

### allowDataConnectors?

```ts
optional allowDataConnectors?: boolean;
```

---

### allowImport?

```ts
optional allowImport?: boolean;
```

---

### allowLocalEdit?

```ts
optional allowLocalEdit?: boolean;
```

---

### allowReordering?

```ts
optional allowReordering?: boolean;
```

---

### dataSourceLabel?

```ts
optional dataSourceLabel?: string;
```

---

### defaultValue?

```ts
optional defaultValue?: ListRecord[];
```

---

### disableAllEdits?

```ts
optional disableAllEdits?: boolean;
```

---

### elements?

```ts
optional elements?: FormlyFieldConfig<FormlyFieldProps & {
[p: string]: any;
}>[];
```

---

### importSettings?

```ts
optional importSettings?: Omit<DataImportHelperSettings, "fields">;
```

---

### label?

```ts
optional label?: string;
```

---

### localListProps?

```ts
optional localListProps?: Record<string, any>;
```

---

### migrateIdGenerateFunction?

```ts
optional migrateIdGenerateFunction?: (element: unknown, list: unknown[], index: number) => string;
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
optional migrateOldArrayTypeList?: boolean;
```

---

### newIdGenerateFunction?

```ts
optional newIdGenerateFunction?: () => string;
```

#### Returns

`string`

---

### onListChangeCallback?

```ts
optional onListChangeCallback?: (list: ListRecord[]) => void;
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
optional readonlyApi?: boolean;
```
