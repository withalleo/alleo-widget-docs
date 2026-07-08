[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / BrowserContextHelper

# Class: BrowserContextHelper

Provides utilities for detecting the browser context and embedding environment.

Helps widgets determine if they're running in a Room application (digital signage/display mode)
versus the standard web interface. Useful for adapting widget behavior based on the display
context, such as adjusting UI for large displays, enabling screensaver modes, or modifying
interaction patterns for room-based scenarios.

## Example

```typescript
// Check if running in a Room context
if (BrowserContextHelper.isRoomApp()) {
  console.log("Running in Room mode");
  // Enable room-specific features
  enableFullscreenMode();
  disableDetailedControls();
} else {
  console.log("Running in web interface");
  // Enable standard web features
  showDetailedUI();
}
```

## Constructors

### Constructor

```ts
new BrowserContextHelper(): BrowserContextHelper;
```

#### Returns

`BrowserContextHelper`

## Methods

### isRoomApp()

```ts
static isRoomApp(): boolean;
```

Determines if the widget is currently running in a Room application context.

Room applications include digital signage displays, interactive kiosks, and screensaver
modes. Returns true for any Room-based embedding scope.

#### Returns

`boolean`

True if running in a Room app (display/signage mode), false otherwise.

#### Static
