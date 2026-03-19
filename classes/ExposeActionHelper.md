[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / ExposeActionHelper

# Class: ExposeActionHelper

Enables inter-widget communication by exposing functions to other widgets on the board.

Provides mechanisms for widgets to expose their functionality to other widgets, enabling
cross-widget interactions and data sharing. Supports both synchronous function calls and
asynchronous message passing. Essential for building widget ecosystems where multiple
widgets need to coordinate or share data.

## Example

```typescript
// Expose functions from a widget
ExposeActionHelper.exposeActions([
  {
    name: 'getData',
    action: () => myData
  },
  {
    name: 'updateValue',
    action: (newValue: number) => this.value = newValue
  }
]);

// Call exposed function from another widget
const targetWidget = BoardObjectHelper.getBoardObjectById(widgetId);
const getData = ExposeActionHelper.getExposedFunction(targetWidget, 'getData');
const data = getData();

// Send async message to widget
ExposeActionHelper.sendAsyncMessage(targetWidget, {
  type: 'update',
  function: 'refresh',
  data: [{ timestamp: Date.now() }]
});
```

## Constructors

### Constructor

> **new ExposeActionHelper**(): `ExposeActionHelper`

#### Returns

`ExposeActionHelper`

## Methods

### exposeActions()

> `static` **exposeActions**(`actions`): `void`

Exposes functions to make them callable by other widgets on the board.

Registers functions in the widget's reference object, making them discoverable and
callable by other widgets. Each exposed function can be invoked remotely by name.

#### Parameters

##### actions

`object`[]

Array of action objects to expose.

#### Returns

`void`

#### Static

***

### getExposedFunction()

> `static` **getExposedFunction**\<`T`\>(`widget`, `functionName`): `T`

Gets an exposed function from the widget by its name.

#### Type Parameters

##### T

`T` *extends* `AnyFunction`

#### Parameters

##### widget

`IBoardObject`

The widget object.

##### functionName

`string`

The name of the function to get.

#### Returns

`T`

The exposed function.

#### Throws

Will throw an error if no DOM is available or if the function is not found.

***

### getRootNode()

> `static` **getRootNode**(): `HTMLElementWithWidgetReference`

Retrieves the widget's root HTML node with widget reference capability.

#### Returns

`HTMLElementWithWidgetReference`

The root node element containing widget references.

#### Throws

Throws if the widget doesn't have a DOM (service widgets not supported).

#### Static

***

### handleAsyncMessage()

> `static` **handleAsyncMessage**(`widgetSyncMessage`, `filterType?`): `Promise`\<`void`\>

Handles an incoming asynchronous message from another widget.

#### Parameters

##### widgetSyncMessage

[`WidgetSyncMessage`](../type-aliases/WidgetSyncMessage.md)

The widget synchronization message.

##### filterType?

`string` = `undefined`

Optional filter type to process specific messages.

#### Returns

`Promise`\<`void`\>

***

### listExposedFunctions()

> `static` **listExposedFunctions**(`widget`): `Record`\<`string`, `AnyFunction`\>

Lists all exposed functions of the widget.

#### Parameters

##### widget

`IBoardObject`

The widget object.

#### Returns

`Record`\<`string`, `AnyFunction`\>

A record of exposed functions.

#### Throws

Will throw an error if no DOM is available.

***

### sendAsyncMessage()

> `static` **sendAsyncMessage**(`functionName`, `type?`, `args?`): `any`

Sends an asynchronous message to connected widgets

#### Parameters

##### functionName

`string`

The name of the function to call.

##### type?

`string` = `''`

The type of the message.

##### args?

`any` = `undefined`

The arguments to pass to the function.

#### Returns

`any`

The result of the function call.

***

### sendAsyncMessages()

> `static` **sendAsyncMessages**(`messages`): `any`

Sends multiple asynchronous messages to connected widgets.

#### Parameters

##### messages

[`StandardSyncMessage`](../type-aliases/StandardSyncMessage.md)[]

The list of messages to send.

#### Returns

`any`

The result of the function calls.

***

### unExposeActions()

> `static` **unExposeActions**(`actions`): `void`

Removes an exposed functionality.

#### Parameters

##### actions

`object`[]

The actions to unexpose.

#### Returns

`void`
