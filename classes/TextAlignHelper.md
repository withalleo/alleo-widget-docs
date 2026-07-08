[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / TextAlignHelper

# Class: TextAlignHelper

Keeps an element's text alignment synced and provides a toolbar submenu.
The helper updates the text-align CSS property of the provided HTML element.

It also provides a submenu so collaborators can
switch alignments and the DOM updates automatically.

## Examples

```ts
const helper = new TextAlignHelper(this.domSelect<HTMLElement>(".label")!, {
  defaultAlign: TextAlignment.Left,
  supportedAlignments: [TextAlignment.Left, TextAlignment.Right],
});
```

```ts
const helper = new TextAlignHelper(this.domSelect(".label"));
```

## Constructors

### Constructor

```ts
new TextAlignHelper(element: HTMLElement | HTMLElement[], options?: TextAlignOptions): TextAlignHelper;
```

#### Parameters

| Parameter | Type                             | Description                                                                      |
| --------- | -------------------------------- | -------------------------------------------------------------------------------- |
| `element` | `HTMLElement` \| `HTMLElement`[] | Element whose `textAlign` style is controlled.                                   |
| `options` | `TextAlignOptions`               | Configuration overrides such as default alignment and available submenu entries. |

#### Returns

`TextAlignHelper`

## Accessors

### align

#### Get Signature

```ts
get align(): TextAlignment;
```

Returns the currently active text alignment.

##### Returns

[`TextAlignment`](../enumerations/TextAlignment.md)

#### Set Signature

```ts
set align(textAlignment: TextAlignment): void;
```

Applies a new alignment, and saves it as a shared variable, and triggers a local callback.

(Note: as the variable changes, the UI is automatically updated via an observer).

##### Throws

Error when the requested alignment is not available in `supportedAlignments`.

##### Parameters

| Parameter       | Type                                                |
| --------------- | --------------------------------------------------- |
| `textAlignment` | [`TextAlignment`](../enumerations/TextAlignment.md) |

##### Returns

`void`

## Methods

### renderContextMenu()

```ts
protected renderContextMenu(): void;
```

Adds or rebuilds the toolbar submenu, ensuring the icon matches the current alignment.

#### Returns

`void`

---

### updateAlignment()

```ts
protected updateAlignment(): void;
```

Ensures the DOM element's `textAlign` style matches the stored alignment.

#### Returns

`void`
