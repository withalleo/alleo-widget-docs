[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / UiButtonHelper

# Class: UiButtonHelper

Manages floating action buttons for service widgets in the Alleo UI.

Creates and positions custom buttons in the bottom-right corner of the interface,
alongside system buttons like Intercom or help. Handles responsive positioning,
button lifecycle, and ensures buttons are properly displayed and accessible.
Primarily used by service widgets that don't have a board presence.

## Example

```typescript
const buttonHelper = new UiButtonHelper();

// Add a simple button
buttonHelper.add({
  id: "my-action",
  label: "Click Me",
  onClick: () => console.log("Button clicked!"),
});

// Add button with icon
buttonHelper.add({
  id: "settings",
  icon: "settings",
  label: "Settings",
  onClick: () => openSettings(),
});

// Remove a button
buttonHelper.remove("my-action");
```

## Constructors

### Constructor

```ts
new UiButtonHelper(): UiButtonHelper;
```

Creates a new UiButtonHelper instance and initializes the button container.

Sets up a fixed-position container in the bottom-right corner for floating action buttons.
Automatically manages positioning relative to other UI elements like Intercom and help buttons.
Cleans up automatically when the widget is destroyed.

#### Returns

`UiButtonHelper`

## Properties

### container

```ts
readonly container: HTMLElement;
```

---

### containerId

```ts
static containerId: string = 'widget-service-ui-helper-main-buttons';
```

## Accessors

### backgroundColor

#### Get Signature

```ts
get backgroundColor(): string;
```

The background color used for buttons, automatically matching the UI theme.

Returns the primary color if Intercom is present (for consistency with Intercom button),
otherwise returns the toolbar background color.

##### Returns

`string`

CSS color value for button backgrounds.

---

### buttons

#### Get Signature

```ts
get buttons(): HTMLElement[];
```

Array of all button HTML elements managed by this helper.

##### Returns

`HTMLElement`[]

Array of button elements currently displayed.

## Methods

### addButton()

```ts
addButton(
   html: string,
   callback: (e: PointerEvent) => void,
   settings?: {
  backgroundColor?: string;
  buttonId?: string;
  callbackAltClick?: (e: PointerEvent) => void;
  callbackPointerDown?: (e: PointerEvent) => void;
  callbackPointerUp?: (e: PointerEvent) => void;
  color?: string;
  position?: number | UiButtonPosition;
}): string;
```

Adds a new button to the UI.

#### Parameters

| Parameter                       | Type                                                                                                                                                                                                                                                                                                                                     | Description                                                  |
| ------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| `html`                          | `string`                                                                                                                                                                                                                                                                                                                                 | The HTML content of the button.                              |
| `callback`                      | (`e`: `PointerEvent`) => `void`                                                                                                                                                                                                                                                                                                          | The callback function to execute when the button is clicked. |
| `settings`                      | \{ `backgroundColor?`: `string`; `buttonId?`: `string`; `callbackAltClick?`: (`e`: `PointerEvent`) => `void`; `callbackPointerDown?`: (`e`: `PointerEvent`) => `void`; `callbackPointerUp?`: (`e`: `PointerEvent`) => `void`; `color?`: `string`; `position?`: `number` \| [`UiButtonPosition`](../enumerations/UiButtonPosition.md); \} | The settings for the button.                                 |
| `settings.backgroundColor?`     | `string`                                                                                                                                                                                                                                                                                                                                 | -                                                            |
| `settings.buttonId?`            | `string`                                                                                                                                                                                                                                                                                                                                 | The ID of the button.                                        |
| `settings.callbackAltClick?`    | (`e`: `PointerEvent`) => `void`                                                                                                                                                                                                                                                                                                          | -                                                            |
| `settings.callbackPointerDown?` | (`e`: `PointerEvent`) => `void`                                                                                                                                                                                                                                                                                                          | -                                                            |
| `settings.callbackPointerUp?`   | (`e`: `PointerEvent`) => `void`                                                                                                                                                                                                                                                                                                          | -                                                            |
| `settings.color?`               | `string`                                                                                                                                                                                                                                                                                                                                 | -                                                            |
| `settings.position?`            | `number` \| [`UiButtonPosition`](../enumerations/UiButtonPosition.md)                                                                                                                                                                                                                                                                    | The position of the button.                                  |

#### Returns

`string`

The ID of the newly added button.

---

### destroy()

```ts
destroy(): void;
```

Destroys all buttons managed by this helper.

#### Returns

`void`

---

### getButton()

```ts
getButton(buttonId: string): HTMLElement;
```

Retrieves the HTML element for a button by its ID.

#### Parameters

| Parameter  | Type     | Description                                      |
| ---------- | -------- | ------------------------------------------------ |
| `buttonId` | `string` | The unique identifier of the button to retrieve. |

#### Returns

`HTMLElement`

The button element, or undefined if not found.

---

### isVisible()

```ts
isVisible(buttonId: string): boolean;
```

Checks whether a button with the specified ID is currently visible.

#### Parameters

| Parameter  | Type     | Description                                   |
| ---------- | -------- | --------------------------------------------- |
| `buttonId` | `string` | The unique identifier of the button to check. |

#### Returns

`boolean`

True if a button with this ID exists and is displayed, false otherwise.

---

### removeButton()

```ts
removeButton(buttonId: string): void;
```

Removes a button with the given ID.

#### Parameters

| Parameter  | Type     | Description                     |
| ---------- | -------- | ------------------------------- |
| `buttonId` | `string` | The ID of the button to remove. |

#### Returns

`void`

---

### reOrderButtons()

```ts
protected reOrderButtons(): void;
```

#### Returns

`void`
