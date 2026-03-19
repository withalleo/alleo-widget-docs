[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / DataConnectorAction

# Enumeration: DataConnectorAction

Supported actions for DataConnector widgets.

## Enumeration Members

### Append

> **Append**: `"append"`

Appends a single record (row) to the widget's data source.

***

### Delete

> **Delete**: `"delete"`

Deletes a specific record from the widget's data source.

The first record is index 0. Deleting a record shifts all subsequent indices.

***

### Export

> **Export**: `"export"`

Exports all data from the widget.

Some concrete widgets may still limit the amount of data they return.

***

### Get

> **Get**: `"get"`

Reads a specific record from the widget's data source.

The first record is index 0.

***

### Import

> **Import**: `"import"`

Imports data into the widget, replacing all existing records.

***

### OnChange

> **OnChange**: `"onChange"`

Logical action for reacting to data changes.

Used by some widgets to describe that they can emit change notifications.

***

### Reset

> **Reset**: `"reset"`

Clears the widget's data source and trims the size to zero.

***

### Set

> **Set**: `"set"`

Replaces a specific record in the widget's data source.

The first record is index 0.
