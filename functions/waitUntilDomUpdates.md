[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / waitUntilDomUpdates

# Function: waitUntilDomUpdates()

> **waitUntilDomUpdates**(): `Promise`\<`void`\>

Waits for the browser to complete all pending DOM rendering and layout operations.

When you modify DOM elements, the browser updates them asynchronously. This function
ensures that all visual updates are complete before proceeding, which is useful for
measuring element dimensions, capturing screenshots, or ensuring animations have started.

## Returns

`Promise`\<`void`\>

A promise that resolves after the DOM has fully updated and rendered.

## Example

```typescript
// Modify DOM and wait for rendering
element.textContent = 'New text';
await waitUntilDomUpdates();
const height = element.offsetHeight; // Now accurate

// Ensure element is visible before interaction
modal.style.display = 'block';
await waitUntilDomUpdates();
modal.querySelector('button').focus();
```
