[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / DataConnectorAction

# Enumeration: DataConnectorAction

Supported actions for DataConnector widgets.

## Enumeration Members

### Append

```ts
Append: "append";
```

Appends a single record (row) to the widget's data source.

---

### Delete

```ts
Delete: "delete";
```

Deletes a specific record from the widget's data source.

The first record is index 0. Deleting a record shifts all subsequent indices.

---

### Export

```ts
Export: "export";
```

Exports all data from the widget.

Some concrete widgets may still limit the amount of data they return.

---

### Get

```ts
Get: "get";
```

Reads a specific record from the widget's data source.

The first record is index 0.

---

### Import

```ts
Import: "import";
```

Imports data into the widget, replacing all existing records.

---

### OnChange

```ts
OnChange: "onChange";
```

Logical action for reacting to data changes.

Used by some widgets to describe that they can emit change notifications.

---

### Reset

```ts
Reset: "reset";
```

Clears the widget's data source and trims the size to zero.

---

### Set

```ts
Set: "set";
```

Replaces a specific record in the widget's data source.

The first record is index 0.
