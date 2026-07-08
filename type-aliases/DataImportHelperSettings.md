[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / DataImportHelperSettings

# Type Alias: DataImportHelperSettings

```ts
type DataImportHelperSettings = {
  allowImportFromDataConnector?: boolean;
  askAboutOverwrite?: boolean;
  fields: {
    label: string;
    name: string;
  }[];
  label?: string;
  lineLimit?: number;
  warningMessage?: string;
};
```

Settings for the DataImportHelper.

## Properties

### allowImportFromDataConnector?

```ts
optional allowImportFromDataConnector?: boolean;
```

---

### askAboutOverwrite?

```ts
optional askAboutOverwrite?: boolean;
```

---

### fields

```ts
fields: {
  label: string;
  name: string;
}
[];
```

#### label

```ts
label: string;
```

#### name

```ts
name: string;
```

---

### label?

```ts
optional label?: string;
```

---

### lineLimit?

```ts
optional lineLimit?: number;
```

---

### warningMessage?

```ts
optional warningMessage?: string;
```
