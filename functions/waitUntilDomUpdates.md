[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / waitUntilDomUpdates

# Function: waitUntilDomUpdates()

> **waitUntilDomUpdates**(): `Promise`\<`void`\>

Waits until the DOM rendering process is finished.

(ie. if you change the content of a html object it will re-render the DOM asynchronously. This function will wait until the rendering is finished.)

## Returns

`Promise`\<`void`\>

A promise that resolves after the DOM updated and the HTML document is full rendered.
