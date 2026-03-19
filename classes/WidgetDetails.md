[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / WidgetDetails

# Class: WidgetDetails

Manages widget metadata including label (caption), visibility, and search description.

Provides utilities for programmatically controlling the widget's display name, label
visibility, and searchable description. Useful for widgets that need to dynamically
update their display properties based on content or state. Automatically handles
backward compatibility with older Alleo versions.

## Example

```typescript
// Set widget label
WidgetDetails.label = 'Data Analysis Dashboard';

// Hide the label
WidgetDetails.hideLabel = true;

// Set search description for better discoverability
WidgetDetails.searchDescription = 'Financial data visualization with charts and graphs';

// Read current label
const currentLabel = WidgetDetails.label;
console.log('Widget is labeled:', currentLabel);

// Check if label is hidden
if (WidgetDetails.hideLabel) {
  console.log('Label is currently hidden');
}
```

## Constructors

### Constructor

> **new WidgetDetails**(): `WidgetDetails`

#### Returns

`WidgetDetails`

## Accessors

### hideLabel

#### Get Signature

> **get** `static` **hideLabel**(): `boolean`

Checks if the widget's label is currently hidden.

##### Static

##### Returns

`boolean`

True if the label is hidden, false if visible.

#### Set Signature

> **set** `static` **hideLabel**(`hide`): `void`

Controls whether the widget's label is hidden or visible.

When hidden, the label still exists but is not displayed on the board.

##### Static

##### Parameters

###### hide

`boolean`

True to hide the label, false to show it.

##### Returns

`void`

***

### label

#### Get Signature

> **get** `static` **label**(): `string`

Retrieves the widget's current display label (caption text).

##### Static

##### Returns

`string`

The widget's caption/label text, or empty string if not set.

#### Set Signature

> **set** `static` **label**(`title`): `void`

Sets the widget's display label (caption text).

Automatically truncates to 250 characters if longer. Updates the widget's caption
displayed above or below the widget on the board.

##### Static

##### Parameters

###### title

`string`

The label text to display. Truncated at 250 characters if longer.

##### Returns

`void`

***

### searchDescription

#### Set Signature

> **set** `static` **searchDescription**(`description`): `void`

Sets the widget's search description for improved discoverability.

The search description helps users find the widget when searching the board.
Falls back to setting the label with visibility hidden for older Alleo versions.

##### Static

##### Parameters

###### description

`string`

The search-friendly description of the widget's content or purpose.

##### Returns

`void`
