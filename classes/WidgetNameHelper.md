[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / WidgetNameHelper

# Class: WidgetNameHelper

Manages widget identification and naming across different contexts.

Provides utilities for retrieving widget names, IDs, and display names from various
sources including manifest configuration, deployment settings, and URL paths. Handles
automatic widget name detection and validation. Essential for widgets that need to
identify themselves or display their name to users.

## Example

```typescript
// Get widget display name
const displayName = WidgetNameHelper.displayName;
console.log("Widget:", displayName); // e.g., "AI Chat"

// Get widget ID (technical name)
const widgetId = WidgetNameHelper.widgetId;
console.log("ID:", widgetId); // e.g., "ai-chat"

// Create instance with preferred name
const nameHelper = new WidgetNameHelper("custom-widget");
console.log("Name:", nameHelper.name);
```

## Constructors

### Constructor

```ts
new WidgetNameHelper(preferredName?: string, currentNote?: string): WidgetNameHelper;
```

Creates a WidgetNameHelper instance with optional custom naming.

#### Parameters

| Parameter        | Type     | Default value | Description                                                              |
| ---------------- | -------- | ------------- | ------------------------------------------------------------------------ |
| `preferredName?` | `string` | `undefined`   | Optional preferred name to use for the widget instead of auto-detection. |
| `currentNote?`   | `string` | `undefined`   | Optional current note/caption text for the widget.                       |

#### Returns

`WidgetNameHelper`

## Accessors

### name

#### Get Signature

```ts
get name(): string;
```

Gets the name of the widget.

##### Returns

`string`

The name of the widget.

#### Set Signature

```ts
set name(name: string): void;
```

Sets the name of the widget.

##### Parameters

| Parameter | Type     | Description                 |
| --------- | -------- | --------------------------- |
| `name`    | `string` | The new name of the widget. |

##### Returns

`void`

---

### note

#### Get Signature

```ts
get note(): string;
```

Gets the note associated with the widget.

##### Returns

`string`

The note associated with the widget.

#### Set Signature

```ts
set note(note: string): void;
```

Sets the note associated with the widget.

##### Parameters

| Parameter | Type     | Description                  |
| --------- | -------- | ---------------------------- |
| `note`    | `string` | The new note for the widget. |

##### Returns

`void`

---

### displayName

#### Get Signature

```ts
get static displayName(): string;
```

Retrieves the human-readable display name of the widget.

Returns the widget's friendly name for display in UI, prioritizing deployment
settings, then manifest configuration, then auto-detected names.

##### Static

##### Returns

`string`

The widget's display name (e.g., "AI Chat", "Hello World").

---

### manifest

#### Get Signature

```ts
get static manifest(): Record<string, any>;
```

Gets the manifest of the widget.

##### Returns

`Record`\<`string`, `any`\>

The manifest of the widget.

---

### widgetId

#### Get Signature

```ts
get static widgetId(): string;
```

Retrieves the technical widget identifier.

Returns the widget's unique ID used for internal references, typically in kebab-case
format. Checks deployment settings, manifest configuration, or derives from entry point URL.

##### Static

##### Returns

`string`

The widget's ID (e.g., "ai-chat", "hello-world").

## Methods

### getFullName()

```ts
protected getFullName(): string;
```

Gets the full name of the widget, including the note.

#### Returns

`string`

The full name of the widget.

---

### updateWidgetName()

```ts
protected updateWidgetName(): void;
```

Updates the widget name.

#### Returns

`void`

---

### setOnlyNote()

```ts
static setOnlyNote(note?: string): void;
```

Sets the note for the widget.

#### Parameters

| Parameter | Type     | Description      |
| --------- | -------- | ---------------- |
| `note?`   | `string` | The note to set. |

#### Returns

`void`
