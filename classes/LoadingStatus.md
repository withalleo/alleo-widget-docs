[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / LoadingStatus

# Class: LoadingStatus

Displays a full-board loading spinner overlay for service widgets.

Provides a visual loading indicator that covers the entire board interface while
a service widget is processing. Features an animated spinner with smooth fade-in/fade-out
transitions. Automatically cleans up when the widget is destroyed. Ideal for indicating
long-running operations in service widgets.

## Example

```typescript
const loadingStatus = new LoadingStatus();

// Show loading indicator
loadingStatus.show();

// Perform async operation
await processData();

// Hide loading indicator
loadingStatus.hide();

// With try-finally for reliable cleanup
try {
  loadingStatus.show();
  await performOperation();
} finally {
  loadingStatus.hide();
}
```

## Constructors

### Constructor

> **new LoadingStatus**(`id?`): `LoadingStatus`

Creates a LoadingStatus instance with a unique identifier.

Automatically registers cleanup handler to remove the loading indicator when the
widget is destroyed.

#### Parameters

##### id?

`string` = `...`

Unique identifier for this loading indicator instance.

#### Returns

`LoadingStatus`

## Properties

### showing

> **showing**: `boolean` = `false`

## Accessors

### loadingButtonHTML

#### Get Signature

> **get** `protected` **loadingButtonHTML**(): `string`

The HTML template for the animated loading spinner.

Includes inline CSS for the spinner animation and styling.

##### Returns

`string`

HTML string with embedded styles and spinner markup.

## Methods

### hide()

> **hide**(): `void`

Hides the loading status by setting the opacity of the DOM element to 0.

#### Returns

`void`

***

### show()

> **show**(): `void`

Displays the loading indicator with a fade-in animation.

Creates and appends the loading overlay to the document if it doesn't exist,
then animates it to full opacity. Safe to call multiple times.

#### Returns

`void`
